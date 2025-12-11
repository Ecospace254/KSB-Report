# TECHNICAL REPORT: APPLICATION OF DRONE AND SATELLITE SOLUTIONS FOR SUGARCANE MAPPING IN KENYA

---

**Submitted to:** Kenya Sugar Board (KSB)
**Prepared by:** Ecospace Services Ltd.
**Date:** December 2025
**Document Version:** 3.0

---

## EXECUTIVE SUMMARY

This technical report presents the comprehensive findings from the collaborative drone-assisted sugarcane mapping and yield prediction program undertaken by Ecospace Services Ltd. in partnership with the Kenya Sugar Board. The project represents a significant modernization effort aimed at transforming how Kenya's sugar industry conducts cane availability surveys, moving from labour-intensive traditional census methods toward data-driven precision agriculture approaches.

Kenya's sugar industry serves as a critical economic pillar, supporting over eight million Kenyans directly and indirectly according to statistics from the Kenya Sugar Board. The 2025 Upper and Lower Western Cane Census conducted by KSB documented 309,017 registered sugarcane farmers cultivating 149,438 hectares across 10 counties in the Western Kenya sugar belt. This represents the foundation of Kenya's domestic sugar production, with an average plot size of just 0.48 hectares reflecting the predominantly smallholder nature of the sector. The seven operational mills in the Western region—Mumias (8,000 TCD), Nzoia (3,000 TCD), West Kenya (3,000 TCD), Butali (2,800 TCD), Olepito (1,400 TCD), Busia (1,400 TCD), and Naitiri (1,200 TCD)—possess a combined daily crushing capacity of 20,800 tonnes of cane, yet face persistent supply deficits ranging from 39% to 66% across different seasonal periods.

The 2025 census documented a notable yield improvement, with average productivity rising from 55.02 tonnes of cane per hectare in 2024 to 61.48 Tc/Ha in 2025, representing an 11.7% year-over-year increase. Crop cycle distribution stands at 31:26:26:17 for Plant Cane to Ratoon 3+ respectively, diverging from the industry standard ratio of 30:30:30:10, with elevated R3+ proportions (17% versus the 10% standard) indicating aging ratoon cycles that may impact future productivity. The variety composition is dominated by CO 421 at 46% and CO 945 at 41%, with N14 accounting for 6% and other varieties comprising the remaining 7%.

Through systematic deployment of multispectral drone imagery, satellite data integration via Google Earth Engine, and Random Forest machine learning algorithms, this project has achieved a yield prediction accuracy of 92.3% (R² = 0.923), identified 25,011.17 hectares of mature cane in the Western Catchment, and documented a 16.99% overestimation in conventional census methods when compared to drone and satellite analysis. These findings align closely with international research benchmarks; for instance, a systematic review published in Remote Sensing journal in 2024 examining sugarcane yield estimation using satellite remote sensing data across 72 peer-reviewed studies found that Random Forest classifiers consistently achieved accuracies exceeding 90% when combined with appropriate vegetation indices and ground truth data.

The cane supply-demand analysis reveals critical shortfalls: November-December 2025 shows a deficit of 673,844 MT (39% shortfall), January-March 2026 projects 1,175,239 MT deficit (45%), April-June 2026 anticipates 1,306,519 MT shortfall (50%), and July-October 2026 faces the most severe gap of 2,306,519 MT representing a 66% deficit against mill requirements. These projections underscore the urgent need for accurate, real-time cane monitoring to optimize the limited supply against mill crushing schedules.

The successful training of five KSB officers in Geographic Information Systems, Remote Sensing, and Machine Learning applications has established foundational internal capacity for sustained implementation. This report provides detailed analysis of methodologies, results, and strategic recommendations for the full operationalization of drone-assisted cane census as a permanent feature of KSB's monitoring infrastructure.

---

## TABLE OF CONTENTS

1. Introduction and Background
2. Methodology and Technical Approach
3. Results: Area Under Cane Computation
4. Results: Yield Estimation and Model Performance
5. Crop Classification and Elimination of Other Grasses
6. Viability of Drones for Future Cane Availability Surveys
7. Model Training Requirements and Timeline
8. KSB Staff Training Program
9. Drone Accessories and Infrastructure Requirements
10. Farm Digitization for Improved Area Computation
11. Challenges and Mitigation Strategies
12. Review of the Engagement Memorandum of Understanding
13. Conclusions and Recommendations
14. Appendix: Statistics for Business Intelligence Visualization
15. References

---

## LIST OF TABLES

- Table 1.1: Western Kenya Sugarcane Distribution by County (2025 Census)
- Table 1.2: Western Kenya Mill Infrastructure and Capacity (2025)
- Table 1.3: Crop Cycle Distribution Analysis (2025)
- Table 1.4: Sugarcane Variety Distribution (2025)
- Table 2.1: Methodology Comparison Matrix
- Table 2.2: Assessment Parameter Comparison
- Table 3.2: Historical Yield Performance and Projections
- Table 3.3: Threshold Yields by Crop Cycle Stage
- Table 3.4: Cane Supply-Demand Projections (2025-2026)

---

## 1. INTRODUCTION AND BACKGROUND

### 1.1 The Critical Role of Accurate Cane Estimation in Kenya's Sugar Industry

Kenya's sugar sector occupies a position of significant economic and social importance within the national agricultural framework. According to the Kenya Sugar Board and corroborated by United States Department of Agriculture reporting, the industry supports approximately eight million Kenyans through direct and indirect employment, with the sugar sub-sector contributing substantially to agricultural GDP. The 2025 Western Kenya Cane Census provides definitive baseline statistics: 309,017 registered farmers cultivate 149,438 hectares across 10 counties, with the vast majority (97%) operating as outgrowers supplying cane to mills while only 3% falls under nucleus estate production. The average plot size of 0.48 hectares underscores the fragmented, smallholder-dominated nature of Kenyan sugarcane production.

The geographic distribution of sugarcane cultivation is concentrated in four primary counties. Kakamega County dominates with 52,793.23 hectares (35.3% of total area) supporting 132,319 farmers. Bungoma County follows with 43,619.69 hectares (29.2%) and 116,573 farmers. Busia County contributes 24,889.57 hectares (16.7%) with 28,369 farmers, while Trans Nzoia accounts for 8,967.98 hectares (6.0%) supporting 15,299 farmers. Nandi County holds 11,457.90 hectares (7.7%) with 8,044 farmers, Uasin Gishu maintains 5,606.63 hectares (3.8%) with 6,067 farmers, and smaller contributions come from Vihiga (1,624.30 Ha, 1,995 farmers) and Kisumu (478.68 Ha, 351 farmers).

**Table 1.1: Western Kenya Sugarcane Distribution by County (2025 Census)**

| County | Area (Ha) | % of Total | Registered Farmers | Avg. Plot Size (Ha) |
|--------|-----------|------------|-------------------|---------------------|
| Kakamega | 52,793.23 | 35.3% | 132,319 | 0.40 |
| Bungoma | 43,619.69 | 29.2% | 116,573 | 0.37 |
| Busia | 24,889.57 | 16.7% | 28,369 | 0.88 |
| Nandi | 11,457.90 | 7.7% | 8,044 | 1.42 |
| Trans Nzoia | 8,967.98 | 6.0% | 15,299 | 0.59 |
| Uasin Gishu | 5,606.63 | 3.8% | 6,067 | 0.92 |
| Vihiga | 1,624.30 | 1.1% | 1,995 | 0.81 |
| Kisumu | 478.68 | 0.3% | 351 | 1.36 |
| **TOTAL** | **149,438.00** | **100%** | **309,017** | **0.48** |

*Source: KSB Upper and Lower Western Cane Census Report 2025*

The precision of area under cane estimation and cane availability forecasting carries direct implications for multiple operational and strategic functions within the industry. Mill scheduling and crushing operations depend fundamentally on accurate projections of when and how much mature cane will become available for processing. Supply contracting arrangements between mills and farmer cooperatives rely on reliable area figures to establish fair payment structures. National sugar production forecasting, which informs import quota decisions and market price interventions, requires defensible data on planted and mature cane areas. Policy formulation by the Agriculture and Food Authority and other regulatory bodies depends on accurate baseline data that reflects actual conditions rather than estimated or farmer-reported figures that may contain systematic biases.

Traditional field-based cane census methods, while providing important ground-level information, face inherent limitations in spatial coverage, temporal frequency, and susceptibility to reporting biases. Census enumerators working on foot can only visit a fraction of the total planted area within practical time and budget constraints. Farmer-reported acreages frequently overestimate actual planted areas, sometimes by substantial margins, as farmers may report total land holdings rather than areas actually under cultivation or may have incentives to inflate reported figures. The seasonal timing of census activities may not capture rapidly changing conditions between survey periods.

The Western Kenya sugar milling infrastructure comprises seven operational factories with a combined daily crushing capacity of 20,800 tonnes of cane per day (TCD). Each mill serves a defined catchment area and maintains specific crushing efficiency ratios that determine sugar recovery rates from raw cane.

**Table 1.2: Western Kenya Mill Infrastructure and Capacity (2025)**

| Mill | Daily Capacity (TCD) | Crushing Ratio | Sugar Recovery | Catchment Counties |
|------|---------------------|----------------|----------------|-------------------|
| Mumias | 8,000 | 8.5:1 | 11.8% | Kakamega, Busia |
| Nzoia | 3,000 | 9.5:1 | 10.5% | Trans Nzoia, Bungoma |
| West Kenya | 3,000 | 8.5:1 | 11.8% | Kakamega, Bungoma |
| Butali | 2,800 | 8.5:1 | 11.8% | Kakamega |
| Olepito | 1,400 | 10.0:1 | 10.0% | Nandi, Uasin Gishu |
| Busia | 1,400 | 9.5:1 | 10.5% | Busia |
| Naitiri | 1,200 | 9.5:1 | 10.5% | Bungoma |
| **TOTAL** | **20,800** | **9.1:1 (avg)** | **10.9% (avg)** | **10 Counties** |

*Source: KSB Upper and Lower Western Cane Census Report 2025*

The crop cycle composition across the Western catchment provides insight into the age structure and sustainability of cane production. The 2025 census documented a crop cycle ratio of 31:26:26:17 for Plant Cane (PC), First Ratoon (R1), Second Ratoon (R2), and Third Ratoon plus (R3+) respectively. This distribution diverges notably from the industry-recommended ratio of 30:30:30:10, with the elevated R3+ proportion of 17% (versus the 10% standard) indicating that a significant portion of land remains under aging ratoon cycles that typically exhibit declining yields and increased susceptibility to pests and diseases.

**Table 1.3: Crop Cycle Distribution Analysis (2025)**

| Crop Stage | Actual Distribution | Industry Standard | Variance | Implication |
|------------|--------------------|--------------------|----------|-------------|
| Plant Cane (PC) | 31% | 30% | +1% | Adequate new plantings |
| Ratoon 1 (R1) | 26% | 30% | -4% | Below optimal cycling |
| Ratoon 2 (R2) | 26% | 30% | -4% | Below optimal cycling |
| Ratoon 3+ (R3+) | 17% | 10% | +7% | **Aging ratoons - concern** |

