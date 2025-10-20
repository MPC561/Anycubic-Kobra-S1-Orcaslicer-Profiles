Profiles:

In his repo you will find a config bundle for OrcaSlicer with PETG and ABS profiles

In detail:
-	a printer profile with new startcode for the Kobra S1
-	Multiple processprofiles for layer heights of 0.08mm, 0.12mm, 0.16mm, 0.2mm, 0.24mm and per layer height a "standard" and "structural" process profile
-	Two Material-/Filamentprofiles, one for generic PETG and one for generic ABS


Printer profile:

The new printer profile has an enhanced startcode. It should, due to enhanced nozzle clean mechanisms, have a better Z-Offset, which will lead to a better and more stable first layer
It´s suggested to use a better nozzle cleaner than the original one from Anycubic. The original cleans the top of the nozzle but not all sides of the nozzle. The enhanced nozzle wiper cleans the nozzle from all sides. The enhanced one can be ordered via Aliexpress:

<img width="533" height="463" alt="Bildschirmfoto 2025-10-13 um 11 05 28" src="https://github.com/user-attachments/assets/d71ba27d-18cd-4daa-847d-0aa1a7ac1752" />


In addition I introduced the hated and beloved "bubble". This "bubble" is created just before printing the purgeline. Means, the Nozzle extrudes so much material that the nozzle is surrounded by material. The material cools only a bit down and then the nozzle is lifted up in Z-direction. The old material which was not cleaned by the nozzle wiper should be kept in the extruded material included. The idea I overtook from the Sovol SV08 startcode where this is done and I loved it, as it cleaned the nozzle well.


Processprofiles:

The process profiles are mainly based on the Prusa Mk4s profiles. Me uses this profiles, and the philosophy behind, in all of my printers, more or less modified.

As mentioned already. For every layer hight I deliver a "Standard" and a "Structural" profile

The "Standard" profile is using the possibilities of the printer more than the Anycubic from Anycubid delivered profile. The acceleratsions a set to high values which may, also with Resonance Compenstaion, lead to a slight "Ringing". On the other hand the print speed for BigSize Models should increase Models drasticaly. It will print fast if the Layer Times are high and slow where the layer times are small.

The "Structural" profile is intended to be used for print objects where you want to avoid to much "Ringing" and "Smoothing", for instance for small, granular and detailed structures.
I reduced the acceleration values here dratsically. The resonance compensation measurements I did showed that the S1 is capable to print up to 5000mm/s2 without to much "ringing" and "smoothing"


Filament profiles:

I had some problems with the high retract values which Anycubic has in the Anycubic PETG Filament profile. In the filament override settings was a retract of 1,5mm set. Which such a high value I had smal holes in my prints on the retract (and seam) positions. I reduced this value drastically but this may lead to a bigger stringing probability. But, small stringing I can remove, holes I can not close.

In addition I mad some adaption in the cooling paramters. Especially smaller, detailed structures/overhangs should look now much more better.

In addition I removed the castration of the printer which Anycubic did in their filament profiles for ABS/PETG. They configured very small volumetric speed of 12/15 mm3/s.

My measurements show, that PETG can be printed up to 23mm3/s, ABS much more up to 28mm3/s. To have a reserve, I introduced 20mm3/s in my profiles. This should increase printing speed drastically for bigger print objects.


