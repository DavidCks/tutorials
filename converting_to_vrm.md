# Converting any 3D model to VRM

## Prerequisits

- Blender 3.6 (LTS)
- Unity
- An FBX or PMX (aka. MMD) model to convert from

## Preface

Blender has add-ons that allow you to work with PMX files and to export to VRM

- VRM: <https://vrm-addon-for-blender.info/en/>
- PMX: <https://github.com/UuuNyaa/blender_mmd_tools>

Since the Bleder add-on is broken when using VRM-1.0, you'll need to use Unity to convert to that.
You'll also need this plugin

- UniVRM: <https://github.com/vrm-c/UniVRM>

## Instructions

Open Blender and install and activate the add-ons (You might need to restart Blender)

### Fixing Textures (Blender)

- In Object Mode, navigate to the Mesh of the model.
- Select the Material tab in the bottom right panel
- Select a Material
- Under "Settings", set the "Blend Mode" and the "Shadow Mode" to "Opaque"
- Scroll down to VRM Material and enable VRM MToon Material
- For Lit Color, select the image associated with the body part
- Fot shade color, pick a light gray. Somehing like value = 0.8
- repeat for all Materials

Once all Textures are fixed, export the model using VRM 0.0

### Fixing the Pose (Unity)

- Import the VRM in unity
- Once the asset is seleceted (and the plugin is activated), you can convert it into VRM 1.0 in the  panel on the right
- Once it's done converting, drag the model into the scene
- Adjust the Arm bones into a T-Pose
- Export the model

Once that is done, there might be some elements that did not come out right, so here's a list of things that might be wrong:

#### Some elements are stuck in place

It's likely that the bones are not connected to the body. You can fix this in Blender:

- Select the Armature and go into edit mode
- Select one of the unconnected bones and the bone you want to connect it to
- hit "Ctrl + P" to connect them

#### The character only becomes visible when I zoom out

The character was probably not exported from the center of the scene in Unity. Here's how you can fix that:

- drag your character into the scene
- position it at the 0 coordinates (in relation to the models center)
- export and check if it worked

#### My character does a weird swivel in animations

Try changing the hip-bone in Blender

- open the vrm plugin settings (the tiny arrow on the right next to the rotation gizmo)
- expand VRM 0.x Humanoid
- select a different hip-bone (the correct one is likely the last one in the list you can select)

### Configuring Expressions

TBD
