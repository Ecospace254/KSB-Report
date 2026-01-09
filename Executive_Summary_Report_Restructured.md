# Application of Drone and Satellite Solutions for Sugarcane Mapping in Kenya
## Restructured Summary Report

**Kenya Sugar Board & Ecospace Services Ltd.**
**December 2025**

---

## 1. Abstract

This technical report presents comprehensive findings from the collaborative drone-assisted sugarcane mapping and yield prediction program undertaken by Ecospace Services Ltd. in partnership with the Kenya Sugar Board. Through systematic deployment of multispectral drone imagery, satellite data integration via Google Earth Engine, and Random Forest machine learning algorithms, the project achieved a yield prediction accuracy of 92.3% (R² = 0.923), identified 34,473.09 hectares of mature cane in the Western Catchment, and documented a 16.99% overestimation in conventional census methods when compared to drone and satellite analysis. The project trained five KSB officers in GIS, Remote Sensing, and Machine Learning applications, establishing foundational internal capacity for sustained implementation. Key findings include critical cane supply-demand deficits ranging from 39% to 66% across different seasonal periods, highlighting the urgent need for accurate, real-time cane monitoring to optimize limited supply against mill crushing schedules.

---

## 2. Introduction

### 2.1 Overview of the Project

Kenya's sugar industry serves as a critical economic pillar, supporting over eight million Kenyans directly and indirectly. The 2025 Upper and Lower Western Cane Census documented 309,017 registered sugarcane farmers cultivating 149,438 hectares across 10 counties in the Western Kenya sugar belt, with an average plot size of just 0.48 hectares reflecting the predominantly smallholder nature of the sector. The seven operational mills in the Western region possess a combined daily crushing capacity of 20,800 tonnes of cane per day (TCD), yet face persistent supply deficits ranging from 39% to 66% across different seasonal periods.

### 2.2 The Importance of Yield Prediction

Accurate cane estimation carries direct implications for multiple operational and strategic functions:
- **Mill scheduling and crushing operations** depend on accurate projections of when and how much mature cane will become available
- **Supply contracting arrangements** between mills and farmer cooperatives rely on reliable area figures
- **National sugar production forecasting** informs import quota decisions and market price interventions
- **Policy formulation** by the Agriculture and Food Authority requires accurate baseline data

### 2.3 Problem Statement

Traditional field-based cane census methods face inherent limitations:
- Census enumerators can only visit a fraction of total planted area within practical constraints
- Farmer-reported acreages frequently overestimate actual planted areas by substantial margins
- Seasonal timing of census activities may not capture rapidly changing conditions
- High labor intensity and associated costs limit frequency and coverage

### 2.4 Objectives of the Research

1. Modernize cane census methodologies through systematic deployment of drone and satellite technology
2. Train machine learning-based yield prediction models capable of estimating cane tonnage from remotely sensed vegetation indices
3. Build internal KSB capacity in geospatial technologies through structured training programmes
4. Establish scalable workflows suitable for national deployment across all sugar-growing regions
5. Provide accurate, validated area under cane and cane availability estimates for mill planning

### 2.5 Scope of the Research

The geographical scope encompassed multiple sugar catchment regions:
- **Western Catchment**: Butali, West Kenya, and Busia sugar companies (fragmented smallholder systems)
- **Nyanza Region**: Muhoroni, South Nyanza, and Sukari Industries (mixed nuclear estate and out-grower systems)
- **Trans Mara Area**: Transmara Sugar (medium-scale farms)
- **Coastal Region**: KISCOL in Kwale County (large-scale plantation agriculture)

---

## 3. Literature Review

### 3.1 Remote Sensing in Sugarcane Yield Estimation

A systematic review published in Remote Sensing journal (February 2024) examined 72 publications on sugarcane yield estimation using remote sensing approaches (January 2017 - June 2023). The review concluded that remote sensing data assimilation in crop models represents a promising approach enhanced by expanding availability of free Earth observation data from platforms such as Sentinel-2 and Landsat.

### 3.2 Machine Learning Applications

Research at the International Society for Photogrammetry and Remote Sensing (May 2024) demonstrated sugarcane recognition accuracies of 91.4% with misrecognition rates as low as 2.8% using joint classification approaches. Studies using Landsat-8 OLI data with Random Forest classification achieved overall accuracies exceeding 92% with Kappa coefficients greater than 0.8.

