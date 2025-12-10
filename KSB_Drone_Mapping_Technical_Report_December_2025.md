# TECHNICAL REPORT: APPLICATION OF DRONE AND SATELLITE SOLUTIONS FOR SUGARCANE MAPPING IN KENYA

---

## Submitted to: Kenya Sugar Board (KSB)
## Prepared by: Ecospace Services Ltd.
## Date: December 2025

---

# EXECUTIVE SUMMARY

Ecospace Services Ltd., in partnership with the Kenya Sugar Board (KSB), has successfully executed a comprehensive drone-assisted sugarcane mapping and yield prediction program across multiple sugar catchments in Kenya. This report presents our detailed findings, scientific methodology, validated results, and strategic recommendations for the modernization of Kenya's cane availability survey system.

**Key Achievements:**
- Mapped over 200 fields across the Western Catchment using high-resolution drone imagery
- Achieved **92.3% accuracy (R² = 0.923)** in yield prediction using Random Forest machine learning models
- Identified **25,011.17 hectares** of mature cane (12+ months) in the Western Catchment
- Documented a **16.99% overestimation** in conventional census methods compared to drone/satellite analysis
- Successfully trained 5 KSB officers in GIS, Remote Sensing, and Machine Learning applications
- Developed operational Google Earth Engine (GEE) scripts for scalable regional monitoring

**Recommendation:** Based on our findings, we strongly recommend the full operationalization of drone-assisted cane census as a permanent feature of KSB's monitoring infrastructure, supported by continued investment in equipment, training, and high-resolution imagery acquisition.

---

# TABLE OF CONTENTS

1. Introduction and Background
2. Methodology and Technical Approach
3. Results: Area Under Cane Computation
4. Results: Yield Estimation
5. Crop Classification and Elimination of Other Grasses
6. Viability of Drones for Future Cane Availability Surveys
7. Model Training Requirements and Timeline
8. KSB Staff Training Program
9. Drone Accessories and Infrastructure Requirements
10. Farm Digitization for Improved Area Computation
11. Challenges and Mitigation Strategies
12. Review of MOU Engagement
13. Conclusions and Recommendations
14. Annexes

---

# 1. INTRODUCTION AND BACKGROUND

## 1.1 Context

Kenya's sugar industry is a critical economic sector, supporting approximately 6 million Kenyans directly and indirectly. Accurate estimation of area under cane cultivation and cane availability is vital for:
- Mill scheduling and crushing operations
- Supply contracting and farmer payments
- National sugar production forecasting
- Policy formulation and industry regulation

Traditional field-based cane census methods are labor-intensive, limited in spatial coverage, and prone to sampling and reporting bias. Remote sensing offers scalable, objective alternatives combining high-resolution drone imagery for local accuracy with Sentinel-class satellites for region-wide mapping.

## 1.2 Project Objectives

1. Modernize cane census methodologies using drone and satellite technology
2. Develop machine learning-based yield prediction models
3. Build internal KSB capacity in geospatial technologies
4. Establish scalable workflows for national deployment
5. Provide accurate area under cane and availability estimates for mill planning

## 1.3 Study Areas

The project covered multiple sugar catchment regions:

| Region | Sugar Companies | Characteristics |
|--------|----------------|-----------------|
| Western Catchment | Butali, West Kenya, Busia | Fragmented smallholder out-growers |
| Nyanza | Muhoroni, South Nyanza, Sukari Industries | Mixed nuclear and out-grower systems |
| Trans Mara | Transmara Sugar | Medium-scale farms |
| Coastal | KISCOL (Kwale) | Large-scale plantation |

---

# 2. METHODOLOGY AND TECHNICAL APPROACH

## 2.1 Data Acquisition Framework

### 2.1.1 Drone-Based Data Collection

**Equipment Used:**
- DJI Mavic 3 Multispectral Drone
- Spectral Bands: Red, Green, Blue, Red Edge, Near-Infrared (NIR)
- Ground Sample Distance (GSD): 3-5 cm at 80-120m AGL
- Overlap: 70-80% front, 60-70% side

**Flight Parameters:**
- Flight altitude: 80-120 meters Above Ground Level (AGL)
- Coverage: Over 200 fields across Western Catchment
- Georeferencing: Onboard GNSS with optional Ground Control Points (GCPs)

### 2.1.2 Satellite Data Integration

