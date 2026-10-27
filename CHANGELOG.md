# Journal des versions

Le format suit [Semantic Versioning](https://semver.org/lang/fr/).

## 1.12.2
- Import corrigé : sélecteur de fichier sans filtre de type (les fichiers CSV/JSON ne sont plus grisés sur Android), bouton en libellé, lecture UTF-8 ou Windows-1252, message clair si un fichier Excel est choisi.

## 1.12.1
- Schémas de piquages corrigés : suppression des bouts de ligne parasites, lignes de fermeture ajoutées en haut et en bas de l'alésage.

## 1.12.0
- Piquages : schémas en coupe du weldolet, du sockolet et du threadolet avec cotes MSS SP-97 taille sur taille (hauteur A, largeur de base B, alésage D).

## 1.11.2
- Allègement de l'interface d'export : suppression de la liste des noms de fichiers, des notes de dossier et des boutons « Ouvrir » en double (reste « Ouvrir le Tableau de Bord »).

## 1.11.1
- Bouton « Ouvrir le Tableau de Bord » : génère et ouvre le fichier en un seul geste (feuille de partage), sans exporter d'abord ; repli sur l'enregistrement si l'appareil ne le permet pas.

## 1.11.0
- Bouton « Ouvrir » après un export : ouvre le dernier fichier (feuille de partage de l'appareil pour choisir Excel, ou nouvel onglet).

## 1.10.1
- Le fichier Excel du récap s'appelle maintenant « Tableau-de-Bord_<projet>_<date>.xlsx ».

## 1.10.0
- Récap Excel : nouvelle feuille « Tableau d'avancement » au modèle du tableau de bord de fabrication tuyauterie (ISO, DN, nombre de soudures, pouces, spool, poids théorique et axe-axe, longueur, peinture, colonnes d'avancement pondérées, totaux, sous-totaux filtrables, couleurs de statut).
- Informations d'en-tête du tableau (projet, code, document, rev, service, classe, SYS) saisies dans l'onglet Rapport par spool et enregistrées avec le projet.
- Feuille Détail : colonne Nuance.

## 1.9.1
- Récap Excel : colonne « Diamètre des pipes » en B (Récap, Par ISO, Détail) ; poids, surface de peinture et soudures décalés à droite.

## 1.9.0
- Soudures : nombre de joints à souder (1 par extrémité raccordée d'un tube, ou valeur imposée), diamètre principal et pouces-diamètre (joints × NPS × quantité) par ligne, par spool, par ISO et au total.
- Récap Excel : colonnes Joints à souder / Pouces à souder dans Récap, Par ISO et Détail. Colonnes ajoutées aux CSV (liste et spools), import compatible.

## 1.8.1
- Schémas de vannes redessinés d'après Pipedata : opercule, soupape, clapet, boisseau (vue de bout + face), papillon wafer.
- Nouvelle vanne papillon à oreilles.

## 1.8.0
- Tableaux SW/TH remplacés par les valeurs réelles de l'ASME B16.11-2021 (B, C, D, G, J, A, K ; 3000/6000 SW, 2000/3000/6000 TH).
- Nouveaux schémas en coupe (style Pipedata) : coude SW 45°, té SW, bouchon SW, coude 90°/45° fileté, té fileté.
- Les poids des raccords forgés SW peuvent varier légèrement (recalibrage sur Pipedata conservé).

## 1.7.4 - 2026-10-26

- Schéma du fond corrigé : demi-vue extérieure et demi-coupe hachurée comme dans Pipedata, biseau de soudure, axe central. Le dessin ne se déforme plus sur les petits diamètres à forte épaisseur (par exemple 1/2" SCH XXS).

## 1.7.3 - 2026-10-26

- Schémas de brides conformes au dessin technique : ligne continue de la face d'étanchéité à travers l'alésage, extrémité du moyeu fermée, arêtes de la bride tracées à travers les trous de boulons, coupure du tube sur les brides SO, SW et filetée.

## 1.7.2 - 2026-10-26

- Brides : schémas en coupe ajoutés pour la bride pleine, à emboîtement glissant (SO), filetée et à souder (SW), avec le diamètre d'alésage SO et la profondeur d'emboîtement SW. La hauteur du moyeu de ces types est estimée et non cotée.

## 1.7.1 - 2026-10-26

- Schémas redessinés à l'échelle dans le style Pipedata : coupes hachurées et cotes à flèches (coudes, tés, réductions, fonds, brides à collerette, coudes et manchons forgés, vannes, goujons, tube).
- Brides : ajout du cercle de boulons, du diamètre de ressaut et du diamètre de moyeu (ASME B16.5), des cotes Y et de la hauteur totale.
- Vannes : face à face par classe selon ASME B16.10 (remplace le coefficient forfaitaire), ce qui affine la surface de peinture.
- Le schéma en coupe des brides n'est donné que pour la bride à collerette ; les autres types affichent leurs cotes.

## 1.7.0 - 2026-10-26

- Fiche de calcul : bloc « Encombrement et schéma » pour chaque catégorie, avec un schéma côté et les dimensions : coudes (R, A, O), tés (C, M), réductions (H), fonds (E), brides (Ø, longueur Y, épaisseur, boulons), vannes (face à face L), raccords forgés B16.11 (A, J, L), boulonnerie et piquages.
- Tube : schéma de la longueur mesurée, des encombrements d'extrémité et du tube net.
- Les dimensions sont indicatives ; la hauteur de vanne et la hauteur de piquage dépendent du fabricant et ne sont pas incluses.

## 1.6.0 - 2026-10-26

- Gestion de plusieurs projets : chaque projet garde ses lignes et ses paramètres (créer, renommer, dupliquer, supprimer, ouvrir).
- Les données de la version 1.5 sont reprises automatiquement dans « Projet 1 ».
- Corbeille : les 5 derniers projets supprimés peuvent être restaurés.
- Sauvegarde d'un projet ou de tous les projets (.json) ; import d'un fichier comme nouveau projet.
- Le nom du projet figure dans les noms de fichiers exportés.
- Demande de stockage persistant au navigateur.

## 1.5.0 - 2026-10-26

- Export « Récap Excel (.xlsx) » : feuilles Récap (ISO, spool, poids, surface de peinture), Par ISO et Détail, avec totaux en formules.
- Génération du fichier Excel dans le navigateur, sans bibliothèque externe, donc utilisable hors connexion.

## 1.4.0 - 2026-10-26

- Nouvelle catégorie « Piquage (olet) » : weldolet (STD, XS, XXS), sockolet (3000#, 6000#) et threadolet, avec poids et surface de peinture.
- Raccords forgés : demi-manchons et manchons, à souder et filetés (3000#, 6000#).
- Une série XS de weldolet n'est jamais plus légère que la STD.
- Le changement de schedule ou de classe ne modifie plus la taille choisie.
- Format de fichier : version 5 (les versions 1 à 4 restent importables).

## 1.3.2 - 2026-10-26

- Icône du raccourci : tous les fichiers sont à la racine du dépôt (plus de dossier `icons/`), car l'envoi par l'interface web de GitHub aplatit les dossiers et cassait les chemins du manifeste.
- Nouvel identifiant d'application dans le manifeste, pour forcer Chrome à réinstaller avec la bonne icône.
- Service worker : un fichier manquant n'empêche plus l'installation.

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
