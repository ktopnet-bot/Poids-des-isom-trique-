# Calcul poids tuyauterie

Application web pour calculer le poids des tuyauteries : tubes, raccords, brides, vannes. Elle fonctionne dans le navigateur, sans serveur et sans installation. Les données restent sur l'appareil.

**Créé par Kamel Nasralli** · Version 1.7.0 · Licence MIT

## Fonctionnalités

- **Fiche** : calcul d'une pièce avec coupe du tube à l'échelle, Ø extérieur, épaisseur, Ø intérieur, section, volume, surface extérieure et tableau de tous les schedules du NPS choisi.
- **Liste** : une carte par ligne, modifiable directement. Chaque ligne porte un isométrique (ISO) et un numéro de spool.
- **Extrémités des tubes** : pour chaque tube, choisissez ce qui est soudé à chaque bout (bride, coude, fond). L'application retire automatiquement l'encombrement de ces pièces de la longueur mesurée et calcule le poids du tube net. Un encombrement imposé (mm) remplace le calcul.
- **Surface de peinture** : surface extérieure en m² pour chaque ligne, avec totaux par catégorie, par ISO et par spool. Une surface imposée remplace le calcul.
- **Raccords forgés ASME B16.11** : coudes 90° et 45°, tés, fonds à souder (SW, 3000# et 6000#) et filetés (2000#, 3000#, 6000#), NPS 1/2 à 4.
- **Boulonnerie** : goujons et écrous des brides (nombre, diamètre, longueur ASME B16.5), par joint.
- **Totaux** : tubes, accessoires, brides et total. Quand il y a plusieurs ISO, chaque ISO a sa propre case de total.
- **Rapport par spool** : regroupement par ISO et par spool, avec le détail des lignes.
- **Paramètres (dans la Fiche)** : matériau, masse volumique du contenu, isolation.
- **Récap Excel** : bouton « Récap Excel (.xlsx) » dans Liste et Rapport par spool. Le fichier est généré dans le navigateur, sans bibliothèque ni connexion.
- **Import et export** : CSV compatible Excel et sauvegarde complète en `.json`.

Pièces gérées (liste non exhaustive) : demi-manchons et manchons forgés B16.11 (à souder et filetés), piquages forgés (weldolet, sockolet, threadolet), tube, coude (90° GR/PR, 45°, 3D, retour 180°), té égal ou réduit, réduction concentrique ou excentrique, fond, bride (WN, SO, SW, TH, BL, LJ, classes 150 à 1500), vanne (opercule, soupape, clapet, boisseau sphérique, papillon) et pièce libre.

## Utilisation

1. Ouvrez `index.html` dans un navigateur, ou la page GitHub Pages du dépôt.
2. Onglet **Liste**, bouton **+ Ajouter une pièce**, puis renseignez l'ISO, le spool et la pièce.
3. Consultez les totaux dans **Liste** et le détail dans **Rapport par spool**.

## Import et export

Les fichiers sont enregistrés dans le dossier **Téléchargements** de l'appareil. Sur iPhone et iPad, la feuille de partage s'ouvre : choisissez « Enregistrer dans Fichiers ».

| Fichier | Nom | Contenu |
|---|---|---|
| Liste | `poids-tuyauterie-liste_AAAA-MM-JJ.csv` | Toutes les lignes, séparateur `;`, décimale `,`, encodage UTF-8 |
| Spools | `poids-tuyauterie-spools_AAAA-MM-JJ.csv` | Totaux par ISO et spool |
| Projet | `poids-tuyauterie-projet_AAAA-MM-JJ.json` | Lignes et paramètres, avec `fileVersion` |
| Récap Excel | `poids-tuyauterie-recap_AAAA-MM-JJ.xlsx` | Trois feuilles : **Récap** (ISO, spool, poids en kg, surface de peinture en m², total), **Par ISO** (un total par isométrique) et **Détail** (une ligne par pièce). Totaux en formules `SUM`, filtres et en-tête figé. |

Colonne ajoutée dans la version 1.3.0 : `Classe forgée (code)`. Codes de catégorie supplémentaires : `forge`, `boulon`.

Colonnes ajoutées dans la version 1.2.0 : `Surface peinture (m²)` et `Surface imposée (m²)`.

Colonnes ajoutées dans la version 1.1.0 : `Longueur mesurée (m)`, `Longueur nette (m)`, `Ext. 1 (code)`, `Ext. 1 type (code)`, `Ext. 2 (code)`, `Ext. 2 type (code)`, `Encombrement imposé (mm)`.

**Import** : bouton « Importer un fichier » dans l'onglet Liste. Deux formats sont acceptés :

- le CSV de la liste exporté par l'application. Il peut être modifié dans Excel. Les colonnes `Catégorie (code)`, `Type (code)`, `NPS`, `NPS réduit`, `Schedule`, `Classe`, `Longueur (m)`, `Quantité`, `Poids imposé`, `Désignation libre` et `Poids libre (kg)` sont lues. Les colonnes calculées (`Désignation`, `Poids unitaire`, `Poids total`) sont ignorées ;
- la sauvegarde `.json`.

Après lecture, l'application propose d'**ajouter** les lignes à la liste ou de **remplacer** la liste.

Codes de catégorie : `tube`, `coude`, `te`, `red`, `fond`, `bride`, `vanne`, `libre`.

### Version du format de fichier

Le JSON contient `app`, `author`, `appVersion` et `fileVersion` (actuellement `5`). Les fichiers des versions 1 à 4 s'importent sans changement. Un fichier d'une version plus récente est importé avec un avertissement.

## Icône et raccourci sur l'écran d'accueil

L'application a une icône (coude de tuyauterie à brides) et un manifeste web. Une fois la page publiée sur GitHub Pages :

- **Android (Chrome)** : menu ⋮ → « Ajouter à l'écran d'accueil » ou « Installer l'application ».
- **iPhone / iPad (Safari)** : bouton Partager → « Sur l'écran d'accueil ».

Si l'icône ne s'affiche pas sur l'écran d'accueil :

1. Vérifiez que le dossier ``, `manifest.webmanifest` et `sw.js` sont bien dans le dépôt, à côté de `index.html`.
2. Ouvrez la page en HTTPS (adresse `github.io`), pas en fichier local ni depuis un lien Claude.
3. Supprimez l'ancien raccourci, rechargez la page deux fois, puis ajoutez-la de nouveau (Android : « Installer l'application »).

