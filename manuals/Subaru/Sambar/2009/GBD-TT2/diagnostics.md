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

- When the system detects a malfunction, the engine warning light comes on. At the same time that the engine warning light comes on or flashes, the [(DTC) table](#6-diagnostic-code-dtc-list) and engine freeze frame status are stored in the on-board computer.
- When the OBD system detects a malfunction, it stores engine status data (engine load, engine coolant temperature, fuel trim, engine RPM, vehicle speed, etc.) in the freeze frame in the on-board computer.

The stored freeze frame engine status data will be maintained until the [(DTC) table](#6-diagnostic-code-dtc-list) is cleared, but the freeze frame

● If a fuel trim or misfire malfunction is detected while the engine status data in the frame is being maintained, it will be overwritten with the engine status data 4 in the freeze frame related to fuel trim or misfire.

If the malfunction does not occur again within three consecutive drive cycles, the engine warning light will go off but the [(DTC) table](#6-diagnostic-code-dtc-list) will remain in the on-board computer.
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
    <td colspan="2">See input/output waveform diagram</td>
    <td></td>
  </tr>
    <tr>
    <td>Knock sensor shield</td>
    <td>R135</td>
    <td>24</td>
    <td colspan="2">Always approx. 0</td>
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
    <td colspan="2">Always approx. 0</td>
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
    <td colspan="2">Always approx. 0</td>
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
    <td colspan="2">About 40°C (about 2.0)<br>
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
    <td colspan="2">About 20°C (about 3.0)<br>
        About 40°C (about 2.0)<br>
        About 60°C (about 1.3)</td>
    <td>See also characteristic graph</td>
  </tr>
    <tr>
    <td>Engine room remperature sensor</td>
    <td>R133</td>
    <td>26</td>
    <td colspan="2">About 20°C (about 3.6)<br>
        About 40°C (about 2.8)<br>
        About 60°C (about 2.0)</td>
    <td></td>
    <tr>
    <td>Rear defogger</td>
    <td>R134</td>
    <td>21</td>
    <td colspan="2">When SW is OFF: 0<br>
        SWON: 10~15</td>
    <td></td>
  </tr>
    <tr>
    <td>Small light</td>
    <td>R134</td>
    <td>13</td>
    <td colspan="2">When SW is OFF: 0<br>
        SWON: 10~15</td>
    <td></td>
  </tr>
    <tr>
    <td>Power steering signal</td>
    <td>R133</td>
    <td>13</td>
    <td colspan="2">When turning (signal ON): 0<br>
        Going straight (signal OFF): 10~15</td>
    <td></td>
  </tr>
    <tr>
    <td>Heater proa</td>
    <td>R134</td>
    <td>11</td>
    <td colspan="2">When SW is OFF: 10 to 15<br>
        SWON: 2 or less</td>
    <td></td>
  </tr>
    <tr>
    <td>A/C signal</td>
    <td>R134</td>
    <td>3</td>
    <td colspan="2">SWON: 10~15<br>
        When SW is off: 0</td>
    <td></td>
  </tr>
    <tr>
    <td>Vehicle speed sensor</td>
    <td>R133</td>
    <td>24</td>
    <td colspan="2">Refer to input/output waveform diagram.</td>
    <td>MT Model</td>
  </tr>
    <tr>
    <td>Vehicle speed sensor (+)</td>
    <td>R133</td>
    <td>21</td>
    <td colspan="2">Refer to input/output waveform diagram.</td>
    <td>AT Model</td>
  </tr>
    <tr>
    <td>Vehicle speed sensor (-)</td>
    <td>R133</td>
    <td>10</td>
    <td colspan="2">Refer to input/output waveform diagram.</td>
    <td>AT Model</td>
  </tr>
    <tr>
    <td>Vehicle speed sensor shield</td>
    <td>R133</td>
    <td>11</td>
    <td colspan="2">Always approx. 0</td>
    <td>AT Model</td>
  </tr>
    <tr>
    <td>Vehicle speed sensor</td>
    <td>R133</td>
    <td>12</td>
    <td colspan="2">Refer to input/output waveform diagram.</td>
    <td>AT Model</td>
  </tr>
    <tr>
    <td>Plake SW</td>
    <td>R134</td>
    <td>18</td>
    <td colspan="2">Brake pedal depressed: 10~15<br>
        Brake pedal released: 0</td>
    <td></td>
  </tr>
    <tr>
    <td>Power mode SW</td>
    <td>R134</td>
    <td>20</td>
    <td colspan="2">During SWON: 0<br>
        When SW is OFF: 10~15</td>
    <td>AT model</td>
  </tr>
    <tr>
    <td>P range</td>
    <td>R133</td>
    <td>7</td>
    <td colspan="2">P range: 10~15<br>
        Other than P range: 0</td>
    <td>AT model</td>
  </tr>
    <tr>
    <td>R range</td>
    <td>R133</td>
    <td>18</td>
    <td colspan="2">R range: 10~15<br>
        Other than R range: 0</td>
    <td>AT model</td>
  </tr>
    <tr>
    <td>N range</td>
    <td>R133</td>
    <td>8</td>
    <td colspan="2">N range: 10~15<br>
        Other than N range: 0</td>
    <td>AT model</td>
  </tr>
    <tr>
    <td>D range</td>
    <td>R133</td>
    <td>19</td>
    <td colspan="2">D range: 10~15<br>
        Other than D range: 0</td>
    <td>AT model</td>
  </tr>
    <tr>
    <td>2 ranges</td>
    <td>R133</td>
    <td>9</td>
    <td colspan="2">2 range: 10~15<br>
        Other than 2 ranges: 0</td>
    <td>AT model</td>
  </tr>
    <tr>
    <td>1 range</td>
    <td>R133</td>
    <td>20</td>
    <td colspan="2">1 range: 10~15<br>
        Other than 1 range: 0</td>
    <td>AT model</td>
  </tr>
    <tr>
    <td>Test terminal</td>
    <td>R134</td>
    <td>19</td>
    <td colspan="2">Terminal release: 10~15<br>
        When terminal is connected: 0</td>
    <td></td>
  </tr>
    <tr>
    <td>Ignition output #1</td>
    <td>R135</td>
    <td>10</td>
    <td>About 0</td>
    <td>See input/output waveform diagram</td>
    <td></td>
  </tr>
    <tr>
    <td>Ignition output #2</td>
    <td>R135</td>
    <td>9</td>
    <td>About 0</td>
    <td>See input/output waveform diagram</td>
    <td></td>
  </tr>
    <tr>
    <td>Injector #1</td>
    <td>R135</td>
    <td>20</td>
    <td>10~13</td>
    <td>See input/output waveform diagram</td>
    <td></td>
  </tr>
    <tr>
    <td>Injector #2</td>
    <td>R135</td>
    <td>19</td>
    <td>10~13</td>
    <td>See input/output waveform diagram</td>
    <td></td>
  </tr>
    <tr>
    <td>Injector #3</td>
    <td>R135</td>
    <td>28</td>
    <td>10~13</td>
    <td>See input/output waveform diagram</td>
    <td></td>
  </tr>
    <tr>
    <td>Injector #4</td>
    <td>R135</td>
    <td>27</td>
    <td>10~13</td>
    <td>See input/output waveform diagram</td>
    <td></td>
  </tr>
    <tr>
    <td>Alternator</td>
    <td>R133</td>
    <td>23</td>
    <td colspan="2">When stopped (not in operation): 5.0~8.5<br>
        When activated: 0 and 5.0~8.5 (duty)</td>
    <td>Period 50ms</td>
  </tr>
    <tr>
    <td>Select monitor</td>
    <td>R134</td>
    <td>9</td>
    <td colspan="2">About 10~15</td>
    <td></td>
  </tr>
    <tr>
    <td>ABS idle up signal</td>
    <td>R133</td>
    <td>14</td>
    <td>10~13</td>
    <td>13~15</td>
    <td></td>
  </tr>
    <tr>
    <td>ISC #1</td>
    <td>R135</td>
    <td>22</td>
    <td>0 or 10 to 13</td>
    <td>0 and 13~15 (pulse)</td>
    <td>See input/output waveform diagram</td>
  </tr>
    <tr>
    <td>ISC #2</td>
    <td>R135</td>
    <td>21</td>
    <td>0 or 10 to 13</td>
    <td>0 and 13~15 (pulse)</td>
    <td>See input/output waveform diagram</td>
  </tr>
    <tr>
    <td>ISC #3</td>
    <td>R135</td>
    <td>30</td>
    <td>0 or 10 to 13</td>
    <td>0 and 13~15 (pulse)</td>
    <td>See input/output waveform diagram</td>
  </tr>
    <tr>
    <td>ISC #4</td>
    <td>R135</td>
    <td>29</td>
    <td>0 or 10 to 13</td>
    <td>0 and 13~15 (pulse)</td>
    <td>See input/output waveform diagram</td>
  </tr>
    <tr>
    <td>Engine room fan relay</td>
    <td>R134</td>
    <td>14</td>
  <td colspan="2"> Non-operating: 10~15<br>
    When in operation approx. 0</td>
    <td></td>
  </tr>
    <tr>
    <td>Powertrain warning light</td>
    <td>R134</td>
    <td>22</td>
    <td>0</td>
    <td>When lights are off: 10~15<br>
        Wheb lit: 0</td>
    <td></td>
  </tr>
    <tr>
    <td>Sub fan relay</td>
    <td>R134</td>
    <td>24</td>
    <td colspan="2"> Non-operating: 10~15<br>
        When in operation approx. 0</td>
    <td></td>
  </tr>
    <tr>
    <td>Radiator fan relay</td>
    <td>R134</td>
    <td>15</td>
    <td colspan="2"> Non-operating: 10~15<br>
        When in operation approx. 0</td>
    <td></td>
  </tr>
    <tr>
    <td>A/C compressor Control</td>
    <td>R134</td>
    <td>16</td>
    <td colspan="2">Non-operating: 10~15<br>
        When in operation approx. 0</td>
    <td></td>
  </tr>
    <tr>
    <td>Fuel pump relay</td>
    <td>R134</td>
    <td>23</td>
    <td>When stopped (not operating):<br>
        10~15<br>
        When in operation approx. 0</td>
    <td>About 0</td>
    <td></td>
  </tr>
    <tr>
    <td>Tachometer output</td>
    <td>R133</td>
    <td>15</td>
    <td>10~13</td>
    <td>0 and 10-14 (duty)</td>
    <td></td>
  </tr>
    <tr>
    <td>Self shut off</td>
    <td>R134</td>
    <td>10</td>
    <td colspan="2">Below 1V</td>
    <td></td>
  </tr>
    <tr>
    <td>CPC solenoid</td>
    <td>R135</td>
    <td>8</td>
    <td>10~13</td>
    <td>See input/output waveform diagram</td>
    <td></td>
  </tr>
    <tr>
    <td>Front O2 sensor heater</td>
    <td>R133</td>
    <td>5</td>
    <td>10~13</td>
    <td>See input/output waveform diagram</td>
    <td></td>
  </tr>
    <tr>
    <td>Rear O2 sensor heater</td>
    <td>R133</td>
    <td>6</td>
    <td>10~13</td>
    <td>See input/output waveform diagram</td>
    <td></td>
  </tr>
    <tr>
    <td>Shift solenoid 1</td>
    <td>R133</td>
    <td>2</td>
    <td colspan="2">1st gear: 10~15<br>
        2nd gear: 10~15<br>
        3rd gear: 0</td>
    <td>AT model</td>
  </tr>
    <tr>
    <td>Shift solenoid 2</td>
    <td>R133</td>
    <td>1</td>
    <td colspan="2">1st gear: 10~15<br>
        2nd gear: 10~15<br>
        3rd gear: 0</td>
    <td>AT model</td>
  </tr>
    <tr>
    <td>Sensor ground 1</td>
    <td>R135</td>
    <td>7</td>
    <td colspan="2">Always approx. 0</td>
    <td></td>
  </tr>
    <tr>
    <td>Sensor ground 2</td>
    <td>R135</td>
    <td>17</td>
    <td colspan="2">Always approx. 0</td>
    <td></td>
  </tr>
    <tr>
    <td>Sensor ground (rear O2 sensor)</td>
    <td>R133</td>
    <td>25</td>
    <td colspan="2">Always approx. 0</td>
    <td></td>
  </tr>
    <tr>
    <td>Sensor ground (body)</td>
    <td>R134</td>
    <td>5</td>
    <td colspan="2">Always approx. 0</td>
    <td></td>
  </tr>
    <tr>
    <td>Power ground</td>
    <td>R133</td>
    <td>3</td>
    <td colspan="2">Always approx. 0</td>
    <td></td>
  </tr>
    <tr>
    <td>Power ground</td>
    <td>R133</td>
    <td>4</td>
    <td colspan="2">Always approx. 0</td>
    <td></td>
  </tr>
    <tr>
    <td>Control system ground</td>
    <td>R135</td>
    <td>1</td>
    <td colspan="2">Always approx. 0</td>
    <td></td>
  </tr>
    <tr>
    <td>Control system ground</td>
    <td>R135</td>
    <td>2</td>
    <td colspan="2">Always approx. 0</td>
    <td></td>
  </tr>
  </tr>
</table>

![img](/assets/images/6-1-3.PNG)

- Engine

![img](/assets/images/6-1-4.PNG)

![img](/assets/images/6-1-5.PNG)

### 3. Inspection mode
A: Carry out the diagnosis shown in the following diagnostic code [(DTC) table](#6-diagnostic-code-dtc-list).

When performing a diagnosis that is not shown in the diagnostic code [(DTC) table](#6-diagnostic-code-dtc-list), refer to the drive cycle section. ([See 6-12 "Drive Cycle".](#4-drive-cycle))

<table>
  <tr>
    <th>DTC</th>
    <th>Category</th>
    <th>Category</th>
  </tr>
    <tr>
    <td>P0031</td>
    <td>O2 Sensor Heater Circuit (LOW) (Bank 1 Sensor 1)</td>
    <td></td>
  </tr>
    <tr>
    <td>P0032</td>
    <td>O2 Sensor Heater Circuit (HIGH) (Bank 1 Sensor 1)</td>
    <td></td>
  </tr>
    <tr>
    <td>P0037</td>
    <td>O2 Sensor Heater Circuit (LOW) (Bank 1 Sensor 2)</td>
    <td></td>
  </tr>
    <tr>
    <td>P0038</td>
    <td>O2 Sensor Heater Circuit (HIGH) (Bank 1 Sensor 2)</td>
    <td></td>
  </tr>
    <tr>
    <td>P0107</td>
    <td>Intake pressure sensor circuit (LOW)</td>
    <td></td>
  </tr>
    <tr>
    <td>P0108</td>
    <td>Intake pressure sensor circuit (HIGH)</td>
    <td></td>
  </tr>
    <tr>
    <td>P0112</td>
    <td>Intake air temperature sensor circuit (LOW)</td>
    <td></td>
  </tr>
    <tr>
    <td>P0113</td>
    <td>Intake air temperature sensor circuit (HIGH)</td>
    <td></td>
  </tr>
    <tr>
    <td>P0117</td>
    <td>Water temperature sensor circuit (LOW)</td>
    <td></td>
  </tr>
    <tr>
    <td>P0118</td>
    <td>Water temperature sensor circuit (HIGH)</td>
    <td></td>
  </tr>
    <tr>
    <td>P0122</td>
    <td>Throttle position sensor A circuit (LOW)</td>
    <td></td>
  </tr>
    <tr>
    <td>P0122</td>
    <td>Throttle position sensor A circuit (HIGH)</td>
    <td></td>
  </tr>
    <tr>
    <td>P0130</td>
    <td>O2 sensor circuit (Bank 1 Sensor 1)</td>
    <td></td>
  </tr>
    <tr>
    <td>P0136</td>
    <td>O2 sensor circuit (Bank 1 Sensor 2)</td>
    <td></td>
  </tr>
    <tr>
    <td>P0327</td>
    <td>Knock sensor 1 circuit (LOW)</td>
    <td></td>
  </tr>
    <tr>
    <td>P0328</td>
    <td>Knock sensor 1 circuit (HIGH)</td>
    <td></td>
  </tr>
    <tr>
    <td>P0335</td>
    <td>Crank angle sensor A system circuit</td>
    <td></td>
  </tr>
    <tr>
    <td>P0340</td>
    <td>Cam angle sensor A system circuit 1</td>
    <td></td>
  </tr>
    <tr>
    <td>P0350</td>
    <td>Ignition coil system circuit</td>
    <td></td>
  </tr>
    <tr>
    <td>P0444</td>
    <td>Canister purge solenoid circuit (LOW)</td>
    <td></td>
  </tr>
    <tr>
    <td>P0445</td>
    <td>Canister purge solenoid circuit (HIGH)</td>
    <td></td>
  </tr>
    <tr>
    <td>P0500</td>
    <td>Vehicle speed sensor system</td>
    <td></td>
  </tr>
    <tr>
    <td>P0562</td>
    <td>Charging circuit (LOW)</td>
    <td></td>
  </tr>
    <tr>
    <td>P0562</td>
    <td>Charging circuit (HIGH)</td>
    <td></td>
  </tr>
    <tr>
    <td>P0705</td>
    <td>AT Range SW circuit</td>
    <td></td>
  </tr>
    <tr>
    <td>P0720</td>
    <td>AT vehicle speed sensor circuit</td>
    <td></td>
  </tr>
    <tr>
    <td>P0753</td>
    <td>AT shift solenoid 1 circuit (shift solenoid A)</td>
    <td></td>
  </tr>
    <tr>
    <td>P0758</td>
    <td>AT shift solenoid 2 circuit (shift solenoid B)</td>
    <td></td>
  </tr>
    <tr>
    <td>P0790</td>
    <td>Mode SW circuit</td>
    <td></td>
  </tr>
    <tr>
    <td>P1510</td>
    <td>ISC signal line 1 circuit (LOW)</td>
    <td></td>
  </tr>
    <tr>
    <td>P1511</td>
    <td>ISC signal line 1 circuit (HIGH)</td>
    <td></td>
  </tr>
    <tr>
    <td>P1512</td>
    <td>ISC signal line 2 circuit (LOW)</td>
    <td></td>
  </tr>
    <tr>
    <td>P1513</td>
    <td>ISC signal line 2 circuit (HIGH)</td>
    <td></td>
  </tr>
    <tr>
    <td>P1514</td>
    <td>ISC signal line 3 circuit (LOW)</td>
    <td></td>
  </tr>
    <tr>
    <td>P1515</td>
    <td>ISC signal line 3 circuit (HIGH)</td>
    <td></td>
  </tr>
    <tr>
    <td>P1516</td>
    <td>ISC signal line 4 circuit (LOW)</td>
    <td></td>
  </tr>
    <tr>
    <td>P1517</td>
    <td>ISC signal line 4 circuit (HIGH)</td>
    <td></td>
  </tr>
    <tr>
    <td>P1521</td>
    <td>Brake signal circuit</td>
    <td></td>
  </tr>
    <tr>
    <td>P1522</td>
    <td>Electrical load signal system circuit</td>
    <td></td>
  </tr>
    <tr>
    <td>P1525</td>
    <td>Blower fan circuit</td>
    <td></td>
  </tr>
    <tr>
    <td>P1559</td>
    <td>Intake system</td>
    <td></td>
  </tr>
    <tr>
    <td>P1560</td>
    <td>Backup power supply</td>
    <td></td>
  </tr>
</table>

1. Preparation for Inspection
    1. Make sure there is about half a fuel tank [10~20 liters (2.7~5.3 US gal, 2.2~ 4.4 Imp gal)] remaining and the battery voltage is 12 V or higher.
    2. Use a garage jack to jack up the vehicle and place it on a rigid rack or run the vehicle on free rollers.

**Warning**:
- Before jacking up the vehicle, make sure the parking brake is on.
- Do not use a pantograph jack instead of a rigid rack.
- Attach a rope or wire to the front or rear towing hook to prevent the front wheel from swaying sideways.
- Before you spin the wheels, make sure there is no one in front of the vehicle, and keep no one in front of the vehicle while you are spinning the wheels.
- Make sure there are no obstacles near the wheels, especially all four wheels if you have an AWD model.
- While working, do not suddenly press or release the clutch pedal or accelerator pedal, regardless of the engine speed. Sudden operation may cause the vehicle to separate from the free rollers.
- To prevent the vehicle from slipping due to vibration, do not place anything between the rigid rack and the vehicle.

![img](/assets/images/6-1-6.PNG)

2. Subaru Select Monitor
    1. After clearing the memory, check that no unsolved fault data remains. (See 6-13 "Clear Memory Mode".)
    2. Warm up the engine.
    3. Prepare the Subaru Select Monitor Kit. [6-2 "Overview and Preparation Tools."](#b-preparation-tools)
       ![img](/assets/images/6-1-7.PNG)
    4. Prepare a computer with the Spartan Select Monitor installed.
    5. Connect the USB cable to the SDI (Subaru Diagnostic Interface) and the computer's USB port (Subaru Select Monitor dedicated port).
    
       > Reference:
       - The Subaru Select Monitor dedicated port refers to the USB port used when installing the Subaru Select Monitor.

    6. Connect the diagnostic cable to SDI.
    7. Connect the test mode connector (A) located at the bottom of the instrument panel (driver's side).
    
        ![img](/assets/images/6-1-8.PNG)
    8. Connect the SDI to the data link connector installed at the bottom of the instrument panel (driver's seat side).

        ![img](/assets/images/6-1-9.PNG)

        **Notice**: Do not connect any scan tools other than the Subaru Select Monitor.
    9. Start your computer.
    10. Turn the ignition switch ON (engine OFF) and launch the "Subaru Select Monitor PC Application."
    11. On the main menu screen, select "Individual System Check."
    12. On the «System Selection Menu» screen, select {Engine}.
    13. After the engine type information is displayed, click the [OK] button.
    14. On the "Engine Fault Diagnosis" screen, select "D Check."
    15. When the message "Do you want to perform a D check?" appears on the screen, click the [Next] button.
    16. Follow the next steps as instructed on the screen.
        
        > Reference:
        - If a malfunction remains in the memory, the corresponding DTC will be displayed on the screen.
        - For detailed operating procedures, refer to the "Subaru Select Monitor PC Application Help."
        - For details on the DTC, refer to the diagnostic code (DTC) table. (See [Diagnostics Code (DTC) table](#6-diagnostic-code-dtc-list) on page 6-14.)
        - If the speed difference between the front and rear wheels occurs, the ABS warning light may come on, but this is not a malfunction. After the engine control diagnosis is complete, perform the ABS memory clear procedure in the self-diagnosis function.

### 4. Drive cycle
#### A: Procedure
The drive patterns shown below are used to diagnose malfunctions. By implementing the specified drive patterns, the malfunctions listed below can be diagnosed. After repairing the malfunctions listed below, be sure to implement the required drive pattern and check that the function has been restored correctly.

1. Preparing the Drive Cycle
    1. Make sure there is about half a tank of fuel [10~20 liters (2.7~5.3 US gal, 2.2~4.4 Imp gal)] remaining and the battery voltage is 12V or higher.
    2. Disconnect the test mode connector.
        > Reference:
        - Unless the engine coolant temperature is specified at start-up, always perform the diagnosis after the engine has warmed up.
        - If the DTC has an * mark, perform the diagnosis twice. After the first diagnosis is completed, stop the engine and perform the second diagnosis under the same conditions.
2. Drive cycle 1 (Drive for 20 minutes at 55-65 km/h, then idle the engine for 3 minutes.)
    > Reference:
    - If it is not possible to drive continuously for 20 minutes, drive the vehicle while meeting the following conditions 4 to 5 times without turning off the engine.
    - Each run lasts approximately 5 minutes.
    - Drive at a constant speed (55-65km/h).
    - Reduce acceleration and deceleration (throttle operation) while driving at a constant speed.

<table>
  <tr>
    <th>DTC</th>
    <th>Project</th>
    <th>Condition</th>
  </tr>
  <tr>
    <td>*P0133</td>
    <td>O2 Sensor response (Bank 1 Sensor 1)</td>
    <td></td>
  </tr>
  <tr>
    <td>*P0139</td>
    <td>O2 Sensor response (Bank 1 Sensor 2)</td>
    <td></td>
  </tr>
  <tr>
    <td>*P0171</td>
    <td>Fuel System 1 (Lean)</td>
    <td></td>
  </tr>
  <tr>
    <td>*P0172</td>
    <td>Fuel System 1 (Rich)</td>
    <td></td>
  </tr>
  <tr>
    <td>*P0301</td>
    <td>#1 Cylinder misfire</td>
    <td></td>
  </tr>
  <tr>
    <td>*P0302</td>
    <td>#2 Cylinder misfire</td>
    <td></td>
  </tr>
  <tr>
    <td>*P0303</td>
    <td>#3 Cylinder misfire</td>
    <td></td>
  </tr>
  <tr>
    <td>*P0304</td>
    <td>#4 Cylinder misfire</td>
    <td></td>
  </tr>
  <tr>
    <td>*P0420</td>
    <td>Catalyst system</td>
    <td></td>
  </tr>
</table>

### 5. Clear Memory Mode
#### A: Operation
1. On the main menu screen, select "Individual System Check."
2. On the «System Selection Menu» screen, select {Engine}.
3. After the engine type information is displayed, click the [OK] button.
4. On the ENGINE DIAGNOSIS screen, select MEMORY CLEAR.
5. When the message "Do you want to clear memory?" appears on the screen, click the [Yes] button.
6. When "Executed" and "Turn IG SW OFF" are displayed on the screen, turn the ignition switch OFF.
    > Reference:
    - For detailed operating procedures, refer to the "Subaru Select Monitor PC Application Help."

### 6. Diagnostic Code (DTC) List
#### A: List

<table>
  <tr>
    <th>DTC</th>
    <th>Project</th>
    <th>Reference</th>
  </tr>
  <tr>
    <td>P0037</td>
    <td>O2 Sensor Heater Circuit (LOW) (Tire 1 Sensor 2)</td>
    <td>(See 6-15 "Diagnostic Procedures Using Diagnostic Codes (DTCs)", DTC P0037<br>
    (See "O2 Sensor Heater Circuit (LOW) (Bank 1 Sensor 2)"</td>
  </tr>
  <tr>
    <td>P0038</td>
    <td>O2 Sensor Heater Circuit (HIGH) (Bank 1 Sensor 2)</td>
    <td>(See 6-17 "Diagnostic Procedures Using Diagnostic Codes (DTCs)", DTC P0038<br>
    (See "O2 Sensor Heater Circuit (HIGH) (Bank 1 Sensor 2)"</td>
  </tr>
  <tr>
    <td>P0136</td>
    <td>O2 Sensor Circuit (Bank 1 Sensor 2)</td>
    <td>6-19 "Diagnostic Procedures Using Diagnostic Codes (DTCs) DTC P0136<br>
    (See "O2 Sensor Circuit (Bank 1 Sensor 2)"</td>
  </tr>
  <tr>
    <td>P0139</td>
    <td>O2 Sensor Response (Bank 1 Sensor 2)</td>
    <td>(See 6-22 "Diagnostic Procedures Using Diagnostic Codes (DTCs)," DTC P0139<br>
    (See "O2 Sensor Response (Bank 1 Sensor 2)"</td>
  </tr>
  <tr>
    <td>P0420</td>
    <td>Catalyst system</td>
    <td>(See 6-24 "Diagnostic Procedures Using Diagnostic Codes (DTCs)," DTC P0420<br>
    (See "Catalyst Systems.")</td>
  </tr>
</table>

### 7. Diagnostic Procedures When Using Diagnostic Codes (DTC)
#### A: DTC P0037 O2 Sensor Heater Circuit (LOW) (Bank 1 Sensor 2)
**Notice**: After repairing or replacing the defective parts, execute the clear memory mode (see "Clear Memory Mode, Operation" on page 6-13) and the inspection mode (see "Inspection Mode, Procedure" on page 6-9).

Wiring diagram:

![img](/assets/images/6-1-10.PNG)

<table>
  <tr>
    <th>Step</th>
    <th>Check</th>
    <th>Yes</th>
    <th>No</th>
  </tr>
  <tr>
    <td>
      <STRONG>Step 1.</STRONG> Check the power supply to the rear 2 sensors<br>
      &nbsp;&nbsp;&nbsp;&nbsp;1. Turn the ignition switch OFF.<br>
      &nbsp;&nbsp;&nbsp;&nbsp;2. Disconnect the connector from the rear O2 sensor.<br>
      &nbsp;&nbsp;&nbsp;&nbsp;3. Turn the ignition switch ON.<br>
      &nbsp;&nbsp;&nbsp;&nbsp;4. Between the rear O2 sensor connector and body ground measure voltage.<br>
      &nbsp;&nbsp;&nbsp;&nbsp;Connectors & terminals:<br>
      &nbsp;&nbsp;&nbsp;&nbsp;(R114) No.2 (+) - Body Earth (-)
    </td>
    <td>Is the voltage 10V or more?</td>
    <td>Proceed to step 2.</td>
    <td>Repair the power supply line.</td>
  </tr>
  <tr>
    <td><STRONG>Step 2.</STRONG> Check the harness between the ECU and the rear O2 sensor<br>
      &nbsp;&nbsp;&nbsp;&nbsp;Measure the resistance between the ECU connector and the Rear O2 sensor connector.<br>
      &nbsp;&nbsp;&nbsp;&nbsp;Connectors & terminals:<br>
      &nbsp;&nbsp;&nbsp;&nbsp;(R133) No. 6 - (R114) No. 4</td>
    <td>Is the resistance less than 12?</td>
    <td>Proceed to step 3.</td>
    <td>Repair the break in the harness between the ECU and the rear O2 sensor.</td>
  </tr>
  <tr>
    <td><STRONG>Step 3.</STRONG> Check the ECU earth circuit<br>
    &nbsp;&nbsp;&nbsp;&nbsp;1. Turn the ignition switch OFF.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;2. Disconnect the connector from the ECU.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;3. Check the harness between the ECU connector and the body ground. Measure resistance.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;Connectors & terminals:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;(R133) No. 3 - Body Earth<br>
    &nbsp;&nbsp;&nbsp;&nbsp;(R133) No. 4 - Body Earth<br>
    &nbsp;&nbsp;&nbsp;&nbsp;(R135) No. 1 - Body Earth<br>
    &nbsp;&nbsp;&nbsp;&nbsp;(R135) No. 2 - Body Earth</td>
    <td>Is the resistance below 52?</td>
    <td>Proceed to step 4.</td>
    <td>Repair the break in the hardness between the ECU and the body ground.</td>
  </tr>
  <tr>
    <td><STRONG>Step 4.</STRONG> Check the rear 2 sensors<br>
    &nbsp;&nbsp;&nbsp;&nbsp;1. Turn the ignition switch OFF.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;2. Measure the resistance between the rear O2 sensor connector terminals.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;Terminals:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;No. 1 - No.2</td>
    <td>Is the resistance 3.0~4.02?</td>
    <td>Repair the poor contact of the ECU connector.</td>
    <td>Rear O2 sensor exchange.</td>
  </tr>
</table>

#### B: DTC P0038 O2 Sensor Heater Circuit (HIGH) (Bank 1 Sensor 2)
**Notice**: After repairing or replacing the defective parts, execute the clear memory mode (see "Clear Memory Mode, Operation" on page 6-13) and the inspection mode (see "Inspection Mode, Procedure" on page 6-9).

Wiring diagram:

![img](/assets/images/6-1-11.PNG)

<table>
  <tr>
    <th>Step</th>
    <th>Check</th>
    <th>Yes</th>
    <th>No</th>
  </tr>
  <tr>
    <td><STRONG>Step 1.</STRONG> Check the harness between the ECU and the rear O2 sensor<br>
    &nbsp;&nbsp;&nbsp;&nbsp;1. Turn the ignition switch OFF.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;2. Disconnect the connector from the rear O2 sensor.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;3. Measure the voltage between the ECU and body ground.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;Connectors & Terminals:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;(R133) No. 6 (+) - Body Earth (-)</td>
    <td>Is the voltage 10V or higher?</td>
    <td>Repair the power short in the harness between the ECU and the rear O2 sensor connector.</td>
    <td>Proceed to step 2.</td>
  </tr>
  <tr>
    <td><STRONG>Step 2.</STRONG> Check the ECU earth circuit<br>
    &nbsp;&nbsp;&nbsp;&nbsp;1. Disconnect the connector from the ECU.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;2. Measure the resistance of the harness between the ECU connector and body ground.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;Connectors & Terminals:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;(R133) No. 3 - Body Earth<br>
    &nbsp;&nbsp;&nbsp;&nbsp;(R133) No. 4 - Body Earth<br>
    &nbsp;&nbsp;&nbsp;&nbsp;(R135) No. 1 - Body Earth<br>
    &nbsp;&nbsp;&nbsp;&nbsp;(R135) No. 2 - Body Earth</td>
    <td>Is the resistance below 52?</td>
    <td>Repair the poor contact of the ECU connector. If there is a problem, replace the ECU.</td>
    <td>Repair the break in the harness between the ECU connector and the body ground.</td>
  </tr>
</table>

#### C: DTC P0136 O2 Sensor Circuit (Bank 1 Sensor 2)
**Notice**: After repairing or replacing the defective parts, execute the clear memory mode (see "Clear Memory Mode, Operation" on page 6-13) and the inspection mode (see "Inspection Mode, Procedure" on page 6-9).

Wiring diagram:

![img](/assets/images/6-1-12.PNG)

<table>
  <tr>
    <th>Step</th>
    <th>Check</th>
    <th>Yes</th>
    <th>No</th>
  </tr>
  <tr>
    <td><STRONG>Step 1.</STRONG> Check the screen for other DTCs.</td>
    <td>Are any other DTCs showing up?</td>
    <td>Check the DTCs using the "Diagnostic Code (DTC) Table". (See "Diagnostic Code (DTC) Table" on page 6-14.)</td>
    <td>Go to Step 2.</td>
  </tr>
  <tr>
    <td><STRONG>Step 2.</STRONG> Checking rear 2 sensor data<br>
    &nbsp;&nbsp;&nbsp;&nbsp;1. Warm up the engine until the engine coolant temperature exceeds 70°C (158°F), then maintain the engine speed between 2,000 rpm and 3,000 rpm for two minutes.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;2. Use the Subaru Select Monitor to read the rear O2 sensor signal data.</td>
    <td>Is the voltage below 1.0V?</td>
    <td>Proceed to Step 3.</td>
    <td>Proceed to Step 8.</td>
  </tr>
  <tr>
    <td><STRONG>Step 3.</STRONG> Check the harness between the ECU and the rear O2 sensor connector.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;1. Turn the ignition switch ON.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;2. Measure the voltage between the ECU connector and body ground.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;Connectors & Terminals:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;(R133) No. 16 (+) - Body Earth (-)</td>
    <td>Is the voltage 10V or higher?</td>
    <td>Repair the power short in the harness between the ECU and the rear O2 sensor connector.</td>
    <td>Proceed to Step 4.</td>
  </tr>
  <tr>
    <td><STRONG>Step 4.</STRONG> Harness between ECU and rear O2 sensor connector:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;Inspection<br>
    &nbsp;&nbsp;&nbsp;&nbsp;1. Turn the ignition switch OFF.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;2. Disconnect the connector from the ECU and the rear O2 sensor.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;3. Measure the resistance between the rear O2 sensor connector and body ground.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;Connectors & Terminals:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;(R114) No. 3 - Body Earth</td>
    <td>Is the resistance greater than 1MΩ?</td>
    <td>Proceed to Step 5.</td>
    <td>Repair the ground short in the harness between the ECU and the rear O2 sensor connector.</td>
  </tr>
  <tr>
    <td><STRONG>Step 5.</STRONG> Check the rear 2 sensor data<br>
    &nbsp;&nbsp;&nbsp;&nbsp;1. Connect all connectors.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;2. Idle the engine.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;3. Idle the engineUse the Subaru Select Monitor to check the rear O2 sensor. Read the data of the sensor signal.</td>
    <td>Is the voltage 0.7 to 0.09V?</td>
    <td>Proceed to Step 6.</td>
    <td>Replace the rear O2 sensor.</td>
  </tr>
  <tr>
    <td><STRONG>Step 6.</STRONG> Harness between ECU and rear O2 sensor connector:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;Inspection:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;1. Turn the ignition switch OFF.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;2. Disconnect the connectors from the ECU and the rear O2 sensor.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;3. Measure the resistance of the harness between the ECU and the rear O2 sensor connector.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;Connectors & Terminals:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;(R133) No. 16 - (R114) No.3</td>
    <td>Resistance less than 12?</td>
    <td>Proceed to Step 7.</td>
    <td>Repair the open circuit in the harness between the ECU and the rear O2 sensor connector.</td>
  </tr>
  <tr>
    <td><STRONG>Step 7.</STRONG> Harness between rear O2 sensor and ECU connector<br>
    &nbsp;&nbsp;&nbsp;&nbsp;Inspection:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;1. Connect the connector to the ECU and rear O2 sensor..<br>
    &nbsp;&nbsp;&nbsp;&nbsp;2. Turn the ignition switch ON.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;3.  Replace the rear O2 sensor harness connector and tighten the ground terminal.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;Connectors & Terminals:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;(R114) No. 3 (+) - Body Earth (-)</td>
    <td>Is the voltage less than 0.2V?</td>
    <td>Repair poor contact in the rear O2 sensor connector and ECU connector.</td>
    <td>Replace the rear O2 sensor.</td>
  </tr>
  <tr>
    <td><STRONG>Step 8.</STRONG> Engine System Inspection<br>
    Inspect the exhaust system components.<br>
    Reference:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;Check the following items:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;- Loose and incompletely installed exhaust system parts<br>
    &nbsp;&nbsp;&nbsp;&nbsp;- Damage to parts (cracks, holes, etc.)<br>
    &nbsp;&nbsp;&nbsp;&nbsp;- Parts between the front O2 sensor and the reas O2 sensor
    &nbsp;&nbsp;&nbsp;&nbsp;- Loose and incomplete installation</td>
    <td>Is there a problem with the exhaust system?</td>
    <td>Repair or replace defective parts.</td>
    <td>Replace the rear O2 sensor.</td>
  </tr>
</table>

#### D: DTC P0139 O2 Sensor Response (Bank 1 Sensor 2)
**Notice**: After repairing or replacing the defective parts, execute the clear memory mode (see "Clear Memory Mode, Operation" on page 6-13) and the inspection mode (see "Inspection Mode, Procedure" on page 6-9).

Wiring diagram:

![img](/assets/images/6-1-13.PNG)

<table>
  <tr>
    <th>Step</th>
    <th>Check</th>
    <th>Yes</th>
    <th>No</th>
  </tr>
  <tr>
    <td><STRONG>Step 1.</STRONG> <br>
    &nbsp;&nbsp;&nbsp;&nbsp;Inspection:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;1. Turn the ignition switch OFF.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;2. Disconnect the connectors from the ECU and rear O2 sensor..<br>
    &nbsp;&nbsp;&nbsp;&nbsp;3. Measure the resistance of the harness between the ECU and the rear O2 sensor connector.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;Connectors & Terminals:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;(R133) No. 16 - (R114) No. 3</td>
    <td>Resistance less than 12?</td>
    <td>Proceed to Step 2.</td>
    <td>Repair the break in the harness between the power connectors.</td>
  </tr>
  <tr>
    <td><STRONG>Step 2.</STRONG> Harness between ECU and rear O2 sensor connector<br>
    &nbsp;&nbsp;&nbsp;&nbsp;Inspection:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;Measure the resistance between the rear O2 sensor connector and body ground.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;Connectors & Terminals:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;(R114) No. 3 - Body Earth</td>
    <td>Is the resistance greater than 1MΩ?</td>
    <td>Proceed to Step 3.</td>
    <td>Repair the short to earth in the harness between the power connectors.</td>
  </tr>
  <tr>
    <td><STRONG>Step 3.</STRONG> Check the rear 2 sensors<br>
    &nbsp;&nbsp;&nbsp;&nbsp;Measure the resistance between the rear O2 sensor terminals..<br>
    &nbsp;&nbsp;&nbsp;&nbsp;Terminals:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;No. 3 - No. 1</td>
    <td>Is the resistance less than 12?</td>
    <td>Rear O2 sensor exchange</td>
    <td>Even if the powertrain warning light comes on, the circuit has returned to  normal at this point. Recreate the fault and perform the diagnosis again.<br>
    <br>
    Reference:<br>
    In this case, a temporary connector contact failure may be the cause.</td>
  </tr>
</table>

#### E: DTC P0420 Catalyst system

**Notice**: After repairing or replacing the defective parts, execute the clear memory mode (see "Clear Memory Mode, Operation" on page 6-13) and the inspection mode (see "Inspection Mode, Procedure" on page 6-9).

Wiring diagram:

![img](/assets/images/6-1-14.PNG)

<table>
  <tr>
    <th>Step</th>
    <th>Check</th>
    <th>Yes</th>
    <th>No</th>
  </tr>
  <tr>
    <td><strong>Step 1.</strong> Inspecting the exhaust system<br>
      &nbsp;&nbsp;&nbsp;&nbsp;Check for gas leaks or air inhalation caused by loose or missing nuts and bolts, and for holes in the exhaust pipe.<br>
      Reference:<br>
      Check the following locations.<br>
      &nbsp;&nbsp;&nbsp;&nbsp;- Between the cylinder head and the front exhaust pipe<br>
      &nbsp;&nbsp;&nbsp;&nbsp;- Between the front exhaust pipe and the front catalyst<br>
      &nbsp;&nbsp;&nbsp;&nbsp;- Between the front and rear catalysts<br>
      &nbsp;&nbsp;&nbsp;&nbsp;- The front O2 sensor or rear O2 sensor is loose or incompletely installed.</td>
    <td>Is there a problem with the exhaust system?</td>
    <td>Repair or replace the exhaust system</td>
    <td>Proceed to Step 2.</td>
  </tr>
  <tr>
    <td><strong>Step 2.</strong> Checking the waveform data on the Subaru Select Monitor (while driving)<br>
      &nbsp;&nbsp;&nbsp;&nbsp;1. Drive at a constant speed of 55-66km/h.<br>
      &nbsp;&nbsp;&nbsp;&nbsp;2. After 5 minutes have elapsed in the state of Step 1), use the Subaru Select Monitor to read the waveform data while the vehicle is still driving.<br>
      - Normal:<br>
      <img src="/assets/images/6-1-15.PNG" alt="Normal Waveform"><br>
      - When abnormal (many inversions)<br>
      <img src="/assets/images/6-1-16.PNG" alt="Abnormal Waveform"><br>
    </td>
    <td>Is the normal waveform displayed?</td>
    <td>Even if the powertrain warning light comes on, the circuit has returned to normal at this point. Recreate the fault and perform the diagnosis again.<br>
      Reference:<br>
      In this case, a temporary connector contact failure is suspected.</td>
    <td>Proceed to Step 3.</td>
  </tr>
  <tr>
    <td><STRONG>Step 3.</STRONG> Checking the waveform data on the Subaru Select Monitor (while idling)<br>
    &nbsp;&nbsp;&nbsp;&nbsp;1. Idle the vehicle.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;2. While in Step 1), use the Subaru Select Monitor to read the waveform data.<br>
    - Normal:<br>
    <img src="/assets/images/6-1-17.PNG" alt="Normal Waveform"><br>
    - Abnormality 1 (many inversions)<br>
    <img src="/assets/images/6-1-18.PNG" alt="Abnormality 1"><br>
    - Abnormality 2 (noise mixed)<br>
    <img src="/assets/images/6-1-19.PNG" alt="Abnormality 2"><br></td>
    <td>Is the normal waveform displayed?</td>
    <td>Proceed to Step 4.</td>
    <td>- If the waveform of abnormality 1 is displayed: Go to Step 4.<br>
    - If the waveform of abnormality 2 is displayed, proceed to Step 5.</td>
  </tr>
  <tr>
    <td><STRONG>Step 4.</STRONG> Inspecting the catalyst</td>
    <td>Is there damage to the catalyst?</td>
    <td>Replace the catalyst</td>
    <td>Proceed to Step 5.</td>
  </tr>
  <tr>
    <td><STRONG>Step 5.</STRONG> Check the rear 2 sensor connector and intermediate connector</td>
    <td>Has water gotten into the connector?</td>
    <td>Completely prevent water ingress.</td>
    <td>Proceed to Step 6.</td>
  </tr>
  <tr>
    <td><STRONG>Step 6.</STRONG> Harness between ECU and rear O2 sensor connector<br>
    &nbsp;&nbsp;&nbsp;&nbsp;Inspection:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;1. Turn the ignition switch OFF.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;2. Disconnect the connectors from the ECU and rear O2 sensor.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;3. Measure the resistance of the harness between the ECU and the rear O2 sensor connector.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;Connectors & Terminals:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;(R133) No. 16 - (R114) No. 3<br>
    &nbsp;&nbsp;&nbsp;&nbsp;(R133) No. 25 - (R114) No. 1</td>
    <td>Resistance less than 12?</td>
    <td>Proceed to Step 7.</td>
    <td>Repair the harness and connectors.<br>
    Reference:<br>
    <br>
    Repair the following locations:<br>
    <br>
    - Disconnection in the harness between the ECU and the rear O2 sensor connector.<br>
    - Poor contact at the short connector.</td>
  </tr>
  <tr>
    <td><STRONG>Step 7.</STRONG> Harness between ECU and rear O2 sensor connector<br>
    &nbsp;&nbsp;&nbsp;&nbsp;Inspection:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;1. Connect the connector to the ECU.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;2. Turn the ignition switch ON.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;3. Measure the voltage between the rear O2 sensor connector and body ground.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;Connectors & Terminals:<br>
    &nbsp;&nbsp;&nbsp;&nbsp;(R114) No. 3 (+) - Body Earth (-)</td>
    <td>Is the voltage 0.2 to 0.5V?</td>
    <td>Proceed to Step 8.</td>
    <td>Repair the harness and connector.<br>
    Reference:<br>
    <br>
    Repair the following locations:<br>
    <br>
    - Open circuit between ECU and rear O2 sensor<br>
    - Poor contact of the ECU connector</td>
  </tr>
  <tr>
    <td><STRONG>Step 8.</STRONG> Check the rear 2 sensor shield<br>
    &nbsp;&nbsp;&nbsp;&nbsp;1. Turn the ignition switch OFF.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;2. Expose the sensor shield on the body side harness of the rear O2 sensor connector.<br>
    &nbsp;&nbsp;&nbsp;&nbsp;3. Measure the resistance between the sensor shield and body ground.</td>
    <td>Is the resistance less than 12?</td>
    <td>Replace the rear O2 sensor.</td>
    <td>Repair the disconnection in the rear O2 sensor heater circuit.</td>
  </tr>
</table>

## 6-2. SC Engine (Diagnosis)
### 1. Clear memory mode
#### A: Operation
