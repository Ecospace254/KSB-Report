# TECHNICAL APPROACH AND METHODOLOGY

## PROVISION OF WORLD GEODETIC SYSTEM-1984 (WGS-84) GROUND AND OBSTACLE MAINTENANCE SURVEY

### Tender No: KCAA/003/2025-2026

### Prepared by: Ecospace Services Ltd

---

## 1. UNDERSTANDING OF THE ASSIGNMENT

Ecospace Services Ltd understands that the Kenya Civil Aviation Authority (KCAA) requires the provision of WGS-84 Ground and Obstacle Maintenance Survey services for **Eldoret International Airport** and **Malindi Airport**. The survey shall be conducted in accordance with ICAO Standards and Recommended Practices (SARPs), specifically:

- **ICAO Annex 14** – Aerodromes (Obstacle Limitation Surfaces)
- **ICAO Annex 15** – Aeronautical Information Services (Chapter 5: Terrain and Obstacle Data)
- **ICAO Doc 9674** – WGS-84 Manual
- **ICAO Doc 10066** – PANS-AIM
- **ICAO Doc 8168** – PANS-OPS (Flight Procedure Design)
- **ICAO Doc 9157** – Aerodrome Design Manual
- **Kenya Survey Act (Cap 299)** and subsidiary legislation

The objective is to maintain, verify, and update the WGS-84 aeronautical survey database for both airports, ensuring data integrity, accuracy, and compliance with international aviation safety standards to support Performance Based Navigation (PBN) implementation and e-TOD National Plans.

---

## 2. SCOPE OF SERVICES

The assignment covers the following key components for each airport:

1. Maintenance of primary control stations and WGS-84 survey control points
2. Resurvey and verification of geodetic connections
3. Aerodrome and facility survey (runway thresholds, touchdown zones, parking stands, holding positions, navigational aids, geoid undulation)
4. Obstacle survey per ICAO Annex 14 Ch.4 and Annex 15 Ch.5 (Areas 2a, 2b, 2c, and Area 3)
5. Post-processing of data with unbroken audit trail
6. Longitudinal and transverse slope determination
7. Magnetic variation and annual change documentation
8. Aerodrome Mapping Data (point, line, polygon features)
9. Production of Aerodrome Charts and Obstacle Type A Charts
10. Final deliverables in both soft and hard copy formats

---

## 3. DETAILED STEP-BY-STEP METHODOLOGY

### PHASE 1: PROJECT INCEPTION AND PLANNING (Week 1–2)

#### Step 1.1: Kick-Off Meeting and Stakeholder Engagement
- Conduct a formal kick-off meeting with KCAA at their offices within **one (1) week** of contract signing.
- Review and confirm scope, access requirements, security clearances for both Eldoret International Airport and Malindi Airport.
- Identify KCAA liaison officers and airport operations contacts for coordination of airside access.
- Obtain existing WGS-84 survey data, previous survey reports, aerodrome reference point (ARP) coordinates, and existing control point documentation from KCAA.

#### Step 1.2: Desk Study and Data Review
- Conduct a comprehensive desk study of all existing survey data provided by KCAA.
- Review previous WGS-84 survey reports for Eldoret and Malindi airports.
- Obtain and review current aeronautical charts (AIP Kenya) for both airports.
- Compile ICAO obstacle surface parameters (approach, transitional, inner horizontal, conical, take-off climb surfaces) for each runway based on its classification and reference code.
- Procure the latest EGM96 geoid model grid files for the project area.
- Download and prepare IGS/AFREF reference station data catalogues for the survey period.

#### Step 1.3: Inception Report Preparation
- Prepare and submit the **Inception Report within two (2) weeks** of contract signing, containing:
  - Confirmed scope of work and interpretation of TOR
  - Detailed work plan and programme
  - Staff deployment plan
  - Equipment mobilization schedule
  - Quality management plan
  - Risk register and mitigation measures
  - Communication and reporting framework
  - Health, Safety, and Environment (HSE) plan

---

### PHASE 2: EQUIPMENT MOBILIZATION AND CALIBRATION (Week 2–3)

#### Step 2.1: Equipment Deployment

Ecospace Services Ltd will deploy the following Trimble GNSS equipment fleet:

| Equipment | Quantity | Role |
|-----------|----------|------|
| **Trimble R12i** | 2 units | Primary geodetic control surveys; base station for RTK operations; static sessions for IGS/AFREF connections |
| **Trimble R6-3** | 2 units | Secondary control densification; aerodrome facility surveys; obstacle surveys |
| **Trimble R4s** | 2 units | Kinematic and rapid-static surveys; obstacle detail surveys; area mapping |
| **Trimble 780 Controllers** | 2 units | Field data collection, real-time QC, feature coding |
| **Trimble Business Center (TBC)** | Licensed | Post-processing, network adjustment, coordinate transformation, report generation |
| **Bernese GNSS Software v5.4** | Licensed | High-precision geodetic processing, IGS station connections, ITRF realization |