Fichiers : `icon.svg` (source), `icon-192.png`, `icon-512.png`, `icon-maskable-512.png`, `apple-touch-icon.png`, `favicon-32.png`, `favicon.svg`, `manifest.webmanifest`, `sw.js`.

## Icône absente sur l'écran d'accueil : vérifications

Tous les fichiers sont à la racine du dépôt, au même niveau que `index.html` (pas de sous-dossier). Cela évite le problème d'un dossier mal envoyé par l'interface web de GitHub.

1. Le dépôt doit contenir : `index.html`, `manifest.webmanifest`, `sw.js`, `icon-192.png`, `icon-512.png`, `icon-maskable-512.png`, `apple-touch-icon.png`, `favicon-32.png`, `favicon.svg`, `icon.svg`.
2. Contrôlez que `https://VOTRE-COMPTE.github.io/icon-192.png` (ou `.../NOM-DU-DEPOT/icon-192.png`) s'ouvre dans le navigateur. Si la page affiche « 404 », le fichier n'est pas au bon endroit.
3. **Désinstallez l'ancienne application** : appui long sur l'icône, puis « Désinstaller ». Ensuite, dans Chrome, ouvrez ⋮ → Infos sur le site → Effacer les données, rechargez la page, puis choisissez « Installer l'application ». Android garde l'icône de la première installation.
4. Ouvrez la page par son adresse `https://` GitHub Pages. L'ouverture du fichier `index.html` depuis le téléphone ou depuis l'application Claude ne donne ni installation ni icône.
5. Une copie de l'icône est aussi intégrée dans `index.html` : même si les fichiers PNG manquent, Chrome et Safari ont une icône pour un simple raccourci.

## Piquages, demi-manchons et manchons (version 1.4.0)

