# freedi-eddy
Adding an eddy duo probe to the qidi x-max 3 running latest freedi

I will probably add additional configurations later as I'm working on adding the LH Pico MMU also

## How to use:
### 1 - Print the bracket
I used ASA filament, it prints well without supports, I suggest adding a brim and also printing the first layer at 15mm/s

### 2 - Take off the toolhead front and back covers
Self explanatory

### 3 - Route the cable
Note: I had an idea to use an Adafruit USB C hub to chain the probe together with the toolhead, but it took a while to arrive so I used the Eddy USB cable
Route the USB cable through the e-chain, start from the toolhead and route it to the mainboard.
Roll the overlength of the cable into an "8" (don't coil it up).

### 4 - Remove the BLTouch/Inductive probe.
Screws will be re-used. You can disconnect the probe.

### 5 - Mount the Eddy probe
#### 5.1 - Remove the Eddy probe covers
#### 5.2 - Put the back cover back on, then screw it into the bracket
#### 5.3 - Mount the bracket onto the toolhead

### 6 - Back up your original config, then add or merge mine. Make sure to copy both the printer.cfg and the macros.cfg

### 7 - Add the device paths to the config
#### 7.1 - Copy the MCU toolhead path from your backup into the [mcu Toolhead] section of the new printer.cfg, then save (no restart)
#### 7.2 - In Mainsail, go to "Machine" -> "Devices" -> "Serial" -> "Refresh"
#### 7.3 - Copy the rp2040 "Path by ID" (probably on ttyACM1 if you have nothing else connected) and paste it into [mcu eddy] section of printer.cfg
#### 7.4 - Save and restart

### 8 - Copy over the begin and end codes
#### 8.1 - Paste the contents of begin_code.txt into your slicer begin code
#### 8.2 - Paste the contents of end_code.txt into your slicer end code

### 9 - Calibrate by following steps 2 through 4 (or 5 as required) from the Eddy probe onwards: https://github.com/bigtreetech/Eddy?tab=readme-ov-file#2-drive-current-calibration
Note: I already included some values regarding calibration, you should still redo everything as no 2 machines are the same
Note2: I increment the drive "reg_drive_current" to 16, your mileage may vary, check the FAQ section of the Eddy github link

### 10 - Do a test print, let me know what glitches you encounter
