# 4_led_pattern_using_keypad
An external Keypad is used

# LED Pattern Controller with Keypad

## Overview

This project uses an external keypad to control the lighting patterns of LEDs connected to an Arduino. Users can input different pattern numbers via the keypad to see various LED sequences. This project demonstrates the use of keypads for input and controlling multiple LEDs.

## Components

- Arduino board (e.g., Uno, Mega)
- 4 LEDs
- 4 current-limiting resistors (220Ω recommended)
- 4x4 Keypad
- Breadboard and jumper wires

## Circuit Diagram

1. **LEDs**
   - Connect the cathode (short leg) of each LED to the ground (GND) on the Arduino.
   - Connect the anode (long leg) of each LED to a current-limiting resistor.
   - Connect the other end of the resistors to digital pins 10, 11, 12, and 13 on the Arduino.

2. **Keypad**
   - Connect the row pins of the keypad to digital pins 2, 3, 4, and 5 on the Arduino.
   - Connect the column pins of the keypad to digital pins 6, 7, 8, and 9 on the Arduino.

## Code Explanation

### Libraries

- `Keypad.h`: For interfacing with the keypad.

### Variables and Objects

- `ledPin`: The pin connected to the LEDs (set to digital pins 10 to 13).
- `customKeypad`: Object to manage keypad input.

### Setup

In the `setup()` function:
- The LED pins are set as OUTPUT.
- Serial communication is initialized at 9600 baud.
- A message is printed to the Serial Monitor prompting the user to enter a pattern number.

### Loop

In the `loop()` function:
- The program reads input from the keypad using `customKeypad.getKey()`.
- Depending on the key pressed (`1`, `2`, `3`, or `4`), the corresponding LED pattern function is called.
- If an invalid key is pressed, an error message is printed to the Serial Monitor.

### LED Patterns

- `ledPattern1()`: Turns on all LEDs sequentially with a 1-second delay and then turns them off sequentially.
- `ledPattern2()`: Turns each LED on and off one by one with a 1-second delay.
- `ledPattern3()`: Turns all LEDs on in reverse order, then turns them off in reverse order with a 1-second delay.
- `ledPattern4()`: Alternates between turning on odd and even-numbered LEDs, then turns them off in the same sequence with a 1-second delay.

## Usage Instructions

1. Assemble the circuit as per the circuit diagram.
2. Upload the provided code to the Arduino board.
3. Open the Serial Monitor from the Arduino IDE (Tools -> Serial Monitor) to view status messages.
4. Use the keypad to enter a pattern number (1, 2, 3, or 4) and observe the corresponding LED pattern.

## Example Output

- Pressing `1` on the keypad will sequentially turn all LEDs on and off.
- Pressing `2` on the keypad will turn each LED on and off one by one.
- Pressing `3` on the keypad will sequentially turn all LEDs on and off in reverse order.
- Pressing `4` on the keypad will turn on and off odd-numbered and then even-numbered LEDs.

This project provides a basic understanding of using a keypad to control LED patterns on an Arduino. Experiment with different patterns and expand the project to include more complex sequences and behaviors!

---


