# Acknowledgements

This project stands entirely on the work of others. It is a fork of **Wine** that
incorporates the macOS performance work from **CodeWeavers' CrossOver**. Enormous thanks
to everyone below.

## The Wine project

The base of this repository is [Wine](https://www.winehq.org/) 11.0 — the compatibility
layer that makes any of this possible. Wine is the work of hundreds of contributors over
three decades. See the `AUTHORS` file for the full list. Wine is licensed under the
**GNU LGPL v2.1-or-later** (`COPYING.LIB`, `LICENSE`).

## CodeWeavers / CrossOver

The macOS-focused performance features ported into this fork are **derived from CodeWeavers'
CrossOver Wine source**, which CodeWeavers publishes under the **LGPL v2.1-or-later** in
fulfilment of Wine's license. Deep thanks to the CodeWeavers engineers whose work this builds
on, including (non-exhaustively) the authors credited in the ported code. Features derived from
their source include:

- **msync** — the macOS shared-memory + Mach-port synchronization engine
- **D3DMetal** integration glue (Direct3D → Metal via Apple's Game Porting Toolkit)
- The **Vulkan/MoltenVK** renderer path and MoltenVK workarounds in wined3d
- **Apple Silicon / Rosetta 2** correctness fixups (signal handling, VM, wow64cpu)
- Cross-process **shared-memory window surfaces**, `WM_POINTER`, and related win32u work

### Not affiliated with CodeWeavers

This is an **independent, community fork**. It is **not** produced, endorsed, or supported by
CodeWeavers. **"CrossOver" is a trademark of CodeWeavers, Inc.** — CrossOver branding, naming,
icons, telemetry, and product-integration code have been deliberately **removed** from this fork.
Only the LGPL-licensed source was reused. If you want the supported, complete product, buy
[CrossOver](https://www.codeweavers.com/crossover) — it funds Wine development.

## Third-party components

- **bcdec** (`dlls/winemac.drv/opengl_bcdec.h`) — BC1–BC7 texture decoder by
  Sergii "iOrange" Kudlai, vendored unmodified (permissive MIT/Unlicense).
- **MoltenVK** (Apache-2.0) — Vulkan-over-Metal, a runtime dependency of the wined3d Vulkan path.
- **Apple Game Porting Toolkit / `libd3dshared.dylib`** — Apple proprietary; required at runtime
  for the D3DMetal path, loaded via `CX_APPLEGPTK_LIBD3DSHARED_PATH`. Not bundled or redistributed.

## License

This fork, like upstream Wine and the CrossOver-derived changes, is distributed under the
**GNU LGPL v2.1-or-later**. See `COPYING.LIB`.
