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