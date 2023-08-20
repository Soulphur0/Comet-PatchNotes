# How to configure Elytra Aeronautics using the /ean command
The /ean command will be used for some versions of Elytra Aeronautics until I find a suitable config library for the mod, that can meet its requirements, for now, you can configure the mod using this command, which has the following structure, each option is explained below the image.

As you can see, the /ean command has two main config categories, FlightConfig, related to elytra flight; and CloudConfig, related to cloud rendering.
<br><br>

---
---
<br>


## FlightConfig
|  option | description | value type | default value |
| ------------- | ------------- | ------------- | ------------- |
| altitudeDeterminesSpeed | Make elytra flight speed increase with altitude.<br>When set to false, flight speed will be equal to the minSpeed setting. | true/false| true |
| minSpeed | Minimal elytra flight speed when travelling at a zero degree angle, achieved at the lowest altitude point of the speed curve and below.<br> Measured in meters/second (blocks/second)| numerical | 30.35 (Vanilla)|
| maxSpeed | Maximum elytra flight speed when travelling at a zero degree angle, achieved at the highest altitude point of the speed curve and above.<br> Measured in meters/second (blocks/second)| numerical | 257.22 |
| minHeight | Altitude (Y) at which flight speed starts to increase, i.e the starting point of the speed curve. | numerical | 250 |
| maxHeight | Altitude (Y) at which flight speed reaches its maximum, i.e the end point of the speed curve. | numerical | 1000 |
| sneakingRealignsPitch | Make the player realign their flight pitch when crouching mid-air. | true/false | true |
| realignAngle | Pitch angle at which the player will align towards when sneaking mid-flight.<br> Measured in angle degrees.|numerical | 0.0 |
| realignRate | Amount of rotation at which the player will realign towards the "realignAngle".<br> Measured in degrees-per-tick. | numerical| 0.1 |

<br>

---
---
<br>

## CloudConfig
This configuration category has a sub-category which will be explained in its own tables below.
|  option | description | value type | default value |
| ------------- | ------------- | ------------- | ------------- |
| useEanCloudRendering | Enable the multi-layer cloud rendering and cloud customization that the mod offers. |  true/false | true |
| setCloudLayerAmount | Amount of cloud layers to render and make available for customization. | numerical | 3 |
| loadPreset | Load one of the presets that the mod has to showcase its cloud customization capabilities.| DEFAULT<br>DENSE_AND_PUFFY<br>WINDY<br>RAINBOW<br>SEA_MIST<br>SKY_HIGHWAY | DEFAULT |
| configCloudLayer | Sub-category for configuring cloud settings. A cloud layer number must be introduced after this argument in order to select a layer to modify, you can also type "all" to change all layers at once. | cloudLayerNumber/all| --- |

### configCloudLayer
| option | description | value type | default value |
| ------------- | ------------- | ------------- | ------------- |
|altitude|Altitude (Y) at which the selected cloud layer/s will render.<br>The altitude of the two additional cloud layers that come by default mark where flight speed starts to increase and where it reaches its maximum by default configuration, although these parameters are also modifiable in the FlightConfig section. | numerical| First layer: 192.0 (Vanilla value)<br>Second layer: 250.0<br>Third layer: 1000.0|
|cloudType|The type of cloud to render for the selected cloud layer/s, there are three types:<br><br>FAST - Vanilla fast clouds<br>FANCY - Vanilla fancy clouds<br>LOD (Level Of Detail) - Clouds that are rendered as 'FAST' when far away and as 'FANCY' when close.<br><br>The LOD clouds' FAST to FANCY transition distance can be configured.|||
|verticalRenderDistance|Maximum vertical distance (in blocks) at which the selected cloud layer/s will be rendered.|numerical|1000|
|horizontalRenderDistance|Area of the sky that the selected cloud layer/s will occupy. Measured in chunks.|numerical|15 (vanilla)|
|lodRenderDistance|Vertical distance from selected cloud layer/s at which LOD clouds will transition its rendering mode.<br>Being a distance greater than this value from the layer will show the clouds as FAST clouds.<br>Being a distance smaller than this value from the layer will show the clouds as FANCY clouds.<br>The cloud type for the layer must be configured as LOD for this to work. | numerical | 150|
|thickness|Amount of blocks that the clouds of the selected layer/s will occupy vertically.|numerical|4 (vanilla)|
|color|Color that the clouds of the selected cloud layer/s will be rendered with.<br>This value must be introduced as an hexadecimal color code.| hexadecimal| FFFFFF|
|opacity|Opacity that the clouds of the selected cloud layer/s will be rendered with.<br>This value ranges between 1.0 (fully opaque) and 0.0 (fully invisible).|numerical| 0.8 (vanilla)|
|shading|Enable cloud shading, the different sides of the clouds will have different tones.<br>Set to false to disable this feature and render clouds with a solid, monochromatic, color.| true/false| true (vanilla)|
|speed|Speed at which the clouds will travel.<br>The input value represents a multiplier for the vanilla cloud speed.<br>This means '2.0' will mean x2 the vanilla cloud speed, '100.0' will mean x100 and so on.| numerical | 1.0 |
|skyEffects|Set to true to let the clouds of the selected layer/s turn darker at night and under weather conditions.<br>Set to false to disable this feature and always render clouds bright, as if they had an emissive texture.<br>When set to false, clouds appear as if they were glowing when the sky is dark.| true/false | true |