**Additional survey equipment:**
- Total station (for indoor/obstructed-sky measurements)
- Digital barometric altimeters (redundant height verification)
- Laser rangefinders/clinometers (obstacle height measurement in obstructed areas)
- UAV/Drone (for aerial verification photography and hard-to-access obstacle identification)
- Surveying accessories: tripods, tribrachs, precise measuring tapes, reflectors

#### Step 2.2: Equipment Calibration and Verification
- All GNSS receivers will be verified against known National Survey Control Points (e.g., Survey of Kenya first-order geodetic network) prior to field deployment.
- Antenna phase centre calibrations will be confirmed from NGS/manufacturer absolute calibration files (ANTEX format).
- The **Trimble R12i** receivers feature 672-channel multi-constellation tracking (GPS, GLONASS, Galileo, BeiDou, NavIC, QZSS, SBAS) and Trimble ProPoint GNSS engine, providing:
  - Sub-centimetre accuracy in static mode
  - Inertial Measurement Unit (IMU) tilt compensation for measuring near obstructions without precise levelling
  - Advanced multipath mitigation for airport environments with reflective surfaces (hangars, terminal buildings, aircraft)
- The **Trimble R6-3** dual-frequency receivers provide reliable L1/L2 tracking suitable for control densification with ±3mm + 0.5ppm horizontal and ±5mm + 0.5ppm vertical accuracy in static mode.
- The **Trimble R4s** dual-frequency receivers provide efficient rapid-static and RTK capability for high-volume detail surveys, achieving ±8mm + 1ppm horizontal accuracy in RTK mode.

#### Step 2.3: Coordinate Reference System Configuration
- All equipment will be configured for the following reference systems:
  - **Horizontal Datum**: WGS-84 (ITRF2014, current realization epoch)
  - **Vertical Datum**: EGM96 Geoid Model for orthometric heights
  - **Projection**: Kenya National Mapping Grid (Cassini-Soldner / UTM Zone 37S as applicable)
- Geoid model grids (EGM96) will be loaded onto all controllers and into TBC for real-time and post-processed geoid-ellipsoid separation.

---

### PHASE 3: GEODETIC CONTROL SURVEY (Week 3–5)

This phase directly addresses the TOR requirement to *"maintain primary control stations and WGS-84 survey control points"* and *"resurvey and verify geodetic connections."*

#### Step 3.1: Reconnaissance and Recovery of Existing Control Points
- Visit all existing WGS-84 control points at Eldoret International Airport and Malindi Airport.
- Document the condition of each monument (intact, disturbed, destroyed, obstructed).
- Photograph and describe each point with GPS-stamped imagery.
- Identify points requiring re-establishment or replacement.
- Select locations for any new control points ensuring clear sky visibility (>15° elevation mask), stable ground, and long-term preservation.

#### Step 3.2: Primary Geodetic Control – Static GNSS Observation

**Connection to National and International Reference Framework:**

Using the **Trimble R12i** receivers (2 units operating simultaneously):

1. **IGS/AFREF Station Connection**: Occupy primary control points at each airport with dual-frequency static GNSS sessions of **minimum 8 hours** to establish traceable connections to the International Terrestrial Reference Frame (ITRF) via the following strategy:
   - Download concurrent observation data from nearby IGS/AFREF permanent stations:
     - **RCMN** (Nairobi) – AFREF station
     - **MAL2** (Malindi) – IGS station (particularly advantageous for Malindi Airport)
     - **MBAR** (Mbarara, Uganda) – IGS station
     - Other available AFREF/IGS stations within 500km baseline
   - Minimum of **3 IGS/AFREF stations** per airport solution for redundancy and reliability.

2. **Processing with Bernese GNSS Software v5.4**:
   - Process long-baseline static data using Bernese Software for scientific-grade geodetic accuracy:
     - Double-difference carrier phase processing
     - Precise ephemerides (IGS final orbits) and clock products
     - Tropospheric delay estimation using Vienna Mapping Function (VMF)
     - Ocean tide loading corrections
     - Antenna phase centre variations (absolute ANTEX calibrations)
     - Ambiguity resolution using quasi-ionosphere-free (QIF) and wide-lane/narrow-lane strategies
   - Compute ITRF2014 coordinates at observation epoch
   - Apply appropriate ITRF2014-to-WGS-84 transformation (noting these are operationally equivalent at the accuracy levels required)
   - **This ensures the geodetic connection is traceable to the global reference frame with sub-centimetre accuracy, far exceeding the ICAO requirement of 5m horizontal / 3m vertical.**

3. **Inter-Airport Baseline Processing**:
   - Process baselines between Eldoret and Malindi primary control using Bernese to verify internal consistency of the national WGS-84 network.

4. **Local Network Static Observations**:
   - Observe a minimum network of **4 control points per airport** using static sessions of **minimum 2 hours** per session.
   - Use both Trimble R12i units as base/rover in session-based observations with redundant baselines.
   - Observe network in multiple sessions to achieve redundancy factor ≥ 3.

