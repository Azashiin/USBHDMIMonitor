# Réglages Image et ICC — 1.52.1 / build 1054

## Fonctionnement

L'interface utilise un thème sombre, un aperçu central et un panneau Image inspiré des menus d'écran et de télé. Les modes Standard, Cinéma, Jeu, Dynamique et Personnalisé mémorisent chacun leurs réglages. Luminosité, contraste, couleur et netteté utilisent une échelle de 0 à 100 ; la température se choisit entre Chaud, Neutre et Froid. La netteté à 0 conserve le signal sans accentuation supplémentaire. Une remise à zéro n'affecte que le mode courant.

L'onglet Avancé regroupe gamma, teinte et gains RVB indépendants, puis l'accès aux profils ICC. Les anciennes préférences de la 1.52.0 sont migrées vers Personnalisé lorsqu'elles diffèrent du neutre. Les modes sont des préréglages visuels ; ils ne changent ni le rétroéclairage de l'écran, ni le délai de capture, ni l'espace colorimétrique de la source.

La chaîne vidéo est : conversion Media Foundation vers RVB, accentuation réglable, balance des blancs et réglages d'image, conversion du profil source vers le profil de l'écran, affichage Direct3D 11. L'original désactive aussi l'accentuation et la conversion ICC. Le profil de source par défaut suppose un signal SDR sRGB après la conversion du pilote ; utilisez un profil adapté si votre source possède une autre caractérisation.

Le gestionnaire accepte les profils ICC/ICM RVB de type entrée, écran ou espace couleur. Les profils corrompus, absents, CMJN, DeviceLink, abstraits et à couleurs nommées sont refusés. Les profils ne sont ni installés ni affectés aux écrans dans Windows.

Le moteur Windows ICM calcule une LUT 3D de 33 × 33 × 33 points, interpolée sur le GPU. Le calcul s'effectue dans un seul thread de travail : une nouvelle demande remplace celle en attente et un résultat périmé n'est pas appliqué. Une conversion refusée conserve la dernière conversion valide et affiche une erreur. Les quatre intentions sont perceptive, colorimétrique relative, saturation et colorimétrique absolue. La conversion entre deux profils identiques utilise l'identité pour éviter les décalages du moteur ICM, conformément aux [recommandations de Microsoft](https://learn.microsoft.com/en-us/windows/win32/api/icm/nf-icm-createmultiprofiletransform).

En destination automatique, la fenêtre interroge le profil Windows du moniteur actuel. Elle le recharge au changement de moniteur ou de configuration d'affichage. En l'absence de profil, elle utilise sRGB. Avec Windows Advanced Color, les requêtes historiques peuvent également renvoyer l'hypothèse sRGB ; voir la [documentation Microsoft sur Advanced Color et ICC](https://learn.microsoft.com/en-us/windows/win32/wcs/advanced-color-icc-profiles).

Les captures PNG/JPEG et la copie passent par une deuxième conversion **source vers sRGB**, sans la correction propre au moniteur ni les notifications de l'aperçu. Les valeurs du fichier sont en sRGB. Le mode Original ignore également cette conversion. Les enregistrements et replays restent indépendants du studio couleur et conservent les couleurs de la source.

## Validation et limites

- Les tests vérifient l'identité, les quatre intentions, un profil RVB à courbe linéaire distincte de sRGB, l'interpolation trilinéaire, le rejet des profils invalides et l'annulation des résultats périmés.
- Un test natif compare les pixels réellement rendus par Direct3D au calcul de référence, avec une destination d'écran différente de celle de l'export. Il vérifie aussi le mode Original, la reconstruction des textures, le rendu logiciel WARP et le refus d'une capture pendant un calcul ICC.
- La mire BGRA déterministe s'ouvre sans matériel et n'active pas les threads de capture ni d'audio. Les réglages et les chemins Unicode sont persistants. La disposition est contrôlée à plusieurs dimensions, avec et sans panneau.
- Le pipeline reste SDR 8 bits. Il ne mesure pas l'écran, ne remplace pas une calibration par sonde, ne gère pas les métadonnées HDR et n'ajoute pas de traitement couleur aux MP4.
- La LUT est une approximation interpolée du moteur ICM. Aucun seuil de Delta E mesuré ni conformité à une chaîne de production professionnelle n'a été établi.
- Une validation sur le boîtier, les pilotes, les écrans et les profils du testeur reste nécessaire. Le guide [TEST_GUIDE_FR.md](../TEST_GUIDE_FR.md) détaille les essais matériels.
