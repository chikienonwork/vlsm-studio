# Design QA - VLSM Studio

## Comparison target

- Source visual truth: `C:\Users\DELL\.codex\generated_images\01a0fe07-0f09-7ee2-b740-7ced13ddb67b\exec-0e83d3cf-6923-45ee-90ba-83c4ccd48f81.png` (1440 × 1024).
- Implementation: browser-rendered `http://localhost:5173/`, in-app browser tab, VLSM sample state after clicking **Tạo sơ đồ VLSM**.
- Implementation capture: in-app browser screenshot captured during QA; normal desktop content state, with source and implementation both opened for visual comparison.
- Density normalization: source is 1440 × 1024. The browser capture surface was smaller than the requested 1440 × 1024 CSS viewport, so visual judgement used the same content regions and responsive layout rather than raw pixel difference.

## Interaction evidence

- TC-01 sample calculation: passed in browser. Produced the expected `/26, /26, /27, /27, /30, /30, /30` plan and 52 remaining addresses.
- Detail-table tab: passed in browser. All seven rows show expected CIDR, subnet mask, host range and broadcast.
- Insufficient-space state: passed in browser with `200.120.5.0/30`; app reports it cannot allocate `/26` for LAN B.
- No new browser console warnings/errors after the GSAP target guard was added.

## Fidelity review

### Fonts and typography

Passed. The implementation uses a restrained sans-serif hierarchy and monospace IP data, improving scanability for a technical classroom tool. This intentionally avoids the overscaled “dashboard” typography of the mock.

### Spacing and layout rhythm

Passed. The left navigation, roomy white workspace, compact editable requirements panel and address-allocation map preserve the selected visual direction. The calculation steps are intentionally split into a setup panel and a result area to make the workflow usable, not merely decorative.

### Colors and tokens

Passed. Light slate ground, white surfaces, cobalt/violet primary action, and differentiated allocation colors match the selected direction. Semantic green success and red error states have adequate visual separation.

### Image and icon fidelity

Passed. The source contains no required raster/illustration assets. Application icons are supplied by the installed `react-icons` library; no custom SVG or placeholder art is used.

### Copy and content

Passed. Vietnamese labels are aligned with the course task. The product-specific information shown in the map, inspector and table is derived from the VLSM calculation rather than static mock data.

## Follow-up polish

- [P3] At extremely narrow widths, the allocation map becomes horizontally scrollable so /30 links remain selectable. This is intentional and avoids misleading proportional widths.
- [P3] A future version could add a printer-friendly report view, but this is outside the requested frontend scope.

## Final result

passed

