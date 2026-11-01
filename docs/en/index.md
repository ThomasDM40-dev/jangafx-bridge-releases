*[Version française](../index.md)*

# JangaFX Bridge for EmberGen

<div class="hero">
<img src="../logos/embergen.png" alt="EmberGen logo">
<div>
<p class="kicker">Documentation · JangaFX Bridge for Blender</p>
<p class="name">Your EmberGen effects, rendered in Blender</p>
<p class="tag">Open the <code>.ember</code> project: smoke, fire, sparks, lights, camera and ground are ready to
render, with the EmberGen look.</p>
</div>
</div>

<div class="badges">
<span><img src="../logos/embergen.png" alt="">.ember projects</span>
<span><img src="../logos/logo-bridge.png" alt="">Blender 4.5 and later</span>
<span>VDB and Alembic</span>
<span>Cycles render</span>
</div>

This documentation mainly covers **EmberGen**; the switch at the top of the page goes to the **LiquiGen**
version.

## What the add-on does

JangaFX Bridge links EmberGen (smoke, fire, sparks) with Blender:

- you open your EmberGen (`.ember`) project directly in Blender;
- the add-on automatically finds the exported files (VDB, Alembic), imports them and rebuilds the project's render:
  materials, lights, camera, ground, post-processing, frame rate and frame range;
- it watches the exports folder: when you re-export from EmberGen, Blender updates;
- it compares Blender's render to EmberGen's and can match the look on its own (**Auto Match**);
- it exports the finished effect as a standalone `.blend`, to add to any other scene (for example sparks in a
  Formula 1 scene);
- an AI assistant, running on your computer, can tweak the look on request.

<p class="strip"><img src="../showcase/embergen-explosion.png" alt="An EmberGen explosion, from flash to smoke"></p>

<p class="gallery g3"><img src="../showcase/embergen-fire.png" alt="EmberGen fire"><img src="../showcase/embergen-smoke.png" alt="EmberGen explosion smoke"><img src="../showcase/embergen-tornado.png" alt="EmberGen tornado"></p>

![The JangaFX tab after opening a project](../images/pp-02-scene.png)

## Contents

1. [Installation](installation.md) — install the add-on and receive updates automatically.
2. [Getting started](premiers-pas.md) — open a project, what appears in the scene, read the report.
3. [The JangaFX panel](panneau.md) — every section of the panel, setting by setting.
4. [Check against EmberGen and Auto Match](verifier-et-auto-match.md) — compare with EmberGen and match the look.
5. [Export the effect to .blend](export.md) — put the effect in another scene.
6. [The AI assistant](assistant-ia.md) — install Ollama and ask for tweaks.
7. [Troubleshooting](depannage.md) — common problems and their solutions.

## Where to find the add-on in Blender

In the 3D viewport, press **N** to open the sidebar, then click the **JangaFX** tab (the **JangaFX AI** tab
contains the AI assistant). Button labels are in English, like the rest of Blender; this
documentation gives their exact name in **bold**.

The **Documentation** button, at the bottom of the **Settings** section, opens this page. In the help popups of the
**?** buttons, the **Learn more** link opens the right section directly.
