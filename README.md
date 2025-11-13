🌾 Power BI Report - Agricultural Survey
📋 Project Description
Detailed Power BI analysis report on an agricultural survey including data on farmers, plots, crops, irrigation, and agricultural equipment.
🎯 Objectives

Analyze farmer profiles
Track production and plot distribution
Evaluate resource utilization (irrigation, equipment)
Identify trends and training needs
Map agricultural areas

📊 Report Pages
1. Summary (Home Page)
Overview of the report with navigation to all sections:

Farmer Contact
Production décole and other plots
General Production
Irrigation
Product Usage
Soil Work
Size
Disaggregators
Harvest
Expenses

2. Farmer Contact
Demographic and geographic analysis of farmers:

Key Statistics: 11 farmers, average age 54.60 years, 4.48 farmers/area
Age Distribution: Young (22%) vs Old (78%)
Geographic Distribution: Interactive map with farmer locations
Farm Types: Initial property, communal property, rental
Training: Number of farmers by education level (Bachelor's degree to Secondary)

3. Décole Production and Other Plots
Detailed analysis of agricultural plots:

Olive Trees Comparison: Old vs New olive trees with temporal evolution
Plantation Types: Statistics on uprooted olive trees, peach trees, new plantations
Data by Plot: Detailed table with identifiers, areas, acquisition years
Mapping: Location of plots 1 and 2 with additional data
Focus: Analysis of farmers with multiple plots

4. Irrigation
Irrigation management and analysis:

Number of Irrigated Plots: 50 plots
Irrigation Types: Local irrigation (92%) vs Social irrigation (8%)
Temporal Evolution: Irrigation trends by year
Techniques: Distribution between Manual, Electric and Solar Pump
Distribution by Crop: Basin, Drip, Cistern
Detailed Data: Tables with initial water table averages, water levels for 2025

5. Product Usage & Equipment
Agricultural Equipment

Inventory: 4 herbicides, 6 soil analyzers
Plow Types: Canadian (7), Moldboard (7), Disc (8)
Details by Plot: Tillage tools (wet and dry season)
Usage Periods: October/July, Fall/Winter/Spring, etc.

Products and Interventions

Feeding: Light, Medium, Heavy
Worker Types: Specialized, manual
Intervention Periods: Before/after harvest, seasonality
Payment Methods: Every year, every 2 years, according to production

6. Diseases and Pests
Phytosanitary monitoring:

Wet Season: 12 wet olive diseases, 14 tree diseases
Dry Season: 14 dry olive diseases, 47 tree diseases
Detailed Tables:

Diseases by delegation (Moth, Psyllid, Moth/Olive fly)
Location (Menzel Kamel, Bebalita)
Types (Cercosporosis, Tuberculosis, Rot, Netoun)



7. Transportation Methods

Self-consumption per year: 500-1200 units
Harvest duration: 0.50 to 1.00 (in months)
Oil format: Continuous chain
Financing modes: Self-financing, Own funds
Oils used: Data by plot

8. Purchases and Expenses
Financial analysis:

Olive purchases: Wet season, wet season borders, dry season lost borders, other wet season
Amounts: 75000, 50000, 39000, 7500, 1200, 900 (in local currency)
Tracking by plot: IDPAR identifiers with transaction details

🛠️ Technologies Used

Power BI Desktop: Report creation and design
SQL Server: Data cleaning and transformation (more dynamic than Power Query)
DAX: Custom measures and calculations
Power Query: Complementary data transformations

🔄 Data Processing
SQL Cleaning
Using SQL Server for dynamic data cleaning, including:

UPDATE with CASE to standardize values (e.g., plow types)
Value replacement to standardize categories
WHERE queries to filter specific plots

Example of SQL code used:
sqlUPDATE [Enquete].[dbo].[la-taille-olivier]
SET [Outil_de_labour_en_année_humide]=
CASE
    WHEN ID_PARCELLE='IDPAR002' THEN 'Charue à soc'
    WHEN ID_PARCELLE='IDPAR005' THEN 'Charrue canadienne'
    ...
END
WHERE [ID_PARCELLE] IN ('IDPAR002', 'IDPAR005', ...);
🎨 Advanced Features

Interactive Navigation: Summary page with navigation buttons to all sections
Mapping: Interactive maps with geographic location of farmers and plots
Dynamic Filters: By delegation, acquisition year, crop type
Custom Visuals:

Dynamic images representing recruiters
Precision agriculture in different sections (irrigation, equipment)
Temporal and comparative charts


KPI Cards: Real-time key indicators

📁 File Structure
enquete-agriculture/
│
├── Agricultural_Survey_Report.pbix     # Main Power BI file
├── README.md                           # This file
└── data/                              # (If applicable) Source data
🚀 How to Use This Report

Open the file: Download and open Agricultural_Survey_Report.pbix with Power BI Desktop
Refresh data: If connected to a SQL source, click "Refresh"
Navigate: Use the Summary page to access different sections
Filter: Use filters at the top of each page to customize analysis
Export: Export visuals or data as needed

📈 Key Insights

78% of farmers are in the "Old" category (vs 22% Young)
92% use local irrigation
Most plots were acquired between 2000-2019
Main crops include olive trees, cereals, and livestock annexes
Diseases are more frequent in dry season (47) than wet season (12)# enquete-agriculture
