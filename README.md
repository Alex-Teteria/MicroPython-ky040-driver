# KY-040 Rotary Encoder Driver
MicroPython driver for the KY-040 rotary encoder module.  
Features debouncing, state machine direction detection, and counts only full detents.

## Features
- Accurate direction detection using state machine
- Full detent counting (reduces sensitivity)
- Debounced rotary input and push button
- Simple callback interface

## Requirements

- MicroPython (ESP32, ESP8266, Raspberry Pi Pico, etc.)
- KY-040 rotary encoder module

## Usage

```python
def rotary_event(pos, direction, button=False):
    if button:
        print("Button pressed at position:", pos)
    else:
        print("Position:", pos, "Direction:", "CW" if direction > 0 else "CCW")

encoder = RotaryEncoder(clk_pin=16, dt_pin=17, sw_pin=18, callback=rotary_event)

while True:
    import utime
    utime.sleep(0.1)
```

## AI Assistance Notice

This codebase was generated with the assistance of AI tools (GitHub Copilot).  
All AI-generated code has been reviewed and adapted by a human prior to inclusion.

## License

See [LICENSE](LICENSE) for details.
