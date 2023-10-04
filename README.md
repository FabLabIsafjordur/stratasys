# How to use the Dimension 1200SST 3D printers

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