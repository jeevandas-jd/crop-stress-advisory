# AI-Driven Automated Crop Type, Moisture Stress Detection and Irrigation Advisory Across Growth Stages Using Moderate Resolution Spectral Signatures (Optical & Microwave Satellite Data)

## Problem statement

Accurate and timely identification of crop types, stage-wise moisture stress, and irrigation need is essential for precision agriculture, drought preparedness, canal command planning, and efficient water management. Traditional field-based monitoring is slow, costly, and difficult to scale across large agricultural regions, especially during cloud-prone crop seasons when optical-only observation becomes unreliable.[1][2][3]

Satellite remote sensing offers a scalable alternative, but operational systems still face three connected challenges: identifying crop type for the current season, detecting moisture stress in a phenology-aware manner, and translating crop water deficit into practical irrigation advisories. Multi-temporal optical data such as Sentinel-2 can capture vegetation vigour and water-related spectral response, while Sentinel-1 SAR supports all-weather monitoring and adds structural and moisture-sensitive information that improves mapping robustness.[4][5][6]

This project addresses these challenges by proposing an AI-driven automated workflow that fuses optical and microwave satellite observations with simple ancillary weather inputs to generate crop type maps, stage-wise moisture stress classes, and irrigation advisory outputs for a pilot command area. The proposed system is designed as a submission-ready hackathon prototype that is technically credible, scalable, and operationally relevant.[1][2][4]

## Abstract

This project proposes a satellite-based AI workflow for automated crop type classification, moisture stress detection across crop growth stages, and irrigation advisory generation using moderate-resolution optical and microwave remote sensing data. The system combines multi-temporal Sentinel-2 spectral indices such as NDVI and NDWI with Sentinel-1 SAR backscatter features such as VV and VH to capture complementary information on vegetation condition, crop structure, and moisture dynamics under both clear and cloudy conditions.[2][5][6]

The implementation is designed around a pilot agricultural command area. Satellite time-series data are preprocessed and converted into phenology-relevant features, which are then used in a supervised machine learning pipeline, with Random Forest as the baseline model for crop type mapping. Moisture stress is estimated using temporal variation in vegetation and water-sensitive indicators, optionally supported by rainfall and evapotranspiration inputs, and then translated into practical advisory classes such as no irrigation, monitor, irrigate soon, and priority irrigation.[4][7][6]

The expected outcome is a dashboard-ready prototype that produces crop classification maps, stress layers, and irrigation advisory outputs that are interpretable for agricultural planning and scalable to wider regions. The approach is aligned with the growing use of Google Earth Engine and multi-source satellite data for operational agricultural monitoring and water management.[1][2][7]

## Expected questions

### 1. What is the core problem this project is solving?

The project solves the connected problem of identifying crop type, detecting moisture stress, and converting that stress into irrigation advice from satellite observations. This is important because water management decisions are more useful when crop identity, crop stage, and crop condition are interpreted together rather than separately.[2][6]

### 2. Why use both optical and microwave satellite data?

Optical data captures vegetation greenness and water-related spectral behaviour through indices such as NDVI and NDWI, which are useful for tracking crop growth and stress. Microwave SAR data from Sentinel-1 remains useful under cloudy conditions and contributes additional sensitivity to crop structure and moisture, making the combined system more reliable than optical-only monitoring.[5][6]

### 3. Why is this project relevant for irrigation management?

Stress detection alone is not enough for farm decision-making. By linking spectral and SAR-derived stress signals with simple irrigation classes, the system translates remote sensing outputs into action-oriented recommendations that support water allocation and irrigation scheduling.[2][8]

### 4. Why choose Random Forest as the baseline model?

Random Forest is a strong baseline for crop classification because it handles tabular remote sensing features well, works effectively with multi-temporal inputs, and is widely used in Earth Engine-based agricultural classification workflows. It is also easier to train, interpret, and demonstrate in a hackathon setting than more complex deep learning models.[4][7]

### 5. How is moisture stress detected in this project?

Moisture stress is estimated by analyzing temporal behaviour of vegetation and water-related indicators such as NDVI and NDWI, optionally supported by SAR backscatter behaviour and simple weather inputs. A drop in moisture-sensitive indicators relative to expected crop-stage conditions is interpreted as low, moderate, or high stress.[2][8][6]

### 6. Why is phenology-awareness important?

The same spectral value can mean different things at different crop stages, so stress must be interpreted in relation to crop growth phase. Phenology-aware features improve classification and make stress assessment more meaningful because crop condition is compared against expected stage-specific behaviour.[4][6]