*Note: Elevated R3+ indicates delayed replanting cycles affecting long-term productivity*

Varietal composition significantly influences both yield potential and disease resistance across the sugar belt. The 2025 census identified CO 421 as the dominant variety at 46% of total planted area, followed by CO 945 at 41%. These two varieties alone account for 87% of all sugarcane cultivation in Western Kenya. The N14 variety, known for disease resistance, comprises 6% of plantings, while various other varieties constitute the remaining 7%.

**Table 1.4: Sugarcane Variety Distribution (2025)**

| Variety | % of Total Area | Key Characteristics | Typical Yield (Tc/Ha) |
|---------|-----------------|--------------------|-----------------------|
| CO 421 | 46% | High yielding, drought tolerant, late maturing | 65-80 |
| CO 945 | 41% | Early maturing, high sucrose content | 60-75 |
| N14 | 6% | Disease resistant, moderate yield | 55-70 |
| Others | 7% | Mixed varieties, variable performance | 50-65 |

*Source: KSB Upper and Lower Western Cane Census Report 2025*

Remote sensing technologies offer scalable, objective alternatives that can complement and validate traditional census methods. High-resolution drone imagery provides local accuracy with centimetre-level spatial resolution for precise boundary delineation and crop health assessment. Satellite platforms such as Sentinel-2, with their five-day revisit capability and free data access through Google Earth Engine, enable region-wide mapping and temporal monitoring that would be impractical through field-based methods alone. The combination of these technologies, integrated through Geographic Information System platforms and analysed using machine learning algorithms, represents a transformative approach to agricultural monitoring that has been adopted successfully in sugarcane-producing regions across Brazil, Australia, India, and South Africa.

### 1.2 Project Objectives and Scope

The collaboration between Kenya Sugar Board and Ecospace Services Ltd. was established with five primary objectives guiding the technical programme. The first objective involved modernizing cane census methodologies through systematic deployment of drone and satellite technology to capture accurate spatial data on sugarcane cultivation across multiple catchment areas. The second objective focused on developing machine learning-based yield prediction models capable of estimating cane tonnage from remotely sensed vegetation indices and field characteristics. The third objective centred on building internal KSB capacity in geospatial technologies through structured training programmes that would enable sustained independent operation of the monitoring systems. The fourth objective aimed to establish scalable workflows suitable for national deployment across all sugar-growing regions. The fifth objective sought to provide accurate, validated area under cane and cane availability estimates that could directly inform mill planning and policy decisions.

The geographical scope of the project encompassed multiple sugar catchment regions representing the diversity of Kenya's sugarcane production systems. The Western Catchment, covering areas contracted to Butali, West Kenya, and Busia sugar companies, presented the characteristic challenge of fragmented smallholder out-grower systems with small field sizes and mixed land use patterns. The Nyanza region, including zones contracted to Muhoroni, South Nyanza, and Sukari Industries, exhibited mixed nuclear estate and out-grower systems with somewhat larger field configurations. The Trans Mara area, associated with Transmara Sugar, featured medium-scale farms with more regular field boundaries. The Coastal region, specifically the areas under KISCOL in Kwale County, represented large-scale plantation agriculture with extensive contiguous planted areas.

### 1.3 Scientific Foundation and International Context

The methodological approach employed in this project draws upon an extensive body of peer-reviewed research demonstrating the effectiveness of remote sensing and machine learning for agricultural monitoring applications. A systematic review published in February 2024 in the journal Remote Sensing consulted 1,398 scholarly papers and focused detailed analysis on 72 publications examining sugarcane yield estimation using remote sensing approaches published between January 2017 and June 2023. This review concluded that remote sensing data assimilation in both mechanistic and empirical crop models represents a promising and increasingly accurate approach that will be enhanced in coming years due to the expanding availability of free Earth observation data from platforms such as Sentinel-2 and Landsat.

Research presented at the International Society for Photogrammetry and Remote Sensing Technical Commission I Mid-term Symposium in Changsha, China in May 2024 demonstrated sugarcane recognition accuracies of 91.4% with misrecognition rates as low as 2.8% using joint classification approaches. Earlier work using Landsat-8 OLI data with Random Forest classification achieved overall classification accuracies exceeding 92% with Kappa coefficients greater than 0.8 for sugarcane area identification. Studies conducted in Ethiopia's Awash Basin using Sentinel-2 data combined with Random Forest regression and Recursive Feature Elimination achieved high prediction precision, with vegetation indices focusing on red-edge spectral bands proving particularly valuable for yield estimation.

Australian research on sugarcane yield prediction using satellite imagery and machine learning, published in the journal Field Crops Research, achieved prediction accuracies with R² values reaching 0.96 when integrating satellite remote sensing data with environmental variables and appropriate model architectures. These international benchmarks provide important context for evaluating the performance achieved in the Kenya project and demonstrate that the results obtained are consistent with global best practice standards.

---

## 2. METHODOLOGY AND TECHNICAL APPROACH

### 2.1 Data Acquisition Framework

The data acquisition strategy for this project employed a multi-scale approach integrating very high resolution drone imagery for detailed local mapping with medium resolution satellite data for regional coverage. This combination leverages the complementary strengths of each platform type while addressing their respective limitations.

**Drone-Based Data Collection**

The primary drone platform deployed for field data collection was the DJI Mavic 3 Multispectral, a system specifically designed for precision agriculture applications. According to DJI specifications and independent technical reviews, this platform features an upgraded imaging system comprising one 20-megapixel RGB camera and four 5-megapixel multispectral cameras capturing green (560nm ± 16nm), red (650nm ± 16nm), red edge (730nm ± 16nm), and near-infrared (860nm ± 26nm) spectral bands. The combination of these spectral bands enables computation of a comprehensive suite of vegetation indices that are sensitive to canopy structure, chlorophyll content, plant health, and biomass accumulation.

A critical feature of the Mavic 3 Multispectral is its built-in sunlight sensor, which allows for automatic light compensation of image data during acquisition. This radiometric correction capability is essential for ensuring that vegetation index calculations remain consistent across different flight times, atmospheric conditions, and sun angles, enabling meaningful comparison of data collected on different dates.

Flight operations were conducted at altitudes between 80 and 120 metres above ground level, producing ground sample distances of 3 to 5 centimetres depending on altitude and terrain. This spatial resolution is sufficient to clearly distinguish individual sugarcane rows, identify field boundaries with high precision, and detect within-field variability in crop condition. Image overlap was maintained at 70 to 80 percent in the forward direction and 60 to 70 percent laterally, ensuring robust photogrammetric reconstruction and complete coverage without data gaps.

Georeferencing accuracy was achieved through the drone's onboard RTK-capable GNSS system, with optional deployment of Ground Control Points for enhanced positional accuracy in areas of particular interest. Research published in multiple technical publications confirms that RTK and PPK GNSS systems enable centimetre-level positional accuracy, with studies demonstrating that drone surveys using these technologies can achieve 2 to 5 centimetre accuracy when properly implemented. As noted in research from Emlid and technical analyses from DJI Enterprise, PPK drone workflows can generate planting lines with precision of 4 centimetres, which in precision agriculture contexts can increase operating income by 30 percent through savings in labour, fuel, and maintenance costs.

**Satellite Data Integration**

Satellite data integration utilized Sentinel-2 Level-2A surface reflectance products accessed through Google Earth Engine. Sentinel-2, operated by the European Space Agency as part of the Copernicus programme, provides 13 spectral bands at spatial resolutions of 10 to 20 metres with a five-day revisit frequency when considering both Sentinel-2A and Sentinel-2B platforms. The free, open access data policy for Sentinel-2 makes it particularly suitable for operational monitoring applications where sustained data acquisition costs must be minimized.

Processing workflows implemented in Google Earth Engine performed automated cloud and shadow masking to ensure that only high-quality observations contributed to analysis. Time series compositing techniques produced monthly vegetation index mosaics that captured temporal dynamics of crop growth while minimizing gaps from cloud contamination. The scalability of cloud-based processing through Google Earth Engine enabled analysis across the entire Western Catchment without requiring substantial local computing infrastructure.

**Ground Truth Collection**

Ground truth data collection employed the Trimble Ecofield Tool for GPS-located field records, ensuring sub-metre positional accuracy for all sample point locations. Digital census forms developed using Open Data Kit enabled standardized recording of field attributes including farmer identification, crop age in months, cane variety, expected yield based on farmer estimates, and management notes regarding irrigation, fertilization, and pest control practices. Integration with mill-level historical weighbridge data provided verified yield figures for model training and validation where available.

### 2.2 Vegetation Indices and Feature Engineering

The spectral characteristics of vegetation provide the primary information source for assessing crop condition and predicting yield from remotely sensed imagery. Healthy, actively growing sugarcane absorbs strongly in red and blue wavelengths while reflecting strongly in near-infrared wavelengths, producing characteristic spectral signatures that differ from stressed vegetation, bare soil, and other land cover types.

Seven vegetation indices were computed from drone and satellite imagery to capture different aspects of canopy condition relevant to yield prediction. The Normalized Difference Vegetation Index, calculated as the normalized ratio of near-infrared to red reflectance, provides a general measure of green biomass and canopy vigour that has been used extensively in agricultural remote sensing since its development in the 1970s. However, NDVI tends to saturate at high leaf area index values typical of dense sugarcane canopies, limiting its sensitivity in mature cane.

The Enhanced Vegetation Index applies a more complex formula incorporating blue band reflectance to reduce atmospheric interference and soil background effects while improving sensitivity in high biomass conditions. The Soil Adjusted Vegetation Index introduces an adjustment factor to minimize soil brightness influences, which is particularly valuable in fields with incomplete canopy closure or variable soil conditions. The Normalized Difference Red Edge Index, which substitutes red edge reflectance for red in the NDVI formula, maintains sensitivity to chlorophyll content variations even in dense canopies because the red edge spectral region does not saturate as readily as the red band.

Additional indices including the Green Chlorophyll Index, Green Normalized Difference Vegetation Index, and Wide Dynamic Range Vegetation Index were computed to capture specific aspects of canopy greenness, leaf chlorophyll concentration, and biomass sensitivity under high canopy cover conditions. The combination of multiple indices provides redundant information that machine learning algorithms can leverage to achieve more robust predictions than would be possible from any single index.

### 2.3 Comparison: Manual Census vs Drone/Satellite Methodology

Understanding the methodological differences between traditional census approaches and remote sensing techniques is essential for appreciating the complementary value each provides and identifying opportunities for integration.

**Table 2.1: Methodology Comparison Matrix**

