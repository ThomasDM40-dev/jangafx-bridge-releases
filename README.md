<p align="center">
  <img src="docs/logos/embergen.png" width="76" alt="EmberGen">&nbsp;&nbsp;&nbsp;
  <img src="docs/logos/logo-bridge.png" width="104" alt="JangaFX Bridge">&nbsp;&nbsp;&nbsp;
  <img src="docs/logos/liquigen.png" width="76" alt="LiquiGen">
</p>

<h1 align="center">JangaFX Bridge</h1>

<p align="center">
  <b>EmberGen et LiquiGen dans Blender : ouvrez le projet, le rendu est prêt.</b><br>
  Add-on Blender 4.5+ — import, look et rechargement en direct des exports de la suite JangaFX.
</p>

<p align="center">
  <a href="https://github.com/ThomasDM40-dev/jangafx-bridge-releases/releases/latest"><img src="https://img.shields.io/badge/version-0.25.3-1c7ed6" alt="Version 0.25.3"></a>
  <img src="https://img.shields.io/badge/Blender-4.5%2B-e87d0d?logo=blender&logoColor=white" alt="Blender 4.5+">
  <img src="https://img.shields.io/badge/EmberGen-.ember-ff7a18" alt="EmberGen">
  <img src="https://img.shields.io/badge/LiquiGen-.liquigen-1c9be6" alt="LiquiGen">
  <img src="https://img.shields.io/badge/licence-GPL--3.0-5d6470" alt="GPL-3.0">
</p>

<p align="center">
  <a href="https://thomasdm40-dev.github.io/jangafx-bridge-releases/"><b>Documentation</b></a> ·
  <a href="https://thomasdm40-dev.github.io/jangafx-bridge-releases/en/"><b>English</b></a> ·
  <a href="https://thomasdm40-dev.github.io/jangafx-bridge-releases/liquigen/"><b>Documentation LiquiGen</b></a> ·
  <a href="https://github.com/ThomasDM40-dev/jangafx-bridge-releases/releases/latest"><b>Télécharger</b></a>
</p>

<p align="center">
  <a href="https://github.com/ThomasDM40-dev/jangafx-bridge-releases/releases/download/v0.25.3/jangafx_bridge-0.25.3.zip?repository=https%3A%2F%2Fraw.githubusercontent.com%2FThomasDM40-dev%2Fjangafx-bridge-releases%2Fmain%2Findex.json&blender_version_min=4.5.0"><img src="https://img.shields.io/badge/%E2%87%A9%20Glisser%20dans%20Blender-install-1c7ed6?style=for-the-badge&logo=blender&logoColor=white" alt="Glisser dans Blender"></a><br>
  <sub>Glissez ce bouton dans la fenêtre de Blender 4.5+ : Blender propose d'ajouter le dépôt, puis installe l'add-on.</sub>
</p>

<p align="center"><img src="docs/showcase/embergen-explosion.png" alt="Une explosion EmberGen, du flash à la fumée"></p>

## Ce que fait l'add-on

<table>
<tr>
<td width="50%" valign="top">
<img src="docs/logos/embergen.png" width="40" align="left" alt="">&nbsp;<b>EmberGen</b> — fumée, feu, étincelles<br clear="left">

- ouvre le projet `.ember` et importe tout seul les VDB et les particules Alembic ;
- reconstruit le look : matériaux, lueurs, lumières, caméra, sol, post-traitement ;
- compare le rendu Blender au flipbook d'EmberGen et cale le look (**Auto Match**).

</td>
<td width="50%" valign="top">
<img src="docs/logos/liquigen.png" width="40" align="left" alt="">&nbsp;<b>LiquiGen</b> — liquides<br clear="left">

- ouvre le projet `.liquigen` : liquide, écume, embruns et bulles ;
- matériau du liquide, soleil, ciel, sol et caméra du projet ;
- compare le rendu Blender à une capture de LiquiGen.

</td>
</tr>
</table>

Pour les deux : le dossier des exports est surveillé (réexport = mise à jour dans Blender), l'effet s'exporte en
`.blend` autonome pour n'importe quelle scène, et un assistant IA local (Ollama) retouche le look à la demande.

## Galerie

<table>
<tr>
<td><img src="docs/showcase/embergen-fire.png" alt="Feu EmberGen"></td>
<td><img src="docs/showcase/embergen-smoke.png" alt="Fumée d'explosion EmberGen"></td>
<td><img src="docs/showcase/embergen-tornado.png" alt="Tornade EmberGen"></td>
</tr>
<tr>
<td align="center">Feu</td>
<td align="center">Explosion et fumée</td>
<td align="center">Tornade de poussière</td>
</tr>
<tr>
<td><img src="docs/showcase/liquigen-gold.png" alt="Or liquide LiquiGen"></td>
<td><img src="docs/showcase/liquigen-whirlpool.png" alt="Tourbillon et écume LiquiGen"></td>
<td><img src="docs/logos/liquigen.png" alt="LiquiGen"></td>
</tr>
<tr>
<td align="center">Or liquide</td>
<td align="center">Tourbillon et écume</td>
<td align="center"><a href="https://thomasdm40-dev.github.io/jangafx-bridge-releases/liquigen/">Documentation LiquiGen</a></td>
</tr>
</table>

<sub>Aperçus enregistrés dans des projets EmberGen et LiquiGen ouverts par l'add-on.</sub>

## Dans Blender

<p align="center"><img src="docs/images/pp-02-scene.png" alt="L'onglet JangaFX après l'ouverture d'un projet EmberGen"></p>

L'onglet **JangaFX** (touche **N** dans la vue 3D) : le projet, ses exports, le rapport et tous les réglages du look.

## Installer avec mises à jour automatiques (recommandé)
1. Blender > Edit > Preferences > Get Extensions > menu **Repositories** (en haut à droite) > **+** > **Add Remote Repository**.
2. URL : `https://raw.githubusercontent.com/ThomasDM40-dev/jangafx-bridge-releases/main/index.json`
3. Cocher **Check for Updates on Startup**, valider, puis installer **JangaFX Bridge** dans la liste.

Les nouvelles versions apparaissent ensuite toutes seules dans Blender (bouton Update).

## Installer à la main
Télécharger `jangafx_bridge-x.y.z.zip` dans [Releases](https://github.com/ThomasDM40-dev/jangafx-bridge-releases/releases), puis
Preferences > Get Extensions > menu > **Install from Disk…**.

---

<p align="center">
  <img src="docs/logos/embergen.png" width="24" alt="">&nbsp;<img src="docs/logos/liquigen.png" width="24" alt=""><br>
  <sub>EmberGen et LiquiGen sont des marques de JangaFX ; leurs logos désignent ici les logiciels.</sub>
</p>