| Pièce | Origine des données | Précision |
|---|---|---|
| Weldolet STD, XS, XXS | Poids Bonney Forge (MSS SP-97), NPS 1/2 à 24 (XXS jusqu'à 6"), piquage de même taille que la ligne | ±25 % |
| Sockolet 3000# / 6000# | Moyenne de deux tableaux publiés (kg et lb), 3000# jusqu'à 6", 6000# jusqu'à 2" | ±25 % |
| Threadolet 3000# / 6000# | Estimé avec le poids du sockolet de même taille | ±25 % |
| Demi-manchon et manchon à souder 3000# / 6000# | Dimensions ASME B16.11, poids calculé et calé comme les coudes SW (Pipedata) | ±25 % |
| Demi-manchon et manchon filetés 3000# / 6000# | Dimensions ASME B16.11, poids calculé et calé comme les coudes filetés (Pipedata) | ±25 % |

Points d'attention :

- Un catalogue (Alleima) indique pour le demi-manchon SW 3000# des poids environ 1,9 fois plus élevés que le calcul fait avec ses propres dimensions (par exemple 0,15 kg au lieu de 0,08 kg en 1/2"). L'application suit le calage Pipedata. En cas de doute, utilisez le poids imposé.
- Dans la source des weldolets, la série XS pèse parfois moins que la STD (12", par exemple) : l'application retient alors le poids de la STD.
- Un piquage réducteur sur une ligne plus grosse est un peu plus lourd que le piquage de même taille.
- La surface de peinture des piquages est estimée à partir du poids.

Sources : [Wermac, dimensions B16.11](https://www.wermac.org/fittings/dim_sw_coupling.html), [Wermac, couplings filetés](https://www.wermac.org/fittings/dim_thd_couplings.html), [Wermac, weldolet](https://www.wermac.org/fittings/dimensions_weldolet_size-on-size_std-wt.html), [ProjectMaterials, poids des weldolets et sockolets](https://blog.projectmaterials.com/pipe-fittings/weldolet-size-weight/), [Hardhat Engineer, sockolet](https://hardhatengineer.com/sockolet-and-sockolet-dimensions), [Alleima, demi-manchons](https://www.alleima.com/cz/products/fittings-flanges/fittings/socket-weld-fittings-ansiasme/couplings-half/).

## Valeurs vérifiées avec Pipedata

Ces valeurs sont reprises telles quelles par l'application :

| Pièce | Valeur Pipedata |
|---|---|
| Coude 90° à souder (SW) 1/2" 3000# | 0,15 kg |
| Coude 90° fileté 1/2" 3000# | 0,44 kg |
| Bride à collerette 12" classe 300 RF SCH STD | 64,02 kg |
| Goujons et écrous, joint 12" classe 300 (16 × 1+1/8" × 170 mm) | 21,77 kg |

Les autres tailles sont calculées d'après les dimensions ASME et calées sur ces valeurs. Pour une valeur exacte, utilisez « Poids imposé ».

## Précision des données

- **Encombrement des extrémités** : bride à collerette (longueur ASME B16.5, valeurs indicatives), coude (cote centre-à-extrémité ASME B16.9, tangente de l'angle), fond (longueur ASME B16.9). Le poids de ces pièces n'est pas ajouté : créez une ligne pour chacune.
- **Raccords forgés B16.11** : poids estimés d'après les dimensions normalisées (ASME B16.11) et calés sur Pipedata : 1/2" cl.3000, coude SW 0,15 kg et coude fileté 0,44 kg. Précision ±10 %. Les fonds SW viennent d'un catalogue fabricant.
- **Boulonnerie** : longueurs de goujon standard ASME B16.5, face à ressaut. Pipedata utilise une longueur théorique plus courte (écart d'environ 10 %).
- **Surface de peinture** : tubes et raccords soudés = surface extérieure exacte. Brides = une face, la tranche et le col. Fonds et vannes = estimation. Précision de ±20 % pour brides, fonds et vannes.
- **Tubes** : épaisseurs ASME B36.10M / B36.19M, poids = 0,02466 × e × (Øe − e) pour l'acier carbone, exact.
- **Coudes, tés, réductions, fonds** : longueurs ASME B16.9 multipliées par le poids linéique du tube, à ±5 %.
- **Brides et vannes** : valeurs indicatives de catalogue, à ±10 %. À confirmer avec Pipedata ou la fiche du fabricant. Le champ « Poids imposé » remplace toujours le calcul.

Cette application est une aide au calcul. Elle ne remplace pas les données du fabricant ni une vérification par un ingénieur.

## Publier sur GitHub Pages

```bash
cd poids-tuyauterie
git init
git add .
git commit -m "Version 1.7.0"
git branch -M main
git remote add origin https://github.com/VOTRE-COMPTE/poids-tuyauterie.git
git push -u origin main
```

Sur GitHub : **Settings → Pages → Build and deployment → Source : Deploy from a branch → Branch : main / (root)**. La page est disponible à l'adresse `https://VOTRE-COMPTE.github.io/poids-tuyauterie/`.

## Structure du dépôt

```
index.html              Application complète (HTML, CSS et JavaScript, sans dépendance)
manifest.webmanifest    Nom, couleurs et icônes du raccourci
sw.js                   Service worker (installation et usage hors connexion)
icon-192.png, icon-512.png, icon-maskable-512.png, apple-touch-icon.png,
favicon-32.png, favicon.svg, icon.svg    Icône de l'application
.nojekyll               Désactive le traitement Jekyll de GitHub Pages (fichier caché)
README.md               Ce fichier
CHANGELOG.md            Journal des versions
LICENSE                 Licence MIT
```

Seules les polices (Barlow Semi Condensed, IBM Plex) sont chargées depuis Google Fonts. Sans connexion, le navigateur utilise des polices système.

## Licence

MIT. Copyright (c) 2026 Kamel Nasralli.