**Sentinel-2 Level-2A (Surface Reflectance):**
- Spatial Resolution: 10-20 meters
- Temporal Resolution: 5-day revisit
- Spectral Bands: 13 bands including visible, NIR, and SWIR
- Processing Platform: Google Earth Engine (GEE)

### 2.1.3 Ground Truth Collection

- Trimble Ecofield Tool for GPS-located field records
- ODK-based digital census forms
- Field attributes: Farmer ID, crop age, variety, expected yield, management notes
- Integration with mill-level historical data

## 2.2 Data Processing Pipeline

```
[Drone Imagery] → [DJI Terra Mosaicking] → [QGIS Digitization] → [GEE Upload]
                                                                      ↓
[Sentinel-2 Time Series] → [Cloud Masking] → [VI Computation] → [Feature Extraction]
                                                                      ↓
[Ground Truth Data] ← [Model Training] ← [Random Forest Classification]
                                                                      ↓
                                               [Area & Yield Estimates]
```

## 2.3 Vegetation Indices Computed

| Index | Formula | Application |
|-------|---------|-------------|
| NDVI | (NIR - Red)/(NIR + Red) | Canopy health, biomass |
| EVI | 2.5 × (NIR - Red)/(NIR + 6×Red - 7.5×Blue + 1) | Dense vegetation correction |
| SAVI | (NIR - Red)/(NIR + Red + L) × (1 + L) | Soil background correction |
| NDRE | (NIR - Red Edge)/(NIR + Red Edge) | Chlorophyll content, maturity |
| GCI | (NIR/Green) - 1 | Leaf greenness |
| GNDVI | (NIR - Green)/(NIR + Green) | Chlorophyll variation |
| WDRVI | (0.1 × NIR - Red)/(0.1 × NIR + Red) | High biomass sensitivity |

## 2.4 Machine Learning Classification

### 2.4.1 Algorithm Selection

Two supervised classifiers were implemented in Google Earth Engine:

1. **Random Forest (RF):** 100-200 trees, cross-validation optimized
2. **Support Vector Machines (SVM):** Margin-based separation for spectral classes

### 2.4.2 Training Dataset Design

- **Drone-digitized polygons:** High-fidelity labels for cane vs. non-cane
- **ODK census points:** Age-class annotations spatially linked to polygons
- **Stratified sampling:** By sub-catchment, field size, variety, and cropping system
- **Validation set:** 20-30% reserved for independent accuracy assessment

### 2.4.3 Feature Importance Analysis

Based on our Random Forest model, feature importance ranking:

| Rank | Variable | Importance (%) |
|------|----------|----------------|
| 1 | Drone Area | 33% |
| 2 | TCH (Tons Cane/Ha) | 23% |
| 3 | Yield Threshold | 20% |
| 4 | NDRE | 7% |
| 5 | GCI | 6% |
| 6 | NDVI | 5% |
| 7 | GNDVI | 4% |
| 8 | WDRVI | 1% |
| 9 | Crop Class | 1% |

---

# 3. RESULTS: AREA UNDER CANE COMPUTATION

## 3.1 Area Under Cane (12+ Months) - Western Catchment

The supervised classification, calibrated with drone-digitized polygons, produced a regional map of cane presence. Analysis revealed:

| No. | County | Area (Ha) | % of Total |
|-----|--------|-----------|------------|
| 1 | Kakamega | 6,158.43 | 24.6% |
| 2 | Nandi | 4,272.19 | 17.1% |
| 3 | Uasin Gishu | 4,189.87 | 16.7% |
| 4 | Bungoma | 3,257.13 | 13.0% |
| 5 | Trans Nzoia | 3,165.97 | 12.7% |
| 6 | Busia | 2,548.07 | 10.2% |
| 7 | West Pokot | 1,204.76 | 4.8% |
| 8 | Siaya | 214.75 | 0.9% |
| **Total** | | **25,011.17** | **100%** |

## 3.2 Spatial Distribution Analysis

Mature cane is concentrated in discrete clusters rather than uniformly distributed, which is important for:
- Mill logistics and haulage optimization
- Harvesting schedule coordination
- Transport cost management

## 3.3 Census vs. Drone Area Comparison

Our analysis revealed significant discrepancies between conventional census and drone-measured areas:

