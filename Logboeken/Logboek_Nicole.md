# Logboek Omics 
Door Nicole Bovenga

#### 20-04-2026
Als start heb ik met mijn groepje overlegd wat onze waarden zijn. Op basis daarvan heb ik deze samenwerkingsovereenkomst gemaakt:

* Elke les aanwezig tenzij anders overlegd.
* Afmelden bij ziekte en niet-tijdige aanwezigheid.
* Wekelijkse overleg wat er is gedaan en wat we gaan doen.
* Contact via Teams en WhatsApp.
* Deadlines worden vooraf afgesproken en nageleefd. Afspraak is afspraak.
* Taken worden eerlijk verdeeld en niet andermans taken doen zonder overleg.
* Als iemand deze overeenkomsten niet naleeft, behouden anderen het recht om naar de docent te stappen.

#### 21-04-2026

Dit is de link naar het wetenschappelijk artikel die wij gaan "nabootsen"
https://www.sciencedirect.com/science/article/pii/S2589004225016438?via%3Dihub

Data staat nu op assemblix in het mapje Thema08\Lypolyse. 

Github: https://github.com/Nikkieeex/Multi-omics_lypolysis_brown_adipocytes

Geef hier uitleg wat we dit project moeten doen!!

Ze onderzoeken hoe bruine vetcellen reageren wanneer ze worden gestimuleerd om vet af te breken en warmte te produceren. 
Dit proces heet thermogene lipolyse en wordt in het experiment opgewekt door de cellen bloot te stellen aan norepinefrine. 
Tijdens dit experiment wordt op meerdere tijdstippen gemeten.


#### 22-04-2026

Onze docent Tsjerk Wassenaar heeft vandaag uitleg gegeven over preproccesing. Ik heb daar wat notities over gemaakt en een stappenplan.

Stappen moeten chronologisch:
 
1.  Artikel lezen (iedereen voorzich) 
Multi-omics analysis of thermogenic lipolysis in brown adipocytes
 
2. Vectorize data (Joris)
Joris heeft alle data gedownload en we kijken naar welke bestanden nuttig zijn voor ons. Er zitten ook nog .raw data tussen en alle drie omics mogen nog gemapped worden tegen referentie genoom. 
 
Wanneer deze eerste stap is afgerond gaat Joris een word document opstellen voor ons artikel. 
Tip van Tsjerk is kijk niet naar opmaakt en hou het simpel, vanwege het herformatteren van artikel later. Hoofdvraag artikel: focus op de methode in het artikel en niet hoofdvraag op biologie zetten
 
3. Ieder een omics (Gea, Janine, Nicole)
Transcriptomics: Gea
Metabolomics: Janine
Proteomics: Nicole
 
Hier duid Tsjerk om 3 veranderingen. 
Log transform, Goed kijken naar hoe de verdeling is. Kijk naar outliers en scheefheid
Normalize observations, Kijk naar samples dus horizontale rijen en normalize deze
Normalize features, Kijk naar features dus kolommen en normalize 
Er zijn 32 samples dus er moeten 32 features komen. Uitleg over features begin mei dus eerst naar eerste stappen kijken.
 
Uiteindelijke resultaat is een numpy.array. 
Wanneer je klaar bent met jouw deel voordat andere dat zijn kun je het volgende doen. Kijk naar de hoofdvraag van het referentie artikel. Wat is er wel en niet onderzocht en hoe kunnen wij onze eigen draai geven. 

Notes: 
Tsjerk heeft een library over regressie van tijd en het patroon in de data. Want we hebben verschillende tijdspunten (library heet chello). Dit kunnen we mogelijk later gebruiken na preprocessing stap. 
 
Logboek inhoud: wat je doet. hoe (methode) en wat er uitkomt


#### 04-05-2026

Ik kwam op google scolar een mooi artikel tegen die mij een beter beeld gaf van protomics. https://www.mdpi.com/2073-4425/15/12/1551

Ik heb ook een intressante tool gevonden genaamd MINIE. Het staat voor Multi-omic network inference from time-series data.
Het is een machine learning tool die ik later wel zou willen uittesten. Ik heb hem gevonden in een artikel op pubmed https://pmc.ncbi.nlm.nih.gov/articles/PMC12521560/

Leg meer uit Nicole


#### 07-05-2026

Ik heb 2 wetenschappelijke artikelen gelezen die lijken op ons project en daar heb ik veel van opgestoken. https://pubmed.ncbi.nlm.nih.gov/41827860/
Een van deze was een review paper en heb ik veel opgestoken over bruine vetcellen. 
De belangrijkste conclusie uit deze studies is dat bruine vetcellen (BAT) veel complexer en belangrijker zijn dan vroeger gedacht. 
Ze zijn niet alleen “warmteproducerende vetcellen”, maar actieve metabole regelcentra. Er werden ook onderzoeken benoemd waar
ze signaal eiwitten voor mogelijk endocriene verbanden en zelf darmmicrobiota verbanden zijn gevonden. We moeten wel voorzichtig conclusies trekken,
omdat de meeste onderzoeken alleen nog op muizen zijn gedaan. 


#### 08-05-2026

Voordat we de data kunnen analyseren moeten we kijken naar de data. De dataset bestaat uit meerdere 
MaxQuant-outputbestanden afkomstig van een LC-MS/MS proteomicsanalyse. De map bevat informatie op verschillende niveaus, 
waaronder 20.015 eiwitgroepen in proteinGroups.txt, 49.782 peptiden in peptides.txt, 349.521 peptide-identificaties in evidence.txt 
en 2.013.893 MS/MS-identificaties in msms.txt. Daarnaast bevat allPeptides.txt 1.096.681 peptidefeatures en msmsScans.txt ongeveer 
504.840 MS/MS-scans.
Ook zijn bestanden aanwezig voor kwaliteitscontrole (summary.txt) en post-translationele modificaties, zoals methionine-oxidatie 
(Oxidation (M)Sites.txt, 1.477 entries). Volgens de beschrijving in tables.pdf bevat proteinGroups.txt onder andere LFQ-intensiteiten,
peptide-aantallen en sequence coverage per eiwitgroep, waardoor dit bestand waarschijnlijk centraal zal staan in de verdere analyse 
van de proteomicsdata.