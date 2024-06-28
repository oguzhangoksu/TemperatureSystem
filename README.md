
![Ekran görüntüsü 2024-06-28 210513](https://github.com/oguzhangoksu/TemperatureSystem/assets/70150316/570eeb2e-cc15-4223-9357-9668c7889d1e)

## **Project Summary:**

This embedded system design project involves a temperature monitoring and display system. The system is built using an AT89C51 microcontroller, an ADC0804 analog-to-digital converter, an LCD display, and a keypad for user interaction. The design is created using Proteus 8 software for simulation and schematic capture.

**Key Components:**

1. **Microcontroller (AT89C51)**: This is the central processing unit of the system, responsible for executing the code and controlling the peripherals.
2. **Analog-to-Digital Converter (ADC0804)**: Converts the analog signals from the temperature sensors to digital values that the microcontroller can process.
3. **LCD Display**: Used to display the temperature readings, average temperature, maximum and minimum temperatures, and system states.
4. **Keypad**: Allows user interaction with the system, enabling the selection of specific temperature channels to display.
5. **Temperature Sensors (LM35)**: Measure the temperature and output analog signals proportional to the temperature.

**Functionality:**

1. **Temperature Measurement**:
    - The system measures temperatures from 8 different channels using LM35 temperature sensors.
    - The analog outputs from these sensors are fed into the ADC0804 for conversion to digital values.
2. **Data Processing**:
    - The microcontroller reads the digital temperature values from the ADC.
    - It calculates the average, maximum, and minimum temperatures.
    - Negative temperature values are handled and counted separately.
3. **User Interaction**:
    - The keypad allows users to select specific temperature channels to view.
    - The system can display temperature readings for the selected channels on the LCD.
4. **Display**:
    - The LCD displays the average temperature, maximum temperature, and minimum temperature.
    - It also displays the state of the system based on the temperature values.
5. **System States**:
    - **State 1**: All temperature readings are below zero.
    - **State 2**: Average temperature is below zero but maximum temperature is above zero.
    - **State 3**: Average temperature is above zero with at least two negative readings.
    - **State 4**: Specific pattern of temperature values across channels.

**Code Highlights:**

1. **Initialization**:
    - The microcontroller ports are initialized for input/output operations.
    - The LCD is initialized with appropriate commands.
2. **Temperature Reading and Processing**:
    - The microcontroller selects each temperature channel, triggers the ADC to convert the analog signal, and reads the digital value.
    - The temperature values are adjusted (subtracted by 50) to convert to the correct scale.
    - Maximum, minimum, and sum of the temperatures are calculated.
3. **Display Functionality**:
    - The lcd_cmd, lcd_data, and lcd_string functions control the LCD to display the required information.
    - The convert_display function formats the temperature values for display on the LCD.
4. **Keypad Functionality**:
    - The key_detect function scans the keypad and returns the code of the pressed key.
    - Based on the key pressed, the system displays the temperature reading of the corresponding channel.