### 3.3 Vegetation Indices for Crop Monitoring

Research in Ethiopia's Awash Basin using Sentinel-2 data combined with Random Forest regression achieved high prediction precision, with vegetation indices focusing on red-edge spectral bands proving particularly valuable. Australian research on sugarcane yield prediction achieved R² values reaching 0.96 when integrating satellite remote sensing with environmental variables.

### 3.4 Field Boundary Mapping

Research published in Frontiers in Artificial Intelligence examining field boundary mapping in African smallholder contexts achieved overall accuracies of 86.7-88% for field boundary delineation, demonstrating proof of concept for national-scale field boundary maps in smallholder-dominated systems.

---

## 4. Methodology

### 4.1 Research Area Description

The Western Catchment study area spans eight counties with 149,438 hectares under sugarcane cultivation. County distribution:

| County | Area (Ha) | % of Total | Registered Farmers | Avg. Plot Size (Ha) |
|--------|-----------|------------|-------------------|---------------------|
| Kakamega | 52,793.23 | 35.30% | 132,319 | 0.40 |
| Bungoma | 43,619.69 | 29.20% | 116,573 | 0.37 |
| Busia | 24,889.57 | 16.70% | 28,369 | 0.88 |
| Nandi | 11,457.90 | 7.70% | 8,044 | 1.42 |
| Trans Nzoia | 8,967.98 | 6.00% | 15,299 | 0.59 |
| Uasin Gishu | 5,606.63 | 3.80% | 6,067 | 0.92 |
| Vihiga | 1,624.30 | 1.10% | 1,995 | 0.81 |
| **TOTAL** | **149,438.00** | **100%** | **309,017** | **0.48** |

### 4.2 Data Collection

#### 4.2.1 Drone-Based Data Collection
- **Platform**: DJI Mavic 3 Multispectral
- **Sensors**: 20-megapixel RGB camera + four 5-megapixel multispectral cameras
- **Spectral Bands**: Green (560nm), Red (650nm), Red Edge (730nm), Near-Infrared (860nm)
- **Flight Altitude**: 80-120 metres AGL
- **Ground Sample Distance**: 3-5 centimetres
- **Image Overlap**: 70-80% forward, 60-70% lateral
- **Positioning**: RTK-capable GNSS with Ground Control Points

#### 4.2.2 Satellite Data Integration
- **Platform**: Sentinel-2 Level-2A surface reflectance products
- **Access**: Google Earth Engine
- **Resolution**: 10-20 metres spatial resolution
- **Revisit Frequency**: 5-day (combined Sentinel-2A/2B)
- **Processing**: Automated cloud/shadow masking, monthly vegetation index mosaics

#### 4.2.3 Ground Truth Collection
- **Tool**: Trimble Ecofield with sub-metre accuracy
- **Data Collection**: Open Data Kit digital census forms
- **Attributes**: Farmer ID, crop age, variety, expected yield, management notes
- **Validation**: Mill-level historical weighbridge data

### 4.3 Data Processing and Analysis

#### 4.3.1 Vegetation Indices Computed
Seven vegetation indices were derived:
1. **NDVI** (Normalized Difference Vegetation Index) - General biomass measure
2. **EVI** (Enhanced Vegetation Index) - Reduced atmospheric interference
3. **SAVI** (Soil Adjusted Vegetation Index) - Soil background minimization
4. **NDRE** (Normalized Difference Red Edge Index) - Chlorophyll sensitivity in dense canopies
5. **GCI** (Green Chlorophyll Index) - Leaf chlorophyll concentration
6. **GNDVI** (Green Normalized Difference Vegetation Index) - Canopy greenness
7. **WDRVI** (Wide Dynamic Range Vegetation Index) - High canopy cover sensitivity

#### 4.3.2 Classification Approach
Multi-strategy approach addressing spectral similarity challenges:
- Temporal profile analysis (NDVI time series)
- Phenological metrics (season length, growth peaks)
- Texture analysis from high-resolution drone imagery (row spacing detection)
- **Overall Classification Accuracy**: 89.7%
- **Sugarcane Producer's Accuracy**: 94.2%
- **Sugarcane User's Accuracy**: 91.8%

### 4.4 Random Forest Model Implementation

#### 4.4.1 Model Configuration
- **Algorithm**: Random Forest ensemble learning
- **Trees**: 100-200 per forest
- **Training Data**: 300+ sample farms across multiple sugar companies
- **Features**: 8 vegetation indices + historical yield data + field characteristics
- **Validation**: 70/30 train-test split with cross-validation