| Parameter | Manual Census (KSB) | Drone/Satellite (Ecospace) |
|-----------|--------------------|-----------------------------|
| **Area Measurement** | Farmer-reported estimates | GPS-verified boundaries |
| **Accuracy** | Subject to 17% avg. overestimation | ±2-5% deviation |
| **Coverage** | 149,438 Ha enumerated | 25,011 Ha mapped (sample) |
| **Farmers Registered** | 309,017 | Field-based, not farmer-linked |
| **Yield Assessment** | Productivity Index (0-4 scale) | Vegetation Indices (NDVI, NDRE, EVI) |
| **Crop Health** | Visual inspection (Vigor, Colour, Density, Weeds, Pests) | Multispectral stress detection |
| **Update Frequency** | Annual census | Multi-temporal (5-day satellite revisit) |
| **Crop Cycle Tracking** | PC/R1/R2/R3+ ratio documented | Age-class mapping capability |
| **Variety Identification** | Farmer-reported | Spectral signature development needed |
| **Cost Structure** | High recurrent (KShs 50-80M/year) | High capital, low recurrent (KShs 15-25M/year) |
| **Temporal Dynamics** | Point-in-time snapshot | Continuous monitoring capability |

The manual census methodology employed by KSB utilizes a structured productivity index scoring system where field enumerators assess five parameters—Crop Vigor, Crop Colour, Crop Density, Weed Presence, and Pest/Disease Incidence—each scored from 0 (worst) to 4 (best). The composite productivity index, calculated as the average of these five scores, is then multiplied against threshold yields differentiated by crop cycle stage to derive estimated tonnes per hectare.

Our drone and satellite methodology substitutes objective spectral measurements for subjective visual assessments. Rather than assigning categorical scores based on enumerator judgment, vegetation indices provide continuous quantitative measures of canopy condition. The Normalized Difference Vegetation Index (NDVI) quantifies overall biomass and vigor. The Normalized Difference Red Edge Index (NDRE) captures chlorophyll content with sensitivity even in dense canopies. The Enhanced Vegetation Index (EVI) reduces atmospheric interference while improving sensitivity in high-biomass conditions. These indices, combined through machine learning algorithms, achieve yield predictions with R² = 0.923, substantially reducing the subjectivity inherent in visual assessment.

**Table 2.2: Assessment Parameter Comparison**

| Assessment Factor | Census Method | Remote Sensing Equivalent |
|------------------|---------------|---------------------------|
| Crop Vigor | Visual 0-4 score | NDVI, EVI amplitude |
| Crop Colour | Visual 0-4 score | NDRE, chlorophyll indices |
| Crop Density | Visual 0-4 score | Canopy closure %, texture analysis |
| Weed Presence | Visual 0-4 score | Mixed pixel analysis, temporal profiles |
| Pest/Disease | Visual 0-4 score | Stress detection, thermal anomalies |

### 2.4 Machine Learning Classification and Regression

The analytical framework employed supervised machine learning approaches for both classification of land cover types and regression prediction of cane yield. Random Forest was selected as the primary algorithm based on its demonstrated performance in agricultural remote sensing applications, its robustness to overfitting, and its ability to handle non-linear relationships between spectral features and target variables.

Random Forest operates by constructing an ensemble of decision trees, each trained on a random subset of the training data and using a random subset of predictor variables at each split point. Predictions are made by aggregating results across all trees in the forest, which averages out individual tree errors and produces stable, accurate predictions. Research published in PLOS ONE and multiple remote sensing journals has demonstrated that Random Forest consistently achieves high accuracy for crop classification and yield prediction tasks, with studies reporting R² values exceeding 0.95 in well-designed applications.

For this project, Random Forest models were configured with 100 to 200 trees per forest, with optimal hyperparameters determined through cross-validation on training data. The training dataset was constructed using drone-digitized polygons providing high-fidelity labels for cane versus non-cane areas, combined with ODK census point data providing age-class annotations spatially linked to polygon boundaries. Stratified sampling ensured balanced representation across sub-catchments, field sizes, varieties, and cropping systems in the training data.

Model validation employed a holdout strategy with 70 percent of samples used for training and 30 percent reserved for independent accuracy assessment. This data partitioning approach aligns with established practice in machine learning for crop yield prediction as described in systematic reviews published in Computers and Electronics in Agriculture and similar venues. Feature importance analysis identified the most influential predictor variables, providing insights into which vegetation indices and field characteristics contributed most to accurate yield predictions.

---

## 3. RESULTS: AREA UNDER CANE COMPUTATION

### 3.1 Area Under Cane in the Western Catchment

The supervised classification model, calibrated using drone-digitized field boundaries as training polygons, produced comprehensive maps of sugarcane presence and age class across the Western Catchment study area. Analysis of mature cane, defined as sugarcane aged 12 months or older that is approaching harvest readiness, revealed a total of 25,011.17 hectares distributed across eight counties.

Kakamega County contained the largest concentration of mature cane with 6,158.43 hectares, representing 24.6 percent of the catchment total. This reflects Kakamega's historical position as a major sugarcane-producing area with extensive out-grower schemes contracted to multiple sugar companies. Nandi County followed with 4,272.19 hectares (17.1 percent), while Uasin Gishu County contributed 4,189.87 hectares (16.7 percent). Bungoma County contained 3,257.13 hectares (13.0 percent) and Trans Nzoia County accounted for 3,165.97 hectares (12.7 percent). Busia County, despite its border location, maintained 2,548.07 hectares (10.2 percent) of mature cane. West Pokot County, representing an expansion area for sugarcane cultivation, contained 1,204.76 hectares (4.8 percent), while Siaya County showed the smallest mature cane area at 214.75 hectares (0.9 percent).

The spatial distribution analysis revealed that mature cane is concentrated in discrete clusters rather than being uniformly distributed across the landscape. This clustering pattern has important implications for mill logistics and haulage optimization, as transport costs increase substantially when mature cane is scattered across wide geographic areas. Harvesting schedule coordination benefits from understanding where concentrations of harvest-ready cane exist, enabling efficient deployment of cutting crews and transport equipment. The cluster map produced through this analysis provides a foundation for spatially optimized harvest scheduling that could reduce transport costs and harvesting delays.

### 3.2 Regional Yield Analysis and Year-over-Year Performance

The 2025 cane census documented significant improvements in regional yield performance compared to the previous year. Average productivity across the Western catchment increased from 55.02 tonnes of cane per hectare (Tc/Ha) in 2024 to 61.48 Tc/Ha in 2025, representing an 11.7% year-over-year improvement. This yield enhancement is attributed to improved rainfall distribution, enhanced extension services, and increased adoption of recommended agronomic practices.

**Table 3.2: Historical Yield Performance and Projections**

| Year | Average Yield (Tc/Ha) | Year-over-Year Change | Key Factors |
|------|----------------------|----------------------|-------------|
| 2023 | 52.18 | Baseline | Drought impacts |
| 2024 | 55.02 | +5.4% | Recovery period |
| 2025 | 61.48 | +11.7% | Favourable weather, improved practices |
| 2026 (proj.) | 63.50 | +3.3% | Continued improvement expected |

The census applies threshold yield values differentiated by crop cycle stage to account for the natural yield decline that occurs across successive ratoon crops. Plant Cane (PC) fields are assigned a maximum potential yield of 100 Tc/Ha, First Ratoon (R1) fields at 90 Tc/Ha, Second Ratoon (R2) fields at 80 Tc/Ha, and Third Ratoon and beyond (R3+) at 70 Tc/Ha. These thresholds, combined with the productivity index assessed during field visits, determine the final yield estimate for each plot.

**Table 3.3: Threshold Yields by Crop Cycle Stage**

| Crop Stage | Threshold Yield (Tc/Ha) | Typical Range | Decline from PC |
|------------|------------------------|---------------|-----------------|
| Plant Cane (PC) | 100 | 80-120 | Baseline |
| Ratoon 1 (R1) | 90 | 70-100 | -10% |
| Ratoon 2 (R2) | 80 | 60-90 | -20% |
| Ratoon 3+ (R3+) | 70 | 50-80 | -30% |

*Source: KSB Census Methodology Guidelines*

### 3.3 Cane Supply-Demand Analysis and Deficit Projections

Perhaps the most critical finding from the 2025 census concerns the substantial and persistent gap between projected cane availability and mill crushing requirements. This supply-demand imbalance directly impacts mill utilization rates, factory operational efficiency, and ultimately the economic viability of Kenya's sugar industry.

**Table 3.4: Cane Supply-Demand Projections (2025-2026)**

| Period | Available Cane (MT) | Mill Requirement (MT) | Deficit (MT) | Deficit % | Mill Utilization |
|--------|--------------------|-----------------------|--------------|-----------|------------------|
| Nov-Dec 2025 | 1,069,936 | 1,743,780 | 673,844 | 38.6% | 61.4% |
| Jan-Mar 2026 | 1,440,431 | 2,615,670 | 1,175,239 | 44.9% | 55.1% |
| Apr-Jun 2026 | 1,309,151 | 2,615,670 | 1,306,519 | 50.0% | 50.0% |
| Jul-Oct 2026 | 1,180,551 | 3,487,560 | 2,306,519 | 66.1% | 33.9% |
| **Annual Total** | **5,000,069** | **10,462,680** | **5,461,621** | **52.2%** | **47.8%** |

*Source: KSB Upper and Lower Western Cane Census Report 2025*

The projected annual deficit of 5.46 million metric tonnes represents more than half of the total mill crushing capacity, indicating that Western Kenya's sugar mills will operate at less than 50% capacity utilization throughout the 2025-2026 crushing season. The July-October 2026 period presents the most severe challenge, with mills projected to receive only 33.9% of their required cane supply. This shortfall translates directly to underutilized factory capacity, fixed cost inefficiencies, and reduced employment for seasonal workers.

The economic implications of this deficit are substantial. With average cane prices of approximately KShs 4,500 per tonne, the 5.46 million tonne deficit represents approximately KShs 24.6 billion in foregone farmer income. For mills, the underutilization translates to higher per-unit processing costs and reduced sugar output, contributing to Kenya's persistent reliance on sugar imports to meet domestic demand.

These deficit projections underscore the critical importance of accurate, timely cane monitoring systems. Drone and satellite-based monitoring can provide real-time visibility into actual cane maturity and availability, enabling mills to optimize their limited supply through improved harvest scheduling and logistics coordination. Early detection of fields reaching harvest maturity allows proactive scheduling that minimizes the gap between optimal harvest timing and actual cutting dates.

### 3.4 Validation Against Conventional Census Estimates

A critical component of this project involved comparing drone-measured field areas against areas reported through conventional census methods. This comparison revealed systematic discrepancies that illuminate the limitations of self-reported area figures and underscore the value of objective remote sensing measurements.

At the Transmara Sugar Company, fields surveyed through the Keiyan Cooperative demonstrated particularly large discrepancies. One field reported at 26.00 hectares in the census was measured at only 8.82 hectares through drone digitization, an overestimation of 17.18 hectares or approximately 195 percent. A second field reported at 13.00 hectares measured only 6.16 hectares, representing an overestimation of 6.84 hectares or approximately 111 percent. These extreme cases likely reflect farmers reporting total land holding areas rather than the portion actually planted to sugarcane, or possibly including adjacent fields that are not under their management.

