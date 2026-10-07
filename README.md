Vehicle & Heavy Equipment Import Study — US East Coast → Latin America
Market study of passenger vehicle and heavy equipment (High & Heavy) imports from the US East Coast into West Coast South America and the Caribbean, built from customs import declarations.
The study was prepared to support commercial planning for a deep-sea RoRo / PCTC (Pure Car & Truck Carrier) operator: sizing each market, identifying the main importers, and spotting opportunities on the US East Coast → Latin America trade lanes.
> **Note on confidentiality:** this repository documents the methodology and approach only. The original analysis used licensed commercial trade data and was prepared for a private client, so no client names, importer names or real figures are included here.
Files in this repository
File	What it is
`README.md`	This case study: scope, methodology, data challenges and findings
`Import_Study_Method_Demo.xlsx`	Working demo of the full method on fictional data (306 declaration lines, 6 countries). All results are live formulas.
How to explore the workbook: open the About sheet first, then Raw_Data (rows highlighted in orange show the repeated-weight check in action), and finally the Ranking sheets, where you can switch country in the yellow cell.
---
Scope
Segment	Definition	Markets
Passenger vehicles & light commercial	Cars and trucks, ≤ 15,000 kg per unit	Chile, Colombia, Peru, Ecuador, Dominican Republic, Panama
High & Heavy (H&H)	Heavy trucks, tractors, buses, construction and agricultural machinery, > 15,000 kg per unit	Chile, Colombia, Peru, Ecuador, Dominican Republic, Panama
Regions
West Coast South America: Chile, Colombia, Peru, Ecuador
Caribbean: Dominican Republic, Panama
Why only two Caribbean markets?
Most other Caribbean markets (Jamaica, Trinidad & Tobago and the English-speaking Caribbean in general) drive on the left and source their fleets mainly from Japan (right-hand-drive vehicles), not from the US. They also lacked usable customs data on the platforms available. The Dominican Republic and Panama were the only markets in the region with both US-origin left-hand-drive demand and reliable import data.
---
Methodology
1. Product classification (HS / HTS codes)
Segment	HS headings
Passenger vehicles & light commercial	8703 (passenger cars), 8704 (goods vehicles)
High & Heavy	8701 (tractors), 8702 (buses), 8704 > 15 t (heavy trucks), 8705 (special-purpose vehicles), 8426 (cranes), 8427 (forklifts), 8429 (bulldozers, excavators, loaders), 8430 (other earthmoving / drilling machinery), 8433 (harvesters)
2. Weight-based segmentation
The split between the two segments is a 15,000 kg per unit threshold.
Unit weight was calculated from each declaration line as gross weight ÷ quantity, rather than relying on the weight implied by the tariff subheading, which is often too broad to separate light from heavy units.
3. Identifying US East Coast origin
Origin data varies a lot by country, so a different approach was used for each:
Approach	Used when
Direct port of loading	The declaration records the US port of shipment
Geographic proxy	Only the port/customs office of entry is available; Atlantic-side entry used as a proxy
Three-bucket split (Atlantic / Pacific / Unclassified)	Countries with access to both oceans, where origin cannot always be determined
4. Importer ranking
Volumes aggregated by importer (units and weight)
Name normalization: variants of the same company (spacing, punctuation, legal suffixes) were unified before ranking
Top-10 rankings and market share calculated per country and segment
---
Data quality challenges
Real customs data is messy. The main issues found and how they were handled:
Repeated weight per declaration: in some datasets the total declaration weight was repeated on every line, inflating unit weights. Detected by grouping by declaration number + tariff heading and checking for identical weights across lines.
Duplicate importer names: the same company appeared under several spellings, which split its volume across multiple rows. Fixed through normalization.
Inconsistent coverage across countries: some headings (e.g. buses, 8702) were not equally available in every country's data. These gaps are documented rather than estimated.
Spreadsheet robustness: row-by-row division inside `SUMPRODUCT` formulas broke when recalculated in Excel. Replaced with helper columns + `SUMIFS`, which are faster and more reliable.
---
Key findings (qualitative)
The passenger vehicle markets are relatively concentrated, with a handful of brand distributors handling most of the volume.
The High & Heavy segment is much more fragmented. In some markets, volume is spread across dozens of small importers with only a few units each.
In some Caribbean markets the top H&H importers are freight forwarders and couriers rather than brand dealers. This matters commercially, because the decision-maker for the ocean freight may not be the end customer.
---
Deliverables (original project)
Importer ranking workbooks for each country and segment (12 in total)
A unified 19-slide presentation, organized by segment and region, with methodology slides
---
Tools
Data sources: commercial customs import databases (licensed)
Analysis: Excel (helper columns, `SUMIFS`, pivot tables)
Presentation: PowerPoint
---
Author
Luis — International trade & commercial analysis
LinkedIn <!-- replace with your profile URL -->