### 7. What are the main input datasets?

The core inputs are Sentinel-2 optical imagery, Sentinel-1 SAR imagery, pilot area boundaries, crop label samples, and simple weather or evapotranspiration support data. This combination is sufficient for building a practical pilot system for crop mapping and irrigation advisory generation.[1][4][6]

### 8. What outputs will the system produce?

The prototype will generate a crop type map, a moisture stress map, a growth-stage-aware interpretation layer, and an irrigation advisory output. These results can be shown as maps, summary tables, and field-level or pixel-level dashboard cards.[1][2]

### 9. How will the project be validated?

Crop classification can be validated using labeled crop samples and standard accuracy measures, while stress and irrigation layers can be checked for logical agreement with index trends, rainfall context, and available field references. Even in a hackathon prototype, validation is important to show that outputs are not just visually attractive but analytically credible.[1][4]

### 10. Why is this project suitable for a hackathon submission?

The project is suitable because it can be scoped to one pilot area, built with openly accessible satellite datasets and cloud platforms, and demonstrated through clear visual outputs. At the same time, it addresses a real agricultural operations problem with scalability potential beyond the prototype stage.[1][7]

## Research questions and answers

| Research question | Short answer |
|---|---|
| Can multi-temporal optical and SAR data improve crop type mapping? | Yes. Multi-temporal Sentinel-1 and Sentinel-2 fusion provides complementary information and improves robustness for crop classification workflows.[4][5] |
| Can satellite indices capture crop moisture stress in near real time? | Yes. NDVI, NDWI, thermal or moisture-related indicators, and SAR behaviour can reveal vegetation and water stress patterns suitable for timely interpretation.[2][8][6] |
| Can stage-wise interpretation improve advisory quality? | Yes. Growth-stage-aware interpretation helps distinguish normal seasonal variation from genuine stress, making advisory outputs more meaningful.[4][6] |
| Can a hackathon prototype generate practical irrigation advice? | Yes. Even a simplified rule-based advisory layer can convert stress estimates into usable irrigation classes for pilot demonstration.[2][1] |
| Is Random Forest enough for the first version? | Yes. Random Forest is a credible and practical baseline for the first submission-ready prototype.[4][7] |

## Implementation phases

### Phase 1: Define pilot scope

Select one pilot command area, identify the target crops, decide the season of interest, and finalize the outputs required for submission. This phase reduces the problem into a manageable demonstration unit and establishes the boundaries of the prototype.[1][4]

### Phase 2: Collect input datasets

Gather Sentinel-2 optical imagery, Sentinel-1 SAR imagery, crop label samples, pilot boundary layers, and rainfall or evapotranspiration support data. These form the minimum data foundation required for crop mapping, stress detection, and irrigation advisory generation.[1][6]

### Phase 3: Preprocess imagery

Filter imagery by time and region, remove cloud-affected optical scenes, prepare temporal composites, and align the optical and SAR data streams. Preprocessing is essential because raw imagery must be converted into stable analysis-ready inputs before modeling.[1][7]

### Phase 4: Extract features

Generate vegetation and moisture-related spectral features such as NDVI and NDWI from Sentinel-2 and extract SAR features such as VV, VH, and ratio-based metrics from Sentinel-1. Aggregate these into monthly or stage-wise features that represent crop behaviour over time.[2][5][6]

### Phase 5: Build crop classification model

Use labeled crop samples to train a supervised machine learning model, with Random Forest as the first baseline. Apply the trained model to the pilot area to produce the crop type map and validate the output using available ground labels.[4][7]

### Phase 6: Detect moisture stress

Analyze temporal deviations in NDVI, NDWI, and SAR response to identify crop moisture stress classes. Interpret these values with respect to crop stage so that stress estimates are phenology-aware rather than based on a single generic threshold.[2][8][6]

### Phase 7: Generate irrigation advisory

Convert moisture stress outputs into irrigation recommendation classes using simplified rules supported by rainfall or evapotranspiration context. The advisory layer is designed to turn remote sensing analysis into a decision-support output rather than just another map.[2][6]

### Phase 8: Visualize and package outputs

Prepare crop maps, stress maps, irrigation advisory layers, summary tables, and short time-series visualizations in a dashboard-ready or presentation-ready format. This phase ensures that the technical output can be communicated clearly in the final hackathon evaluation.[1][2]

### Phase 9: Validate and prepare submission

Review model outputs, verify logical consistency, refine the explanation of the methodology, and package the final materials for submission. This includes documentation, architecture explanation, map screenshots, and concise speaking points for presentation.[1][4]