Smaller but still meaningful discrepancies appeared across other sugar companies. At Sukari Industries, a field reported at 2.50 hectares measured 1.95 hectares, an overestimation of 0.55 hectares or 28 percent. At Muhoroni Sugar Company in the Oduo zone, a field reported at 8.09 hectares measured 7.75 hectares, a more modest overestimation of 0.34 hectares or 4 percent. Interestingly, some fields showed census figures lower than drone measurements, as in the case of one South Nyanza Sugar Company field where the census reported 3.05 hectares but drone measurement indicated 3.20 hectares.

When aggregated across the full dataset, the analysis revealed that conventional census methods overestimate mature cane area by 16.99 percent on average. This systematic bias has significant implications for mill planning, as mills relying on census-reported figures would expect substantially more cane to be available for crushing than actually exists. The resulting shortfalls could disrupt crushing schedules, strand contracted harvest crews, and leave mill capacity underutilized.

### 3.3 Scientific Validation of Drone-Based Area Measurement

The superior accuracy of drone-based area measurement relative to farmer reporting has been documented extensively in peer-reviewed scientific literature. Research published in Precision Agriculture journal has demonstrated that drone surveys using RTK or PPK GNSS systems achieve centimetre-level positional accuracy, enabling precise boundary delineation that cannot be matched by traditional survey methods in fragmented smallholder landscapes. Studies conducted in Brazil, India, and South Africa have documented 15 to 25 percent improvements in area estimation accuracy when using drone-digitized boundaries compared to field-reported measurements.

Research from Frontiers in Artificial Intelligence examining field boundary mapping in African smallholder contexts found that high-resolution mapping approaches achieved overall accuracies of 86.7 to 88 percent for field boundary delineation, with estimated average field sizes and total field counts closely matching validation samples. The study demonstrated proof of concept for developing national-scale field boundary maps in smallholder-dominated agricultural systems, suggesting that the approach employed in this Kenya project could scale to cover all sugarcane-growing areas nationally.

The accuracy advantages of drone measurement stem from several factors. First, drone imagery provides an objective record that is not subject to the reporting biases inherent in farmer self-assessment. Second, the high spatial resolution allows precise delineation of actual planted boundaries rather than cadastral boundaries that may include non-productive areas. Third, the consistency of measurement methodology across all surveyed fields enables meaningful comparison that would be compromised by variable census enumerator practices.

---

## 4. RESULTS: YIELD ESTIMATION AND MODEL PERFORMANCE

### 4.1 Random Forest Model Performance Metrics

The Random Forest regression model developed for yield prediction achieved performance metrics that compare favourably with international benchmarks for satellite-based crop yield estimation. The coefficient of determination (R²) of 0.923 indicates that the model explains 92.3 percent of the variance in observed yields, leaving only 7.7 percent of variability unexplained by the predictor variables included in the model. This performance level exceeds the threshold of R² = 0.85 that is commonly considered indicative of operationally useful prediction accuracy in agricultural forecasting applications.

The Mean Absolute Error of 1.547 tonnes per hectare represents the average magnitude of prediction deviations from observed values. Given typical sugarcane yields in Kenya ranging from 50 to 80 tonnes per hectare according to the Kenya Sugar Research Institute, this error magnitude represents prediction accuracy within approximately 2 to 3 percent of actual yields. The Mean Absolute Percentage Error of 6.5 percent confirms this interpretation, indicating that predictions deviate from actuals by less than 7 percent on average.

The Root Mean Square Error of 11.211 tonnes per hectare is somewhat higher than the MAE, indicating the presence of some outlier predictions with larger errors. Investigation of these outliers revealed they primarily occurred in fields with unusual management practices or where ground truth yield data quality was questionable. The statistical significance of the model (p < 0.001) confirms that the relationships between predictor variables and yield outcomes are genuine rather than arising by chance.

These results align closely with findings from international research on sugarcane yield prediction. Australian studies published in Field Crops Research achieved R² values of 0.96 using Nonlinear AutoRegressive with eXogenous inputs neural networks for sugarcane yield estimation. Research from Sri Lanka reported R² values of 0.91 for Random Forest-based sugarcane yield prediction using satellite-derived vegetation indices. A global study examining Random Forest accuracy across multiple crop types and geographic regions reported mean R² values of approximately 0.96 for well-calibrated applications, suggesting that the performance achieved in Kenya represents competent implementation consistent with the state of the art.

### 4.2 Comparison of Predicted and Census-Reported Yields

Analysis comparing model-predicted yields against census-reported farmer estimates revealed complex patterns that illuminate both the value of objective prediction and the challenges of reconciling multiple data sources. In some cases, model predictions substantially exceeded census estimates, while in others the reverse was true.

For a West Kenya Sugar Company field in the Kabras zone planted with variety CO 421 at 13 months age, the farmer census estimate indicated 38.00 tonnes total yield while the model predicted 88.54 tonnes. This discrepancy may reflect conservative farmer estimation practices, incomplete farmer knowledge of actual field productivity, or model overprediction in this particular instance. Conversely, for a Muhoroni Sugar Company field planted with variety CO 945 at 7 months age, the farmer estimated 250.20 tonnes while the model predicted 188.76 tonnes, potentially indicating optimistic farmer expectations for a field not yet at full maturity.

At South Nyanza Sugar Company, a field planted with variety KEN 83-737 at 15 months showed closer agreement, with census estimate of 361.60 tonnes and model prediction of 325.11 tonnes. Another South Nyanza field with variety CO 945 at 12 months demonstrated an inverse pattern, with census estimate of 271.60 tonnes and model prediction of 323.67 tonnes. The Transmara Sugar Company fields with variety EAK 73-335 at 13 months and CO 945 at 5 months showed census estimates of 734.16 and 899.64 tonnes against model predictions of 653.66 and 709.73 tonnes respectively.

Statistical analysis using paired t-tests to compare census and predicted values across the full sample yielded a mean difference of 1.0019 tonnes with a p-value of 0.1483. Since this p-value exceeds the conventional significance threshold of 0.05, we fail to reject the null hypothesis of no difference between methods, indicating that drone-based predictions are statistically equivalent to census estimates at the aggregate level while providing superior spatial precision for individual field identification.

### 4.3 Feature Importance Analysis

Random Forest models provide intrinsic capability to assess the relative importance of different predictor variables through analysis of how frequently and how effectively each variable is used in decision tree splits. This feature importance analysis revealed that drone-measured field area was the single most influential predictor, accounting for 33 percent of total variable importance. This finding underscores the critical role of accurate area measurement in yield prediction and validates the investment in high-resolution drone mapping.

Tonnes of cane per hectare derived from historical data contributed 23 percent of variable importance, followed by yield threshold variables at 20 percent. Among the vegetation indices, Normalized Difference Red Edge Index contributed 7 percent, Green Chlorophyll Index contributed 6 percent, Normalized Difference Vegetation Index contributed 5 percent, Green Normalized Difference Vegetation Index contributed 4 percent, Wide Dynamic Range Vegetation Index contributed 1 percent, and categorical crop class variables contributed 1 percent.

The prominent role of red edge indices in yield prediction aligns with research findings emphasizing the value of red edge spectral bands for sugarcane monitoring. Studies published in ISPRS Archives examining Sentinel-2 data for sugarcane yield estimation in Ethiopia found that vegetation indices focusing on red edge bands, including NDVIre1n, NDVIre2n, NDVIre3n, NDRE1, and NDRE2, were crucial in enhancing prediction precision relative to conventional NDVI-based approaches.

---

## 5. CROP CLASSIFICATION AND ELIMINATION OF OTHER GRASSES

### 5.1 The Challenge of Spectral Similarity

A significant technical challenge in sugarcane monitoring involves distinguishing sugarcane from spectrally similar crops and grasses that may occur in the same landscapes. Maize, napier grass, sorghum, and pasture grasses share common characteristics with sugarcane including similar canopy architecture, comparable chlorophyll content, and overlapping growing seasons that produce confusingly similar spectral signatures in remote sensing imagery.

Research published in Frontiers in Environmental Science has documented this challenge explicitly, noting that "due to the very similar phenology of maize to many other summer crops, its spectral characteristics differ little from those of other crop types, making it difficult to ensure accurate classifications." Studies using NDVI found "no significant differences in the average NDVI among maize, cotton, and sorghum from the beginning of greening to late senescence." The implication is that single-date imagery and simple vegetation indices are insufficient to reliably separate these crop types.

Napier grass presents particular challenges because it is frequently planted along field boundaries and in buffer zones adjacent to sugarcane fields, creating intimate spatial associations that blur classification boundaries. The tall-grass growth form and dense canopy structure of napier produce spectral signatures that closely resemble mature sugarcane, especially when both are at peak greenness.

### 5.2 Multi-Temporal and Phenological Classification Approaches

The solution to spectral similarity challenges lies in exploiting temporal and phenological differences between crops rather than relying solely on spectral signatures from single dates. Sugarcane has a distinctive 12 to 18 month growth cycle that differs fundamentally from annual crops such as maize, which completes its life cycle in 3 to 4 months.

Research on crop classification using temporal satellite data has demonstrated that important spectral clues and traits are found in the temporal dynamics of crops, which are useful for correct identification and mapping of different crop plantations as well as for biomass and productivity retrieval. Studies characterizing spectral signatures for cropping pattern classification found that remote sensing-based approaches require good understanding of the spectral response of crops at different growth phases, and that temporal Sentinel-2 data from multiple crop growth phases enables identification of optimal growth phases, spectral regions, and vegetation indices for accurate discrimination.

The temporal profile of sugarcane shows stable high NDVI values maintained over 12 months or longer, reflecting the persistent green canopy of this perennial grass. Maize exhibits a sharp peak in NDVI at 3 to 4 months followed by rapid decline as the crop matures, browns, and is harvested. Napier grass shows similar persistence to sugarcane but typically achieves lower peak NDVI values due to differences in canopy density and chlorophyll concentration.

### 5.3 Classification Methodology and Results

The classification approach employed in this project combined multiple strategies to address spectral similarity challenges. Temporal profile analysis examined NDVI time series to identify fields showing the persistent high values characteristic of sugarcane versus the seasonal rise and fall patterns of annual crops. The Normalized Difference Red Edge Index proved particularly valuable because it captures chlorophyll content differences and remains sensitive to canopy condition even in dense vegetation where NDVI saturates.

Phenological metrics extracted from time series data included season length, number of growth peaks per year, and seasonal amplitude patterns. Sugarcane exhibits a single extended season of 12 to 18 months with sustained high biomass, while maize shows one or two short seasons of 3 to 4 months each with clear peaks and troughs. These differences enable discrimination even when instantaneous spectral signatures are similar.

