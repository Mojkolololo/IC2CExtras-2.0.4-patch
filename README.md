IC2CExtras 2.0.4 – Unofficial Crash Fix
This is an unofficial patched version of IC2CExtras 2.0.4 that fixes a crash occurring when playing with IC2 Classic 2.1.3 or newer.
The Problem
When opening the Ore Washing Plant or Thermal Centrifuge GUI, the game crashes with the following error:
java.lang.NoClassDefFoundError: ic2/core/inventory/gui/components/simple/ChargebarComponent
JEI also shows no recipes for these machines at all.
Root Cause
IC2CExtras 2.0.4 was compiled against an older version of IC2 Classic where a GUI class was named ChargebarComponent (lowercase 'b'). In IC2 Classic 2.1.3 and newer, this class was renamed to ChargeBarComponent (uppercase 'B'). Since Java is case-sensitive, the class could not be found at runtime, causing the crash.
The following 4 container classes were affected:

ContainerThermalCentrifuge
ContainerOreWashingPlant
ContainerElectricHeatGenerator
ContainerThermoElectricGenerator

The Fix
The compiled .class files inside the JAR were patched using a binary replacement, changing the incorrect reference ChargebarComponent to ChargeBarComponent in all 4 affected files. No source code changes were needed.
Affected Versions

Minecraft: 1.19.2
Forge: 43.x
IC2 Classic: 1.19.2-2.1.3 and newer
IC2CExtras: 2.0.4

Installation

Download IC2CExtras-2_0_4-patched.jar from the Releases page
Remove the original IC2CExtras-2.0.4.jar from your mods folder
Place the patched JAR into your mods folder
Launch the game

Disclaimer
This is an unofficial community patch and is not affiliated with or endorsed by the original author (trinsdar). The original mod can be found on CurseForge. Please report this issue to the original author so it can be fixed in an official release.
