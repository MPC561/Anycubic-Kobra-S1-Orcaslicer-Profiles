Profile:

Angehangen ist ein config bundle für den Orcaslicer mit PETG und ABS Profilen

Im Detail:
-	Ein Druckerprofil mit neuem Startcode für den Kobra S1
-	Multiple Prozessprofile für Layerhöhen von 0,08mm, 0,12mm, 0,16mm, 0,2mm, 0,24mm und für jede Layerhöhe jeweils eines genannt „Standard“ und eines genannt „Structural“ 
-	Zwei Material-/Filamentprofile, eines für Generisches PETG und eines für Generisches ABS



Druckerprofil:

Das neue Druckerprofil hat einen vereinfachtem Startcode. Ich habe anfangs den Startcode von Kreativling aus dem 3D Druck Forum verwendet. Der funktioniert exzellent und umgeht einige Probleme, die eine unsaubere Nozzle beim Z-Offset machen kann, braucht aber auch viel Zeit.
Dieses Profil hier basiert auf jenem Profil aber ist wesentlich schneller und sollte diese Probleme auch umgehen, am besten in Kombination mit einem der neuen Filamentabstreifer von Aliexpress die nicht nur zwei, sondern vier Seiten der Nozzle reinigen.

Ich halte nicht viel von dem original verbauten Filamentabstreifer. Der streift nicht alles Filament ab. Deswegen „sifft“ der Drucker mitunter bei den ersten Layern, weil altes Filament doch noch runtertropft/sich löst. Das vermeide ich, indem ich eine „Bubble“ vorm Druckbeginn mache. Diese Bubble umschließt die Nozzle und schließt damit auch altes, noch an der Nozzle weiter oben klebendes, Filament ein. Die Bubble kühlt dann leicht ab und wenn ich die Nozzle abhebe um danach die Purgeline zu ziehen, bleibt das alte Filament daran hängen. Die Idee habe ich vom Sovol SV08, da wird diese „Bubble“ auch gemacht und das funktioniert wirklich gut.


Prozessprofile:

Die Prozessprofile basieren primär auf Prusa Profilen vom vom Mk4s.
Ich nutze diese Profile, leicht modifiziert, bei allen meinen aktiven Druckern.

Dabei gibt es zu jeder Layerhöhe ein „Standard“ und ein „Structural“ Profil. 

Das Standardprofil reizt die Möglichkeiten des Druckers mehr aus und nimmt ggf. eher ein gewisses „Ringing“ in Kauf, sprich arbeitet auch mit hohen Beschleunigungswerten und druckt mit hohen Druckgeschwindigkeiten (da wo die Layerzeiten hoch genug sind) und langsam da wo die Layerzeiten eher klein sind.  

Das „Structural“ Profil zielt auf Druckobjekte ab, bei denen man „Ringing“ und „Smoothing“ vermeiden möchte, weil zum Beispiel sehr kleine, feine Strukturen gedruckt werden sollen. Bei denen kommt es nicht mal auf die Maximal Geschwindigkeiten im Prozessprofil an, sondern das die Beschleunigungswerte hinreichend gering sind.

Der Kobra S1 kann Beschleunigungen bis ca. 5000mm/s2 ohne „Ringing“ und mit geringem „Smoothing“ drucken. „Smoothing“ bedeutet ein „Weichbügeln“ von Details, ähnlich einem Filter den man über ein Selfie legt um Pickel und Hautunreinheiten zu verbergen, sprich man verliert dabei ggf. etwas, das man hier bei feineren Strukturen  nicht verlieren möchte.
Diese maximalen ermittelten 5000mm/s2, und die Wahl des richtigen Inputshapers, mit den korrespondierenden „Vibrations“ und „Smoothing“ Werten sieht man leider nur via Mainsail/Fluidd WebGUI wenn man Rinkenhals installiert hat.  

Eine weitere Unterscheidung der Prozessprofile nach Materialtypen oder Kriterien wie „Stabil“ nutze ich bei den Standardfilamenten ABS/ASA/PETG/PLA nicht. Will ich etwas Stabileres drehe ich die Anzahl der „Walls“, der „Top/Bottom Layer“ hoch und erhöhe den „Infill“ Prozentsatz und ggf. noch paar andere Parameter. 



Materialprofile:

In den Materialprofilen sind die wichtigsten Einstellungen enthalten. Sie können sogar Einstellung im Druckerprofil, via der Sektion „Filament Overrides“, überschreiben. Sehr wichtig zum Beispiel bei PETG, wo man einen höheren Retract als bei PLA/ABS einstellt um Stringing zu vermeiden und ohne das Druckerprofil selber ändern zu müssen. 

Ich hatte mit den abartig hohen Retract bei PETG (Filament Overrides) einige Probleme an den Retract Positionen (sind meist auch die „Seam“ Stellen). Da hatte ich „Löcher“ im Druckobjekt. Den Wert habe ich drastisch verringert, auch wenn die Stringing Wahrscheinlichkeit dadurh etwas steigt. Stringing kann ich entfernen. Löcher im Druckobjekt kann ich nicht auffüllen.

Dann habe ich basierend auf dem Anycubic Filamenteinstellungen einige Optimierungen bei PETG und ABS bei den Kühlungseinstellungen vorgenommen. Die sollte man auch bei einem anderen Filament einsetzen können. Speziell sehr filigrane Strukturen und überhänge sollten damit jetzt besser aussehen.


Ich nehme hier in den Material/Filament Profilen auch noch die starke Kastrierung der Druckgeschwindigkeiten via volumetrischen Fluss raus, die Anycubic in seinen Profilen hat. Eine Limitierung auf 12mm3/s bei PETG bzw. 15mm3/s bei ABS ist Nonsens. Der Kobra S1 schafft bei PETG ca. 23mm3/s und bei ABS noch wesentlich mehr. Getestet habe ich das nichtmal mit HS-Filament. Also sollte ein Wert von ca. 20mm3/s vollkommen sicher sein, selbst bei PETG bzw. ABS anderer Hersteller. Das verringert die Druckgeschwindigkeit bei größeren Druckobjekten signifikant.