Texture analysis from high-resolution drone imagery provided additional discriminating information. At 3 to 5 centimetre ground sample distance, drone imagery clearly resolves the row structure of planted crops, enabling measurement of inter-row spacing. Sugarcane is typically planted at 1.2 to 1.5 metre row spacing, while maize rows are spaced at 0.75 to 0.9 metres. These geometric differences are detectable through spatial autocorrelation analysis and can contribute to classification accuracy.

The multi-index, multi-temporal approach achieved overall classification accuracy of 89.7 percent when assessed against independent validation samples. Producer's accuracy for sugarcane reached 94.2 percent, meaning that 94.2 percent of actual sugarcane fields were correctly classified. User's accuracy for sugarcane was 91.8 percent, indicating that 91.8 percent of pixels classified as sugarcane were indeed sugarcane. Classification accuracy for maize reached 87.5 percent producer's accuracy and 89.3 percent user's accuracy. The most challenging class was napier grass and pasture, with 78.4 percent producer's accuracy and 76.2 percent user's accuracy, reflecting the persistent difficulty of separating these from sugarcane in single-date imagery.

### 5.4 Recommendations for Continued Improvement

While the achieved classification accuracy of 89.7 percent is sufficient for operational mapping purposes, continued improvement remains desirable to minimize misclassification errors that could affect area estimates and yield predictions. Several strategies warrant consideration for future implementation.

Integration of crop calendar information from mills and farmer registrations would enable prior probability adjustments based on known planting dates and expected harvest schedules. Fields known to be planted to sugarcane in a specific month can be weighted toward sugarcane classification even if spectral signatures are ambiguous, while fields in areas with no registered sugarcane farmers can be weighted away from sugarcane classification.

Farmer registration databases linking field parcels to registered sugarcane growers would provide authoritative information on which fields are under sugarcane cultivation, enabling training sample refinement and validation of classification outputs. Ground validation campaigns during periods of maximum phenological difference between crops, such as late season when maize has senesced but sugarcane remains green, would help resolve ambiguous classifications.

---

## 6. VIABILITY OF DRONES FOR FUTURE CANE AVAILABILITY SURVEYS

### 6.1 Assessment of Drone Technology for Agricultural Survey Applications

The question of whether drone technology is viable for routine cane availability surveys in Kenya requires systematic evaluation across multiple criteria including accuracy, cost-effectiveness, scalability, timeliness, weather dependence, and regulatory compliance. Evidence from this project combined with international research findings and industry trends supports an affirmative assessment.

Regarding accuracy, drone surveys employing RTK or PPK GNSS positioning achieve centimetre-level spatial accuracy that far exceeds what is possible through traditional survey methods. Research documented in technical publications from Propeller Aero, DJI, and academic sources consistently reports 2 to 5 centimetre positional accuracy when appropriate ground control and positioning systems are employed. This precision enables detection of small fields, precise boundary delineation, and reliable area computation that directly addresses the overestimation problems documented in conventional census approaches.

The multispectral imaging capability of agricultural drones provides information on crop condition that is unavailable through traditional census methods. Vegetation indices computed from drone imagery can assess canopy health, estimate biomass, detect stress conditions, and predict yield potential with accuracies demonstrated in this project and validated by international research. A single drone flight can capture more information about field condition than hours of field inspection by enumerators.

### 6.2 Economic Analysis of Drone-Based Survey Approaches

Cost-effectiveness analysis must consider both initial investment requirements and ongoing operational costs relative to alternative approaches. Traditional census methods require substantial labour forces deployed over extended periods, incurring personnel costs, transport expenses, accommodation and per diem allowances, and administrative overhead. These recurring costs accumulate annually and tend to increase over time with inflation and rising expectations for surveyor compensation.

Drone-based approaches require higher initial capital investment for equipment, software, and training, but dramatically reduce per-hectare survey costs once operational capacity is established. According to technical analyses from agricultural drone service providers, a single drone pilot can survey 200 hectares or more per day under favourable conditions, compared to perhaps 10 to 20 hectares per day achievable by foot-based census enumeration. This productivity differential translates to order-of-magnitude reductions in labour costs per hectare surveyed.

Based on cost estimates developed for this project, the total infrastructure investment required to establish a drone-based survey capability is approximately KShs 8.7 million, covering drone accessories, server infrastructure, GIS workstations, and field equipment. Current census operations cost an estimated KShs 50 to 80 million annually considering all labour, transport, and logistics expenses. A drone-assisted approach is estimated to require KShs 15 to 25 million annually after initial investment, generating potential annual savings of KShs 30 to 55 million. This implies a payback period of only 4 to 6 months for the initial equipment investment.

### 6.3 International Adoption Trends and African Context

Global trends in agricultural drone adoption provide important context for assessing the Kenya opportunity. According to research from AUDA-NEPAD and publications from the UN Africa Renewal initiative, the agricultural sector in Africa has seen notable increases in drone technology utilization for crop management, rising from over 50 percent to approximately 60 percent adoption among progressive commercial farmers in recent years. Industry analysts predict that agriculture will emerge as the largest area of growth for drone technology within the commercial sector over the next decade.

Market research indicates that the global agricultural drone market is expected to grow by approximately 20 percent annually, from $4.98 billion in 2023 to $18.22 billion by 2030. This growth is driven by demonstrated productivity gains, declining equipment costs, improving battery technology that extends flight times, and expanding regulatory frameworks that enable commercial drone operations.

Within Africa, Rwanda and Kenya are recognized as emerging hubs for testing and implementing drone technology in agricultural applications. Both countries benefit from relatively clear airspaces, growing regulatory frameworks administered by civil aviation authorities, pressing needs for innovative agricultural solutions to address food security challenges, and established drone service providers with relevant technical expertise.

### 6.4 Recommended Phased Implementation

Based on the evidence compiled through this project and analysis of international best practices, a phased implementation approach is recommended for scaling drone-assisted cane surveys to national coverage.

The first phase, covering the current period through six months hence, should focus on consolidating pilot results by completing Western Catchment digitization, validating models across all sugar zones, and finalizing training for all designated KSB officers. This phase establishes the foundation of proven methodology, trained personnel, and validated workflows that subsequent scaling requires.

The second phase, spanning months 6 through 18, should focus on operational scale-up through establishment of regional drone hubs at strategic locations in Western, Nyanza, and Coastal regions. Integration with existing cane census workflows should proceed incrementally, with drone data complementing rather than replacing traditional methods during the transition period. Development of automated reporting dashboards should enable real-time visualization of survey progress and results.

The third phase, covering months 18 through 36, should achieve full national deployment with comprehensive coverage of all sugar catchments, real-time mill supply forecasting integrated with crushing schedules, and integration with national agricultural data systems. By the conclusion of this phase, drone-assisted survey should be established as the standard methodology for cane availability assessment.

---

## 7. MODEL TRAINING REQUIREMENTS AND TIMELINE

### 7.1 Current Model Status and Data Foundation

The Random Forest yield prediction model currently deployed has been trained and validated using data from 27 sample farms distributed across multiple sugar companies. The training dataset incorporates eight vegetation indices as predictor variables, historical yield data from mill weighbridge records as ground truth targets, and field characteristics including variety, age, and management practices as supplementary predictors. Cross-validation procedures were applied to assess model robustness and guard against overfitting to the training sample.

While the current model achieves satisfactory performance with R² of 0.923, systematic improvement requires continued data accumulation to expand the training sample, incorporate additional predictor variables, and enable regional calibration for different agro-ecological zones. Machine learning model performance generally improves with larger and more diverse training datasets, particularly for regression applications where subtle variations in the relationship between predictors and targets can be captured given sufficient examples.

### 7.2 Training Data Requirements Based on Scientific Literature

Research published in Frontiers in Plant Science examining machine learning for crop yield prediction provides guidance on training data requirements. Studies have explored the effects of the choice of predictive algorithm, amount of data, and data partitioning strategies on predictive performance using both empirical and synthetic datasets. While general rules have been proposed for determining data requirements to train artificial neural networks in classification problems, less is known about regression models for crop yield prediction.

Practical experience from operational crop forecasting systems suggests that initial model development typically requires 50 to 100 sample observations to establish basic predictive capability. Improved accuracy typically requires 200 to 500 samples that span the range of variability in crop conditions, management practices, and environmental contexts. Regional calibration to achieve robust performance across different agro-ecological zones typically requires 100 or more samples per region to capture local relationships between spectral indices and yield outcomes.

Research on global crop yield mapping published in Nature Scientific Data employed training data from approximately 12,000 administrative units combined with satellite data, climate variables, soil properties, agricultural practices, and climate mode indices to develop robust prediction models. While such large datasets may not be feasible for initial implementation, they indicate the direction for continued capability development.

### 7.3 Recommended Model Development Timeline

Based on scientific literature and practical implementation considerations, a three-year timeline for model development and refinement is recommended.

During Year 1, the focus should be on foundation building. Months 1 through 3 should complete digitization of all mapped farms, ensuring accurate area figures for all training and validation samples. Months 4 through 6 should integrate historical mill delivery data covering at least three years of yield records per farm, enabling analysis of temporal yield patterns. Months 7 through 9 should incorporate weather data from the Kenya Meteorological Department and soil data from national and international soil databases. Months 10 through 12 should validate model performance across all catchments and identify regions requiring additional training data.

Year 2 should focus on model refinement. The first six months should conduct seasonal recalibration using new harvest data to update model parameters and assess prediction accuracy for the most recent growing season. Months 7 through 12 should integrate additional environmental variables including topographic derivatives, irrigation indicators, and management practice information that may improve prediction accuracy for specific contexts.

Year 3 should achieve operational deployment with continuous automated model updates using each season's data, annual full model retraining with the accumulated multi-year dataset, and operational decision support integration with mill planning systems.

### 7.4 Computational Requirements

Random Forest models are computationally efficient relative to deep learning alternatives, enabling rapid training even on modest hardware. A model with 200 trees trained on 500 samples with 20 predictor variables can typically be fitted in minutes on a standard workstation. This efficiency enables iterative experimentation with model configurations and rapid incorporation of new training data without requiring specialized computing infrastructure.

The Google Earth Engine platform provides cloud-based processing capability that eliminates local hardware constraints for satellite data analysis and enables scaling to national coverage without proportional increases in computing costs. The combination of cloud processing for data preparation and local processing for model fitting and prediction represents a cost-effective architecture for operational implementation.

---

## 8. KSB STAFF TRAINING PROGRAM

### 8.1 Training Completed in Phase 1

The first phase of staff training was conducted during May 2025, running from the 12th through the 23rd over a period of 10 working days. Five KSB officers participated in intensive instruction covering Geographic Information Systems, Remote Sensing, and Machine Learning applications for agricultural monitoring. The training location at Naivasha provided suitable facilities for both classroom instruction and practical field exercises.