#### Step 3.3: Network Adjustment and Verification
- Perform a rigorous **least-squares network adjustment** in Trimble Business Center:
  - Minimally constrained adjustment to check internal consistency
  - Constrained adjustment holding IGS/AFREF-derived coordinates fixed
  - Statistical testing: Chi-square test, Tau-test for outlier detection
  - Error ellipse computation at 95% confidence level
- Compare adjusted coordinates with previous KCAA WGS-84 values to detect any ground movement or monument displacement.
- Document all coordinate differences and provide analysis of any movements detected.
- **Accuracy target**: Horizontal ≤ 0.02m, Vertical ≤ 0.03m (control level), far exceeding the 5m/3m requirement for derived products.

#### Step 3.4: Vertical Control and Geoid Determination
- Determine orthometric heights using the **EGM96 geoid model** as specified.
- Compute geoid undulation (N) values at each control point: **h (ellipsoidal) – H (orthometric) = N (geoid undulation)**.
- Where possible, connect to existing Kenya levelling benchmarks (Survey of Kenya) for independent verification of EGM96-derived orthometric heights.
- Document the geoid undulation values for inclusion in the deliverables, as required by the TOR.

---

### PHASE 4: AERODROME AND FACILITY SURVEY (Week 4–8)

This phase addresses the TOR requirement for *"aerodrome and facility survey including runway thresholds, touchdown zones, parking stands, holding positions, navigational aids, and geoid undulation."*

#### Step 4.1: Survey Control Densification
- From the primary control network, densify survey control to provide RTK base station positions and local control for total station traverses.
- Use **Trimble R6-3** receivers in rapid-static mode (20-minute sessions) to establish secondary control points around the aerodrome.
- Verify by closed-loop traverses with total station where GNSS is obstructed.

#### Step 4.2: Runway and Taxiway Survey

Using **Trimble R4s** in RTK mode (base: Trimble R12i on primary control, rover: R4s with Trimble 780 controller):

**For each runway at both airports, survey:**

| Feature | Parameters Captured | Method |
|---------|-------------------|--------|
| Runway thresholds | WGS-84 coordinates (lat, lon, elevation), threshold crossing height | RTK GNSS |
| Runway end points | Coordinates and elevation | RTK GNSS |
| Touchdown zone (TDZ) | Elevation at TDZ, coordinates of TDZ markers | RTK GNSS |
| Runway centreline points | At 50m intervals for longitudinal profile | RTK GNSS |
| Runway edge points | At 50m intervals for transverse profile | RTK GNSS |
| Runway strip boundary | Coordinates of strip limits | RTK GNSS |
| Stopway/Clearway | If present, coordinates and elevation | RTK GNSS |
| RESA (Runway End Safety Area) | Coordinates and dimensions | RTK GNSS |

**Longitudinal and Transverse Slopes:**
- Compute **longitudinal slope** from centreline profile data at 50m intervals.
- Compute **transverse slope** from cross-section data at 50m intervals.
- Present slopes in percentage (%) and verify compliance with ICAO Annex 14 design standards (e.g., max longitudinal slope, max rate of slope change).
- Generate longitudinal and transverse profile diagrams.

#### Step 4.3: Taxiway and Apron Survey

| Feature | Parameters Captured |
|---------|-------------------|
| Taxiway centreline | Coordinates at regular intervals, widths |
| Taxiway holding positions | CAT I/II/III holding point coordinates |
| Parking stands | Stand centre coordinates, lead-in line geometry |
| Apron boundaries | Perimeter coordinates and elevations |
| Aircraft stand reference points | WGS-84 coordinates |

#### Step 4.4: Navigational Aid Survey

Survey the precise WGS-84 position of all navigational aids at each airport:

| Navigational Aid | Survey Parameters |
|-----------------|-------------------|
| VOR/DME | Antenna reference point coordinates and elevation |
| ILS Localizer | Antenna array reference point, offset from centreline |
| ILS Glide Path | Antenna reference point, GPIP coordinates |
| NDB | Antenna reference point |
| PAPI/VASI | Light unit positions |
| Aerodrome Reference Point (ARP) | Geometric centre of all runway coordinates |
| Wind indicators | Position and elevation |
| Meteorological stations | Position and elevation |

- Use **Trimble R6-3** with precise point positioning where equipment mounting points require careful antenna placement.
- For ILS critical areas, coordinate with KCAA and airport operations to ensure survey does not interfere with active navigation signals.

#### Step 4.5: Other Aerodrome Facility Features

Survey all features required for the **Aerodrome Mapping Database**:

**Point features:** Lighting fixtures (edge, centreline, approach), signage, fire hydrants, utility access points, spot elevations

**Line features:** Runway/taxiway/apron edges, fencing, roads, drainage lines, building outlines, power lines, cables

**Polygon features:** Buildings (terminal, hangar, ATC tower, fire station), pavement areas, grassed areas, water bodies, restricted areas