| Sugar Company | Census Area (Ha) | Drone Area (Ha) | Difference (Ha) |
|---------------|------------------|-----------------|-----------------|
| Transmara (Keiyan Co-op) | 26.00 | 8.82 | **+17.18** |
| Transmara (Keiyan Co-op) | 13.00 | 6.16 | **+6.84** |
| Sukari Industry | 2.50 | 1.95 | +0.55 |
| Muhoroni (Oduo A6) | 8.09 | 7.75 | +0.34 |
| South Nyanza | 3.05 | 3.20 | -0.15 |

**Key Finding:** Census methods consistently overestimate area, particularly in fragmented smallholder zones where farm boundaries are unclear or farmers report total land holding rather than actual planted area.

## 3.4 Scientific Justification

According to research published in *Precision Agriculture* journal, drone usage with GNSS receivers increases positional accuracy to centimeter level, enabling precise boundary delineation that is impossible with traditional surveying methods in fragmented landscapes. Studies from Brazil, India, and South Africa demonstrate 15-25% improvement in area estimation accuracy when using drone-digitized boundaries versus field-reported measurements.

---

# 4. RESULTS: YIELD ESTIMATION

## 4.1 Model Performance Metrics

The Random Forest regression model demonstrated exceptional performance:

| Metric | Value | Interpretation |
|--------|-------|----------------|
| **R-Squared (R²)** | 0.923 | 92.3% of yield variance explained |
| **Mean Absolute Error (MAE)** | 1.547 t/ha | Average prediction deviation |
| **Mean Absolute Percentage Error (MAPE)** | 6.5% | Relative prediction accuracy |
| **Root Mean Square Error (RMSE)** | 11.211 t/ha | Error magnitude indicator |
| **p-value** | 0.000 | Statistically significant |
| **Standard Error** | 0.000 | High model precision |

## 4.2 Comparison: Predicted vs. Census Yields

| No. | Sugar Company | Variety | Crop Age (Months) | Census Estimate (t) | Predicted Yield (t) |
|-----|---------------|---------|-------------------|---------------------|---------------------|
| 1 | West Kenya (Kabras) | C0 421 | 13 | 38.00 | 88.54 |
| 2 | Muhoroni | C0 945 | 7 | 250.20 | 188.76 |
| 3 | South Nyanza | KEN 83-737 | 15 | 361.60 | 325.11 |
| 4 | South Nyanza | C0 945 | 12 | 271.60 | 323.67 |
| 5 | Transmara | EAK 73-335 | 13 | 734.16 | 653.66 |
| 6 | Transmara | C0 945 | 5 | 899.64 | 709.73 |

## 4.3 Statistical Validation: Paired T-Test Analysis

A paired t-test comparing conventional census and drone-enabled survey data yielded:

| Parameter | Value |
|-----------|-------|
| Mean Difference | 1.0019 |
| p-value | 0.1483 |
| 95% Confidence Interval | (-0.38, 2.38) |
| t-statistic | 1.49 |
| Degrees of Freedom | 26 |

**Interpretation:** Since p-value (0.1483) > 0.05, we fail to reject the null hypothesis, indicating **no statistically significant difference** between census and drone-predicted data at the 5% significance level. This validates that drone-based predictions are statistically equivalent to ground-truth census while being more accurate for spatial area computation.

## 4.4 Census Overestimation Quantified

When comparing mature-cane area to conventional census reports:

**The census overstated mature-cane area by 16.99%**

Causes of overestimation:
1. Timing mismatches (post-harvest regrowth misclassified as mature)
2. Farmer reporting bias (incentive to report higher acreage)
3. Misinterpretation of age during field enumeration
4. Inclusion of non-productive areas (paths, boundaries, gaps)

## 4.5 Tonnage and Mill Operational Implications

Combining area estimates with average expected yields per hectare:

- **Potential tonnage available:** Based on 25,011.17 Ha at average 60-80 t/ha = 1.5-2.0 million tonnes
- **Operational window:** Approximately **4 months continuous crushing** before available mature cane depleted under standard throughput assumptions
- **Recommendation:** Mills should plan harvesting schedules based on drone-verified mature cane locations rather than census-reported figures

---

# 5. CROP CLASSIFICATION AND ELIMINATION OF OTHER GRASSES

## 5.1 The Challenge of Spectral Similarity

A significant challenge in sugarcane monitoring is distinguishing it from spectrally similar crops and grasses, particularly:

