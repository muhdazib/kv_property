# KVProperty Power BI Dashboard Redesign Guide

This guide is based on the extracted structure of `dashboard.pbix`. The report uses a 1280 x 720 canvas and contains three pages: Home, Infrastructure, and Economic Zones.

## Theme

Import `kvproperty_powerbi_theme.json` in Power BI Desktop:

1. Open `C:\Users\azib\FYP\Website\dashboard.pbix`.
2. Go to `View` > `Themes` > `Browse for themes`.
3. Select `C:\Users\azib\FYP\Website\kvproperty_powerbi_theme.json`.
4. Save the PBIX.

Color system:

- Background: `#F4F1EA`
- Card surface: `#FFFFFF`
- Primary teal: `#008C83`
- Price/action coral: `#E85F3F`
- Amenity amber: `#C69232`
- Education violet: `#7357A6`
- Text: `#132327`
- Muted labels: `#637171`

## Global Dashboard Rules

Use a consistent report title band on every page:

- Position: `x 24`, `y 18`, `w 1232`, `h 52`
- Fill: `#132327`
- Text: white, 18-22px, Segoe UI Semibold
- Add a thin accent line under the title band using teal/coral/amber.

Use slicers as a left control rail:

- Position rail: `x 24`, `y 90`, `w 280`, `h 570`
- Slicer fill: `#FFFDF8`
- Slicer title: teal, uppercase style
- Keep slicers compact and aligned vertically.

Use 8px corner radius and light borders on all visuals. Keep visuals aligned to a 24px spacing system.

## Page 1: Home

Current visuals:

- 3 card visuals
- 3 slicers: district, mukim, property type
- 1 area chart: average transaction price by year
- 1 ribbon chart: district transaction ranking

Recommended layout:

- Left rail: place the 3 slicers from `x 24`, `y 96`, each `w 280`, `h 70`.
- KPI cards: place 3 cards across the top, starting at `x 328`, `y 96`, each around `w 292`, `h 118`.
- Area chart: place at `x 328`, `y 238`, `w 904`, `h 200`.
- Ribbon chart: place at `x 328`, `y 462`, `w 904`, `h 198`.

Suggested titles:

- Card 1: `Total Land Parcel Area`
- Card 2: `Average Transaction Price`
- Card 3: `Total Transaction Value`
- Area chart: `Average Transaction Price Trend`
- Ribbon chart: `District Transaction Ranking`

Polish:

- Use coral for price cards.
- Use teal for trend line/area.
- Turn on data labels only where values remain readable.
- Format currency as `RM #,0,,.0M` where suitable.

## Page 2: Infrastructure

Current visuals:

- 1 district slicer
- 2 clustered bar charts
- 1 pie chart
- 1 treemap

Recommended layout:

- Left rail: district slicer plus a short text box explaining infrastructure layers.
- Top row: mall distribution pie and university by state bar.
- Bottom row: combined infrastructure count by district as the main wide visual.
- Keep railway network treemap smaller as supporting context.

Suggested positions:

- Slicer: `x 24`, `y 96`, `w 280`, `h 72`
- Pie chart: `x 328`, `y 96`, `w 330`, `h 245`
- University bar: `x 682`, `y 96`, `w 550`, `h 245`
- Treemap: `x 24`, `y 392`, `w 280`, `h 268`
- Infrastructure district bar: `x 328`, `y 386`, `w 904`, `h 274`

Suggested titles:

- `Mall Distribution by District`
- `Universities by State`
- `Rail Network Composition`
- `Infrastructure Count by District`

Polish:

- Use mall amber, railway teal, university violet.
- Sort district bars descending by total infrastructure count.
- Avoid pie labels if crowded; use legend plus tooltip.

## Page 3: Economic Zones

Current visuals:

- 1 district slicer
- 1 table
- 1 map
- 1 donut chart
- 1 card

Recommended layout:

- Make the map the hero visual on this page.
- Keep the table as a ranked nearest-rail reference.
- Use the donut chart as a district composition summary.

Suggested positions:

- Slicer: `x 24`, `y 96`, `w 280`, `h 72`
- Card: `x 24`, `y 192`, `w 280`, `h 120`
- Donut chart: `x 24`, `y 346`, `w 280`, `h 314`
- Map: `x 328`, `y 96`, `w 560`, `h 564`
- Table: `x 912`, `y 96`, `w 320`, `h 564`

Suggested titles:

- Card: `Nearest Economic Zone`
- Donut chart: `Economic Zones by District`
- Map: `Economic Zone Locations`
- Table: `Nearest Rail Access by Economic Zone`

Polish:

- Use teal map bubbles with 65-75% transparency.
- Use coral for closest-distance emphasis.
- Rename `nearest_distance` to `Nearest Rail Distance` and format as km if the source unit is km.

## High-Impact Fixes Before Submission

1. Rename all auto-generated field labels into readable names.
2. Add report page title bands so screenshots look intentional.
3. Align every visual to the same left/top edges.
4. Use no more than 4 main colors per page.
5. Format all price values with `RM` and thousands separators.
6. Use tooltips instead of overcrowded data labels.
7. Keep slicers in the same location on every page.
