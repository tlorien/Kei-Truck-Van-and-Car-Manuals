---
layout: manual
title: "Diagnostics"
brand: "Subaru"
model: "Sambar"
year: "2009"
chassis: "GBD-TT2"
---

# {{ page.title }}
## 6-1. NA Engine (Diagnosis)
### 1. Overview
#### A: Reference
The on-board diagnostic (OBD) system detects and indicates malfunctions in the inputs and outputs of complex electronic controls. The engine warning light on the instrument panel alerts the driver of any malfunctions or breakdowns.
- In addition, a fail-safe function is installed to ensure a minimum level of driving performance in the event that the vehicle is unable to drive due to sensor failure.
- The OBD system installed in vehicles with this type of engine complies with JOBD regulations. The OBD system monitors for failures of the components and systems described in the "Engine section" that affect emissions.

- When the system detects a malfunction, the engine warning light comes on. At the same time that the engine warning light comes on or flashes, the DTC and engine freeze frame status are stored in the on-board computer.
- When the OBD system detects a malfunction, it stores engine status data (engine load, engine coolant temperature, fuel trim, engine RPM, vehicle speed, etc.) in the freeze frame in the on-board computer.

The stored freeze frame engine status data will be maintained until the DTC is cleared, but the freeze frame

● If a fuel trim or misfire malfunction is detected while the engine status data in the frame is being maintained, it will be overwritten with the engine status data 4 in the freeze frame related to fuel trim or misfire.

If the malfunction does not occur again within three consecutive drive cycles, the engine warning light will go off but the DTC will remain in the on-board computer.
- When diagnosing vehicle malfunctions, connect the Subaru Select Monitor to the vehicle.

#### B: Preparation Tools

|          Illustration          |Tool Number|             Name            |                    Use                   |
|--------------------------------|-----------|-----------------------------|------------------------------------------|
|![img](/assets/images/6-1-1.PNG)|  1B02XJ0  |Subaru Select Monitor III Kit|Used to diagnose electrical system faults.|

### 2. Engine Control Unit (ECU) I/O Signals
#### A. Specifications (Electrical Equipment)
![img](/assets/images/6-1-2.PNG)


<table>
  <tr>
    <th>Name</th>
    <th>Connector Number</th>
    <th>Terminal Number</th>
    <th colspan="2">Signal (V)</th>
    <th>Reference</th>
  </tr>
    <tr>
    <th></th>
    <th></th>
    <th></th>
    <th>Ignition switch ON (engine OFF)</th>
    <th>Engine ON (idling)</th>
    <th></th>
  </tr>
  <tr>
    <td>Main power supply 1</td>
    <td>R134</td>
    <td>2</td>
    <td>10 ~ 30</td>
    <td>13 ~ 15</td>
    <td></td>
  </tr>
  <tr>
    <td>Main power supply 2 TA</td>
    <td>R134</td>
    <td>1</td>
    <td>10 ~ 13</td>
    <td>13 ~ 15</td>
    <td></td>
  </tr>
    <tr>
    <td>Backup power supply</td>
    <td>R134</td>
    <td>8</td>
    <td>10 ~ 13</td>
    <td>13 ~ 15</td>
    <td></td>
  </tr>
    <tr>
    <td>Sensor system power supply</td>
    <td>R135</td>
    <td>18</td>
    <td>5</td>
    <td>5</td>
    <td></td>
  </tr>
    <tr>
    <td>IG SW</td>
    <td>R134</td>
    <td>4</td>
    <td>10 ~ 13</td>
    <td>13 ~ 15</td>
    <td></td>
  </tr>
    <tr>
    <td>Crank angle sensor</td>
    <td>R135</td>
    <td>16</td>
    <td>~ 5</td>
    <td>See input/output waveform diagram</td>
    <td></td>
  </tr>
    <tr>
    <td>Cam angle sensor</td>
    <td>R135</td>
    <td>6</td>
    <td>~ 5</td>
    <td>See input/output waveform diagram</td>
    <td></td>
  </tr>
    <tr>
    <td>Throttle opening</td>
    <td>R135</td>
    <td>3</td>
    <td>Fully close: 0.5 <br>
        Fully open: 4.3</td>
    <td>0.5 <br>
        (Throttle fully closed)</td>
    <td>See also characteristic graph</td>
  </tr>
    <tr>
    <td>Knock sensor</td>
    <td>R135</td>
    <td>23</td>
    <td>See input/output waveform diagram</td>
    <td>See input/output waveform diagram</td>
    <td></td>
  </tr>
    <tr>
    <td>Knock sensor shield</td>
    <td>R135</td>
    <td>24</td>
    <td>Always approx. 0</td>
    <td>Always approx. 0</td>
    <td></td>
  </tr>
    <tr>
    <td>Front O2 sensor</td>
    <td>R135</td>
    <td>14</td>
    <td>0 ~ 1.0</td>
    <td>See input/output waveform diagram</td>
    <td></td>
  </tr>
    <tr>
    <td>Front O2 sensor shield</td>
    <td>R135</td>
    <td>26</td>
    <td>Always approx. 0</td>
    <td>Always approx. 0</td>
    <td></td>
  </tr>
    <tr>
    <td>Rear O2 sensor</td>
    <td>R133</td>
    <td>16</td>
    <td>0 ~ 1.0</td>
    <td>See input/output waveform diagram</td>
    <td></td>
  </tr>
      <tr>
    <td>Rear O2 sensor shield</td>
    <td>R133</td>
    <td>17</td>
    <td>Always approx. 0</td>
    <td>Always approx. 0</td>
    <td></td>
  </tr>
    <tr>
    <td>Pressure sensor signal</td>
    <td>R135</td>
    <td>4</td>
    <td>~ 4.3</td>
    <td></td>
    <td>See also characteristic graph</td>
  </tr>
    <tr>
    <td>Water temperature sensor</td>
    <td>R135</td>
    <td>5</td>
    <td>About 40°C (about 2.0)<br>
        About 60°C (about 1.2)<br>
        About 80°C (about 0.8)</td>
    <td>About 40°C (about 2.0)<br>
        About 60°C (about 1.2)<br>
        About 80°C (about 0.8)</td>
    <td>See also characteristic graph</td>
  </tr>
    <tr>
    <td>A/C thermo signal</td>
    <td>R134</td>
    <td>6</td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
    <tr>
    <td>Intake air temperature sensor</td>
    <td>R135</td>
    <td>15</td>
    <td>About 20°C (about 3.0)<br>
        About 40°C (about 2.0)<br>
        About 60°C (about 1.3)</td>
    <td>About 20°C (about 3.0)<br>
        About 40°C (about 2.0)<br>
        About 60°C (about 1.3)</td>
    <td>See also characteristic graph</td>
  </tr>
</table>