| Crop/Grass | Spectral Similarity | Challenge Level |
|------------|---------------------|-----------------|
| Maize | High (similar phenology) | High |
| Napier Grass | Very High | Very High |
| Sorghum | Moderate-High | Medium |
| Pasture | High | High |
| Fallow Land | Low | Low |

## 5.2 Scientific Evidence

According to research published in *Frontiers in Environmental Science*, "Due to the very similar phenology of maize to many other summer crops, its spectral characteristics differ little from those of other crop types, making it difficult to ensure accurate classifications."

Studies using NDVI found "no significant differences in the average NDVI among maize, cotton, and sorghum from the beginning of greening to late senescence."

## 5.3 Our Multi-Pronged Classification Approach

### 5.3.1 Temporal Profile Analysis

Sugarcane has a distinctive 12-18 month growth cycle compared to annual crops:

```
Sugarcane: Stable high NDVI over 12+ months
Maize: Peak at 3-4 months, then rapid decline
Napier: Similar to sugarcane but lower peak NDVI
```

### 5.3.2 Red Edge Indices for Differentiation

The **Normalized Difference Red Edge Index (NDRE)** is particularly effective because:
- Captures chlorophyll content differences
- Less saturated than NDVI in dense canopy
- Sensitive to nitrogen status (sugarcane is heavy nitrogen feeder)

### 5.3.3 Phenological Metrics

We extract phenological indicators from time-series data:
- Season length (sugarcane: 12-18 months; maize: 3-4 months)
- Number of growth peaks (sugarcane: 1; maize: 1 per season)
- Seasonal amplitude patterns

### 5.3.4 Texture Analysis from High-Resolution Drone Imagery

Drone imagery (3-5 cm GSD) enables:
- Row spacing analysis (sugarcane: 1.2-1.5m; maize: 0.75-0.9m)
- Canopy texture classification
- Field boundary precision

## 5.4 Results: Classification Accuracy

Our multi-index, temporal approach achieved:

| Class | Producer's Accuracy | User's Accuracy |
|-------|---------------------|-----------------|
| Sugarcane | 94.2% | 91.8% |
| Maize | 87.5% | 89.3% |
| Napier/Pasture | 78.4% | 76.2% |
| Other | 92.1% | 93.5% |

**Overall Accuracy: 89.7%**

## 5.5 Recommendations for Improved Grass Elimination

1. **Acquire hyperspectral data** for detailed spectral fingerprinting
2. **Integrate crop calendar** with planting/harvesting dates from mills
3. **Phenological monitoring** using bi-weekly Sentinel-2 composites
4. **Ground validation campaigns** during ambiguous periods
5. **Farmer registration database** linking parcels to registered sugarcane growers

---

# 6. VIABILITY OF DRONES FOR FUTURE CANE AVAILABILITY SURVEYS

## 6.1 Assessment Criteria

| Criterion | Drone Performance | Rating |
|-----------|-------------------|--------|
| Accuracy | Centimeter-level precision | Excellent |
| Cost-effectiveness | Lower per-hectare cost at scale | Good |
| Scalability | Requires fleet expansion | Moderate |
| Timeliness | Real-time data collection | Excellent |
| Weather dependence | Affected by rain/wind | Moderate |
| Regulatory compliance | KCAA licensing required | Compliant |

## 6.2 Scientific Evidence Supporting Drone Adoption

According to research from the UN Africa Renewal publication and AUDA-NEPAD:

> "The agricultural sector in Africa has seen a notable increase in the utilization of drone technology for crop management, rising from over 50% to approximately 60% in recent years."

> "Experts predict that agriculture will emerge as the largest area of growth for drone technology within the commercial sector over the next decade."

> "The global agriculture drone market is expected to grow by approximately 20% annually from $4.98 billion in 2023 to $18.22 billion by 2030."

## 6.3 Kenya-Specific Context

Rwanda and Kenya are emerging as key hubs for testing drone technology in agriculture. Key advantages:
- Relatively clear airspaces
- Growing regulatory framework (KCAA)
- Pressing need for innovative agricultural solutions
- Established drone service providers (Fahari Aviation, Precision Drones)

## 6.4 Recommended Operational Model

### Phase 1: Pilot Consolidation (Current - 6 months)
- Complete Western Catchment digitization
- Validate models across all sugar zones
- Finalize training for all designated KSB officers

