---
<<<<<<< HEAD
sidebar: auto
prev: ./platforms-guide.md
description: Bobbies gids voor het maken van Custom Blokken!
---

# De Custom Blokken gids
_Bobbies gids voor het maken van custom blokken._

## Introductie
Deze handleiding vereist basiskennis over 3d modelleren en de Unity Engine. Er zijn een paar dingen nodig:

* De Unity Editor - specifieker, [Unity version 2018.1.6f1](https://download.unity3d.com/download_unity/57cc34175ccf/Windows64EditorInstaller/UnitySetup64-2018.1.6f1.exe).
* Het [custom notes Unity project](https://github.com/legoandmars/CustomNotesUnityProject/archive/master.zip).
* Als je nog geen mesh hebt wat je wilt gebruiken, heb je een 3d modelleringsprogramma nodig. Persoonlijk stel ik [Blender](https://www.blender.org/) voor.
* Afhankelijk van wat je precies maakt, is een fotobewerkingssoftware zoals [Photoshop](https://www.adobe.com/products/photoshop.html) of [GIMP](https://www.gimp.org/downloads/) mogelijk nodig.

## Unity Project
::: danger WAARSCHUWING
Zorg ervoor dat je Unity versie 2018.1.6f1 gebruikt!
::: Open de custom notes project met Unity.

![Unity Project](~@images/models/notes/unity_window.png)

In het hiërarchieën venster aan de linker kant zijn er enkele voorbeelden te vinden.

![Objecthiërarchie](~@images/models/notes/02.png)

Als je op een van deze voorbeeld blokken klikt, zie je dat er een `NoteDescriptor` aan gekoppeld is.

![NoteDescriptor](~@images/models/notes/03.png)

Laten we kort ingaan op wat elk van deze instellingen nou eigenlijk doen.

### Note Name & Author Name
Deze is redelijk makkelijk. Wat de naam van het blok en de naam van de auteur ook zijn, deze worden in het Custom Notes selectie UI weergegeven, zoals weergegeven in de afbeelding hieronder.

![Voorbeeld van note name en author name in het spel](~@images/models/notes/04.png)

### Icoon
Deze instelling neemt een afbeelding die zal worden gebruikt als icoon. Het icoon wordt weergegeven in de Custom Notes selectie UI, zoals gezien in de bovenstaande afbeelding.

### Disable Base Note Arrows
Als deze is ingeschakeld, zal deze instelling de standaard pijlen die aanwezig zijn op de blokken onzichtbaar maken. Opmerking: je moet de `NoteDotLeft` en `NoteDotRight` gameobjecten in jouw blok hebben als je deze optie wilt inschakelen.

### Uses Note Color
Als deze optie is ingeschakeld, gebruikt het de huidige kleuren van de speler om je blokken in de goeie kleur te tinten. Dit stelt je blokken in staat om `CustomColors` te ondersteunen. Als je dit goed wilt gebruiken, zorg er dan voor dat je de sectie leest die gericht is aan het maken van jouw blokken met custom kleuren.

### Note Color Strength
Deze optie wordt alleen gebruikt als `Uses Note Color` is ingeschakeld. Note Color Strength definieert hoe sterk de tint word die op je blokken toegepast is, en is standaard 1. Hoe lager je dit nummer maakt, hoe subtieler de tint zal zijn.

## Het maken van een blok
Je zou al een 3D-model moeten hebben wat je gaat gebruiken voor je blok. Voor deze tutorial ga ik een eenvoudig triangle mesh gebruiken wat ik gemaakt heb in blender. Importeer je model in het project.

![Importeren in het unity project](~@images/models/notes/05.png)

Nadat je je model hebt geïmporteerd, maak je een nieuw leeg `GameObject` in de hiërarchie weergave en noem het hoe je wilt dat je blok gaat heten. Ik zal die van mij `TriangleNote` noemen.

![Een nieuw gameobject maken](~@images/models/notes/07.png)

In het `GameObject` van jouw blok klik je op `Add Component` en voeg je een `NoteDescriptor` toe. Maak je voor nu geen zorgen over het wijzigen van de opties in de `NoteDescriptor`, dat doen we later.

![Een NoteDescriptor toevoegen](~@images/models/notes/08.png)

Nu kunnen we beginnen met toevoegen van children aan het belangrijkste GameObject van ons blok. `NoteLeft` en `NoteRight` zijn de twee vereiste blokken, maar je kan ook een `NoteDotRight`, `NoteDotLeft` of `NoteBomb` toevoegen aan je hoofd GameObject. Voor het doel van deze gids ga ik alleen maar een `NoteLeft` en `NoteRight` maken.

Maak een nieuw leeg GameObject in jouw hoofd GameObject en noem het `NoteLeft`.

![Een leeg GameObject maken in TriangleNote](~@images/models/notes/09.png)

![Toont de hiërarchie van TriangleNote en NoteLeft](~@images/models/notes/10.png)

`NoteLeft` zal dienen als een soort "container" voor alle GameObjecten die meshes bevatten in ons blok. We kunnen onze meshes vrij positioneren en draaien als we ze in een aparte GameObject plaatsen in `NoteLeft`, wat we niet zouden kunnen doen als we gewoon mesh onderdelen direct zouden toevoegen aan het `NoteLeft` GameObject.

Sleep jouw geïmporteerde mesh op `NoteLeft` in het hiërarchieën scherm.

![Het slepen van het mesh op NoteLeft](~@images/models/notes/note_drag.png)

![Het slepen van het mesh op NoteLeft](~@images/models/notes/56.png)

Je zou nu je geïmporteerde mesh als een child GameObject van `NoteLeft` moeten hebben. Afhankelijk van het modelleringsprogramma wat je hebt gebruikt, moet je sommige niet-mesh objecten verwijderen. Als je objecten in jouw mesh ziet die `Camera` of `Lamp` heten, **ZORG DAN DAT JE DEZE VERWIJDERT!** Als je de "breaking the prefab instance" waarschuwing ziet, druk dan op "Continue".

![Toont hiërarchie en wijst naar Camera](~@images/models/notes/64.png)

![Druk op continue op de waarschuwing](~@images/models/notes/59.png)

Klik op het object wat je net hebt toegevoegd en zorg ervoor dat het een positie heeft van `(0,0,0)`

![Controleren van positie](~@images/models/notes/61.png)

Zodra je het mesh hebt geselecteerd, moet je het naar de grootte van een blok in het spel maken. Selecteer `NoteLeft` en plaats het in de buurt van het `TemplateNotesize`. Het `TemplateNoteSize` zou het witte vierkant moeten zijn in jouw project.

::: warning WAARSCHUWING Zorg ervoor dat je `NoteLeft` selecteert wanneer je jouw blok verplaatst. Als je per ongeluk de children van `NoteLeft` verplaatst, kloppen de meshes niet meer! De meshes in `NoteLeft` zouden bijna ALTIJD op positie `(0,0,0)` moeten zijn, tenzij je ze doelbewust aanpast. :::

![Laat het mesh zien naast TemplateNoteSize](~@images/models/notes/62.png)

Zodra je de `NoteLeft` hebt verplaatst om dichterbij de `TemplateNotesize` te zijn, selecteer je de scale tool links bovenin van het scherm.

![Selecteren van het scaling tool](~@images/models/notes/63.png)

Met het GameObject in `NoteLeft` geselecteerd, klik en sleep het grijze vierkant totdat het blok ongeveer dezelfde grootte heeft als het `TemplateNoteSize`.

![Laat zien hoe je het scale tool gebruikt](~@images/models/notes/60.png)

::: warning WAARSCHUWING Zorg ervoor dat je de schaal van de objecten IN `NoteLeft` aanpast. `NoteLeft` zal altijd een geforceerde schaal hebben van 1, dus als je de schaal op iets anders zet dan `(1,1,1)` zal je model er anders uitzien in het spel! :::

![Laat het goed geschaalde mesh zien naast TemplateNoteSize](~@images/models/notes/66.png)

Zoals je kunt zien, is de schaal die werkte voor mijn mesh ongeveer `(0,65,0,65)`. Deze waarde zal anders kunnen zijn afhankelijk van het mesh dat je gebruikt. Als je het mesh niet precies even groot kan krijgen als `TemplateNotesize`, maak je dan niet te veel zorgen want het hoeft niet precies te zijn. Houd er rekening mee dat het over het algemeen beter is als een blok beetje te groot is dan dat het een beetje te klein is.

::: warning WAARSCHUWING Zorg ervoor dat je blokken in de juiste richting staan. Kijk naar de richting van alle andere blokken in het scherm, en zorg dat je meshes dezelfde kant op staan. **ONTHOUD**: Het `NoteLeft` GameObject moet altijd een rotatie hebben van `(0,0,0)`. Als je je blok moet roteren, draai dan niet `NoteLeft`, maar draai in plaats daarvan de meshes die er in zitten! :::

## Materials toevoegen
Nu het mesh goed geschaald is, kunnen we er een material aan toevoegen. Klik in het projectvenster met de rechtermuisknop op `Materials` en doe vervolgens `Create->Material`. Omdat dit het material voor de mesh van mijn `LeftNote` zal zijn, noem ik het `LeftMaterial`.

![Het maken van een nieuw material](~@images/models/notes/17.png)

Nu we LeftMaterial hebben, moeten we kiezen welke shader we daarvoor gaan gebruiken. Als je een van de standaard Unity shaders gebruikt, zullen ze er niet goed uitzien in het spel. dus moeten we een van de `BeatSaber` shaders gebruiken.

![Het instellen van de shader voor het nieuwe material](~@images/models/notes/18.png)

Voor mijn LeftMaterial, Ga ik `Unlit Glow` gebruiken. Maar, je kan ook een andere shader gebruiken afhankelijk van het mesh dat je gebruikt. Hier zijn de belangrijkste verschillen tussen de shaders:

* Lit glow is belicht en heeft dus schaduwen. Je kan de richting van het licht veranderen, en hoe sterk het is.
* Metallic maakt het material iets donkerder en laat je een metalen reflectie toevoegen.
* Unlit glow is vergelijkbaar met Lit glow maar is niet belicht en heeft dus geen schaduwen.
* Unlit glow cutout dither is hetzelfde als unlit glow maar laat je transparantie toevoegen aan je material.

Alle vier de shaders geven je ook de mogelijkheid om textures te gebruiken, hoewel Metallic het texture gebruikt voor reflectie in plaats van het direct toe te passen.

Zodra je je shader hebt geselecteerd, kies je een kleur voor je linker material. Aangezien dit het linker blok is, zal ik een roodachtige kleur kiezen.

![De kleur van het material kiezen](~@images/models/notes/19.png)

Nu de kleur is ingesteld, ga je terug naar je mesh en stel je het in als het material.

![Het materiaal op het mesh selecteren](~@images/models/notes/20.png)

![Het materiaal op het mesh selecteren](~@images/models/notes/21.png)

Jouw blok zou nu een material moeten hebben dat er normaal uit ziet in het spel. Nu moeten we een rechter blok maken en de stappen opnieuw doen. Klik met de rechtermuisknop op `NoteLeft` en `Duplicate` het. Noem het nieuwe blok `NoteRight`.

![Het linker blok dupliceren](~@images/models/notes/67.png)

![Laat de hiërarchie van het blok zien, met NoteLeft en NoteRight](~@images/models/notes/68.png)

Volg nu de stappen hierboven opnieuw om een tweede material te maken. Zorg ervoor dat je dezelfde shader gebruikt als je wilt dat de blokken consistent zijn bij andere de kleuren. Voor mijn tweede material, ga ik het RightMaterial noemen en het een blauwe kleur geven.

![De kleur van het RightMaterial kiezen](~@images/models/notes/25.png)

Nu je het tweede material hebt pas je het toe op het mesh van `NoteRight`.

![Op de mesh van het rechter blok klikken](~@images/models/notes/69.png)

![Het selecteren van het rightnote material op het rightnote mesh](~@images/models/notes/27.png)

![Het selecteren van het rightnote material op het rightnote mesh](~@images/models/notes/28.png)

Je hebt nu twee blokken die beide de correcte texture hebben en die in het spel zullen verschijnen.

## Het exporteren van je blokken

Nu onze meshes en materials kloppen, kunnen we terug gaan naar `NoteDescriptor` en de instellingen ervan wijzigen. Ga naar het hoofd GameObject van jouw blok en bekijk de `NoteDescriptor` in het properties paneel.

![De NoteDescriptor laten zien](~@images/models/notes/29.png)

Stel `Note Name` in op hoe je wilt hoe jouw blok in het spel heet. Ik zet die van mij op "Triangle Notes". Stel ook de `Author Name` in op de naam waarmee je genoemd wilt worden. Ik zet die van mij op "Bobbie".

![De NoteDescriptor laten zien](~@images/models/notes/30.png)

::: warning WAARSCHUWING
Hoewel het technisch gezien niet nodig is wordt het sterk aanbevolen dat je een pictogram aan jouw blokken toevoegt, zodat ze gemakkelijker te identificeren zijn in de UI.
:::

Importeer de afbeelding die je gaat gebruiken voor het pictogram door op `Import New Asset` te klikken. Ik ga een driehoekig icoon gebruiken dat ik heb gemaakt.

![Een nieuwe asset importeren](~@images/models/notes/31.png)

Als jouw afbeelding transparant is, controleer dan of `Alpha Is Transparency` is aangevinkt en klik dan op apply.

![Alpha is transparency aan zetten](~@images/models/notes/32.png)

![Op apply klikken](~@images/models/notes/33.png)

Ga nu terug naar `NoteDescriptor` en selecteer de afbeelding die je zojuist hebt geïmporteerd.

![Het texture selecteren](~@images/models/notes/34.png)

![Het texture selecteren](~@images/models/notes/35.png)

Nu hebben we nog drie opties over - `Disable Base Note Arrows`, `Uses Note Color` en `Note Color Strength`. Omdat mijn model geen custom arrows heeft, ga ik `Disable Base Note Arrows` niet gebruiken, zodat we de standaard pijlen kunnen behouden. Ook ga ik `Uses Note Color` voor nu niet gebruiken, wat betekend dat we `Note Color Strength` ook niet hoeven te veranderen.

::: warning WAARSCHUWING Als je `Uses Note Color` gaat inschakelen - en ik raad je dat sterk aan - zorg ervoor dat je de sectie leest over hoe je custom colors correct ondersteunt! :::

![De NoteDescriptor laten zien](~@images/models/notes/36.png)

Nu onze `NoteDescriptor` opties volledig zijn ingesteld, kunnen we onze blokken exporteren met behulp van de `Note Exporter`. Om bij de `Note Exporter` te komen, zoeken we naar het tabblad aan de linkerkant van het scherm in de buurt van het `Hierarchy` tabblad.

![Op note exporter klikken](~@images/models/notes/70.png)

![Het blok laten zien in note exporter](~@images/models/notes/38.png)

Jouw blok zou bovenaan de `Note Exporter` moeten staan. Zodra je zeker weet dat al je `NoteDescriptor` instellingen correct zijn. klik op de export knop onder jouw blok in de `Note Exporter`. Zorg ervoor dat je het exporteert in jouw `Beat Saber/CustomNotes` map zodat je het in het spel kan testen.

::: warning WAARSCHUWING
Als je nog een blok nog een keer wilt exporteren, zorg er dan voor dat je de oude versie verwijdert. De Note Exporter zal geen blok exporteren als er al een blok in de map is met dezelfde naam.
:::

![Op export note klikken](~@images/models/notes/39.png)

![Het exporteren van het blok](~@images/models/notes/40.png)

Nu je blokken zijn geëxporteerd, kan je beat saber starten en kan je zien zien hoe ze er in het spel uitzien. Klik in beat saber op `Mods` en vervolgens op `Custom Notes`. Als je alles goed hebt gedaan, zal je jouw blokken in de lijst moeten zien.

![Het blok preview laten zien in het spel](~@images/models/notes/41.png)

Selecteer je blokken en probeer een level te spelen.

![Het blok in het spel laten zien](~@images/models/notes/42.png)

### Bekijk jouw blok in het spel zonder je bril op te zetten met FPFC
First Person Flying Controller (FPFC) is een startparameter wat gebruikt kan worden door Steam of Oculus gebruikers. FPFC opent Beat Saber op je computer en laat je het besturen met je toetsenbord en muis.

While a map is playing, pressing:

* `P` **P**auses the map
* `M` Returns to **m**enu if paused
* `R` **R**estarts the map if paused
* `C` Unpauses and **c**ontinues playing

You will need the SiraUtil mod in order move the camera while a map is playing. Without it, the camera is fixed in the floor at an undesirable angle. Install SiraUtil from Mod Assistant and run Beat Saber to create a config json file. SiraUtil also adds additional useful features such as camera FOV, sensitivity, and rebindable pause and exit controls. Edit the `SiraUtil.json` file in your `UserData` folder to tweak settings.

**For Steam Users:**

Open the game properties and add `fpfc` to the Steam launch options in the General tab. ![Fpfc launch options](~@images/mapping/fpfc.png)

**For Oculus Users:**

1. Rechtsklik op Beat Saber.exe en maak een snelkoppeling.
2. Bewerk het doel en voeg "fpfc" toe aan het einde ervan. Bijv: `C:\Program Files\Oculus\Software\Software\hyperbolic-magnetism-beat-saber\Beat Saber.exe" fpfc`

After installing the mods and adding the launch parameter you can then now move around and pause in a map. The default toggle key to switch between headset and mouse/keyboard control is <kbd>G</kbd>.

:::warning NOTE

* If you go back into vr and the game doesn't load in the headset either:
  * Press the <kbd>G</kbd> key until the headset displays the game  
    **==OR==**
  * Quit the game, remove the launch option, and relaunch the game.

* If the mod doesn't seem to be working, make sure the in-game Smooth Camera setting is disabled. :::

If everything looks good ingame, you should be finished! Make sure to try playing with your notes with your headset on at least once before releasing them.

## Custom Colors
This section is assuming you already have a custom note fully set up and simply want to add support for custom colors, which is highly recommended because it will almost always enhance the user experience.

CustomColor support works by tinting the notes to the current player-set color. If your material has a texture, lighter colors will be tinted more, whilst darker colors will be tinted less.

Go ahead and create a new material in the `Materials` folder. With CustomColor support, generally you're going to be using the same material for both the left and right note, so I'm going to name my material `NoteMaterial`.

![Creating a new material](~@images/models/notes/43.png)

Now select the shader you want to use for your note. If you're not sure which shader you want to use, refer back to the `Adding Materials` section of this guide. For my note, I'm going to use `Unlit Glow`.

![Selecting shader](~@images/models/notes/44.png)

Now apply this material to both your NoteLeft mesh and your NoteRight mesh. Make sure to apply it to BOTH!

![Clicking TriangleMesh](~@images/models/notes/71.png)

![Selecting Material](~@images/models/notes/46.png)

![Material selecteren](~@images/models/notes/47.png)

Now that you're done applying the material to all of your note's meshes, go back to the `NoteMaterial` in the inspector. To double check that your notes look good when using CustomColors, try messing around with the `Color` property; this is what property will be changed when the notes are tinted.

![Changing color of material](~@images/models/notes/48.png)

![De kleur van het material veranderen](~@images/models/notes/49.png)

![De kleur van het material veranderen](~@images/models/notes/50.png)

Once you've confirmed that the notes change color when you change the material's `Color` property, go to your note's main GameObject and go to the `NoteDescriptor`. Enable `Uses Note Color` and feel free to mess around with `Note Color Strength`. When Note Color Strength is at 1, it will tint the color with 100% strength. The lower you go from one, the more subtle it will be. For the purposes of this tutorial, I will be leaving `Note Color Strength` at one.

![Enabling uses note color](~@images/models/notes/51.png)

Your note should now be compatible with Custom Colors! Go ahead and re-export it. If you need a refresher, read the section on Exporting up above.

### Custom Colors uitschakelen op specifieke GameObjecten

In some cases, you may want CustomColors to not affect a certain mesh. For example, if you have a part of your model that needs to stay the same color, such as an arrow needing to be white. There is a simple solution to this problem.

In this example, I have two meshes inside of my `LeftNote` object. I want the `TriangleMesh` to be affected by custom colors, but not `SmallerTriangleMesh`.

![Double mesh example](~@images/models/notes/52.png)

![Double mesh hierarchy](~@images/models/notes/53.png)

All you have to do is go into the GameObjects that you do not want to be affected by custom colors and add a `Disable Note Color On GameObject` component. Any GameObject with this component will retain how it looks and not be affected by custom colors.

::: warning WARNING
Remember to apply these changes to all of the notes in your CustomNote!
:::

![Adding a disable note color on gameobject component](~@images/models/notes/54.png)
=======
sidebar: false
---

<!-- Disable header rule to hide page from search -->
<!-- markdownlint-disable MD041 -->
Sorry, deze pagina is nog niet vertaald.

Je kan:

* Overschakelen naar de Engelse versie vanuit het taal menu.
* Wachten totdat deze pagina is vertaald.
* Helpen met het vertalen van deze pagina vanuit het Engels, samen met de rest van de wiki, door [hier](https://forms.gle/e3BqA3poMjESARe76) te solliciteren!

[Ga terug naar de startpagina](/nl/)
>>>>>>> master
