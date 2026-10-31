*[Version française](../export.md)*

# Export the effect to .blend

Typical case: you tuned EmberGen sparks in a working file, and you want to add them to your Formula 1 car's
scene. The **Export to .blend** section writes the effect into a standalone `.blend` file that you then add to any
scene, **even on a computer without the add-on**.

## Export the effect to .blend

In the file where the project is open:

1. select an object of the effect (or the export's row in the list): the **Export to .blend** section
   shows the project name;
2. tick the parts to write:
   - **Sparks** (LiquiGen: **Liquid**): the particles with their Geometry Nodes and their material;
   - **Smoke / Fire** (LiquiGen: **Volumes**): the VDB volumes with the EmberGen look and its glows;
   - **Embers** (LiquiGen: **Bubbles**): the objects added by the AI assistant (greyed out if there are none);
   - **Lights**: the project's lights (sun, points, spots);
3. set **Starts at Frame** (see below);
4. click **Export to .blend...** and choose where to save the file.

![The Export to .blend section](../images/exp-01-panneau.png)

The file is finished by a background Blender: the line "Exporting in the background..." is displayed (the cross
cancels it, nothing is written). At the end, the green line says "Exported <project> to <file>". Your working
file is not modified.

![Export finished](../images/exp-02-termine.png)

If you untick **Sparks** while the sparks' glow in the smoke needs them, the sparks are still
written, but hidden: the smoke stays lit the same.

**The sun** also lights the whole scene that receives the effect. To keep only the car scene's lighting,
untick **Lights**.

## Choose the start frame

**Starts at Frame** is the frame of the receiving file where the effect's first frame plays. By default, it is the export's
frame in your working file. The offset applies to the VDBs, the Alembic caches, the look's keys and
the sparks' births, **in the written file only**.

Example: the car passes in front of the camera at frame 120 and the sparks must burst out at that moment: enter
120.

## What is frozen

The written file is **frozen**: all values stay those computed from the project at import (the sparks'
width, for example, was computed from the render resolution of your working file). Nothing is
recomputed from the resolution, camera, frame rate or colour grading of the receiving file, and the add-on in that
file never modifies it, unless you click **Make Editable** (see below).

The file contains:

- a **collection** named after the project, marked as an **asset**;
- a **common parent**, the "<project> · Root" object, to move everything at once;
- **names prefixed** with the project ("<project> · <name>"): nothing gets mixed with another effect.

**The VDB files are not copied**: they stay on disk, at their full path (the optimized copy
if **Optimize VDB Files** was used). Do not move or delete the exports folder as long as you
use the effect.

## Add the effect to another scene

Open the scene that is to receive the effect (the car), then either:

**With File > Append**: **File > Append**, choose the exported `.blend` file, go into the
**Collection** folder and choose the collection named after the project.

**With the Asset Browser**: add the exported file's folder as an asset library (**Edit > Preferences
> File Paths > Asset Libraries**, or **Asset Libraries** depending on the version), open an **Asset Browser** editor,
choose this library, then drag the effect into the 3D viewport.

![The exported effect in the Asset Browser](../images/exp-03-asset-browser.png)

## Edit the effect in the receiving scene

Select an object of the effect, then click **Make Editable** in the **Export to .blend** section of the JangaFX
panel. The effect is no longer frozen: its exports come back in the add-on's list with their settings (look,
Auto Match corrections, start frame), and are adjusted or reloaded like an import done in this file.
The project and the export files must still be on disk.

An effect exported before version 0.15.0 did not keep its settings: its exports are found again in the project
folder, and the add-on's settings (look, Auto Match corrections) go back to their default values at the next
**Reload**. An effect already imported in the scene cannot be made editable a second time.

## Place the effect on the emitter object

If the project's emitter has the shape of an object exported from Blender (**Import** node plugged into **Shape**):
select that object in Blender, then click **Snap to Emitter Object** in the export panel. The
"<project> Root" parent is placed on the object, and the origin of each part of the effect (sparks, smoke) is set to
the emitter ("JangaFX Pivot" modifier, right after the cache): the Import offset in EmberGen is corrected,
and moving, rotating or scaling the parent or a part keeps the effect on the object. If the object moves,
click again: the emitter object is remembered, no need to reselect it.

## Animate the effect's time

In the export panel, under **Starts at Frame**, click **Animate Effect Time**. An **Effect Frame** value
appears: it is the simulation frame shown (the number of the exported files). It is placed on the
"<project> Root" parent and drives the smoke, the particles, the sparks' age and the animated look **all at once**.

At first, it follows normal playback (two keyframes, extended in a straight line). Put your own keyframes
on it (hover over the value, **I** key):

- **move** the effect: shift the keyframes in the timeline;
- **slow down / speed up**: move the keyframes apart or closer together;
- **freeze**: two keyframes with the same value;
- **reverse**: a value that goes down.

**Different frame rate** (EmberGen project at 60 fps, scene at 30 fps): a VDB sequence has one file per project
frame, so it would play twice too slowly next to the sparks (the Alembic, on the other hand, is in seconds). The
button is then called **Convert 60 fps to 30 fps**: Effect Frame advances two files per scene frame,
and the smoke and sparks stay together in real time, without changing the scene's frame rate.

**Override Frame** (Alembic cache setting, Mesh Sequence Cache modifier tab): ticked by Effect Frame,
it makes the cache read the frame given by its **Frame** field (driven) instead of the scene's frame. Do not touch
it: the **X** of Effect Frame unticks it.

Outside the exported files, the smoke is hidden. Effect Frame is kept in the `.blend` export (it works without
the add-on). The **X** returns to normal playback. While it is active, **Starts at Frame** and **Skip Invisible
Frames** are disabled, and the smoke's visibility (render / viewport) is driven by Effect Frame. The embers and
bubbles added by the assistant stay on the scene's time.

## Move the effect

Select the **"<project> · Root"** object (in the Outliner) and move, rotate or scale it:
the whole effect follows, sun included.

## What stays with the receiving scene

The effect brings its objects, materials and lights, but **not the scene settings**. Those stay
the car scene's, and the add-on does not touch them:

- colour grading (**Color Management**: View Transform, Look, exposure, curve);
- the frame rate (frames per second);
- Cycles render settings: step and bounces in volumes, light bounces;
- motion blur;
- transparent film;
- post-processing done in compositing (glow, saturation, vignette…);
- the world (**World**);
- the camera: the project's is not exported, the effect is seen through the receiving scene's camera.

The result can therefore differ from your working file. To warn you, the **Export to
.blend** section of the receiving scene shows one line per difference (nothing is fixed automatically):

- "<effect>: colour settings differ from the source file, the effect may look different": the colour grading
  differs;
- "<effect>: made at 60 fps, this scene plays it at another speed": the frame rate differs;
- "<effect>: render settings differ from the source file: volume step, bounces, motion blur, post-FX, world":
  the list says which render settings differ.

![The information lines in the receiving scene](../images/exp-04-notes.png)

What to do: see [Colours change after adding the effect](depannage.md#colours-change-after-adding-the-effect) and
[The speed is wrong](depannage.md#the-speed-is-wrong).