### Phase 2: Operational Scale-Up (6-18 months)
- Establish regional drone hubs (Western, Nyanza, Coast)
- Integrate with existing cane census workflow
- Develop automated reporting dashboard

### Phase 3: National Deployment (18-36 months)
- Full coverage of all sugar catchments
- Real-time mill supply forecasting
- Integration with national agriculture data systems

## 6.5 Conclusion: Drone Viability

**YES - Drones are highly viable for future cane availability surveys**, provided:
1. Adequate investment in equipment and infrastructure
2. Continued capacity building for KSB staff
3. Integration with satellite data for regional scaling
4. Clear protocols and standard operating procedures

---

# 7. MODEL TRAINING REQUIREMENTS AND TIMELINE

## 7.1 Current Model Status

The Random Forest model has been trained and validated with:
- 27 sample farms across multiple sugar companies
- 8 vegetation indices as predictor variables
- Historical yield data as ground truth
- Cross-validation for robustness assessment

## 7.2 Training Data Requirements

Based on scientific literature from *Nature Scientific Data* and *Frontiers in Remote Sensing*:

| Training Phase | Data Requirement | Timeline |
|----------------|------------------|----------|
| Initial Model | 50-100 sample farms | 2-3 months |
| Improved Accuracy | 200-500 sample farms | 6-9 months |
| Regional Calibration | 100+ farms per catchment | 12-18 months |
| Operational Maturity | Continuous data ingestion | Ongoing |

## 7.3 Recommended Model Training Timeline

### Year 1: Foundation Building
- **Months 1-3:** Complete digitization of all mapped farms
- **Months 4-6:** Integrate historical mill delivery data (3 years)
- **Months 7-9:** Incorporate weather and soil datasets
- **Months 10-12:** Validate model across all catchments

### Year 2: Model Refinement
- **Months 1-6:** Seasonal recalibration with new harvest data
- **Months 7-12:** Integrate additional environmental variables

### Year 3: Operational Deployment
- **Continuous:** Automated model updates with each season's data
- **Annual:** Full model retraining with accumulated multi-year dataset

## 7.4 Data Sources for Model Enhancement

| Data Type | Source | Frequency |
|-----------|--------|-----------|
| Yield Data | Mill weighbridge records | Per harvest |
| Weather | Kenya Met Department | Daily/Monthly |
| Soil | ISRIC/National Soil Survey | Static |
| Planting Dates | Farmer registration | Annual |
| Satellite Imagery | Sentinel-2 via GEE | 5-day |
| Drone Imagery | Field campaigns | Seasonal |

## 7.5 Computational Requirements

Training a Random Forest model with 200-500 samples:
- **CPU:** Multi-core processor (Intel Xeon/AMD EPYC)
- **RAM:** 16-64 GB
- **Training Time:** Minutes to hours (depending on features)
- **Platform:** Google Earth Engine (cloud-based, scalable)

**Note:** Unlike deep learning models requiring weeks of training, Random Forest models can be retrained rapidly, enabling iterative improvement.

---

# 8. KSB STAFF TRAINING PROGRAM

## 8.1 Training Completed

**Phase 1: May 2025 (12th - 23rd)**
- **Duration:** 10 working days
- **Participants:** 5 KSB officers
- **Location:** Naivasha (Lot 1)

### Training Curriculum

| Day | Module | Topics |
|-----|--------|--------|
| 1-2 | Introduction to GIS & Remote Sensing | Electromagnetic radiation, Satellite vs Drone RS, Multispectral sensors |
| 3-4 | Vegetation Indices | NDVI, EVI, SAVI, NDRE applications in crop monitoring |
| 5-6 | GIS Data Processing | ArcGIS Pro, QGIS, georeferencing, feature extraction |
| 7-8 | Machine Learning for Yield Prediction | Random Forest regression, data splitting, model evaluation |
| 9-10 | Advanced Spatial Analysis | Time-series analysis, yield forecasting, visualization |

## 8.2 Training Outcomes

Trained officers can now:
- Operate drone data collection campaigns
- Process multispectral imagery using DJI Terra
- Digitize farm boundaries in QGIS
- Execute GEE scripts for vegetation index computation
- Interpret model outputs for decision support

## 8.3 Recommended Future Training

### Phase 2: Q1 2026
- **Participants:** 5 additional officers
- **Focus:** Advanced GIS analysis, Python scripting

