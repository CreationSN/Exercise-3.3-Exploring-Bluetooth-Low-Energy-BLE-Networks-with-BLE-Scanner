# Exercise-3.3-Exploring-Bluetooth-Low-Energy-BLE-Networks-with-BLE-Scanner

#  Bluetooth Low Energy (BLE) Investigation and Analysis Report

## Objective
To investigate and analyse nearby Bluetooth Low Energy (BLE) devices within a single-room residential environment and evaluate signal characteristics, environmental effects, and security implications.

---

## 1. Scanning Environment Description

**Environment:** Single-room apartment (indoor residential setting)  
**Scan Device:** Android smartphone using the BLE Scanner application  
**Scan Mode:** Passive scanning only (no connections established)  
**Scan Duration:** Approximately 3 minutes  
**Device Position:** Smartphone placed stationary on desk  

### Environmental Conditions
- WiFi router operating at 2.4 GHz (same ISM band as BLE)
- Personal laptop and smartphone present
- Possible BLE signals from neighbouring apartments
- Walls and furniture are causing signal attenuation

No connection attempts were made to any detected devices to maintain ethical and privacy standards.

---

## 2. Collected Data

| Device Name | MAC Address | RSSI (dBm) | Approx Distance | Connectable |
|-------------|------------|------------|----------------|-------------|
| N/A | 20:B7:94:D2:C8:FD | -85 | 19.95 m | No |
| N/A | 7D:03:06:5C:F1:4C | -73 | 5.01 m | Yes |
| N/A | D0:C2:4E:64:52:07 | -107 | 251.19 m | No |
| JEDIDIAH'S Samsung | B0:E4:5C:91:8C:87 | -78 | 8.91 m | Yes |
| N/A | 0C:99:4C:4E:F7:C1 | -90 | 35.48 m | No |
| N/A | EA:8A:59:D0:2D:9C | -61 | 1.26 m | No |
| ZONE2 (ID-67C3) | 78:02:B7:D2:67:C3 | -69 | 3.16 m | Yes |

---

##  3. Technical Analysis

### RSSI vs Distance Relationship

An inverse relationship between RSSI and distance was observed:

- -61 dBm → ~1.26 m (very close device)
- -69 to -78 dBm → 3–9 m (likely same room)
- -85 to -90 dBm → 20–35 m (likely behind walls or neighbouring apartment)
- -107 dBm → extremely weak signal

The device showing -107 dBm with an estimated 251 m distance is unrealistic for an indoor setting. This highlights that RSSI-based distance estimation becomes highly inaccurate at very weak signal levels.

BLE follows a logarithmic path-loss model, and small RSSI changes at low signal strengths can result in large distance estimation errors.

---

### Environmental Impact

**1. Wall Attenuation**  
Signals weaker than -85 dBm likely passed through walls.

**2. WiFi Interference**  
BLE operates in the 2.4 GHz ISM band, overlapping with WiFi networks, which may cause fluctuations in RSSI readings.

**3. Multipath Reflection**  
Indoor environments cause signals to reflect from walls and furniture, leading to unstable signal strength measurements.

---

### Device Density

Even in a single-room apartment, 7 BLE devices were detected. These likely include:

- Personal devices
- Neighbouring devices
- IoT devices operating in advertising mode

This demonstrates that BLE signals extend beyond physical room boundaries.

---

### Connectable vs Non-Connectable Devices

Out of 7 detected devices:
- 3 were connectable
- 4 were non-connectable

Most BLE devices operate in advertising-only mode to reduce power consumption and limit exposure.

---

##  4. Security and Privacy Considerations

### Passive Tracking Risk
BLE devices continuously broadcast advertising packets. An observer can detect device presence without establishing a connection.

### Identifier Exposure
Visible MAC addresses may allow device fingerprinting if not randomised.

### Movement Profiling
Repeated detection of the same device across locations can reveal user movement patterns.

### Neighbor Device Visibility
Devices from nearby apartments were detectable, indicating BLE signals penetrate physical boundaries.

---

## Key Findings

- RSSI decreases as distance increases, but accuracy reduces significantly at low signal strengths.
- BLE signals penetrate walls and extend beyond private indoor spaces.
- Even passive scanning reveals presence and proximity information.
- Environmental factors strongly influence signal behaviour.

---

##  Final Conclusion

The investigation confirms that BLE provides efficient low-power communication but creates a measurable digital footprint. RSSI correlates with proximity, but environmental interference and physical obstructions significantly impact accuracy.

Although modern devices implement MAC randomisation and privacy mechanisms, passive scanning still presents tracking and privacy risks in residential environments.

---
