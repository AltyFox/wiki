---
sidebar: auto
prev: ./avatars-guide.md
next: ./notes-guide.md
description: Emma's gids voor het maken van custom platforms!
---

# De Custom Platforms gids
_Emma's gids voor het maken van custom platforms._

## Project
Open the current [Custom Platforms Project](https://github.com/affederaffe/CustomPlatforms/releases/latest) with Unity [2019.3.15f1](https://unity3d.com/get-unity/download/archive)

* You need to go to the tab that says `Unity 2019.x` and scroll down to 2019.3.15. This has to be installed with [Unity Hub](https://unity3d.com/get-unity/download).
* Need a guide on how to install? [Check out this Unity guide to Unity Hub.](https://docs.unity3d.com/Manual/LicensesAndActivation.html)

## Eerste stappen
![Custom Platform Script](~@images/models/platforms/CustomPlatformScript.png)

Maak een `Empty GameObject` door met re rechtermuisknop op het Hierarchy venster te klikken en `Create Empty` te selecteren. Zorg ervoor dat de positie in de Inspector wordt ingesteld op de oorsprong (0,0,0). Zoek in de inspecteur naar het `Custom Platform` script en pas het toe op dit Gameobject. Alles binnen dit object zal worden geëxporteerd wanneer de knop op het `Custom Platform` script wordt ingedrukt. In het script zijn er ook opties voor het exporteren. Hiermee schakel je delen van het originele platform uit (Voor wanneer je iets gedeeltelijk wilt vervangen).

## Modellen toevoegen
![Objects](~@images/models/platforms/Objects.png)

Drag all models you want in your Platform into the GameObject created in the second step and position them to your liking. Voor de materialen van de modellen zorg je ervoor dat je Beat Saber compatibele shaders gebruikt of degene die je kunt vinden in het Project, genaamd `_dark_replace` en `_glow_replace`. Dit zijn custom materialen die werken zoals de Beat Saber materialen, of te wel, react to the tube lights and mist.

### Track Rings
Het `Track Rings` script maakt track ringen zoals ze eruit zien in het spel. Om dit te bereiken moet het script een prefab nemen. Currently I haven't been able to figure out how to use a prefab in it, so I used a gameObject, that is part of the platform hierarchy, that I later moved off to `y = -1000`. For the ring-preview to show correctly, move this gameObject to (0,0,0) and adjust your settings and before importing move it off to somewhere offscreen.

Het inschakelen van het rotation effect, zorgt ervoor dat de ringen draaien door het opgegeven evenement, afhankelijk van de variabelen die gegeven zijn. (Ik heb hier nog niet mee gespeeld dus je zal moeten experimenten).

Het inschakelen van het step effect verandert de afstand tussen de ringen wanneer het opgegeven evenement tussen 2 variabelen wisselt.

![Track Rings Script](~@images/models/platforms/TrackRingsScript.png)

### Tube Light
![Tube Light](~@images/models/platforms/TubeLightScript.png)

Dit script maakt knipperende verlichting mogelijk. Putting this on an empty gameObject changes the background and adds a bit of color to that space, according to the light ID's. When there's also a mesh renderer on it, it'll change the meshes color according to the light ID's. When using this no color adding is needed, so I change the size on the script to 0.

### Song Events
![Song Event Handler](~@images/models/platforms/SongEventHandler.png)

The event manager is the most useful script. With it you can trigger an action on any beat saber event (even unused ones). Voor het toevoegen van een event druk je op de `+` knop onder `On Trigger ()`. Drag in the object you want to manipulate into the box that just got created. Press the dropdown menu to the right and choose what that object should do, by first selecting what component, then what action. Make sure that you only use 1 event Handler per gameObject, as only 1 will work per gameObject.

### Spectrogram
![Spectrogram](~@images/models/platforms/Spectrogram.png)

The spectrogram script works like the track rings script and also requires a prefab or gameObject. This will get stretched and shrunk according to the sound of the game and the variables provided. (Haven't played with this either).

## Exporteren

![Saving](~@images/models/platforms/Save.png)

Export the platform trough the script that you previously added to the gameObject to the location of your choosing. Preferably the game's directory `Beat Saber/CustomPlatforms`.

::: tip NOTE **Once you've got your new platform working**, [upload them to ModelSaber](https://modelsaber.com) if you want to share them with the world. :::

![Cat](~@images/models/platforms/Cat.png)