### Phase 3: Q2 2026
- **Participants:** Selected officers from sugar mills
- **Focus:** Data interpretation and mill-level applications

### Drone Pilot Certification
- **Participants:** 2-3 designated KSB officers
- **Provider:** KCAA-approved training center
- **Duration:** 2-3 weeks
- **Certification:** Remote Pilot License (RPL)

## 8.4 Continuous Professional Development

- Annual refresher training (2-3 days)
- Access to online GIS courses (Esri, Coursera)
- Participation in regional precision agriculture conferences
- Knowledge exchange with peer institutions

---

# 9. DRONE ACCESSORIES AND INFRASTRUCTURE REQUIREMENTS

## 9.1 Current Equipment Gap Assessment

| Item | Current Status | Required | Gap |
|------|----------------|----------|-----|
| DJI Mavic 3M Drone | 1 unit | 3 units | 2 units |
| Batteries | 3 | 9 (3 per drone) | 6 |
| D-RTK 2 Station | 0 | 1 | 1 |
| DJI Terra License | 0 | 1 | 1 |
| Processing Workstation | 0 | 2 | 2 |

## 9.2 Recommended Procurement

### A. Drone Accessories (Approx. KShs. 2,035,000)

| Item | Purpose | Amount (KShs) |
|------|---------|---------------|
| D-RTK 2 Station | High-precision GNSS RTK correction | 560,000 |
| DJI Terra Software | Data processing | 650,000 |
| Additional Batteries (6) | Full-day operations | 330,000 |
| Charging Hub | Multi-battery charging | 50,000 |
| Spare Propellers (5 pairs) | Replacements | 125,000 |
| Calibration Panel | Radiometric correction | 100,000 |
| MicroSD Cards (1TB) | Image storage | 45,000 |
| Car AC Converter | Field charging | 175,000 |

### B. Server Infrastructure (Approx. KShs. 3,500,000)

| Component | Specification |
|-----------|---------------|
| CPU | Dual Intel Xeon Silver 4316 (16 cores each) |
| RAM | 256 GB DDR4 ECC (expandable to 512 GB) |
| Storage | 4 TB NVMe SSD + 24 TB RAID-10 SATA |
| GPU | NVIDIA A6000 / RTX 5000 |
| Network | Dual 10GbE NICs |
| OS | Ubuntu Server 22.04 LTS / Windows Server 2022 |
| Database | PostgreSQL + PostGIS |
| UPS | APC Smart-UPS 6000VA |

### C. GIS Workstations (Approx. KShs. 2,500,000)

| Component | Specification |
|-----------|---------------|
| CPU | AMD Ryzen 9 7950X / Intel Core i9 13900K |
| RAM | 64 GB DDR5 (expandable to 128 GB) |
| Storage | 1TB NVMe SSD + 4TB SATA SSD |
| GPU | NVIDIA RTX 4070/4080 |
| Monitor | Dual 27" 4K (calibrated) |
| Software | ArcGIS Pro, QGIS, DJI Terra |

### D. Field Equipment (Approx. KShs. 675,000)

| Item | Amount (KShs) |
|------|---------------|
| Rugged Field Laptop | 300,000 |
| GNSS Handheld Receiver | 375,000 |

## 9.3 Total Infrastructure Investment

| Category | Amount (KShs) |
|----------|---------------|
| Drone Accessories | 2,035,000 |
| Server Infrastructure | 3,500,000 |
| GIS Workstations | 2,500,000 |
| Field Equipment | 675,000 |
| **Total** | **8,710,000** |

## 9.4 Return on Investment Analysis

**Current census cost:** KShs 50-80M annually (labor, transport, logistics)
**Drone-assisted approach:** KShs 15-25M annually (after initial investment)
**Potential annual savings:** KShs 30-55M
**Payback period:** 4-6 months of operation

---

# 10. FARM DIGITIZATION FOR IMPROVED AREA COMPUTATION

## 10.1 The Case for High-Resolution Imagery

### Current Challenge
- Farmer-reported areas are unreliable
- Survey-grade measurements are expensive
- Cadastral data is often outdated
- Mill records based on historical estimates

### Solution: Satellite-Based Farm Digitization

Comprehensive digitization of all sugarcane-growing areas using high-resolution satellite imagery will provide:
1. Accurate farm boundaries (sub-meter precision)
2. Precise acreage figures
3. Base layer for all yield estimation models
4. Transparent, consistent data across farms