#### 4.4.2 Model Evaluation Metrics
- **R² (Coefficient of Determination)**: 0.923
- **MAE (Mean Absolute Error)**: 1.547 tonnes/hectare
- **MAPE (Mean Absolute Percentage Error)**: 6.5%
- **RMSE (Root Mean Square Error)**: 11.211 tonnes/hectare
- **Statistical Significance**: p < 0.001

---

## 5. Results

### 5.1 Model Performance

The Random Forest regression model achieved:
- **R² = 0.923**: 92.3% of variance in observed yields explained
- **MAE = 1.547 Tc/Ha**: Average prediction deviation ~2-3% of typical yields
- **RMSE = 11.211 Tc/Ha**: Some outlier predictions with larger errors identified

These results compare favorably with international benchmarks (Australian studies achieved R² = 0.96; Sri Lankan studies reported R² = 0.91).

### 5.2 Area Under Cane Results

#### 5.2.1 Mature Cane Distribution (Western Catchment)
Total mature cane identified: **25,011.17 hectares**

| County | Area (Ha) | % of Total |
|--------|-----------|------------|
| Kakamega | 6,158.43 | 24.6% |
| Nandi | 4,272.19 | 17.1% |
| Uasin Gishu | 4,189.87 | 16.7% |
| Bungoma | 3,257.13 | 13.0% |
| Trans Nzoia | 3,165.97 | 12.7% |
| Busia | 2,548.07 | 10.2% |
| West Pokot | 1,204.76 | 4.8% |
| Siaya | 214.75 | 0.9% |

#### 5.2.2 Census Overestimation Finding
**Conventional census methods overestimate mature cane area by 16.99% on average**

Notable discrepancies:
- Transmara (Keiyan Co-op): 26.00 Ha reported vs 8.82 Ha measured (195% overestimation)
- Transmara (Keiyan Co-op): 13.00 Ha reported vs 6.16 Ha measured (111% overestimation)

### 5.3 Cane Supply-Demand Analysis

| Period | Available Cane (MT) | Mill Requirement (MT) | Deficit (MT) | Deficit % | Mill Utilization |
|--------|--------------------|-----------------------|--------------|-----------|------------------|
| Nov-Dec 2025 | 1,069,936 | 1,743,780 | 673,844 | 38.6% | 61.4% |
| Jan-Mar 2026 | 1,440,431 | 2,615,670 | 1,175,239 | 44.9% | 55.1% |
| Apr-Jun 2026 | 1,309,151 | 2,615,670 | 1,306,519 | 50.0% | 50.0% |
| Jul-Oct 2026 | 1,180,551 | 3,487,560 | 2,306,519 | 66.1% | 33.9% |
| **Annual** | **5,000,069** | **10,462,680** | **5,461,621** | **52.2%** | **47.8%** |

### 5.4 Feature Importance Analysis

| Variable | Importance (%) |
|----------|---------------|
| Drone-measured Area | 33% |
| Tonnes of Cane/Ha (Historical) | 23% |
| Yield Threshold | 20% |
| NDRE | 7% |
| GCI | 6% |
| NDVI | 5% |
| GNDVI | 4% |
| WDRVI | 1% |
| Crop Class | 1% |

### 5.5 Statistical Validation

Paired t-test comparing census and predicted values:
- **Mean difference**: 1.0019 tonnes
- **p-value**: 0.1483
- Since p > 0.05, drone-based predictions are statistically equivalent to census estimates at aggregate level while providing superior spatial precision

---

## 6. Discussion

### 6.1 Interpretation of Model Performance

The R² value of 0.923 indicates operationally useful prediction accuracy, exceeding the commonly accepted threshold of R² = 0.85 for agricultural forecasting. The model successfully captured key factors affecting yield variation including environmental conditions, crop health, and growth patterns.

The 16.99% average overestimation in census-reported areas has significant implications:
- Mills relying on census figures would expect substantially more cane than actually exists
- Resulting shortfalls disrupt crushing schedules and leave mill capacity underutilized
- Economic impact: 5.46 million tonne deficit represents ~KShs 24.6 billion in foregone farmer income

### 6.2 Comparison with Existing Studies

