# tera-sensor-docs — Contenu documentaire TERA Sensor

> Source unique des instructions projet. CLAUDE.md n'est qu'un renvoi vers ce fichier.

## Ce que c'est

Le **contenu** de la documentation produit : NextPM, NextCO2, PMScan, PMDuct, SafyrOPC.
Uniquement du Markdown et des images. Aucun moteur de rendu ici.

Ex-`GITBOOK-TERA-SENSOR`, ex-source de GitBook. GitBook a été retiré le 02/09/2026
(un bandeau « This platform has moved » a été posé sur ses 31 pages).

## Structure

```
README.md    — page d'accueil
SUMMARY.md   — la navigation : c'est lui qui ordonne les pages
sensors/     — NextPM, NextCO2
devices/     — appareils
pmscan/      — PMScan
pmduct/      — PMDuct
```

## Qui le consomme

`tera-sensor/tera-group-sites`, dossier `sites/knowledge-center`. À chaque build,
`scripts/sync-docs.mjs` fait un `git clone --depth 1` de ce dépôt dans `.docs-source/`
(ignoré par git, détruit et refait à chaque fois) et génère les 31 pages publiées
sous `tera-sensor.com/resources/`.

## ⚠️ Ce dépôt doit rester PUBLIC

Le build du site tourne dans un conteneur Alpine **sans aucun jeton GitHub** — le
`Dockerfile` de tera-group-sites le dit explicitement : « Depot public, aucun jeton
necessaire ».

Le passer en privé casserait la construction du **site sensor entier**, pas seulement
du Knowledge Center. Si tu dois le fermer un jour, ajoute d'abord un jeton au build.

## Faire évoluer

Édite le Markdown ici, pousse. Le site reprend le contenu à son prochain build.
Pour voir le rendu : `cd tera-group-sites/sites/knowledge-center && npm run dev`
(la synchro est automatique).

Une page n'apparaît que si elle est dans `SUMMARY.md` **et** dans le `SCOPE` de
`docs.config.mjs` côté tera-group-sites.

## Où il vit

`tera-sensor/tera-sensor-docs`, branche `main`, **public**.
Clone : `Dev\tera-sensor\tera-sensor-docs`.
