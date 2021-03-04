# Raise3D-E2
Profile for Raise3D E2 printer for use in PrusaSlicer 2.3.0-Beta3 and newer.

### Profile status
0.4mm profiles are tuned in.
0.6mm profiles are tuned in.
IDEX and different modes are working

#### Filament profiles:
* PLA
* PETG
* WOOD
* ABS
* FLEX
* PVA

##### What works:
* Left printhead mode
* Right printhead mode
* Mirror mode
* Duplicate mode
* Dual extrusion mode

##### What sort of works:
* ~~Dual extrusion, some users have had mixed experience with this. small parts work, but large parts seems to create a crash between X and U axis.~~

##### What is not working:
* Full mesh bed leveling around the object, like Ideamaker. As of now it does mesh bed level as you have set on the Printer. Either 3x3 or 6x9.
Seems like the only option as of now is to run a PostProcess script to generate a "Bounding box" to probe around print area: https://forum.duet3d.com/topic/15302/cura-script-to-automatically-probe-only-printed-area/57


## Importing the profile
For importing the profile, download Raise3D - E2.ini file in the main folder.
Start Prusaslicer -> File -> Import -> Import Config Bundle...

Then you are set :)



## Manually importing the config files
If you want to manually import the config files, download the whole repository
Move the folders in "Config files" folder to (on windows) C:\Users\%username%\Appdata\Roaming\Prusaslicer-Beta\

Then the profiles should be available when you start Prusaslicer


## Using Overlay
If you want to use the Overlay.svg to get a better "view" of the Printbed, you can do so this way:

Prusaslicer -> Printer Settings -> General -> Size and coordinates -> Bed shape -> Texture -> Add the Overlay.svg there
You will need to do this for all the Printer profiles.

**View of buildplate with Overlay.svg:**
![Screenshot](Overlay.PNG)


**View of buildplate without Overlay.svg:**
![Screenshot](Without_Overlay.PNG)

# Changelog

## [v3] - 2021-03-04
### Notes:

* Added nozzle diameter check on filament profiles
* Added 0.6n filament profiles
* 0.6n: Removed Deretract speed (similiar as Retract speed)
* 0.6n: Removed M221 flow rate in Start/End G-code (respect Filament multiplier instead)
* 0.6n: Adjusted retraction from 0.1mm to 0.6
* 0.6n: Added Lift Z 0.2mm
* 0.6n: Adjusted retract when toolchange from 2mm to 1mm
* 0.6n: Removed retract before travel 
* 0.6n: Tuned Bridge flow ratio (from 0.95 to 1.4)
* 0.6n: Adjusted bridgespeed from 25mm/s to 15mm/s
* 0.6n: Activated option 'External perimeters first'
* 0.6n: Deactivated option 'Ensure vertical shell thickness'
* 0.6n: Adjusted Gap fill speed from 50mm/s to 25mm/s due to printer wobbling
* 0.6n: Adjusted infill overlap from 30% to 0%
* 0.6n: Removed max volumetric speed values
* 0.6n: Adjusted seam position to aligned
* 0.6n: Tuned support settings
* 0.6n: Adjusted printspeeds



## [v2.2] - 2021-02-16
### Notes:

* Tuned 0.4n profiles
* Increased print speed
* Added better break-away supportsettings
* Fine-tuned retraction
* Fine-tuned bridging settings
* Adjusted Printer acceleration speeds for better time-estimate
* Removed Flow rate in Start/End G-code
* Tuned PLA profile for better cooling



## [v2.1] - 2021-01-19
### Notes:

* Moved M605 to start of G-code for the printer to accept it each time

## [v2.0] - 2021-01-08
### Notes:

* Tuned start/end G-codes
* Added Pressure Advance (M572) values for filament profiles
* Added 0.4mm nozzle profiles

## [v1.4] - 2020-12-27
### Notes:

* Added max_volumetric_speed based on filament type
* Added 0.2mm Z-hop
* Added Flex profile
* Added Extruder max_volumetric_speed
* Tuned retraction to 0.1mm (from 0.5mm)
* Added feed, jerk and acceleration speeds to get time_estimate more reliable.
* Removed silent_mode as that is not supported on this printer.
* Added 0.4mm nozzle printer-profiles (print profiles yet to be added)


## [v1.3] - 2020-12-21
### Notes:

* Adjusted Min/Max layer height according to nozzle size (for better variable layerheight procedure)
* Tuned support settings for 0.6mm nozzle
* Added filament_weight on output filename
* Tuned Ironing for 0.6mm nozzle
* Tuned retraction for dual extrusion prints


## [v1.2] - 2020-12-18
### Notes:

* Dual extrusion is working!
* Optimized start and end G-codes


## [v1.1.1] - 2020-12-17
### Notes:

Added RaiseTouch specific Gcodes
* End of Start G-code: M1001
* Start of End G-code: M1002
* Pause/Colorchange G-code: M2000


## [v1.1] - 2020-12-17
### Notes:

* Edit compatible printers to accept every PRINTER_MODEL_E2 independendent of nozzle size
* Edit compatible print profiles to accept every PRINTER_MODEL_E2 and choose appropriate profiles depending of nozzle size
* Changed default filament color to Orange
* Optimized Filament profiles
* Add WOOD filament profile
* Changed start G-code with Intro line Z0.35 instead of Z0.2 for increased throughput of filament at intro line.
* Added Z5 before move to intro line, to prevent nozzle scraping heatbed while moving

Still not working correctly:
* Dual extrusion with large parts, small parts seems to work ok now.


## [v1.0] - 2020-12-16
### Notes
0.6mm profiles are pretty much done.
Some work remains on Dual extrusion print profile as some users still report crash in X and U axis while printing some objects.

Profiles are tuned in for 0.6mm nozzles.
* Added auto-select on the Print profiles dependend on Nozzle type.
* Reworked Print profile names
* Reworked Filament profile names

Will make a try at 0.4mm nozzles next week if i get the time.


## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

