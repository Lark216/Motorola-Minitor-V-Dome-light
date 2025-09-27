import board
import neopixel
import time
import digitalio

# Motorla Basestation Input
din = digitalio.DigitalInOut(board.D0)
din.direction = digitalio.Direction.INPUT
din.pull = digitalio.Pull.UP

# External NeoPixel
neo = neopixel.NeoPixel(board.D10, 4, pixel_order=neopixel.GRBW)

# Timer
end_time = 0

while True:
    # Check for din
    if not din.value:  # Relay closed (signal detected)
        print("DIN Trigger received! Restarting 2-minute timer...")
        end_time = time.monotonic() + 120  # extend timer 2 minutes from now

    # If we are inside the active window, run the flash pattern
    if time.monotonic() < end_time:
        neo.fill((0, 255, 0, 0))   # RED
        time.sleep(0.25)
        neo.fill((0, 0, 255, 0))   # Blue 
        time.sleep(0.25)
    else:
        neo.fill((0, 0, 0, 0))  # Off when idle
        time.sleep(0.1)
