# Gravimeter with GPS Calibration

## Project Description

This project implements a phyphox experiment to measure gravitational acceleration using the smartphone's accelerometer with automatic GPS-based calibration.

## Functionality

### Basic Principle
The experiment uses:
- **Accelerometer** to measure acceleration along the Z-axis
- **GPS** to obtain latitude and altitude
- **Automatic calibration** to correct systematic errors of the accelerometer

### Calibration Formula
The theoretical value of g is calculated using the formula:
```
g = 9.7803184 × (1 + 0.0053024 × sin²(lat) - 0.0000059 × sin²(lat)) - 0.000003086 × altitude
```

### Calibration Process
1. The system calculates the theoretical value of g based on GPS position
2. Measures the average of raw accelerometer data
3. Calculates the correction factor: `bias = g_theoretical / raw_average`
4. Applies the corrective factor: `g_calibrated = g_raw × bias`

## Usage Instructions

### Requirements
- Smartphone with phyphox app installed
- Functional accelerometer sensor
- Active GPS connection

### Procedure
1. **Positioning**: Hold the device still on a flat surface
2. **GPS Wait**: Wait for GPS to get a good fix (stable GPS signal)
3. **Calibration**: Press the "Calibrate now" button when the device is still
4. **Measurement**: Observe the calibrated data in the interface

### User Interface
The experiment offers two views:

#### 1. Statistical Measurement of g_z
- Time graph of g_z
- Histogram with Gaussian fitting
- Instantaneous and statistical values
- Calibration button

#### 2. GPS and Reference
- GPS data (latitude, altitude)
- Theoretical value of g
- Applied calibration factor
- Histogram of calibrated data

## Exportable Data

The experiment allows exporting:
- Time and raw accelerometer data
- Calibrated data
- Statistical parameters
- GPS information and theoretical g value

## Technical Notes

### Implemented Improvements
- **Multiplicative calibration** instead of additive for better accuracy
- **Automatic centering** of calibrated data on theoretical g value
- **Clear user interface** with display of key parameters

### Limitations
- Requires good GPS signal for accurate calibration
- Device must be still during calibration
- Accuracy depends on smartphone sensor quality

## Credits

Project developed for smartphone physics experiments.
Based on the phyphox framework for mobile scientific experiments.
