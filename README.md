# DC Pump Aggregates Database for Autonomous Photovoltaic Water-Supply Systems
[![DOI](https://zenodo.org/badge/1334002775.svg)](https://doi.org/10.5281/zenodo.21932530) 
A curated, source-traceable database of pump aggregate configurations for autonomous photovoltaic water-supply systems.

> **Release status:** Inventory-grade. This release is suitable for equipment inventory, classification, source tracing, and database-architecture studies. It is not yet a fully verified hydraulic dataset for all 300 configurations.

## Overview

The database was developed to organize technical information on pump aggregates that may be used in autonomous photovoltaic water-supply systems. A pump aggregate is treated as an operating configuration consisting of a pump, motor, and associated controller or drive.

The database retains direct-DC pumps, controller-fed DC systems, integrated AC/DC products, and photovoltaic variable-frequency-drive systems as separate electrical architectures. Missing manufacturer values are left blank rather than estimated.

The current frozen release contains 300 configurations collected primarily from official manufacturer catalogs, product pages, brochures, datasheets, project documents, and selection tools.

## Dataset summary

| Item | Value |
|---|---:|
| Pump aggregate configurations | 300 |
| Manufacturers | 9 |
| Household configurations | 100 |
| Farm/SME configurations | 100 |
| Industrial configurations | 100 |
| Electrical controller and drive records | 71 |
| Registered source records | 39 |
| Pump records with numerical Q–H data | 22 |
| Numerical Q–H point rows | 217 |
| Curves passing internal QA | 10 |
| Curves requiring redigitization | 12 |
| Configurations awaiting numerical curve extraction | 278 |
| Experiment-ready configurations | 0 |

## Application segments

| Segment | Pump ID range | Records |
|---|---|---:|
| Household | `HH001–HH100` | 100 |
| Farm/SME | `FM001–FM100` | 100 |
| Industrial | `IN001–IN100` | 100 |

The equal segment sizes were imposed during dataset construction to support comparison across application scales. They should not be interpreted as manufacturer market shares.

## Manufacturer coverage

| Manufacturer | Records |
|---|---:|
| Wassermann | 108 |
| Franklin Electric | 48 |
| CHIMP | 25 |
| ZRI Solar | 25 |
| COM PUMP | 25 |
| Wilo | 25 |
| LORENTZ | 24 |
| Grundfos | 14 |
| SAER | 6 |
| **Total** | **300** |

Manufacturer representation reflects the availability and level of detail of official product information. It does not indicate relative manufacturer importance or market position.

## Electrical supply architectures

| Supply architecture | Records |
|---|---:|
| Direct DC | 15 |
| DC controller | 195 |
| Integrated AC/DC | 35 |
| PV–VFD–AC | 55 |
| **Total** | **300** |

The explicit architecture field prevents direct-DC pumps, controller-fed motors, integrated products, and photovoltaic-driven AC systems from being treated as technically identical configurations.

## Frozen workbook

The principal data file is:

[`DC_Pump_Master_Dataset_300_FROZEN_QA_v1.xlsx`](./DC_Pump_Master_Dataset_300_FROZEN_QA_v1.xlsx)

The workbook contains twelve worksheets:

| Worksheet | Purpose |
|---|---|
| `README` | Dataset purpose, collection rules, freeze status, and summary |
| `Pump_Aggregates` | Main table containing 300 pump aggregate configurations |
| `Hydraulic_Curves` | Numerical flow–head points and curve-level metadata |
| `Electrical_Drives` | Controller, integrated-drive, and PV-VFD information |
| `Sources` | Source register and official document or webpage links |
| `Manufacturer_Roadmap` | Manufacturer and product-family collection plan |
| `Data_Dictionary` | Field definitions, types, units, and collection rules |
| `Validation_Lists` | Controlled categories used for data validation |
| `Dashboard` | Dataset population and QA indicators |
| `QH_Verification` | Pump-level numerical-curve verification status |
| `QA_Report` | Structural and hydraulic quality-assurance results |
| `Freeze_Log` | Dataset version, freeze scope, restrictions, and corrections |

## Core data model

Four linked worksheets form the core data structure:

- `Pump_Aggregates` is the central configuration table.
- `Electrical_Drives` contains controller and drive information linked through `Controller_Drive_ID`.
- `Hydraulic_Curves` contains numerical Q–H points linked through `QH_Curve_ID` and `Pump_ID`.
- `Sources` records the evidence associated with pump, controller, and curve data through `Source_ID`.

The database is distributed as a structured Excel workbook rather than as a standalone database-management system.

## Quality-assurance status

Structural checks confirmed:

- 300 unique `Pump_ID` values;
- 100 records in each application segment;
- valid source references for all pump records;
- valid nonblank controller foreign keys;
- controlled identifiers, units, and categories;
- explicit missing values rather than inferred technical parameters.

Hydraulic verification remains incomplete:

- numerical Q–H points are available for 22 pump configurations;
- the stored curves contain 217 flow–head point rows;
- 10 curves passed the current internal endpoint and monotonicity checks;
- 12 curves require redigitization;
- 278 configurations still require numerical curve extraction;
- no pump configuration is currently marked as finally `Verified`.

The label `Internal QA passed` should not be interpreted as independent experimental validation.

## Intended use

The current release may be used for:

- pump and controller inventory analysis;
- application-segment comparison;
- electrical supply-architecture analysis;
- manufacturer and product-family mapping;
- source and parameter traceability;
- database and software-architecture development;
- preparation of candidate records for later pump-selection studies.

## Limitations

The current release should not be used to claim verified hydraulic interpolation or optimization across all 300 configurations.

Important limitations include:

- uneven manufacturer representation;
- incomplete model-level flow and head information;
- limited industrial flow and head coverage;
- incomplete numerical Q–H curve coverage;
- catalog values obtained under potentially different operating and test conditions;
- absence of a final `Verified` experiment-ready subset.

Users must check technical parameters against the cited original manufacturer evidence before engineering design, equipment procurement, or operational use.

## Version and integrity

- Workbook version: `QA-FROZEN-v1`
- Repository release version: `v1.0.0-inventory`
- Population freeze date: `2026-08-13`
- Post-freeze dashboard correction: `2026-08-14`
- Population status: `FROZEN`
- Experiment release status: `HOLD`

SHA-256 checksum for the released workbook:

`127ac72091b16ee24305595b46a95f9f2e9c061d9ca7d265ef79aadcdb8889d5`

The checksum is also provided in [`SHA256SUMS.txt`](./SHA256SUMS.txt).

## Citation

Citation metadata are provided in [`CITATION.cff`](./CITATION.cff). GitHub users may select **Cite this repository** to obtain APA or BibTeX metadata.

## Citation

Eshkulov, M. O., Khamdamov, R. Kh., and Mustafakulov, A. (2026). *DC Pump Aggregates Database for Autonomous Photovoltaic Water-Supply Systems* (Version 1.0.0-inventory) [Data set]. Zenodo. https://doi.org/10.5281/zenodo.21932531

- Specific version DOI: https://doi.org/10.5281/zenodo.21932531
- Concept DOI for all versions: https://doi.org/10.5281/zenodo.21932530

## License

The authors' original database compilation, normalized records, documentation, and quality-assurance metadata are released under the Creative Commons Attribution 4.0 International License.

See [`LICENSE-DATA.md`](./LICENSE-DATA.md) for the complete scope, attribution requirements, third-party information, and disclaimer.

Manufacturer names, trademarks, product specifications, and linked source materials remain the property of their respective rights holders.

## Authors

- Mukhriddin Eshkulov — ORCID: [0000-0001-6315-6561](https://orcid.org/0000-0001-6315-6561)
- Rustam Kh. Khamdamov — ORCID: [0000-0003-3796-4631](https://orcid.org/0000-0003-3796-4631)

## Associated research

The database supports the manuscript:

**Development of a Comprehensive Database of DC Pump Aggregates for Autonomous Photovoltaic Water Supply Systems**

The article is currently under preparation. Publication metadata will be added after acceptance.
