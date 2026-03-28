# Known Issues

## Labels Not Functioning

**Status:** Open
**Branch:** `draw-box`

The coordinate ruler labels along the canvas edges are not rendering or responding correctly. This affects the Excel-style column and row labels displayed in the ruler strips (top, bottom, left, right).

### What should happen
- Column labels (A, B, C… or 1, 2, 3… depending on label mode) display in the top and bottom rulers
- Row labels display in the left and right rulers
- Label mode switcher (Alpha, Numeric, Zero-based, From centre, Hex, Binary) updates all four rulers immediately

### What is happening
- Labels are not displaying as expected

### Where to look
- `xLabel(c)` and `yLabel(r)` functions
- The ruler rendering block inside `draw()` — top ruler, bottom ruler, left ruler, right ruler sections
- The `label-select` change handler

### Related
- Label mode: `let labelMode = 'alpha'`
- Functions: `xLabel()`, `yLabel()`, `colLabel()`