- Use **Trimble R4s** in RTK mode for efficient collection of high-volume features.
- Feature coding in the **Trimble 780 controllers** using a pre-configured feature code library aligned with ICAO Aerodrome Mapping Database (AMDB) feature catalogue.
- Capture attributes: feature type, elevation, description, condition, material (for surfaces).

---

### PHASE 5: OBSTACLE SURVEY (Week 5–9)

This phase addresses the TOR requirement for *"obstacle survey per ICAO Annex 14 Ch.4, Annex 15 Ch.5"* including **Areas 2a, 2b, 2c, and Area 3**.

#### Step 5.1: Obstacle Surface Definition

For each runway, compute the ICAO Obstacle Limitation Surfaces (OLS) based on the runway classification and reference code:

- **Approach Surface** (Annex 14, Table 4-1)
- **Transitional Surface**
- **Inner Horizontal Surface**
- **Conical Surface**
- **Take-off Climb Surface**
- **Inner Approach Surface** (precision runways)
- **Balked Landing Surface** (precision runways)

Model these surfaces as 3D digital surfaces in GIS for intersection analysis with terrain and obstacles.

#### Step 5.2: Area 2 Obstacle Data Collection

**Area 2a – Aerodrome area:**
- Coverage: Inner horizontal surface and conical surface (typically 4km radius from ARP, extending to conical surface outer edge)
- Collection threshold: All obstacles penetrating the OLS
- Method: RTK GNSS survey using **Trimble R4s** for accessible obstacles; photogrammetric/remote sensing measurement for inaccessible obstacles; laser rangefinder for heights where GNSS cannot be placed atop obstacles
- Systematic windshield/ground reconnaissance survey of the entire Area 2a

**Area 2b – Approach and departure areas:**
- Coverage: Approach surfaces, take-off climb surfaces
- Collection threshold: Objects penetrating the respective surfaces
- Extended coverage along approach/departure paths as defined by ICAO
- Method: Combination of RTK GNSS, total station (for tall structures with no roof access), laser rangefinder/clinometer triangulation

**Area 2c – Circling area:**
- Coverage: As defined for each runway based on aircraft approach category
- Collection threshold: Objects exceeding specified heights above aerodrome elevation
- Method: Systematic survey using RTK GNSS and visual/photographic identification

**Area 3 – Aerodrome movement area:**
- Coverage: 90m from runway centreline, 50m from edges of other movement areas
- **Collection height: 0.5m** (all objects above 0.5m)
- This is the most intensive obstacle survey area requiring comprehensive ground survey
- Method: Systematic grid-based RTK survey using **Trimble R4s** and **Trimble R6-3** with all obstacles logged, measured for position, top elevation, and feature type

#### Step 5.3: Obstacle Data Attributes

For each obstacle, the following attributes will be collected:

| Attribute | Description |
|-----------|-------------|
| Obstacle ID | Unique identifier |
| Type | Building, tower, mast, tree, terrain, power line, crane, etc. |
| WGS-84 Latitude | Decimal degrees, 8 decimal places |
| WGS-84 Longitude | Decimal degrees, 8 decimal places |
| Top Elevation (MSL) | Orthometric height via EGM96 |
| Height AGL | Above ground level |
| Marking | Day marking status |
| Lighting | Obstacle lighting status |
| Material/Construction | Type of structure |
| Accuracy | Horizontal and vertical accuracy achieved |
| Penetration | Height above relevant OLS (if penetrating) |
| Data Source | Survey method used |
| Survey Date | Date of observation |

#### Step 5.4: Obstacle Measurement Techniques

**Direct GNSS measurement (preferred):**
- Place GNSS antenna directly on top of obstacle (for accessible structures)
- **Trimble R12i IMU tilt compensation** allows accurate measurement even when the antenna cannot be held perfectly level on irregular surfaces — critical advantage for obstacle top measurements
- Accuracy: ±10mm horizontal, ±15mm vertical (RTK)

**Indirect measurement (where direct GNSS not possible):**
- **Trigonometric heighting**: Total station measurement of angles to obstacle top from two or more known stations, computing height by trigonometry
- **Laser rangefinder/clinometer**: Measure slope distance and vertical angle to obstacle top from a known position at ground level
- **Combined GNSS + offset**: GNSS at obstacle base + tape/laser measurement of height above ground
- All indirect methods will achieve accuracy well within 3m vertical / 5m horizontal requirements

---

### PHASE 6: DATA PROCESSING AND QUALITY CONTROL (Week 7–10)

This phase addresses the TOR requirement for *"post-processing of data with unbroken audit trail."*

#### Step 6.1: Daily Field Data Processing
- Download all GNSS raw data daily from **Trimble 780 controllers** and receivers.
- Process all RTK observations in **Trimble Business Center (TBC)** to verify:
  - Fix quality (all observations must have fixed integer ambiguity solutions)
  - PDOP values (reject observations with PDOP > 3.0)
  - Base-rover baseline lengths within acceptable limits
  - Observation duration meets minimum requirements
