
📖 About the Project
This Power BI project presents a comprehensive and interactive analysis of an agricultural survey conducted with 50 farmers distributed across 5 delegations in the Monastir region: Zéramdin, Menzel Kamel, Touza, Jemmal, and Bébalita. The main objective is to apply precision agriculture principles by analyzing farming practices, resource utilization, and phytosanitary challenges.
🎯 Problem Statement
How can we optimize agricultural production in the Monastir region by identifying the most effective practices, irrigation needs, and phytosanitary threats? This analysis enables data-driven decision-making to improve productivity and sustainability.

🏗️ Technical Architecture
Star Schema Data Model
The data model follows a star schema architecture with the PARCELLE (Plot) table as the central fact table (the "dynamo" of the model). This design optimizes performance and facilitates multidimensional analysis.
                   
Primary join key: ID_PARCELLE + DELEGATION
This architecture enables:

✅ Efficient cross-filtering between all dimensions
✅ Fast aggregations by delegation, farmer, or plot
✅ Consistent temporal analysis
✅ Scalability to add new dimensions


🗂️ Report Structure (11 Interactive Pages)
#PageDescriptionKey Visualizations1SummaryCentral navigation hub with images of 2 surveyorsNavigation buttons, dynamic images2Farmer ContactDemographic profiles (age, education, property type)Geographic map, age charts, KPIs3Olive ProductionAnalysis of olive trees (old/new, uprooted)Temporal charts, detailed table4General ProductionCrop types by delegationBar charts, distribution5Irrigation50 irrigated plots, types (local 92% / social 8%)Temporal evolution, techniques (manual/electric/solar)6Product UsageAgricultural equipment (4 herbicides, 6 soil analyzers)Inventory, seasonal usage7Soil WorkTillage tools (Canadian, moldboard, disc plows)Detailed table by plot and season8Olive Tree PruningPruning practices, interventions, paymentsIntervention analysis by period9Pests & Diseases12 diseases (wet) vs 47 diseases (dry season)Tables by delegation and type10HarvestTransportation methods, self-consumption, durationFinancial and logistics data11ExpensesOlive purchases and expenses by seasonFinancial tracking by plot

🔬 Methodology: Precision Agriculture
This project applies precision agriculture principles through:

Exact Geolocation: Interactive mapping of plots by delegation
Granular Analysis: Plot-level data (ID_PARCELLE)
Temporal Monitoring: Practice tracking by season (wet/dry)
Data-Driven Decisions: Real-time KPIs to optimize resources

📊 Key Performance Indicators (KPIs)

50 agricultural farmers
50+ irrigated plots
10 farmers per delegation (average)
54.6 years average age
92% local irrigation vs 8% social
78% "older" farmers vs 22% "young"


🛠️ Technologies & Tools
ToolUsageWhy This Choice?Power BI DesktopReport creation, visualizationsIntuitive interface, native interactivitySQL ServerData cleaning and transformationMore dynamic than Power Query for massive UPDATEsDAXCustom calculated measuresComplex aggregations and time intelligencePower Query (M)Complementary transformationsSource connections and restructuring

🧹 Data Processing: Advanced SQL Cleaning
Why SQL Over Power Query?
For this project, SQL Server was preferred for data cleaning because:

✅ Faster for UPDATEs on large tables
✅ More flexible with complex CASE WHEN statements
✅ Traceability: Reusable and versioned scripts
✅ Standardization: Value uniformization (e.g., plow types)

SQL Script Example
sql-- Standardization of tillage tools in wet season
UPDATE [Enquete].[dbo].[la-taille-olivier]
SET [Outil_de_labour_en_année_humide] = 
    CASE 
        WHEN ID_PARCELLE = 'IDPAR002' THEN 'Charue à soc'
        WHEN ID_PARCELLE = 'IDPAR005' THEN 'Charrue canadienne'
        WHEN ID_PARCELLE = 'IDPAR011' THEN 'Charrue canadienne'
        WHEN ID_PARCELLE = 'IDPAR016' THEN 'Charue à soc'
        WHEN ID_PARCELLE = 'IDPAR017' THEN 'Charue à soc'
        WHEN ID_PARCELLE = 'IDPAR019' THEN 'Charue à soc'
        WHEN ID_PARCELLE = 'IDPAR020' THEN 'Charue à soc'
        WHEN ID_PARCELLE = 'IDPAR021' THEN 'Charue à soc'
        WHEN ID_PARCELLE = 'IDPAR028' THEN 'Charrue canadienne'
        WHEN ID_PARCELLE = 'IDPAR030' THEN 'Charue à disque'
        ELSE [Outil_de_labour_en_année_humide]
    END
WHERE ID_PARCELLE IN (
    'IDPAR002', 'IDPAR005', 'IDPAR011', 'IDPAR016', 'IDPAR017',
    'IDPAR019', 'IDPAR020', 'IDPAR021', 'IDPAR028', 'IDPAR030'
);

-- Result: Standardized values for 3 plow types
-- Canadian (7), Moldboard (7), Disc (8)

🎨 Advanced Features
1. Dynamic Surveyor Images

Photos of 2 surveyors that change based on selected delegation
Creates a human connection with the data

2. Intuitive Navigation

Home page (Summary) with buttons to all sections
Return to summary available from each page

3. Interactive Maps

Precise geolocation of farmers by delegation
Location of plots 1 and 2 with additional data

4. Dynamic Filters

By delegation (5 zones)
By acquisition year
By crop type
Cross-filtering across all pages

5. Comparative Analysis

Old vs new olive trees (temporal evolution)
Wet vs dry season (diseases, tools)
Local vs social irrigation


📈 Key Insights & Recommendations
🔍 Major Findings

Aging Agricultural Population

78% of farmers are over 50 years old
Recommended Action: Training programs for young farmers


Local Irrigation Dominance

92% local irrigation vs 8% social
Recommended Action: Study access to collective irrigation networks


Increased Phytosanitary Pressure in Dry Season

47 diseases in dry season vs 12 in wet season
Recommended Action: Strengthen monitoring and preventive treatments


Concentration of Acquisitions

Majority of plots acquired between 2000-2019
Insight: Recent agricultural investments, modernization opportunity


Diversity of Tillage Equipment

3 types of plows used equally
Insight: Adaptation to soil types and crops
