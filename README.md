# Performance-Based-Dashboard
## STEP 1 Prepare Your Data
Your dashboard shows these exact columns, so your CSV must have:
Match_No, Format, Year, Opponent, Runs, Average, Highest, 100s, 50s
Make sure Format column has values: ODI, T20, Test

Make sure Opponent has: Australia, England, WestIndies, SriLanka, SouthAfrica
## STEP 2  Load Data

Open Power BI Desktop
Click Home → Get Data → Text/CSV
Select your CSV → click Load

## STEP 3  Set Canvas Size

Go to View → Page view → Actual size
Click blank canvas → Format pane (paint roller) → Canvas settings
Set Width: 1280, Height: 720
Background color: keep default grey (as in your screenshot)

## STEP 4 Add the Kohli Background Image (Left Half)

Click Insert → Image
Upload your Kohli cricket photo (black & white style)
Drag it to cover the entire left side of the canvas
Right click image → Send to back
In Format → set Transparency to 30% so "KING KOHLI" text shows through

## STEP 5 Add "KING KOHLI" Text Watermark

Click Insert → Text Box
Type KING KOHLI in very large font (size 80–100)
Font: Impact or Arial Black, color: light grey/white
Set transparency to 60% so it looks like a watermark behind Kohli's image
Position it over the centre-left of the canvas

## STEP 6 Add the Cricket Career Info Box (top centre)
This is the grey rounded box showing Cricket career / ODI-2008 T20-2010 Test-2011:

Click Insert → Text Box
Type:

  Cricket career
  ODI- 2008  T20- 2010  Test- 2011

Format: background grey #D9D9D9, font size 11, border radius on (Format → Border)
Position it top-centre of the right panel

## STEP 7 Add the Year Slicer (Range Slider)
This is the Year slider showing 2008 → 2022:

Click Insert → Slicer
Drag Year column into the Field box
In Format → Slicer settings → Style → Between
This creates the exact range slider you see in your screenshot
Label it Year using the title setting in Format pane


## STEP 8 Create DAX Measures
Click Home → New Measure and create these one by one:
daxTotal Runs = SUM('Data'[Runs])

Team Count = COUNTROWS('Data')

AVG% = AVERAGE('Data'[Average])

Highest = MAX('Data'[Highest])

Total 100s = SUM('Data'[100s])

Total 50s = SUM('Data'[50s])

## STEP 9 Add the 6 KPI Cards (RUNS, TEAM COUNT, AVG%, Highest, 100s, 50s)
This is the row of white boxes showing 23709 / 516 / 45.95 / 254 / 77 / 129:

Click Insert → Card — do this 6 times
Assign each measure: Total Runs, Team Count, AVG%, Highest, Total 100s, Total 50s
For each card → Format pane:

Callout value: font size 36, color black, bold
Category label: font size 10, text = RUNS / TEAM COUNT / AVG% / Highest / 100s / 50s
Background: white, border: thin grey line


Line all 6 cards up in a row — use View → Snap to grid to align perfectly

## STEP 10 Add "Sum of runs by opponent" Bar Chart (bottom left of data panel)

Click Insert → Clustered Bar Chart (vertical bars)
Set:

X-axis → Opponent column
Y-axis → Total Runs measure


In Format → Data colors → set each opponent a different colour (pink, blue, purple, orange — matching your screenshot)
Format → Gridlines → Horizontal → color: light blue dashed line (matching the 5K and 0K gridlines you see)
Title: type Sum of runs by opponent
Background: white/light grey


## STEP 11 Add "Sum of Match_No by opponent" Donut Chart (bottom right of data panel)

Click Insert → Donut Chart
Set:

Legend → Opponent column
Values → Team Count measure (Match_No count)


In Format → Data colors: assign each opponent the exact colours matching your legend:

Australia → blue
England → dark blue
SouthAfrica → orange
SriLanka → purple/pink
WestIndies → pink


Enable Detail labels → set to show percentage (18.42%, 24.14%, etc.)
Title: Sum of Match_No by opponent

## STEP 12 Add the Legend Box
Your donut chart has a legend on the right side:

The legend appears automatically when you add the Opponent to Legend field
In Format → Legend → Position → Right
Font size: 10, color: dark grey

## STEP 13  Add "Sum of runs by Year" Line Chart (bottom full-width panel)
This is the large line chart at the bottom showing values like 325, 1021, 1644...:

Click Insert → Line Chart
Set:

X-axis → Year column
Y-axis → Total Runs measure


In Format → Data labels → On → this shows the numbers (325, 1021, 1644, etc.) on each point
Markers → On → shows the diamond dots on each year
Line color: blue (matching your screenshot)
Background: dark grey #3A3A3A
Title: Sum of runs by Year, color white, italic
Y-axis labels: white (500, 1000, 1500, 2000, 2500)
X-axis labels: white (2008 through 2022)

## STEP 14 Arrange All Visuals
Your exact layout from the screenshot:
[ Kohli Image + KING KOHLI text ] | [ Career info box ]  [ Year slicer ]
                                  | [ RUNS ][ TEAM ][ AVG ][ High ][ 100s ][ 50s ]
                                  | [ Bar chart (runs/opp) ] [ Donut chart ]
                                  | [ Line chart (runs by year) full width ]

Use Format → Align to align cards in a straight row
Use Ctrl + click to select multiple visuals and align them


## STEP 15 Publish / Export

Save as .pbix file → upload directly to GitHub
File → Export → Export to PDF → attach to README
Home → Publish → sign in to Power BI Service → get a shareable web link

## Image of Dashboard
<img width="1218" height="747" alt="Screenshot 2026-06-17 131312" src="https://github.com/user-attachments/assets/407e1418-2ebc-4f64-865e-0a4ee89ce7fa" />