- Flag and schedule re-observation of any points failing quality thresholds.

#### Step 6.2: Static GNSS Processing in TBC
- Import all static session RINEX files into TBC.
- Process baselines using L1/L2 ionosphere-free combinations.
- Resolve carrier-phase integer ambiguities.
- Review baseline processing reports for:
  - Ambiguity resolution success (require >99.5% confidence)
  - RMS of residuals
  - Ratio test statistics
- Perform network adjustment as described in Phase 3.

#### Step 6.3: High-Precision Processing with Bernese GNSS Software

**Why Bernese Software adds value to this project:**

Bernese GNSS Software v5.4 (developed by the Astronomical Institute, University of Bern) is the gold standard for scientific geodetic GNSS processing. We use it specifically for:

1. **IGS Station Connections**: Processing long baselines (>100km) to IGS/AFREF permanent stations where commercial software may have limitations. Bernese handles:
   - Precise orbit and clock products from IGS
   - Proper modelling of tropospheric gradients
   - Higher-order ionospheric corrections
   - Antenna phase centre modelling (absolute, from IGS ANTEX)
   - Earth tide and ocean loading corrections

2. **ITRF Realization**: Computing coordinates directly in ITRF2014 at observation epoch, then rigorously transforming to WGS-84 (which is aligned with ITRF at centimetre level). This ensures **traceability** to the global reference frame — a fundamental ICAO requirement for WGS-84 surveys.

3. **Audit Trail**: Bernese produces comprehensive processing logs and residual files, providing the **unbroken audit trail** required by the TOR from raw observation to final coordinate.

4. **Velocity Estimation**: Where repeat observations exist, Bernese can estimate site velocities due to tectonic motion (East Africa Rift), important for long-term coordinate maintenance.

**Processing workflow in Bernese:**
- Import RINEX observation files and IGS products
- Perform code-based clock synchronization
- Form double-difference observations
- Resolve ambiguities (wide-lane then narrow-lane)
- Estimate tropospheric parameters
- Final coordinate solution in ITRF2014
- Helmert transformation quality check
- Export coordinates and full processing statistics

#### Step 6.4: Geoid Undulation Computation
- Apply **EGM96 geoid model** to all ellipsoidal heights to derive orthometric heights.
- H (orthometric) = h (ellipsoidal) – N (EGM96 geoid undulation)
- Verify geoid model performance by comparing against any available levelled benchmarks.
- Report geoid undulation values at all key aerodrome positions (ARP, runway thresholds, control points).

#### Step 6.5: Obstacle Surface Analysis
- Import all obstacle positions into GIS software (QGIS/ArcGIS).
- Generate 3D Obstacle Limitation Surfaces from runway parameters.
- Perform 3D intersection analysis: identify all obstacles penetrating OLS.
- Compute penetration heights above each relevant surface.
- Classify obstacles by area (2a, 2b, 2c, 3) and surface penetrated.
- Generate obstacle database in tabular and GIS format.

#### Step 6.6: Magnetic Variation
- Obtain magnetic variation values from the current **World Magnetic Model (WMM)** or **IGRF (International Geomagnetic Reference Field)** for each airport reference point.
- Compute annual rate of change.
- Verify against latest published AIP Kenya values.
- If field measurements are required, perform compass observations at the ARP and runway thresholds.

#### Step 6.7: Quality Assurance / Quality Control

**QA/QC Framework:**

| Check | Method | Criteria |
|-------|--------|----------|
| Coordinate repeatability | Multi-session comparison | σ < 0.01m (control) |
| RTK observation quality | PDOP, fix status, baseline length | PDOP < 3, fixed, < 10km |
| Height verification | Independent check measurements | Differences < 0.05m |
| Obstacle position accuracy | Redundant measurements | Within 5m horizontal, 3m vertical |
| Feature completeness | Systematic checklist per airport | 100% TOR features captured |
| Metadata completeness | Database audit | All attributes populated |
| Datum verification | Comparison with KCAA previous data | Within expected tolerances |
| Processing audit trail | Log file review | Complete, unbroken chain |

- Designate the **QA/QC Expert** to perform independent checks on a minimum 10% random sample of all surveyed points by re-observation.
- All field books, raw data files, processing logs, and adjustment reports will be archived as part of the audit trail.

---

### PHASE 7: DELIVERABLE PRODUCTION (Week 9–12)

#### Step 7.1: Obstacle Database Compilation
- Compile the complete obstacle database for Areas 2a, 2b, 2c, and Area 3 for both airports.
- Format: Excel/CSV spreadsheet with all attributes per Step 5.3, plus GIS shapefile/GeoPackage.
- Include obstacle penetration analysis results.