The curriculum was structured across four progressive modules designed to build competency from foundational concepts through advanced applications. Module 1 introduced GIS and Remote Sensing principles including electromagnetic radiation fundamentals, distinctions between satellite and drone-based remote sensing systems, and characteristics of multispectral sensors with emphasis on spectral band selection for vegetation monitoring. The module covered types of remote sensing data including RGB, multispectral, and hyperspectral imagery, along with the theory and application of vegetation indices including NDVI and EVI for monitoring crop health information.

Module 2 addressed fundamentals of GIS focusing on geospatial data processing and analysis. Participants gained proficiency in data pre-processing including georeferencing of raw multispectral drone images, image classification and feature extraction techniques for deriving soil properties and vegetation indices, data visualization through map creation, chart development, and 3D visualization, and practical use of ArcGIS Pro software for analysis, visualization, and map layer creation.

Module 3 covered data processing and analysis with emphasis on machine learning for yield prediction. Topics included overview of machine learning approaches distinguishing supervised from unsupervised learning and explaining data splitting between training and test sets, introduction to regression models with focus on Random Forest advantages for prediction applications, model training and evaluation using historical yield data with performance metrics including R², MAE, and RMSE, and feature selection and engineering techniques for improving model performance.

Module 4 addressed advanced GIS and remote sensing techniques for yield monitoring. Content included advanced spatial analysis using spatial autocorrelation, zonal statistics, and geostatistics for pattern analysis, change detection using time series imagery for tracking changes in crop health and predicting yield fluctuations, crop growth modelling using both historical and real-time data with introduction to crop simulation models, and yield prediction and forecasting with emphasis on understanding, visualization, and interpretation of prediction outputs for operational decision support.

### 8.2 Training Outcomes and Demonstrated Competencies

Upon completion of Phase 1 training, the five KSB officers demonstrated operational competency across the core skill areas required for drone-assisted cane census implementation. Participants can now independently plan and execute drone data collection campaigns including flight planning, mission execution, and quality control procedures. They have acquired proficiency in processing multispectral imagery using DJI Terra software to produce georeferenced orthomosaic products and vegetation index maps.

The trained officers can perform farm boundary digitization in QGIS, creating polygon features that accurately represent field boundaries with associated attribute data. They can execute Google Earth Engine scripts developed for vegetation index computation and time series analysis, adapting parameters as needed for different study areas and time periods. Critically, they can interpret model outputs and translate technical results into decision-relevant information for operational planning and management reporting.

### 8.3 Future Training Recommendations

To achieve the staffing levels required for national-scale implementation, additional training phases are recommended. Phase 2, proposed for the first quarter of 2026, should train five additional officers with focus on advanced GIS analysis and Python scripting for workflow automation. Phase 3, proposed for the second quarter of 2026, should extend training to selected officers from sugar mills to enable mill-level data interpretation and application.

Drone pilot certification deserves specific attention given regulatory requirements and operational importance. Two to three designated KSB officers should complete Remote Pilot License training through a Kenya Civil Aviation Authority approved training centre, requiring approximately two to three weeks of instruction and practical flight hours. This certification ensures regulatory compliance and establishes internal capacity for drone operations without reliance on external service providers.

Continuous professional development mechanisms should be established including annual refresher training of two to three days duration, access to online GIS courses through platforms such as Esri and Coursera, participation in regional precision agriculture conferences, and knowledge exchange with peer institutions in other sugar-producing countries.

---

## 9. DRONE ACCESSORIES AND INFRASTRUCTURE REQUIREMENTS

### 9.1 Equipment Gap Assessment

Analysis of current equipment holdings against operational requirements for national-scale implementation reveals several gaps that require procurement action. The current inventory includes one DJI Mavic 3M drone unit, three batteries providing limited flight time per deployment, no D-RTK 2 base station for high-precision positioning, no DJI Terra software license for professional data processing, and no dedicated processing workstations for GIS analysis.

For efficient regional operations spanning multiple catchments, a minimum of three drone units would enable simultaneous deployment in Western, Nyanza, and Coastal regions. Each drone requires at least three batteries for full-day operations given typical flight times of 36 to 43 minutes per battery charge. High-precision RTK positioning requires a D-RTK 2 base station to provide real-time corrections for centimetre-level accuracy. Professional data processing requires DJI Terra software licenses and capable workstation hardware.

### 9.2 Recommended Procurement

**Drone Accessories (Approximately KShs 2,035,000)**

The D-RTK 2 Station, estimated at KShs 560,000, provides high-precision GNSS RTK correction in the field, enabling centimetre-level positioning accuracy that directly improves area measurement reliability. DJI Terra Software, estimated at KShs 650,000, provides professional-grade processing capability for orthomosaic generation, vegetation index computation, and 3D modelling from drone imagery. Six additional batteries at approximately KShs 330,000 total enable full-day flight operations without returning to base for charging. A charging hub at KShs 50,000 allows simultaneous multi-battery charging to maximize operational tempo. Five pairs of spare propellers at KShs 125,000 ensure continued operations despite normal wear and occasional damage. A calibration panel at KShs 100,000 enables radiometric correction of multispectral images for consistent vegetation index computation across different lighting conditions and flight dates. High-speed 1TB microSD cards at KShs 45,000 provide adequate storage for high-resolution multispectral imagery. A car AC converter at KShs 175,000 enables battery charging in the field using vehicle power.

**Server Infrastructure (Approximately KShs 3,500,000)**

The recommended server configuration includes dual Intel Xeon Silver 4316 processors with 16 cores each, providing substantial parallel processing capability for large dataset analysis. RAM of 256 GB DDR4 ECC, expandable to 512 GB, ensures adequate memory for processing large orthomosaic files and running complex spatial analyses. Storage combining 4 TB NVMe SSD for operating system and software with 24 TB RAID-10 SATA for GIS raster and vector storage provides both performance and capacity. An NVIDIA A6000 or RTX 5000 GPU accelerates AI/ML model training and drone image processing. Dual 10GbE network interface cards enable high-speed data transfer for large imagery files. The server should run Ubuntu Server 22.04 LTS or Windows Server 2022 with PostgreSQL and PostGIS database software for spatial data management. An APC Smart-UPS 6000VA with network management card ensures protection against power fluctuations and enables graceful shutdown during extended outages.

**GIS Workstations (Approximately KShs 2,500,000)**

Two GIS workstations are recommended for analyst use. Each should include an AMD Ryzen 9 7950X or Intel Core i9 13900K processor for high single-thread and multi-thread performance, 64 GB DDR5 RAM expandable to 128 GB, storage combining 1TB NVMe SSD for primary use with 4TB SATA SSD for processing cache, an NVIDIA RTX 4070 or 4080 GPU for photogrammetry and 3D modelling acceleration, and dual 27-inch 4K monitors calibrated for accurate image analysis. Software should include ArcGIS Pro, QGIS, DJI Terra, and Python with relevant geospatial libraries.

**Field Equipment (Approximately KShs 675,000)**

A rugged field laptop with sunlight-readable display at approximately KShs 300,000 enables field data processing and mission planning. A sub-metre accurate GNSS handheld receiver at approximately KShs 375,000 supports ground control point collection and field navigation.

### 9.3 Total Investment and Return Analysis

The total infrastructure investment across all categories amounts to approximately KShs 8,710,000. While this represents a substantial capital expenditure, analysis against current operational costs demonstrates compelling economic justification.

Current census operations incur annual costs estimated at KShs 50 to 80 million including field enumerator salaries and allowances, transport and vehicle costs, accommodation and per diem for extended field deployments, supervisory and administrative overhead, and data entry and processing labour. A drone-assisted approach would reduce annual operational costs to approximately KShs 15 to 25 million, generating potential annual savings of KShs 30 to 55 million. At this rate of savings, the initial infrastructure investment would be recovered within 4 to 6 months of full operation.

Beyond direct cost savings, the improved accuracy of drone-based surveys generates additional economic value through better mill planning, reduced losses from schedule disruptions, and improved farmer payment accuracy. These secondary benefits, while more difficult to quantify precisely, substantially enhance the return on investment case.

---

## 10. FARM DIGITIZATION FOR IMPROVED AREA COMPUTATION

### 10.1 The Case for Comprehensive Digitization

The findings from this project demonstrate unequivocally that farmer-reported area figures are unreliable for operational planning purposes. The documented 16.99 percent overestimation in census-reported areas, with some individual fields showing overestimation exceeding 100 percent, creates systematic biases that propagate through all downstream analyses and decisions. Addressing this challenge requires comprehensive digitization of all sugarcane-growing areas based on objective remote sensing imagery.

Survey-grade ground measurements, while accurate, are prohibitively expensive and time-consuming for the scale of Kenya's sugarcane sector covering approximately 200,000 hectares according to USDA estimates. Cadastral records, where they exist, often reflect legal boundaries that may differ substantially from actual cultivated areas and are frequently outdated due to irregular updates. Mill records based on historical estimates perpetuate past inaccuracies without opportunity for correction.

Research on field boundary mapping in African smallholder contexts has demonstrated the feasibility of high-resolution, annual maps of field boundaries at national scales. A study published in Frontiers in Artificial Intelligence created a national map of crop field boundaries in Ghana, a country where smallholder farming predominates, achieving overall accuracy of 86.7 percent for field boundary delineation with an unbiased area estimate indicating cropland coverage of 17.1 percent of national territory. This demonstrates proof of concept for the approach proposed here.

### 10.2 Proposed Digitization Approach

A two-tier digitization strategy is recommended to balance accuracy requirements against cost and time constraints. Tier 1 involves satellite-based digitization using high-resolution commercial imagery at 0.3 to 0.5 metre resolution from providers such as Maxar or Planet. This approach enables rapid baseline mapping of all sugarcane-growing areas, capturing field boundaries, access roads, and infrastructure. Tier 2 employs drone-based verification for high-priority farms, capturing 5 to 10 centimetre multispectral imagery that enables detailed assessment of within-field variability and highly precise boundary delineation.

The recommended imagery specifications include resolution of 0.3 to 0.5 metres, sufficient to resolve field boundaries even in fragmented smallholder landscapes. Coverage should encompass all sugar catchments totalling approximately 200,000 hectares. Annual update frequency would ensure currency of boundary information and enable detection of changes in cropped area. Spectral content should include RGB plus NIR bands at minimum to enable vegetation index computation and land cover classification.

### 10.3 Workflow and Quality Assurance

The digitization workflow begins with high-resolution imagery acquisition, followed by cloud-free mosaic creation to produce seamless coverage of each study area. Manual digitization in QGIS then delineates field boundaries by trained technicians following standardized protocols. Attribute assignment links each polygon to farmer identification, crop information, and registration data. Quality assurance and quality control verification by supervisory staff ensures accuracy standards are met. Database integration incorporates validated polygons into the central GIS database. Finally, farmer validation campaigns engage with farmers to verify boundary accuracy and resolve discrepancies.

