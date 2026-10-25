# Calcul poids tuyauterie

Application web pour calculer le poids des tuyauteries : tubes, raccords, brides, vannes. Elle fonctionne dans le navigateur, sans serveur et sans installation. Les données restent sur l'appareil.

**Créé par Kamel Nasralli** · Version 1.0.0 · Licence MIT

## Fonctionnalités

- **Fiche** : calcul d'une pièce avec coupe du tube à l'échelle, Ø extérieur, épaisseur, Ø intérieur, section, volume, surface extérieure et tableau de tous les schedules du NPS choisi.
- **Liste** : une carte par ligne, modifiable directement. Chaque ligne porte un isométrique (ISO) et un numéro de spool.
- **Totaux** : tubes, accessoires, brides et total. Quand il y a plusieurs ISO, chaque ISO a sa propre case de total.
- **Rapport par spool** : regroupement par ISO et par spool, avec le détail des lignes.
- **Paramètres (dans la Fiche)** : matériau, masse volumique du contenu, isolation.
- **Import et export** : CSV compatible Excel et sauvegarde complète en `.json`.

Pièces gérées : tube, coude (90° GR/PR, 45°, 3D, retour 180°), té égal ou réduit, réduction concentrique ou excentrique, fond, bride (WN, SO, SW, TH, BL, LJ, classes 150 à 1500), vanne (opercule, soupape, clapet, boisseau sphérique, papillon) et pièce libre.

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

**Import** : bouton « Importer un fichier » dans l'onglet Liste. Deux formats sont acceptés :

- le CSV de la liste exporté par l'application. Il peut être modifié dans Excel. Les colonnes `Catégorie (code)`, `Type (code)`, `NPS`, `NPS réduit`, `Schedule`, `Classe`, `Longueur (m)`, `Quantité`, `Poids imposé`, `Désignation libre` et `Poids libre (kg)` sont lues. Les colonnes calculées (`Désignation`, `Poids unitaire`, `Poids total`) sont ignorées ;
- la sauvegarde `.json`.

Après lecture, l'application propose d'**ajouter** les lignes à la liste ou de **remplacer** la liste.

Codes de catégorie : `tube`, `coude`, `te`, `red`, `fond`, `bride`, `vanne`, `libre`.

### Version du format de fichier

Le JSON contient `app`, `author`, `appVersion` et `fileVersion` (actuellement `1`). Un fichier d'une version plus récente est importé avec un avertissement.

## Icône et raccourci sur l'écran d'accueil

L'application a une icône (coude de tuyauterie à brides) et un manifeste web. Une fois la page publiée sur GitHub Pages :

- **Android (Chrome)** : menu ⋮ → « Ajouter à l'écran d'accueil » ou « Installer l'application ».
- **iPhone / iPad (Safari)** : bouton Partager → « Sur l'écran d'accueil ».

Fichiers : `icons/icon.svg` (source), `icons/icon-192.png`, `icons/icon-512.png`, `icons/icon-maskable-512.png`, `icons/apple-touch-icon.png`, `icons/favicon-32.png`, `manifest.webmanifest`.

## Précision des données

- **Tubes** : épaisseurs ASME B36.10M / B36.19M, poids = 0,02466 × e × (Øe − e) pour l'acier carbone, exact.
- **Coudes, tés, réductions, fonds** : longueurs ASME B16.9 multipliées par le poids linéique du tube, à ±5 %.
- **Brides et vannes** : valeurs indicatives de catalogue, à ±10 %. À confirmer avec Pipedata ou la fiche du fabricant. Le champ « Poids imposé » remplace toujours le calcul.

Cette application est une aide au calcul. Elle ne remplace pas les données du fabricant ni une vérification par un ingénieur.

## Publier sur GitHub Pages

```bash
cd poids-tuyauterie
git init
git add .
git commit -m "Version 1.0.0"
git branch -M main
git remote add origin https://github.com/VOTRE-COMPTE/poids-tuyauterie.git
git push -u origin main
```

Sur GitHub : **Settings → Pages → Build and deployment → Source : Deploy from a branch → Branch : main / (root)**. La page est disponible à l'adresse `https://VOTRE-COMPTE.github.io/poids-tuyauterie/`.

## Structure du dépôt

```
index.html     Application complète (HTML, CSS et JavaScript, sans dépendance)
manifest.webmanifest   Nom, couleurs et icônes du raccourci
icons/         Icône de l'application (SVG et PNG)
README.md      Ce fichier
CHANGELOG.md   Journal des versions
LICENSE        Licence MIT
```

Seules les polices (Barlow Semi Condensed, IBM Plex) sont chargées depuis Google Fonts. Sans connexion, le navigateur utilise des polices système.

## Licence

MIT. Copyright (c) 2026 Kamel Nasralli.