#### Step 7.2: Aerodrome Charts Production
- Produce **Aerodrome Chart (ICAO)** for each airport showing:
  - Runway and taxiway layout with WGS-84 coordinates
  - Apron areas and parking stands
  - Navigational aids
  - Control tower
  - Key elevations (TDZ, threshold, ARP, highest point on runway)
  - Declared distances (TORA, TODA, ASDA, LDA)
  - Magnetic variation
- Format: A3 colour prints as specified, plus soft copy (PDF and CAD/GIS format).

#### Step 7.3: Obstacle Type A Chart
- Produce **Obstacle Type A Chart** for each airport per ICAO Annex 4 specifications:
  - Plan view showing OLS and obstacles
  - Profile views of approach/take-off climb surfaces with obstacles
- Format: A3 colour prints plus soft copy.

#### Step 7.4: Aerodrome Mapping Database
- Compile complete **Aerodrome Mapping Database** with:
  - Point features (navigational aids, lighting, spot elevations)
  - Line features (runway/taxiway edges, fencing, roads)
  - Polygon features (buildings, pavement areas, restricted zones)
- Format: GIS geodatabase (shapefile/GeoPackage), CAD (DWG/DXF), and KML for visualization.
- Metadata compliant with ISO 19115 geographic metadata standard.

#### Step 7.5: Longitudinal and Transverse Slope Diagrams
- Produce profile diagrams for all runways showing:
  - Longitudinal profile along centreline with elevations and computed slopes
  - Transverse cross-sections at key intervals with slopes
  - Comparison against ICAO Annex 14 design standards
  - Rate of slope change computations

#### Step 7.6: Control Point Documentation
- Produce a comprehensive control point register for each airport:
  - Point ID, description, photograph
  - WGS-84 coordinates (latitude, longitude in decimal degrees and DMS)
  - Ellipsoidal height, EGM96 geoid undulation, orthometric height
  - Accuracy (standard deviations from network adjustment)
  - Monument description and condition
  - Access sketch

---

### PHASE 8: REPORTING (Week 10–13)

#### Step 8.1: Draft Report (Month 2)
Submit Draft Report containing:
1. Introduction and project background
2. Reference documents and standards applied
3. Personnel deployed
4. Equipment used and calibration certificates
5. Methodology applied (control survey, detail survey, obstacle survey)
6. Control network diagram, coordinates, and adjustment statistics
7. Aerodrome survey results (all features with coordinates and elevations)
8. Obstacle survey results (complete database, penetration analysis)
9. Obstacle Limitation Surface analysis
10. Longitudinal and transverse slope analysis
11. Magnetic variation data
12. Geoid undulation values
13. Aerodrome Mapping Database description
14. QA/QC results and accuracy statement
15. Conclusions and recommendations
16. Appendices: raw data, processing logs, photographs, certificates

#### Step 8.2: Review and Revision
- Present draft report to KCAA for review.
- Incorporate KCAA comments and feedback.
- Perform any additional field verification if required by KCAA.

#### Step 8.3: Final Report (Month 3)
Submit Final Report as specified:
- **2 hard copies** (bound, printed) per airport
- **Soft copies** on portable hard disk (USB) including:
  - Full report in PDF format
  - All GIS data (shapefiles, geodatabase)
  - CAD drawings (DWG/DXF)
  - Obstacle database (Excel/CSV)
  - Raw survey data (RINEX files)
  - Processing reports
  - Photographs
- **Aerodrome Charts**: 2 hard copies (A3 colour) per airport + soft copies
- **Obstacle Type A Charts**: 2 hard copies (A3 colour) per airport + soft copies
- **Aerodrome Mapping Data**: Soft copy on portable hard disk

---

## 4. EQUIPMENT CAPABILITIES AND ACCURACY BENEFITS

### 4.1 Trimble R12i GNSS Receiver (2 Units)

The Trimble R12i is a flagship multi-constellation GNSS receiver that provides exceptional accuracy for this project:

- **672 channels** tracking GPS, GLONASS, Galileo, BeiDou, NavIC, QZSS, and SBAS simultaneously
- **Trimble ProPoint GNSS engine**: Advanced positioning algorithm that uses raw measurements from all constellations simultaneously, providing faster convergence and more reliable solutions in challenging environments (airport reflective surfaces, buildings, aircraft)
- **Inertial Measurement Unit (IMU)**: Enables tilt compensation up to 60°, allowing the surveyor to measure points without levelling the pole — critical for obstacle top measurements and measurements near structures where the pole cannot be held vertically
- **Static accuracy**: Horizontal 3mm + 0.1ppm, Vertical 3.5mm + 0.4ppm
- **RTK accuracy**: Horizontal 8mm + 1ppm, Vertical 15mm + 1ppm

**Project benefit**: The R12i will serve as the primary instrument for geodetic control establishment and as base stations for RTK operations. Its superior tracking capability ensures reliable observations even in the electromagnetically noisy airport environment. The IMU tilt compensation is particularly valuable for obstacle surveys where the antenna must be placed on irregular surfaces.

### 4.2 Trimble R6-3 GNSS Receiver (2 Units)

