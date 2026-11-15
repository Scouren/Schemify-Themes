# Changelog

All notable changes to this project are documented here. The format follows
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/). No version has been tagged yet, so
everything is under Unreleased, grouped by date.

## [Unreleased]

### 2026-11-14

- Changed: the template follows Schemify's current Modern preset, so every scheme also
  recolours the store, settings, packages, chat, layout and docs panels added since the first
  release. Before this, those panels kept Schemify's light defaults under a theme and their text
  was unreadable on dark schemes.
- Changed: `tools/check_theme.py` is Schemify's current theme gate. All 115 schemes pass it over
  Schemify's current base UI; the palette table was regenerated to get there.
- Changed: the SDK dependency (`schemify-abi`) and the gate's base UI come from the public
  [Scouren/Schemify-Plugins](https://github.com/Scouren/Schemify-Plugins) repository. The
  README and CI no longer point at the old OpenFAT URLs.
- Fixed: `build.sh` maps the standard library's source paths back to `/rustc/<commit>`, so a
  toolchain with the `rust-src` component builds the same module as one without it.
- Added: this changelog, and README sections on development and testing.

### 2026-11-06

- Changed: `schemify-abi` pinned to Schemify 39da966d, the public SDK commit; module rebuilt.

### 2026-11-02

- Changed: README with a themes table and a folded gallery.

### 2026-10-29

- Added: the plugin. 15 themes with 115 colour schemes, ported from a community catalogue of
  colour schemes onto the roles of Schemify's Modern preset. **View → Themes** lists them, and
  each one is also a `theme.<theme>.<scheme>` command, with `theme.off` to return to the
  default look.
- Added: the generator (`tools/spicetify.py`), which pushes any colour that misses a contrast
  threshold toward white or black until the scheme passes the gate.
- Added: Schemify's theme gate (`tools/check_theme.py`, `tools/gate.py`) and CI that runs it on
  every scheme and runs the plugin's tests.