## 10.2 Recommended Imagery Specifications

| Parameter | Specification |
|-----------|---------------|
| Resolution | 0.3-0.5 meters (Maxar/Planet) |
| Coverage | All sugar catchments (~200,000 Ha) |
| Frequency | Annual update |
| Bands | RGB + NIR minimum |

## 10.3 Digitization Workflow

```
[High-Res Imagery Acquisition] → [Cloud-Free Mosaic Creation]
                                          ↓
[Manual Digitization in QGIS] ← [Farm Boundary Delineation]
                                          ↓
[Attribute Assignment] → [QA/QC Verification] → [Database Integration]
                                          ↓
                               [Farmer Validation Campaigns]
```

## 10.4 Timeline and Cost Estimate

| Phase | Activity | Duration | Estimated Cost |
|-------|----------|----------|----------------|
| 1 | Imagery acquisition | 1-2 months | KShs 5-10M |
| 2 | Digitization | 3-4 months | KShs 3-5M |
| 3 | Validation | 2 months | KShs 1-2M |
| **Total** | | **6-8 months** | **KShs 9-17M** |

## 10.5 Expected Benefits

1. **Accuracy:** Eliminate area estimation discrepancies
2. **Transparency:** Farmer-verified boundaries
3. **Efficiency:** One-time investment with annual updates
4. **Integration:** Foundation for precision agriculture tools

---

# 11. CHALLENGES AND MITIGATION STRATEGIES

## 11.1 Operational Challenges Encountered

### 11.1.1 Field Fragmentation

**Challenge:** Continuous land subdivision in portions of the Western Catchment has resulted in increasingly fragmented and smaller field sizes. This significantly reduces mapping efficiency.

**Impact:** More time and resources required to cover adequate sample areas.

**Mitigation:**
- Use satellite imagery for broad coverage
- Reserve drone missions for high-value verification
- Develop sampling protocols for fragmented landscapes

### 11.1.2 Weather and Cloud Cover

**Challenge:** The Western Catchment experiences persistent cloud cover and rapidly changing weather patterns that frequently disrupted mapping operations.

**Impact:** Limited optimal flying windows, extended deployment periods, compromised image quality.

**Mitigation:**
- Schedule flights during dry seasons (January-March, July-September)
- Use cloud-free Sentinel-2 composites for regional coverage
- Implement cloud masking algorithms in GEE

### 11.1.3 Equipment and Resource Limitations

**Challenge:** Insufficient battery capacity and data storage reduced daily operational capacity.

**Impact:** Directly impacted pace and scale of data collection.

**Mitigation:**
- Procure additional batteries (6 minimum)
- Invest in field charging solutions
- Deploy portable NAS storage for backup

### 11.1.4 Transportation Logistics

**Challenge:** Geographic spread of sampling locations combined with poor road conditions.

**Impact:** Reduced time available for actual mapping activities.

**Mitigation:**
- Strategic hub-and-spoke deployment model
- 4x4 vehicles with adequate clearance
- Advance route planning

### 11.1.5 Power Supply Issues

**Challenge:** Frequent power outages significantly disrupted data processing workflows.

**Impact:** Delayed output delivery, risk of data corruption.

**Mitigation:**
- UPS systems for all workstations
- Generator backup at processing facilities
- Cloud-based processing (GEE) as primary platform

## 11.2 Technical Challenges

### 11.2.1 Spectral Similarity of Crops

**Challenge:** Difficulty distinguishing sugarcane from maize, napier grass, and pasture.

**Mitigation:** Multi-temporal analysis, phenological profiling, texture analysis (see Section 5).

### 11.2.2 Model Generalization

**Challenge:** Model trained in one region may not perform equally in others.

**Mitigation:** Regional calibration with local training data, transfer learning techniques.

### 11.2.3 Data Integration

**Challenge:** Combining diverse data sources (drone, satellite, census, mill records).

**Mitigation:** Standardized data formats, centralized GIS database, clear metadata protocols.

## 11.3 Institutional Challenges

### 11.3.1 Staff Turnover

**Mitigation:** Cross-train multiple officers, document all procedures.

### 11.3.2 Inter-Agency Coordination

**Mitigation:** Clear MOU terms, regular stakeholder meetings, defined data sharing protocols.

---

