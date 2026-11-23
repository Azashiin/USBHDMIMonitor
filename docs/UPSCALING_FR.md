# Agrandissement FSR 1 — 1.53.0 / build 1056

Le moteur spatial reconstruit l'image du boîtier à la taille de l'aperçu, jusqu'à **3840 × 2160** en plein écran sur un affichage 4K. Il utilise les deux étapes officielles AMD FidelityFX Super Resolution 1 : **EASU** pour reconstruire les contours, puis **RCAS** pour la netteté adaptative.

## Activation

Ouvrez **Paramètres > Vidéo**, laissez **Autoriser l'agrandissement GPU** activé, puis cliquez sur **Moteur d'agrandissement** jusqu'à **FSR 1 - 4K**. Le bouton passe par Standard/Douce, Pixels nets/Nette et FSR 1. Standard reste la valeur par défaut et les anciens choix sont conservés.

L'agrandissement s'applique lorsque l'aperçu est plus grand que la source. Il fonctionne en fenêtre et en plein écran ; une entrée 1080p n'est pas artificiellement convertie en 4K pour être ensuite affichée dans une petite fenêtre. En fenêtre, un badge **FSR1** dans l’en-tête indique la hauteur de reconstruction lorsqu’il y a assez de place ; cet en-tête est masqué en plein écran. La commande Netteté du panneau Image règle aussi la force de RCAS ; aucune seconde accentuation simple n'est ajoutée au rendu FSR.

**Voir l'image d'origine** ignore temporairement FSR et les corrections couleur. Les captures PNG/JPEG et le presse-papiers utilisent une cible GPU séparée à la résolution d'entrée, avec les réglages Image et la conversion sRGB. Les enregistrements et replays conservent aussi leur résolution et leurs couleurs de source.

## Compatibilité et coût

Le moteur emploie Direct3D 11, niveau de fonctionnalités **11.0**. Il n'exige pas une marque particulière de GPU. En cas d'indisponibilité, d'erreur de shader ou d'allocation, le logiciel conserve l'affichage standard et indique le repli. Le rendu reste SDR 8 bits.

FSR 1 travaille sur chaque image indépendamment : il ne génère pas d'images et n'attend pas les images suivantes. Les intermédiaires restent sur le GPU. La limite d'une image pour la file de présentation de la 1.52.2 est conservée. Le calcul ajoute toutefois un coût GPU : le délai physique manette-écran doit être comparé sur le boîtier, notamment en 1080p50 sur la RTX 4060 du testeur.

## Qualité et limites

Le résultat contient bien le nombre de pixels de la sortie choisie, mais un signal 1080p ne contient pas tous les détails d'une source 4K native. Ce moteur spatial n'est pas un modèle d'intelligence artificielle. Il peut rendre les contours plus nets ; les escaliers, la compression et le bruit de la source peuvent aussi devenir plus visibles. Comparez les mêmes scènes à la même taille, avec une netteté modérée.

Les contrôles automatisés vérifient les couleurs constantes, l'orientation, les tailles impaires, le redimensionnement, les limites d'allocation, le moteur matériel et WARP, un véritable tampon GPU UHD, l'intégration avec l'ICC et les dimensions natives des captures. Une mire et une comparaison bilinéaire/FSR sont générées pour inspection. Les mesures GPU synthétiques portent uniquement sur EASU + RCAS, après initialisation ; elles ne mesurent ni toute l'application ni le délai du boîtier.

## Composant tiers

L'implémentation AMD est figée au commit `a21ffb8f6c13233ba336352bdff293894c706575`, avec ses empreintes dans `third_party/fidelityfx-fsr/UPSTREAM.json`. Les en-têtes sont intégrés à la compilation, sans téléchargement à l'exécution. La licence MIT est livrée dans `THIRD_PARTY_NOTICES.txt`. Le code de l'application reste dans le dépôt privé.

Références : [AMD FSR 1](https://gpuopen.com/fidelityfx-superresolution/) et [implémentation officielle](https://github.com/GPUOpen-Effects/FidelityFX-FSR).
