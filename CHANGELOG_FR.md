# Historique des versions

Cet historique ne conserve plus que les grands jalons du produit.
Les petits correctifs, ajustements UI et etapes intermediaires trop fines sont volontairement retires.

## 1.51.0 - Build 1051

- Ajout d'un guide de demarrage integre directement dans la fenetre du moniteur, rendu sur l'overlay GPU moderne.
- Le guide met maintenant en avant les controles principaux et peut etre relance depuis `Parametres > General`.

## 1.50.0 - Build 1050

- Suppression du fallback legacy actif pour `Parametres` : l'application ouvre maintenant toujours la fenetre moderne custom au lieu d'alterner entre deux implementations runtime.
- Clarification du wording autour de l'option d'attente de signal au demarrage : il est maintenant explicite que si cette attente est desactivee alors que le lancement Windows reste actif, le moniteur s'ouvre directement a la connexion.

## 1.49.0 - Build 1049

- Ajout d'un vrai export diagnostic depuis l'application, accessible dans la page moderne `Avance`.
- L'export genere maintenant un dossier exploitable pour le support avec le log courant, la configuration actuelle et un resume systeme.

## 1.48.0 - Build 1048

- Durcissement de la distribution client autour d'un flux base sur l'installateur uniquement.
- Ajout des fichiers d'integrite `SHA256SUMS.txt` et `RELEASE_MANIFEST.txt`.
- Nettoyage des scripts et de la documentation de release pour mieux coller au produit reellement distribue.

## 1.45.0 - Build 1045

- Ajout d'une vraie confirmation visuelle de sauvegarde pour `Instant Replay` et pour `Record`.
- Les clips sauvegardes utilisent maintenant un flash, une reduction vers le coin, une vignette temporaire, la duree reelle du clip et un clic direct vers le fichier dans l'explorateur Windows.

## 1.43.0 - Build 1043

- Refonte du pipeline `Instant Replay` pour mieux separer la capture live, le buffer circulaire et l'export.
- L'export replay se fait maintenant en arriere-plan, avec ajout de metriques dans les logs pour le diagnostic et l'optimisation.

## 1.40.0 - Build 1040

- Refonte des pages d'information du logiciel dans la fenetre moderne `Parametres`.
- `A propos`, `Notes de version`, `Sur le developpeur` et `Mentions legales` ont ete retravailles comme un vrai espace support produit avec acces direct aux logs, a GitHub, au contact et au soutien du projet.

## 1.34.0 - Build 1034

- La nouvelle fenetre custom `Parametres` est devenue le chemin par defaut pour l'utilisateur.
- L'ancien chemin legacy reste disponible uniquement comme repli explicite pour la transition et la verification.

## 1.23.0 - Build 1023

- Debut de la grosse refonte de `Parametres` sur une nouvelle base UI custom dans `ui/`.
- Mise en place de la fondation en couches avec shell Win32, rendu Direct2D/DirectWrite, layout, input, scroll et pages dediees.

## 1.1.2 - Build 1012

- Unification du rendu du moniteur autour de `Direct3D 11`.
- Passage des captures d'ecran et du presse-papiers sur la frame finale GPU.
- Separation de la logique d'enregistrement en deux handlers dedies : `Record` et `Instant Replay`.

## 1.1.1 - Build 1011

- Renforcement important de la stabilite au demarrage, a la fermeture, a la reduction en tray et lors des pertes/reprises de signal ou d'audio.
- Reduction de l'impact de l'enregistrement et du replay sur la stabilite et la reactivite du preview live.

## 1.1.0 - Build 1010

- Transformation de l'application en vrai logiciel Windows installable au lieu d'un simple utilitaire portable.
- Ajout de l'installateur, de la desinstallation propre, des chemins Windows standards, de la configuration persistante et des logs runtime structures.

## 1.0.9 - Build 1009

- Ajout des premieres fondations dediees a l'enregistrement manuel et a `Instant Replay`.
- Apparition des controles utilisateur, raccourcis et parametres de sortie pour ces deux modes video.

## 1.0.8 - Build 1008

- Ajout des options de qualite de scaling plein ecran et de nettete amelioree.
- Amelioration de la qualite d'affichage sur les ecrans haute resolution sans modifier le flux HDMI source.

## 1.0.7 - Build 1007

- Ajout du watcher de demarrage et de l'integration tray.
- Introduction des options de lancement automatique et d'ouverture sur detection de signal.

## 1.0.6 - Build 1006

- Ajout de la capture d'ecran via `F2` et de la copie rapide dans le presse-papiers.
- Ajout du retour visuel de capture et de l'ouverture directe de l'image sauvegardee depuis la preview temporaire.

## 1.0.5 - Build 1005

- Ajout de la premiere vraie fenetre `Parametres` avec categories structurees comme `General`, `Demarrage`, `Captures`, `Audio`, `Video`, `Raccourcis` et `Avance`.

## 1.0.2 - Build 1002

- Refonte de l'interface du moniteur vers une vraie UI Windows plus produit.
- Ajout d'etats plus clairs, d'un meilleur retour visuel et de la persistance des reglages de session essentiels.

## 1.0.1 - Build 1001

- Migration du concept portable d'origine vers une vraie application Windows native avec sa propre base de code et son propre pipeline de moniteur.

## 1.0.0 - Build 1000

- Version portable d'origine.
