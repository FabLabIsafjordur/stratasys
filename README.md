# How to use the Dimension 1200SST 3D printers

![The printers](images/printers.jpg)
## Set up the software

Set up the [Stratasys Insight](files/InsightTo114-64Test-off.exe) software.

## Connect to the printer

You need to plug the printer into power to turn it on. It takes a moment to turn on and heat up. To connect to the printer and send print jobs, you need to connect the printer with a LAN cable to a router, and your computer needs to be connected to the same router.

To connect to the printer, first go into the menu on the LCD screen on the printer itself: Go into Maintenance -> System -> Set Network. You can select either Static IP or Dynamic IP. Dynamic IP worked for me. I selected that and noted the 3D printer's IP address.

Then you open Control Center to connect to the printer (it came with the Insight software installation).

![Control Center](images/control_center.jpg)*Stratasys Control Center*

To connect to the printer, select the Manage FDM Systems button near the top.

![FDM Systems - Add manually](images/fdm_systems-add_manually.jpg)*In the FDM Systems window, select Add Manually...*

![Add FDM System](images/add_fdm_system.jpg)*Here you input the IP address of the printer and you can also give it a name. Select Fortus 250mc in the dropdown menu at the bottom.*

Now your printer should appear in the list of FDM Systems.

## Load material

The modeling material (ABS) goes in the top tray and the support material (HIPS or SR-30) goes in the bottom tray. Let's go through how to load modeling material into the printer.

The printers have a self-load feature which you can access from the main menu by going into Material. This takes a long time. It's much quicker to do it manually.

Go into Maintenance -> Machine. Then you need to wait while the printer calibrates itself and warms up. Once it's warm you get another menu. Go into Head. The head will warm up to melting temperature. Once the head is hot you can choose which side you want to work on. Choose Model material. Then select Forward. The wheel in the printhead starts turning. You load the filament through the little hole inside the cartridge in the top bay in the printer (the one marked with 'M'). Then you need to push the filament into the printer, all the way up to the printhead, where it engages with the wheel and starts extruding through the tip.

Press Stop, then choose the Support side. Do the same thing with the HIPS material in the bottom bay (the one marked 'S').

## Print test part

Go to Maintenance -> System -> Test parts and choose a test part to print.
## Slice an STL model

Open the Insight software. 

![Insight](images/insight.jpg)

Select the icon that looks like the 3D printer.

The printer has been [modified](https://www.reddit.com/r/3Dprinting/comments/atwlq6/stratasys_insight_and_dimension_1200_sst/) to operate exactly like a Fortus 250 printer. So you configure the printer as Fortus 250.

![Modeler](images/modeler.jpg)

Here's a  [basic tutorial](https://www.youtube.com/watch?v=jisB9HIgxOc) on how to process parts in Insight.

[Here's a tip](https://www.youtube.com/watch?v=HfuPfBoaE1U) on modifying supports in Insight. There are more Insight tutorial videos on the same Youtube channel.

## Upgrade print options in Insight

Download and extract [kapaa.zip](files/kapaa.zip).

Go to C:\Program Files\Stratasys\Insight 11.4\modelers and rename the kapaa folder to kapaa_old. Copy the extracted kapaa folder to the location.

The next time you open Insight you should have more layer height options.

![Slice height](images/slice_height.jpg)

If you open Control Center you should also see a larger build volume.

![Build volume](images/build_volume.jpg)

## Reset the cartridge chips in the printer

1. Get a serial cable and a USB to serial adapter
1. Connect it to the back of the printer and your computer
1. Download [Material.zip](https://github.com/FabLabIsafjordur/stratasys/blob/main/files/Material.zip) and extract it
1. Open StrataToolNK.exe
1. The printer needs to be in IDLE or PAUSED state (not MATERIAL or PRINTING)
1. Select pclass at the top
1. Select Material or Support in OPTIONS
1. Select the right COM port
1. Then click 'Read Chip' - this will fill out the fields.
1. Click 'Create Chip' twice
1. Click 'Write Chip' and if you get an error, try clicking it again
1. Select Materials from the main menu of the printer and check if the cartridge is now full

## Reset the cartridge chips with an Arduino
When the printer says that your model or support cartridge is empty, it ejects the cartridge. Then you need to:

1. Get an Arduino and a 2.2 kΩ resistor
1. Download the [OneWire library](https://github.com/PaulStoffregen/OneWire) (click the Code button and download the zip folder)
1. Extract the zip folder to '...\Documents\Arduino\libraries'
1. Download the [Arduino IDE](https://www.arduino.cc/en/software)
1. Open [this Arduino program](files/onewireProxy.ino/) ([source](https://github.com/meawoppl/eepromTool-ds2433)) in the Arduino IDE and upload it to your Arduino board
1. Download [CartridgeWriter](https://github.com/slaytonrnd/CartridgeWriter) by clicking the Code button, downloading the zip folder and extracting it to any folder
1. Then you'll need to connect the 2.2 kΩ resistor and run CartridgeWriter to 'refill' the cartridge with material, as shown in this video tutorial:

[![Chip reset Youtube video](images/chip_reset_play.jpg)](https://www.youtube.com/watch?v=M94D-Pot6c8)

There are people selling Stratasys chip reset devices online for hundreds of dollars, but they are just Arduino boards in nice enclosures.

## Advanced printer settings

The printer has fixed printing temperatures, which are set in the material profiles. But you can manually set the chamber and tip temperatures with the [Maraca EX software](files/MaracaEX-V440-4274.zip), which is rarely seen online, since only Stratasys service technicians are supposed to have access to it.

## Further instructions

You'll can find the user guides and service manual in the [files](https://github.com/FabLabIsafjordur/stratasys/tree/main/files) folder.

## Specifications

- The SST 1200es uses Soluble Support Technology in which the supports are dissolved after printing in a solution
- Dimension SST 1200es: $32,900*
- Model material:
ABSplus in ivory, white, black, red, olive green, nectarine, fluorescent yellow, blue or gray.
- Support material:
Soluble Support Technology (SST)
- Build Size:
254 x 254 x 305 mm (10 x 10 x 12 inches)
- Layer Thickness:
.254 mm (.010 in.) or .33 mm. (.013 in.) of precisely deposited ABSplus model and support material.
- Workstation Compatibility:
Windows® XP / Windows Vista® / Windows® 7
- Network Connectivity:
Ethernet TCP/IP 10/100Base-T
- Size and Weight:
838 x 737 x 1143 mm (33 x 29 x 45 in.)
148 kg (326 lbs.)
- Power Requirements:
110-120 VAC, 60 Hz, minimum15A dedicated circuit;
or 220-240 VAC, 50/60 Hz, minimum 7A dedicated circuit
- Regulatory Compliance:
CE / ETL
