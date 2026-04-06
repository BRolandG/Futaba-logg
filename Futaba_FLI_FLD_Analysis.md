# Technical Analysis of Futaba FLI/FLD Format

## Introduction
This document serves as a comprehensive technical analysis of the Futaba FLI/FLD file format used for storing telemetry data. The analysis is based on reverse engineering findings and aims to provide insights for developers and enthusiasts working with Futaba telemetry systems.

## Overview of the Futaba FLI/FLD Format
The Futaba FLI (Flight Log Information) and FLD (Flight Log Data) formats are binary data formats used by Futaba telemetry systems to log flight data such as telemetry values, flight parameters, and other relevant information.

### Structure of FLI/FLD Files
- **Header**: Contains metadata about the log, including version, timestamp, and configuration settings.
- **Data Records**: These records store telemetry data in a structured format. Each record is associated with a specific timestamp and contains various telemetry parameters.
- **Footer**: Includes checksums or other validation data to ensure integrity.

### Analysis Findings
#### Header Structure
- **Byte 0-3**: Signature (e.g., "FLI\0" or "FLD\0")
- **Byte 4-7**: Version Number (e.g., 1, 2, etc.)
- **Byte 8-11**: Timestamp (UTC)
- **Byte 12-15**: Configuration Flags (e.g., settings enabling/disabling features)

#### Data Records
Each data record typically comprises:
- **Timestamp**: 4 bytes (air time)
- **Telemetry Data**: Variable length, often structured as a series of key-value pairs or fixed-size fields.
  - **Example Parameters**: Altitude, Speed, GPS coordinates, Battery voltage, etc.

#### Footer Structure
- **Checksum**: Ensures the integrity of the log data.

### Reverse Engineering Methodology
1. **File Inspection**: Examination of raw FLI/FLD files using hex editors.
2. **Data Parsing**: Writing scripts to parse the binary format and visualize the data.
3. **Comparative Analysis**: Comparing logged data against known telemetry outputs to validate findings.

### Practical Applications
- **Data Analysis**: Understanding flight performance and making informed decisions.
- **Custom Applications**: Developers can create software that reads and processes FLI/FLD files for analytics.

## Future Work
- **Enhanced Documentation**: Continue to refine and expand documentation as new findings emerge.
- **Community Contributions**: Encourage community input for refining the format's understanding and functionality.

## Conclusion
The Futaba FLI/FLD file format offers a rich set of telemetry data suitable for detailed flight analysis. The findings from this analysis provide a foundational understanding for developers looking to interface with Futaba's telemetry systems effectively.

## References
- Futaba Telemetry System Documentation
- Reverse Engineering Tools and Techniques
- Community Forums Discussions on Futaba Telemetry