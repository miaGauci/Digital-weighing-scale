# Digital-weighing-scale

To develop an accurate digital weighing scale system that can:

Measure loads up to 500 grams.
Convert load cell analog signals to digital.
Transmit data to a PC for analysis via RS232 protocol.
Display real-time data in LabVIEW.
2. System Design
Load Cell and Amplifier
Load Cell (TAL221): Converts weight into an electrical signal through strain gauge deformation. This signal is processed through a Wheatstone bridge, yielding a differential voltage that changes with the applied load.
HX711 Amplifier: Amplifies the load cell signal and converts it to digital. Channel A of the amplifier is set with a gain of 128 for high sensitivity, ideal for small signal measurement.
Arduino Uno Microcontroller
The ATmega328P on the Arduino Uno reads the amplified signal and transmits data via RS232 to the PC.
Serial Communication: Handled through the USART on the ATmega328P, sending data to LabVIEW for display.
Calibration and Data Conversion
Known weights were used to calibrate the system, generating a relationship between raw data and actual weight.
Calibration Equation: Weight(g) = 0.0003132 * Raw Data - 1087.2678
This equation is applied within the LabVIEW program to convert raw ADC data into weight values.
3. LabVIEW Software Interface
The LabVIEW interface facilitates real-time data monitoring and unit conversion. Key features include:

Unit Conversion: Supports grams, kilograms, pounds, and ounces.
TARE Function: Allows zeroing the displayed weight.
Data Averaging: Averages 100 samples to reduce measurement noise and improve accuracy.
4. Testing and Results
Comparative testing against a commercial scale showed high accuracy, with percent errors below 0.5%.
Sensitivity of the scale is notable, detecting small environmental changes like air currents, which may affect readings.
5. Challenges and Future Improvements
Initial PIC Microcontroller Issues: Initially intended to use the PIC18F87K22 microcontroller, but communication issues led to the use of Arduino instead.
Future Enhancements:
Physical Tare Button: Improve ease of use with a hardware tare option.
LCD Display: Add a direct display for real-time weight readings without needing a PC.
Portable Power and Bluetooth: Allow wireless operation and remote monitoring.
