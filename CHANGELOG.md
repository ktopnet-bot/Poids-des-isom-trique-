# Journal des versions

Le format suit [Semantic Versioning](https://semver.org/lang/fr/).

## 1.3.1 - 2026-10-26

- Boulonnerie : longueur de goujon = 2 × épaisseur de bride + 2,5 × diamètre, calée sur Pipedata (12" classe 300 : 170 mm, 21,77 kg).
- Icône du raccourci : copie intégrée dans `index.html` en secours, au cas où le dossier `icons` n'est pas envoyé avec la page.
- Cache hors connexion : version 1.3.1.
- README : vérifications de l'icône et valeurs Pipedata de référence.

## 1.3.0 - 2026-10-25

- Raccords forgés ASME B16.11 : coudes 90° et 45°, tés, fonds, à souder (3000#, 6000#) et filetés (2000#, 3000#, 6000#), NPS 1/2 à 4, avec poids et surface de peinture.
- Boulonnerie des brides : goujons et écrous, par classe et NPS (ASME B16.5).
- Bride WN 12" classe 300 calée sur Pipedata (64,02 kg).
- Raccourci sur l'écran d'accueil : service worker, identifiant du manifeste, icône SVG, `.nojekyll`.
- Format de fichier : version 4 (les versions 1 à 3 restent importables).

## 1.2.0 - 2026-10-25

- Surface de peinture (m²) pour chaque ligne : tubes, raccords, brides, vannes. Surface imposée possible.
- Totaux de surface par catégorie, par ISO et par spool, et dans la Fiche.
- Export CSV : colonnes `Surface peinture (m²)` et `Surface imposée (m²)`, et surface par spool.
- Format de fichier : version 3 (les versions 1 et 2 restent importables).

## 1.1.0 - 2026-10-25

- Extrémités des tubes : bride, coude ou fond à chaque bout. L'encombrement est retiré automatiquement de la longueur mesurée (longueur nette).
- Encombrement imposé (mm) pour remplacer le calcul.
- Export CSV : colonnes de longueur mesurée, longueur nette et extrémités. Le réimport relit ces colonnes.
- Format de fichier : version 2 (les fichiers de la version 1 restent importables).

## 1.0.0 - 2026-10-25

Première version publiée.

- Calcul du poids des tubes (ASME B36.10M / B36.19M), coudes, tés, réductions, fonds, brides, vannes et pièces libres.
- Fiche de calcul avec coupe du tube à l'échelle et tableau des schedules par NPS.
- Liste de calcul modifiable ligne par ligne, avec isométrique (ISO) et numéro de spool.
- Total général et total par ISO.
- Rapport par ISO et par spool.
- Matériaux, contenu et isolation (paramètres de la fiche).
- Import et export : CSV (Excel), sauvegarde projet `.json`.
- Format de fichier : version 1.
- Icône de l'application et manifeste pour le raccourci sur l'écran d'accueil.