- Reliable dual-frequency (L1/L2) receiver
- **Static accuracy**: Horizontal 3mm + 0.5ppm, Vertical 5mm + 0.5ppm
- **RTK accuracy**: Horizontal 8mm + 1ppm, Vertical 15mm + 1ppm
- Proven track record in aeronautical survey applications

**Project benefit**: Ideal for control densification and navigational aid surveys where high reliability and consistent performance are required. Serves as a dependable secondary control survey instrument.

### 4.3 Trimble R4s GNSS Receiver (2 Units)

- Dual-frequency GNSS receiver optimized for high-productivity surveys
- **RTK accuracy**: Horizontal 8mm + 1ppm, Vertical 15mm + 1ppm
- Compact, lightweight design for efficient field operations

**Project benefit**: Primary workhorse for high-volume detail surveys — aerodrome features, obstacle positions, mapping data. Its compact design allows rapid mobilization across the aerodrome.

### 4.4 Trimble 780 Controllers (2 Units)

- Large touchscreen display for field data collection
- Pre-loaded feature code libraries for aerodrome mapping
- Real-time QC indicators (PDOP, fix status, accuracy estimates)
- Direct interface with all Trimble receivers

**Project benefit**: Enables real-time quality control in the field, reducing re-work. Feature coding ensures systematic and complete data collection aligned with the ICAO AMDB feature catalogue.

### 4.5 Trimble Business Center (TBC)

- Industry-standard GNSS post-processing software
- Supports all Trimble receiver data formats
- Baseline processing with L1/L2 combinations
- Rigorous least-squares network adjustment
- Coordinate transformation and datum management
- Report generation with full statistical output
- CAD and GIS export capabilities

**Project benefit**: Provides the complete post-processing chain from raw data to final coordinates with full statistical rigour. Its network adjustment module ensures all control coordinates meet the required accuracy with documented uncertainty. The audit trail from raw observation through processing to final coordinate is fully maintained within TBC.

### 4.6 Accuracy Summary vs. ICAO Requirements

| Parameter | ICAO Requirement | Our Capability | Margin |
|-----------|-----------------|----------------|--------|
| Horizontal accuracy | 5m | 0.01m (control), 0.02m (RTK detail) | 250x–500x better |
| Vertical accuracy | 3m | 0.015m (control), 0.025m (RTK detail) | 120x–200x better |
| Resolution | 0.1m | 0.001m | 100x better |
| Confidence level | 90% | 95% standard, expandable to 99% | Exceeds |
| Integrity | Essential | Full audit trail, redundant observations, QA/QC | Met |

---

## 5. OPINION ON BERNESE SOFTWARE AND IGS STATION CONNECTIVITY

### 5.1 Recommendation: YES — Include Bernese Software

**We strongly recommend mentioning and using Bernese GNSS Software in this bid.** Here is why:

1. **Scientific credibility**: Bernese is used by national geodetic agencies, IGS analysis centres, and academic institutions worldwide. Mentioning it demonstrates that Ecospace Services Ltd operates at the highest level of geodetic practice — this differentiates us from competitors who rely solely on commercial software.

2. **IGS/AFREF connectivity**: The TOR requires WGS-84 coordinates traceable to the global reference frame. Bernese is purpose-built for processing long baselines to IGS permanent stations, handling all the complex corrections (precise orbits, tropospheric modelling, ocean loading, etc.) that commercial software may simplify or omit.

3. **Audit trail**: Bernese produces detailed processing logs at every step — exactly what the "unbroken audit trail" requirement demands.

4. **ITRF realization**: Bernese computes coordinates directly in ITRF, which is the practical realization of WGS-84. This is technically more rigorous than relying on broadcast ephemerides in commercial software.

5. **Technical evaluation advantage**: Under the "Approach & Methodology" scoring criterion (15 marks), demonstrating a dual-software approach (Bernese for geodetic control + TBC for production surveys) shows methodological sophistication and will likely score higher than a single-software approach.

### 5.2 How to Position Bernese in the Bid

Present the **dual-software approach** as follows:

- **Bernese GNSS Software v5.4**: Used for high-precision geodetic control processing — connecting primary airport control to IGS/AFREF permanent reference stations, computing coordinates in ITRF2014/WGS-84, establishing the absolute accuracy framework.
- **Trimble Business Center**: Used for production survey processing — control densification, detail survey post-processing, network adjustment, report generation, and deliverable production.

This two-tier approach ensures:
- The geodetic foundation is established with scientific rigour (Bernese)
- Production efficiency and compatibility with Trimble hardware is maintained (TBC)
- Full audit trail from IGS permanent stations through to final deliverable coordinates

### 5.3 Relevant IGS/AFREF Stations for This Project

| Station | Location | Distance to Eldoret | Distance to Malindi |
|---------|----------|-------------------|-------------------|
| RCMN | Nairobi, Kenya | ~260km | ~480km |
| MAL2 | Malindi, Kenya | ~550km | ~10km |
| MBAR | Mbarara, Uganda | ~350km | ~900km |
| ADIS | Addis Ababa, Ethiopia | ~750km | ~1200km |