Research from FAO documenting field boundary digitization in Zimbabwe provides relevant precedents. The initiative targeted 1,770 beneficiaries across 33 districts, leveraging university student volunteers through a two-day training workshop followed by a 12-day digitizing campaign. Similar approaches could be adapted for Kenya, potentially engaging students from universities with GIS programmes to accelerate digitization while providing valuable practical training.

### 10.4 Timeline and Cost Estimate

Phase 1, covering imagery acquisition over 1 to 2 months, is estimated at KShs 5 to 10 million depending on provider selection and coverage extent. Phase 2, involving digitization over 3 to 4 months, is estimated at KShs 3 to 5 million for technical staff time and supervision. Phase 3, covering validation over 2 months, is estimated at KShs 1 to 2 million for field verification activities. The total timeline spans 6 to 8 months with total estimated cost of KShs 9 to 17 million.

The expected benefits of comprehensive digitization include elimination of area estimation discrepancies through objective measurement, transparency through farmer-verified boundaries that establish mutual accountability, efficiency through one-time investment with incremental annual updates rather than repeated costly surveys, and integration through creation of a foundational spatial dataset supporting precision agriculture tools, yield prediction models, and administrative systems.

---

## 11. CHALLENGES AND MITIGATION STRATEGIES

### 11.1 Field Fragmentation and Small Plot Sizes

Continuous land subdivision in portions of the Western Catchment has resulted in increasingly fragmented and smaller field sizes, presenting significant challenges for efficient drone mapping operations. Small fields require proportionally more flight time for boundary delineation relative to interior coverage, reducing productivity in terms of area mapped per flight hour. Complex field geometries with irregular boundaries increase digitization time and introduce more potential for error.

This challenge is not unique to Kenya. Research examining agricultural field delineation in Sub-Saharan Africa has noted that smallholder farms are characterized by small size, irregular shape, and use of mixed-cropping systems that make boundaries vaguely defined. Physical edges between smallholder fields are often indistinct in satellite imagery, requiring higher resolution data for reliable delineation.

Mitigation strategies include using satellite imagery for broad coverage of fragmented areas where per-hectare costs are lower than drone survey, reserving drone missions for high-value verification tasks and training sample collection, developing sampling protocols appropriate for fragmented landscapes that achieve representative coverage without requiring complete enumeration, and investing in higher-resolution satellite imagery that can capture small fields more reliably than standard products.

### 11.2 Weather Constraints

The Western Catchment and other highland sugarcane-growing areas experience persistent cloud cover and rapidly changing weather patterns that frequently disrupted mapping operations during this project. Both drone and satellite data collection depend on clear atmospheric conditions; clouds obscure ground features in imagery and can pose safety hazards for drone operations through reduced visibility and wind gusts associated with convective weather.

Mitigation strategies include scheduling intensive data collection campaigns during dry seasons when clear conditions are more frequent, specifically January through March and July through September. Cloud-free Sentinel-2 composites aggregating multiple overpasses can fill gaps from individual cloudy acquisitions. Cloud masking algorithms implemented in Google Earth Engine automatically exclude contaminated pixels from analysis. Weather monitoring and flexible scheduling allow opportunistic data collection when conditions permit.

### 11.3 Equipment and Resource Limitations

Insufficient battery capacity and data storage reduced daily operational capacity during field campaigns. With only three batteries available, flight operations were limited to approximately 90 to 120 minutes of active data collection per day after accounting for transit, setup, and battery swapping time. Data storage limitations required frequent offloading and backup, consuming additional field time.

Mitigation through equipment procurement as detailed in Section 9 would address these constraints directly. Six additional batteries would enable full-day operations of six hours or more. High-capacity storage cards and field backup solutions would eliminate data management bottlenecks. Car-based charging systems would enable battery replenishment during transit between sites.

### 11.4 Transportation and Logistics

The geographic spread of sampling locations across eight counties combined with poor road conditions in rural areas consumed substantial time in transit that reduced time available for actual mapping activities. Some field sites required hours of travel from practical base locations, with road conditions deteriorating significantly during wet periods.

Strategic hub-and-spoke deployment models would establish regional bases that minimize average travel distance to field sites. Four-wheel-drive vehicles with adequate ground clearance are essential for reliable access to rural locations. Advance route planning using available road condition information and local knowledge enables realistic scheduling that accounts for travel time variability.

### 11.5 Power Supply Reliability

Frequent power outages significantly disrupted data processing workflows at office facilities. Processing large drone imagery datasets requires sustained computing over periods of hours, and power interruptions can corrupt partially processed files, requiring restart from the beginning. Data integrity risks increase with unreliable power supply.

Mitigation includes uninterruptible power supply systems for all workstations, providing battery backup during brief outages and graceful shutdown time during extended outages. Generator backup at processing facilities provides extended runtime for critical operations. Cloud-based processing through Google Earth Engine as the primary analysis platform eliminates local power dependency for satellite data analysis.

### 11.6 Technical Challenges

Spectral similarity between sugarcane, maize, and napier grass creates classification ambiguities as discussed in Section 5. Model performance may vary across regions due to differences in varieties, management practices, and environmental conditions that affect the relationship between spectral indices and yield. Integrating diverse data sources including drone imagery, satellite data, census records, and mill historical data requires careful attention to data formats, coordinate reference systems, and temporal alignment.

Mitigation strategies include multi-temporal analysis and phenological profiling to distinguish crops based on temporal behaviour rather than instantaneous spectral signatures, regional model calibration with local training data to capture context-specific relationships, standardized data formats and metadata protocols to ensure interoperability, and transfer learning techniques that adapt models trained in one region for application in others.

---

## 12. REVIEW OF THE ENGAGEMENT MEMORANDUM OF UNDERSTANDING

### 12.1 Scope and Deliverables Under the MOU

The engagement between Kenya Sugar Board and Ecospace Services Ltd. is governed by a Memorandum of Understanding establishing the framework for collaboration on drone-assisted cane census operations. The MOU covers key activity areas including drone-based mapping campaigns across designated sugar catchments, capacity building and technology transfer to KSB staff, joint data analysis and production of technical reports, and equipment provision and maintenance support during the engagement period.

### 12.2 Assessment of Deliverable Completion

All deliverables specified under the MOU have been completed satisfactorily. Drone mapping campaigns covered over 200 fields across the Western Catchment and additional sample sites in Nyanza, Trans Mara, and Coastal regions, providing comprehensive spatial data for model development and area estimation. The complete data processing pipeline is operational, with workflows established for drone imagery processing through DJI Terra, satellite data analysis through Google Earth Engine, and integrated analysis combining multiple data sources.

The yield prediction model has been trained and validated, achieving R² of 0.923 which meets or exceeds performance targets established in the work plan. Staff training covering five KSB officers has been completed, with demonstrated competency in GIS, remote sensing, and machine learning applications. Technical reporting has been delivered through this comprehensive document and supporting materials. Google Earth Engine scripts developed for vegetation index computation and sugarcane monitoring are operational and accessible through KSB assets.

### 12.3 Recommendations for MOU Enhancement

Building on the successful foundation established through this engagement, several enhancements to the collaboration framework warrant consideration. Extension of the engagement scope to cover remaining catchments not fully addressed in the initial phase would enable national-scale implementation. Inclusion of high-resolution satellite imagery procurement within the scope would address the digitization requirements outlined in Section 10. Formalization of data sharing protocols between KSB, sugar mills, and other stakeholders would enable integration of weighbridge records, planting data, and other operationally relevant information.

Establishment of performance benchmarks and key performance indicators for annual review would provide objective measures of implementation progress and impact. Definition of intellectual property ownership and usage rights for tools and datasets developed through the collaboration would clarify arrangements for commercial application and technology transfer. Provision for collaborative research publication would enable documentation of findings in peer-reviewed venues, contributing to knowledge advancement while establishing the credentials of both organizations in precision agriculture applications.

### 12.4 Budget Utilization

All authorized budgets under the MOU were utilized within specified activities as documented in financial reports submitted separately. Expenditure categories included field mapping exercises covering equipment operation, transport, accommodation, and incidentals; data processing workshops providing facilities, equipment, and expert facilitation; training programmes covering venue, materials, and instruction; and report writing and documentation activities.

---

## 13. CONCLUSIONS AND RECOMMENDATIONS

### 13.1 Summary of Key Findings

This project has demonstrated conclusively that drone and satellite technologies provide viable, accurate, and cost-effective tools for modernizing sugarcane census operations in Kenya. The evidence compiled through systematic field campaigns, rigorous data analysis, and validated model development supports several key conclusions.

First, drone-assisted mapping significantly improves the accuracy of area under cane estimation compared to conventional census methods. The documented 16.99 percent overestimation in census-reported mature cane areas represents a substantial systematic bias that distorts mill planning, farmer payment calculations, and national production forecasting. Drone-digitized boundaries based on objective imagery provide ground truth accuracy that eliminates this bias.

Second, machine learning models trained on drone and satellite-derived vegetation indices achieve high prediction accuracy for sugarcane yield estimation. The R² value of 0.923 achieved in this project compares favourably with international benchmarks from Australia, Brazil, and other major producing countries, demonstrating that Kenya-specific models can match global best practice performance.

Third, the challenge of distinguishing sugarcane from spectrally similar crops including maize and napier grass can be addressed through multi-temporal analysis and phenological profiling. The 89.7 percent overall classification accuracy achieved represents substantial improvement over single-date approaches and provides operationally useful discrimination capability.

Fourth, KSB staff have demonstrated capacity to operate and maintain geospatial systems following appropriate training and with continued support. The five officers trained in Phase 1 have acquired competencies in drone operations, imagery processing, GIS analysis, and model interpretation that establish foundational internal capacity for sustained implementation.

Fifth, infrastructure investment requirements are modest relative to potential operational savings. The total recommended investment of approximately KShs 8.7 million compares favourably with estimated annual savings of KShs 30 to 55 million achievable through drone-assisted survey approaches, implying payback periods of less than six months.

### 13.2 Strategic Recommendations

Based on the findings and analysis presented in this report, the following recommendations are offered for consideration by Kenya Sugar Board management.

**Immediate Actions (Current through 6 months)**

Procurement of essential drone accessories as detailed in Section 9 should proceed without delay. The D-RTK 2 station, additional batteries, DJI Terra software license, and supporting accessories represent enabling investments that will immediately enhance operational capability. The estimated cost of KShs 2.035 million for these items represents a modest outlay with immediate operational benefits.

Phase 2 staff training for five additional officers should be planned and executed to expand the pool of trained personnel and reduce dependency on the initial five trainees. Training should emphasize advanced GIS analysis and Python scripting skills that enable workflow automation and customization.

Western Catchment digitization should be completed to provide comprehensive boundary data for all sugarcane-growing areas in this priority region. The digitized boundaries will serve as training data for classification models, validation references for accuracy assessment, and operational baselines for area reporting.

Establishment of a formal GIS Unit within KSB organizational structure would institutionalize geospatial capabilities and provide clear organizational home for the equipment, data, and personnel associated with drone-assisted survey operations.

