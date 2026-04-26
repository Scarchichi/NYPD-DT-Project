# NYPD Domain Awareness System Supplement

## Purpose
This supplement provides industry context, technology details, governance frameworks, and definitions needed to support instructor-led discussion of the NYPD DAS case.

## DAS Overview
The Domain Awareness System is a sensor fusion platform that aggregates multiple data streams for use by the NYPD. It connects cameras, license plate readers, radiation detectors, and other public safety sensors into a unified interface. The system was developed in partnership with Microsoft and was designed to support both counterterrorism and routine crime analysis.

### Core components
- **CCTV network**: Approximately 9,000 cameras citywide, including NYPD-owned and privately owned feeds.
- **Automated License Plate Readers (LPRs)**: Hundreds of fixed LPRs on bridges, tunnels, and major thoroughfares, recording plate sightings that can be searched against alert lists.
- **Sensor array**: Radiation detectors, chemical sensors, gunshot detection systems, and other environmental sensors integrated for threat detection.
- **Mobile access**: Tablets and handheld devices that allow officers to query DAS data from the field.
- **Patternizr**: An analytics tool that identifies similar unsolved crimes and suggests links between incidents based on historical police data.

## Technology and operational design
The DAS platform is built to deliver real-time situational awareness. Key design features include:
- centralized data ingestion and indexing
- geospatial search across cameras, plates, and sensor feeds
- real-time alerting for events and matches
- mobile query capability for officers in the field
- integration with existing NYPD systems such as AVL and crime reporting databases

## Data governance and privacy issues
The NYPD's published Impact and Use Policy establishes the department's own rules for DAS. Important governance elements include:
- access control requirements for authorized users
- limits on data sharing and external disclosure
- retention policies for surveillance footage and plate reads
- provisions for supervision of analytic use

Critics argue the policy does not fully address:
- independent oversight and auditability
- algorithmic bias in Patternizr and camera search
- community notice and consent
- the risk of mission creep from counterterrorism to everyday policing

## Historical context
The NYPD's modernization efforts began in the early 2000s, with Commissioner Kelly moving the department from officer-managed IT to professional technology leadership. The Lower Manhattan Security Initiative served as an early prototype for DAS. The 2010 Times Square bombing attempt accelerated political support for expanding surveillance capabilities.

## Glossary
- **DAS**: Domain Awareness System
- **LPR**: License Plate Reader
- **AVL**: Automatic Vehicle Locator
- **Patternizr**: NYPD crime pattern analytics tool
- **Counterterrorism Bureau**: NYPD bureau responsible for terrorism prevention and response

## Discussion aids
- Exhibit 1: Timeline of DAS development
- Exhibit 2: NYPD DAS data sources and sensors
- Exhibit 3: Summary of NYPD Impact and Use Policy
- Exhibit 4: List of stakeholder groups (police leadership, federal funders, civil liberties organizations, community members)

## Use cases
- real-time search for suspicious vehicles following a shooting
- retrospective pattern analysis for a series of burglaries
- counterterrorism monitoring during large public events
- mobile officer access to surveillance feeds in the field

## Risks and tradeoffs
- improved operational effectiveness vs. expanded surveillance scope
- centralized intelligence capabilities vs. decentralized civil liberties protections
- rapid investigative power vs. accountability and transparency