# 12. REVIEW OF MOU ENGAGEMENT

## 12.1 MOU Overview

The engagement between Kenya Sugar Board and Ecospace Services Ltd. is governed by a Memorandum of Understanding covering:
- Drone-assisted cane census operations
- Capacity building and technology transfer
- Joint data analysis and report production
- Equipment provision and maintenance

## 12.2 Deliverables Assessment

| Deliverable | Status | Remarks |
|-------------|--------|---------|
| Drone mapping campaigns | Completed | 200+ fields mapped |
| Data processing and analysis | Completed | Full pipeline operational |
| Yield prediction model | Completed | R² = 0.923 achieved |
| Staff training (Phase 1) | Completed | 5 officers trained |
| Technical reports | Completed | This document |
| GEE scripts | Completed | Operational on KSB assets |

## 12.3 Recommendations for MOU Enhancement

1. **Extend engagement** to cover remaining catchments (Coast, Nyanza expansion)
2. **Include satellite imagery procurement** in scope
3. **Formalize data sharing protocols** with sugar mills
4. **Establish performance benchmarks** for annual review
5. **Define intellectual property** ownership of developed tools

## 12.4 Budget Utilization

All authorized budgets were utilized within specified activities:
- Field mapping exercises
- Data processing workshops
- Training programs
- Report writing seminars

---

# 13. CONCLUSIONS AND RECOMMENDATIONS

## 13.1 Key Conclusions

1. **Drone-assisted mapping significantly improves accuracy** of area under cane estimation, reducing census overestimation by approximately 17%.

2. **Machine learning models achieve high prediction accuracy** (R² = 0.923), demonstrating the viability of technology-driven yield forecasting.

3. **Crop classification challenges can be addressed** through multi-temporal analysis and advanced vegetation indices, achieving 89.7% overall accuracy.

4. **KSB staff have demonstrated capacity** to operate and maintain geospatial systems with appropriate training and support.

5. **Infrastructure investment requirements are modest** (KShs 8.7M) relative to potential annual savings (KShs 30-55M).

## 13.2 Strategic Recommendations

### Immediate Actions (0-6 months)

1. **Procure essential drone accessories** (KShs 2.035M)
2. **Complete Phase 2 staff training** (5 additional officers)
3. **Finalize Western Catchment digitization**
4. **Establish GIS Unit at KSB headquarters**

### Medium-Term Actions (6-18 months)

5. **Acquire high-resolution satellite imagery** for national digitization
6. **Deploy drone hubs** at strategic regional locations
7. **Integrate model outputs** with mill scheduling systems
8. **Conduct annual model recalibration**

### Long-Term Actions (18-36 months)

9. **Achieve full national coverage** of all sugar catchments
10. **Implement real-time monitoring dashboard**
11. **Establish data sharing agreements** with county governments
12. **Publish research findings** in peer-reviewed journals

## 13.3 Final Statement

The collaboration between Kenya Sugar Board and Ecospace Services Ltd. has demonstrated the transformative potential of drone and satellite technology for modernizing Kenya's sugar industry. The evidence presented in this report strongly supports continued investment in precision agriculture technologies as a strategic priority for the sector.

With proper implementation of the recommendations herein, KSB will be positioned as a regional leader in data-driven agricultural management, delivering tangible benefits to farmers, millers, and the national economy.

---

# 14. ANNEXES

## Annex A: Google Earth Engine Code Repository

The developed scripts are available at:
- Asset Path: `projects/ee-espace/assets/`
- Version: KSB Sugarcane Monitoring System v1.4

## Annex B: Equipment Specifications

Detailed specifications attached separately.

## Annex C: Training Materials

Available upon request from Ecospace Services Ltd.

## Annex D: Raw Data and Shapefiles

Archived at KSB GIS database and Ecospace cloud storage.

---

**Report Prepared By:**

**Ecospace Services Ltd.**
*Providing Geospatial Solutions*

**Contact:**
- Email: info@ecospace.co.ke
- Website: www.ecospace.co.ke

---

**Document Control:**
- Version: 1.0
- Date: December 2025
- Classification: Official - KSB Internal Use
- Distribution: KSB Executive Management, Technical Advisory Services, Market Research & Product Development

---

*This report contains proprietary methodologies and findings developed through the KSB-Ecospace partnership. Reproduction or distribution without authorization is prohibited.*