For **Malindi Airport**, the proximity of the MAL2 IGS station (~10km) is an exceptional advantage — providing a very short baseline to a permanent reference station, virtually guaranteeing sub-centimetre geodetic accuracy.

For **Eldoret Airport**, the RCMN station in Nairobi (~260km) and MBAR in Uganda (~350km) provide a good geometry for long-baseline processing in Bernese.

---

## 6. WORK PLAN AND TIMELINE

| Week | Activity | Location | Key Equipment |
|------|----------|----------|---------------|
| 1 | Kick-off meeting, desk study | Nairobi/Office | — |
| 2 | Inception report, mobilization | Office | — |
| 2–3 | Equipment calibration, reconnaissance | Eldoret | All GNSS |
| 3–4 | Geodetic control survey | Eldoret | Trimble R12i (×2) |
| 4–6 | Aerodrome & facility survey | Eldoret | R6-3, R4s, 780 |
| 5–7 | Obstacle survey Areas 2a/2b/2c/3 | Eldoret | R4s, R6-3, rangefinder |
| 6 | Mobilize to Malindi | Transit | — |
| 6–7 | Geodetic control survey | Malindi | Trimble R12i (×2) |
| 7–9 | Aerodrome & facility survey | Malindi | R6-3, R4s, 780 |
| 8–9 | Obstacle survey Areas 2a/2b/2c/3 | Malindi | R4s, R6-3, rangefinder |
| 7–10 | Data processing (ongoing) | Office | TBC, Bernese |
| 8 | Draft report submission | Office | — |
| 9–11 | Chart and database production | Office | TBC, GIS software |
| 11 | KCAA review period | — | — |
| 12 | Incorporate comments | Office | — |
| 13 | Final report submission | Nairobi | — |

---

## 7. ORGANIZATION AND STAFFING

### 7.1 Project Organization Structure

```
                        KCAA Project Manager
                              |
                    Ecospace Team Leader
                    /         |         \
          Project Manager   QA/QC Expert  Admin/Logistics
              |                |
    +---------+---------+     |
    |         |         |     |
Senior    GIS/CAD    Carto-   |
Surveyor  Expert    grapher   |
    |                         |
Field Survey Teams (2)        |
(Survey assistants,           |
chainmen, drivers)      Independent QC checks
```

### 7.2 Key Personnel Roles

| Position | Key Responsibilities |
|----------|---------------------|
| **Team Leader** | Overall technical leadership, client liaison, final quality sign-off, ICAO standards compliance |
| **Project Manager** | Day-to-day project management, scheduling, resource allocation, progress reporting, HSE management |
| **Senior Surveyor** | Field survey operations, control network design, GNSS observation planning, field QC |
| **GIS/CAD Expert** | Aerodrome mapping database, GIS analysis, obstacle surface modelling, digital deliverables |
| **Cartographer** | Aerodrome chart production, Obstacle Type A chart production, graphic design and layout |
| **QA/QC Expert** | Independent quality checks, audit trail verification, accuracy assessment, statistical analysis |

### 7.3 Field Team Deployment

**Two simultaneous field teams** can be deployed (given paired equipment) or teams work sequentially airport-by-airport:

- **Team A (Control)**: 1 Senior Surveyor + 2 assistants + Trimble R12i (×2)
- **Team B (Detail)**: 1 Surveyor + 2 assistants + Trimble R6-3 (×1) + Trimble R4s (×2) + Trimble 780 (×2)

---

## 8. RISK MANAGEMENT

| Risk | Likelihood | Impact | Mitigation |
|------|-----------|--------|------------|
| Airside access delays | Medium | High | Early coordination with airport operations; flexible scheduling |
| Adverse weather | Medium | Medium | Plan buffer days; GNSS not weather-dependent for positioning |
| Equipment failure | Low | High | Paired equipment provides 100% redundancy; TBC-certified service centre backup |
| Monument destruction | Medium | Medium | Establish multiple redundant control points; photograph and document all |
| Data loss | Low | High | Daily backup to multiple media; cloud backup where connectivity allows |
| Scope expansion | Medium | Medium | Clear TOR documentation; variation order procedures in contract |

---

## 9. HEALTH, SAFETY AND ENVIRONMENT

- All field staff will hold valid airside safety induction certificates.
- High-visibility clothing mandatory in all airside operations.
- Two-way radio communication with ATC/airport operations at all times.
- Vehicle operations on runways/taxiways only with ATC clearance and follow-me vehicle escort.
- No survey operations during active aircraft movements on the surveyed surface.
- Risk assessments completed before each field activity.
- First aid kits carried by all field teams.
- Environmental: No disturbance to airport drainage or vegetation; all waste removed.

---

*Prepared by Ecospace Services Ltd*
*Survey, GIS & Geospatial Solutions*
