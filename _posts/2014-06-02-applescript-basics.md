---
title:  "Applescript - The basics"
date:   2014-06-02 22:00:00
tags:
- AppleScript
---
Dette indlæg er til Mac folket. Det omhandler nemlig noget så spændende som **Applescript**.   
Dette kunne måske lyde skræmmende for den gængse "ikke udviklertype" macbruger. Men det skulle gerne i løbet af indlægget stå klart, at det faktisk ikke er helt så kompleks og ret nemt at komme igang med.

*AppleScript* er dog ikke noget jeg hurtigt kan gennemgå i én artikel. Så dette vil være en hurtig intro til nogle af de sjove ting man kan lave med *AppleScript*, som forhåbentlig vil få Jer igang med selv at lege med sproget.

##Hvad er AppleScript
Men hvad er *AppleScript*, og hvorfor er det værd at vide noget om som Macbruger? *AppleScript* er et simpelt engelsklignende scriptingsprog, der er indbygget i Mac OS X. Sproget har en dyb integration til hele operativsystemet, så det kan bruges både til at automatisere rigtigt mange OS specifikke handlinger, men også handlinger knyttet til de installerede programmer.
Denne dybe integration kommer fra brugen af såkaldte *AppleEvents*. Dette er en grundlæggende kommunikationsform for Mac applikationer, der har været brugt helt tilbage fra før Mac OS X tiden. Disse simple events bliver brugt hele vejen igennem OS X arkitekturen både til interne kommandoer såsom: Åben fil, Luk Finder vindue, klik på dette menupunkt osv. osv. Men også til kommunikation fra OS'et til de installerede programmer. Og mange af de applikationer man har installeret tilbyder faktisk et lille library af operationer man kan bruge direkte fra sit *AppleScript* til at udføre opgaver i programmet.

##AppleScript editor
Den nemmeste måde at komme igang med *AppleScripts* er via den indbyggede editor, *AppleScript Editor*.
![Editor](/blog-images/applescript1/1.png)
Editoren er opdelt i to felter. I det øverste felt skal man skrive sin kode, og i det nederste felt kan man se resultatet af den kørte kode.

##Kompileret eller fortolket
Nu vil jeg ikke komme ud i en lang snak omkring kompilerede og fortolkede sprog - men mange vil nok falde over "Compile" knappen i editoren. Dette betyder ikke at *AppleScript* i den traditionelle C/Java forstand er et kompileret sprog. Der sker godtnok en kompilering af koden over til noget lidt nærmere maskinsprog. Men dette sker Run-time. Så det "compile" knappen hjælper os med er nærmere en parsning og hjælp til at validere vores syntaks. Det vil sige, den fortæller os ikke om scriptet laver det vi forventer, men mere om vi har lavet nogle slå-fejl eller har brugt forkerte navne på operationer.

##Det første *AppleScript*
Men lad os komme igang med at skrive det første *AppleScript*. Dette vil ikke være en introduktion til programmering, og det er som sagt heller ikke nødvendigt.

Men her er vores første script:
{% gist mortensieker/29cbada42dc9be918f45 %}
Som sagt så har sproget en syntaks, der minder rigtigt meget om det engelske sprog. 

Så det vi i denne type script gør er ```tell application "Application name"```. Her fortæller vi at vi vil have applikation X til at gøre noget.
Denne blok afsluttes med en ```end tell``` for at fortælle compileren at nu er vi færdig med at udføre det vi vil have applikation X til at gøre.
Applikationsnavnet er det navn applikationen har i Jeres Application folder. Dette navn skal altid sættes i citationstegn.

Indeni sådan vores "tell blok" fortæller vi så hvad vi vil have den angivne application til at lave. Dette foregår også via vores pseudo engelsklignende sprog. I dette tilfælde ```make new Finder window```.

##Library
Ligesom med andre programmeringssprog så er der naturligvis også et [API](http://da.wikipedia.org/wiki/Application_programming_interface) hvor man kan finde mere information om hvilke programmer, der tilbyder *AppleScript* integration og hvilke metoder de udstiller. Dette er det såkaldte "Library". 
![Library](/blog-images/applescript1/2.png)

Når du åbner *Library* første gang så er det ikke alle apps du kan finde derinde. Men via den lille "plus" knap i øverste venstre side kan du tilføje de apps du gerne vil interagere med. Hvis du dobbeltklikker på den app du gerne vil kode op imod, så kommer der en ny dialog frem hvor man kan se alle de kommandoer man kan kalde i applikationen.
![API](/blog-images/applescript1/3.png)

##Thats it...
Mere skal der sådanset ikke til, og du er nu klar til selv at gå ud og lave din egne *AppleScripts*. Det virker måske meget simpelt lige nu, og det er hele hemmeligheden... Det er det også... 

Selv med simple scripts kan man lave utroligt meget.
Noget der også gør sproget utroligt brugbart er at rigtigt rigtigt mange apps tilbyder at køre *Applescripts* som en del af deres workflows.
Heriblandt apps såsom **[Alfred][alfred]**, **[Hazel](http://infiniteloop.dk/2014/01/17/hazel/)**, **[Text Expander](https://smilesoftware.com/TextExpander/index.html)** osv. osv.

Et par eksempler på scripts jeg bruger næsten hver dag er:
 
- Når jeg skal til at optage et podcast så vil jeg gerne have så lidt kørende i baggrunden som overhovedet muligt. Jeg har derfor lavet et lille [Alfred][alfred] workflow som i bund og grund bare kører en mængde små *AppleScripts*, der lukker alle de applikationer jeg ved tager mange ressourcer, samt pauser alle mine backup programmer.
På samme måde har jeg et lille workflow, der kører scripts der starter alt op igen når jeg er færdig.
- Jeg har lavet et script til at interagere med [MAMP](http://www.mamp.info/en/): Start, stop osv. osv.
- Jeg har scripts, der hjælper mig med at deaktivere og aktivere de ting jeg vil have kørende når jeg tager min laptop med mig og reelt ikke vil have den til at fungere som en "desktop" computer længere.

Det korte af det lange er. Der er uanede muligheder og det er super super nemt at komme igang.

Rigtig god fornøjelse.

[alfred]: http://www.alfredapp.com/