Results align with international research benchmarks:
- Australian studies (Field Crops Research): R² = 0.96
- Sri Lankan studies: R² = 0.91
- Global Random Forest meta-analysis: mean R² ≈ 0.96

The prominence of red-edge indices (NDRE) aligns with Ethiopian Sentinel-2 studies showing red-edge bands crucial for enhancing prediction precision.

### 6.3 Practical Implications

**For Mill Operations:**
- Real-time visibility into cane maturity and availability
- Optimized harvest scheduling and logistics coordination
- Early detection of fields reaching harvest maturity

**For Farmers:**
- More accurate payments based on objective measurements
- Transparent boundary verification
- Access to precision agriculture tools

**Economic Benefits:**
- Current census costs: KShs 5-15 million annually
- Drone-assisted costs: KShs 2-5 million annually (after initial investment)
- Potential annual savings: KShs 3-10 million
- Payback period: 4-6 months

### 6.4 Limitations and Challenges

1. **Field Fragmentation**: Average plot size of 0.48 Ha increases per-hectare mapping costs
2. **Weather Constraints**: Persistent cloud cover disrupts both drone and satellite data collection
3. **Spectral Similarity**: Sugarcane, maize, and Napier grass share similar spectral signatures
4. **Equipment Limitations**: Battery capacity and data storage reduced daily operational capacity
5. **Power Supply**: Frequent outages disrupted data processing workflows
6. **Transportation**: Poor road conditions consumed substantial transit time

### 6.5 Recommendations for Future Research

1. **Additional Data Integration**: Soil type, weather data, pest/disease information
2. **Temporal Analysis**: Time-series monitoring throughout growth cycles
3. **Model Optimization**: Seasonal recalibration with each harvest season's data
4. **Regional Calibration**: Local training data for different agro-ecological zones
5. **Decision Support Integration**: Real-time recommendations for farm management

---

## 7. Conclusion

### 7.1 Summary of Key Findings

1. **Drone-assisted mapping significantly improves accuracy**: 16.99% overestimation documented in conventional census methods eliminated through objective drone measurement

2. **Machine learning achieves high prediction accuracy**: R² = 0.923 matches global best practice standards for sugarcane yield estimation

3. **Crop classification challenges addressable**: 89.7% overall accuracy achieved through multi-temporal analysis and phenological profiling

4. **KSB staff capacity established**: Five officers trained in GIS, Remote Sensing, and Machine Learning applications

5. **Infrastructure investment justified**: KShs 8.7 million total investment recoverable within 4-6 months through operational savings

### 7.2 Implications for Sugarcane Farming in Kenya

- **Industry Impact**: Supports 8 million Kenyans; 309,017 registered farmers across 149,438 hectares
- **Supply Crisis**: 52.2% annual deficit (5.46 million MT) against mill requirements
- **Modernization Potential**: Drone technology viable for routine cane availability surveys
- **Scalability**: Applicable from smallholder (0.48 Ha average) to large-scale plantations

### 7.3 Limitations of the Research

- Model trained on specific regions; generalization requires regional calibration
- Temporal snapshots may not capture rapid condition changes
- Environmental factors (soil, irrigation, pests) not fully incorporated
- Current equipment inventory limits simultaneous multi-region deployment

### 7.4 Recommendations for Future Implementation

**Immediate (0-6 months):**
- Procure essential drone accessories (KShs 2.035 million)
- Complete Western Catchment digitization
- Train five additional KSB officers

**Medium-term (6-18 months):**
- Acquire high-resolution satellite imagery for all catchments
- Deploy regional drone hubs (Western, Nyanza, Coastal)
- Integrate with mill scheduling systems

**Long-term (18-36 months):**
- Achieve full national coverage
- Implement real-time monitoring dashboard
- Establish data sharing agreements with stakeholders

### 7.5 Final Thoughts

The collaboration between Kenya Sugar Board and Ecospace Services Ltd. has demonstrated the transformative potential of drone and satellite technology for modernizing agricultural monitoring in Kenya. With proper implementation, Kenya Sugar Board will be positioned as a regional leader in data-driven agricultural management, demonstrating innovation that peer institutions across Africa may seek to emulate.

The foundation has been established; the path forward is clear; the opportunity for transformative impact awaits execution.

---

**Report Prepared By:** Ecospace Services Ltd.
**Contact:** services@ecospace.co.ke | +254 798 740 614
**Version:** 3.0 | December 2025
**Classification:** Official - KSB Internal Use