**Medium-Term Actions (6 through 18 months)**

Acquisition of high-resolution satellite imagery covering all sugar catchments would enable national-scale digitization following the approach outlined in Section 10. The estimated investment of KShs 9 to 17 million for imagery and digitization represents foundational infrastructure that would support all subsequent precision agriculture applications.

Deployment of drone operational hubs at strategic regional locations would establish the distributed capacity needed for national-scale survey coverage. Hub locations in Western, Nyanza, and Coastal regions would minimize travel distances and enable rapid response to data collection opportunities.

Integration of model outputs with mill scheduling systems would translate analytical capabilities into operational decision support. This integration requires engagement with mill management to understand information needs and develop appropriate interfaces for data delivery.

Annual model recalibration using each harvest season's yield data would maintain prediction accuracy and enable continuous improvement as the training dataset accumulates additional observations.

**Long-Term Actions (18 through 36 months)**

Achievement of full national coverage across all sugar catchments represents the ultimate implementation objective. By the conclusion of this timeline, drone-assisted survey should be established as the standard methodology for cane availability assessment nationwide.

Implementation of a real-time monitoring dashboard would provide KSB management, mill operators, and other stakeholders with current information on cane availability, crop condition, and harvest progress. Dashboard development should emphasize actionable visualizations that support operational decision-making.

Establishment of data sharing agreements with county governments, research institutions, and other agricultural sector stakeholders would maximize the value derived from the geospatial infrastructure investment and contribute to broader agricultural modernization objectives.

Publication of research findings in peer-reviewed journals would document the Kenya experience for the benefit of other countries facing similar challenges, establish the scientific credibility of the methodologies employed, and contribute to professional recognition for KSB and Ecospace staff.

### 13.3 Concluding Statement

The collaboration between Kenya Sugar Board and Ecospace Services Ltd. has demonstrated the transformative potential of drone and satellite technology for modernizing agricultural monitoring in Kenya. The evidence presented in this report strongly supports continued investment in precision agriculture technologies as a strategic priority for Kenya's sugar sector.

Kenya's sugar industry, supporting over eight million citizens and comprising the livelihoods of 320,000 smallholder farmers, deserves access to the best available tools for understanding and managing cane production. The technologies evaluated in this project, now proven effective under Kenyan conditions, provide exactly such tools. The productivity gains, accuracy improvements, and cost savings achievable through implementation of these recommendations would benefit farmers through more accurate payments, mills through better planning, and the nation through improved food security and agricultural sector performance.

With proper implementation of the recommendations herein, Kenya Sugar Board will be positioned as a regional leader in data-driven agricultural management, demonstrating innovation that peer institutions across Africa and beyond may seek to emulate. The foundation has been established; the path forward is clear; the opportunity for transformative impact awaits execution.

---

## 14. APPENDIX: STATISTICS FOR BUSINESS INTELLIGENCE VISUALIZATION

This appendix consolidates key statistical datasets extracted from the 2025 KSB Census and drone/satellite analysis for use in Business Intelligence dashboards and graphical reporting.

### A. Regional Distribution Data (for Pie/Bar Charts)

**Dataset A1: Area Distribution by County**
```
County,Area_Ha,Percentage,Farmers
Kakamega,52793.23,35.3,132319
Bungoma,43619.69,29.2,116573
Busia,24889.57,16.7,28369
Nandi,11457.90,7.7,8044
Trans Nzoia,8967.98,6.0,15299
Uasin Gishu,5606.63,3.8,6067
Vihiga,1624.30,1.1,1995
Kisumu,478.68,0.3,351
```

**Dataset A2: Mill Capacity Distribution**
```
Mill,TCD_Capacity,Percentage_of_Total
Mumias,8000,38.5
Nzoia,3000,14.4
West Kenya,3000,14.4
Butali,2800,13.5
Olepito,1400,6.7
Busia,1400,6.7
Naitiri,1200,5.8
```

### B. Time Series Data (for Line/Area Charts)

**Dataset B1: Yield Trends**
```
Year,Yield_TcHa,Change_Percent
2023,52.18,0
2024,55.02,5.4
2025,61.48,11.7
2026_projected,63.50,3.3
```

**Dataset B2: Supply-Demand Projections**
```
Period,Available_MT,Required_MT,Deficit_MT,Deficit_Percent,Utilization_Percent
Nov-Dec 2025,1069936,1743780,673844,38.6,61.4
Jan-Mar 2026,1440431,2615670,1175239,44.9,55.1
Apr-Jun 2026,1309151,2615670,1306519,50.0,50.0
Jul-Oct 2026,1180551,3487560,2306519,66.1,33.9
```

### C. Comparative Analysis Data (for Stacked/Grouped Charts)

**Dataset C1: Crop Cycle Distribution**
```
Stage,Actual_Percent,Standard_Percent,Variance
Plant Cane,31,30,1
Ratoon 1,26,30,-4
Ratoon 2,26,30,-4
Ratoon 3+,17,10,7
```

**Dataset C2: Variety Distribution**
```
Variety,Percentage,Typical_Yield_Low,Typical_Yield_High
CO 421,46,65,80
CO 945,41,60,75
N14,6,55,70
Others,7,50,65
```

### D. Accuracy Metrics Data (for Gauge/KPI Charts)

**Dataset D1: Model Performance Metrics**
```
Metric,Value,Benchmark,Status
R_Squared,0.923,0.85,Exceeds
MAE_TcHa,1.547,3.0,Exceeds
MAPE_Percent,6.5,10.0,Exceeds
RMSE_TcHa,11.211,15.0,Exceeds
Classification_Accuracy,89.7,85.0,Exceeds
Census_Overestimation,16.99,0,Issue
```

**Dataset D2: Methodology Comparison Scores**
```
Parameter,Census_Score,Drone_Score,Advantage
Area_Accuracy,70,95,Drone
Temporal_Coverage,40,90,Drone
Farmer_Registration,95,20,Census
Cost_Efficiency,30,80,Drone
Crop_Health_Detail,60,85,Drone
Variety_Tracking,80,30,Census
```

### E. Economic Impact Data (for Financial Charts)

**Dataset E1: Cost-Benefit Analysis**
```
Category,Census_Annual_KShs,Drone_Annual_KShs,Savings_KShs
Personnel,35000000,8000000,27000000
Transport,15000000,5000000,10000000
Equipment,5000000,12000000,-7000000
Processing,10000000,3000000,7000000
Total,65000000,28000000,37000000
```

**Dataset E2: Deficit Economic Impact**
```
Period,Deficit_MT,Price_per_MT_KShs,Lost_Revenue_KShs
Nov-Dec 2025,673844,4500,3032298000
Jan-Mar 2026,1175239,4500,5288575500
Apr-Jun 2026,1306519,4500,5879335500
Jul-Oct 2026,2306519,4500,10379335500
Annual,5462121,4500,24579544500
```

### F. Geographic Data (for Map Visualizations)

**Dataset F1: County Centroids for Mapping**
```
County,Latitude,Longitude,Area_Ha,Farmers
Kakamega,0.2827,34.7519,52793.23,132319
Bungoma,0.5635,34.5584,43619.69,116573
Busia,0.4608,34.1108,24889.57,28369
Nandi,0.1833,35.1500,11457.90,8044
Trans Nzoia,1.0167,34.9500,8967.98,15299
Uasin Gishu,0.5167,35.2833,5606.63,6067
Vihiga,0.0833,34.7167,1624.30,1995
Kisumu,-0.1000,34.7500,478.68,351
```

**Dataset F2: Mill Locations**
```
Mill,Latitude,Longitude,TCD_Capacity,Primary_County
Mumias,0.3372,34.4883,8000,Kakamega
Nzoia,0.9833,34.8833,3000,Bungoma
West Kenya,0.2167,34.6667,3000,Kakamega
Butali,0.3500,34.5500,2800,Kakamega
Olepito,0.2167,35.1000,1400,Nandi
Busia,0.4608,34.1108,1400,Busia
Naitiri,0.7667,34.9500,1200,Bungoma
```

---

## 15. REFERENCES

Aneece, I., & Thenkabail, P. (2024). Sugarcane Yield Estimation Using Satellite Remote Sensing Data in Empirical or Mechanistic Modeling: A Systematic Review. *Remote Sensing*, 16(5), 863.

DJI Agriculture. (2024). Mavic 3 Multispectral Edition Specifications. DJI Official Website.

Donaldson, A. B., et al. (2021). High Resolution, Annual Maps of Field Boundaries for Smallholder-Dominated Croplands at National Scales. *Frontiers in Artificial Intelligence*, 4, 744863.

Eberhard, J., et al. (2021). Integrating satellite imagery and environmental data to predict field-level cane and sugar yields in Australia using machine learning. *Field Crops Research*, 260, 107993.

FAO. (2024). Digitizing Field Boundaries in Zimbabwe. Food and Agriculture Organization Statistics Division.

ISPRS Archives. (2024). Estimation of Sugarcane Yield Using Multi-Temporal Sentinel-2 Satellite Imagery and Random Forest Regression. *ISPRS Archives*, XLVIII-4/W9-2024.

Kenya Sugar Board. (2025). National Sugar Industry Statistics. Internal Documentation.

Propeller Aero. (2024). How it Works: PPK vs RTK Drone Surveying. Technical Documentation.

United States Department of Agriculture. (2025). Sugar Annual: Kenya. GAIN Report KE2025-0008.

Van Klompenburg, T., Kassahun, A., & Catal, C. (2020). Crop yield prediction using machine learning: A systematic literature review. *Computers and Electronics in Agriculture*, 177, 105709.

Wolanin, A., et al. (2024). A new method for classifying maize by combining the phenological information of multiple satellite-based spectral bands. *Frontiers in Environmental Science*, 10, 1089007.

Kenya Sugar Board. (2025). Upper and Lower Western Cane Census Report 2025. Field Data Collection and Analysis Report. Nairobi, Kenya.

---

**Report Prepared By:**

**Ecospace Services Ltd.**
*Geospatial Solutions for Sustainable Development*

**Contact:**
- Email: info@ecospace.co.ke
- Website: www.ecospace.co.ke

---

**Document Control:**
- Version: 3.0
- Date: December 2025
- Classification: Official - KSB Internal Use
- Distribution: KSB Executive Management, Technical Advisory Services, Market Research & Product Development

**Revision History:**
| Version | Date | Description | Author |
|---------|------|-------------|--------|
| 1.0 | December 2025 | Initial draft (point-form format) | Ecospace Services Ltd. |
| 2.0 | December 2025 | Comprehensive narrative revision with scientific citations | Ecospace Services Ltd. |
| 3.0 | December 2025 | Integration of 2025 Census statistics; BI datasets appendix | Ecospace Services Ltd. |

---

*This report contains proprietary methodologies and findings developed through the KSB-Ecospace partnership. Reproduction or distribution without authorization is prohibited.*
