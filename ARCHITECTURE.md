# Architecture de Lightbox

Version 1.0.0 · HTML, CSS et JavaScript natifs.

| Fichier | Rôle |
| --- | --- |
| index.html | Présentation bilingue et accès à la table. |
| lightbox.html | Interface, styles, traductions, gestes tactiles et guides. |
| favicon/favlightbox.png | Icône du navigateur et de l’écran d’accueil iOS. |

## Organisation de la table

La photo importée est affichée via une URL de Blob. Les Pointer Events alimentent le déplacement et le zoom. Les transformations CSS cadrent l’image et appliquent le miroir. Les filtres SVG renforcent le trait ou éclaircissent les gris.

Les portées et la perspective occupent deux SVG indépendants du cadrage de la photo. La longueur de référence de 50 mm détermine les dimensions de lettrage. La luminosité agit sur la surface entière.

Le gel global masque les commandes et suspend les gestes. Les verrous de taille et de cadrage gardent leur état à la libération de la table. La Screen Wake Lock API est sollicitée si disponible.

Le code mémorise la langue et l’étalonnage dans localStorage. La photo et son cadrage restent propres à la session. Aucune bibliothèque externe ni étape de compilation.
