# Futaba FLI/FLD Format Specification Document

## Table of Contents
1. [Overview](#overview)
2. [Binary Structure](#binary-structure)
3. [Byte Layout](#byte-layout)
4. [Data Conversions](#data-conversions)
5. [CSV Output Format](#csv-output-format)
6. [Sensor Port Mapping](#sensor-port-mapping)
7. [Parsing Algorithm](#parsing-algorithm)

## Overview
The Futaba FLI/FLD format is used for telemetry data in various Futaba equipment. This document aims to provide a comprehensive technical reference for developers and users of this format.

## Binary Structure
The binary structure of the Futaba FLI/FLD format is composed of a series of fields, each with a specified size and type. The primary elements include:
- Packet Type (1 byte)
- Sensor Data (variable length)
- Checksum (1 byte)

## Byte Layout
The byte layout for each packet is as follows:
```
| Byte Position | Field        | Size   |
|---------------|--------------|--------|
| 0             | Packet Type  | 1 byte |
| 1             | Sensor Data   | N bytes|
| N+1          | Checksum     | 1 byte |
```

## Data Conversions
Data should be converted as follows:
- Sensor readings must be converted from raw binary to human-readable formats based on sensor type (e.g., volts, temperature).

## CSV Output Format
When exporting to CSV, the structure should be:
```
Packet Type, Sensor ID, Sensor Value, Timestamp
```
Example:
```
1, 101, 25.5, 2026-04-06 13:54:10
```

## Sensor Port Mapping
Sensors are mapped to ports as follows:
```
| Sensor ID | Port  |
|-----------|-------|
| 101       | A1    |
| 102       | A2    |
| 201       | B1    |
```

## Parsing Algorithm
1. Read the binary data stream.
2. Identify the packet type.
3. Extract the sensor data based on the packet type.
4. Validate the checksum.
5. Convert to human-readable format and prepare for output.

## Conclusion
This document serves as a complete reference for working with the Futaba FLI/FLD format. Proper understanding of the specifications is essential for accurate telemetry data handling.