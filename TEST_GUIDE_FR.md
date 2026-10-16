# USB HDMI Monitor 1.52.1 — préversion publique

Cette préversion publique conserve les fonctions de capture et propose une interface sombre avec un menu Image inspiré des écrans et des télés. La gestion ICC est accessible dans Avancé. Les essais matériels restent à effectuer avec les testeurs.

## Essayer sans boîtier

Installez l'application avec `USBHDMIMonitor-Setup-v1.52.1.exe`, puis utilisez le raccourci **Mire de demonstration** du menu Démarrer. Il lance l'application avec `--demo`. L'application affiche une mire fixe sans ouvrir de caméra, de microphone ou de périphérique de capture. Le bouton **Mire démo** permet aussi d'y accéder depuis l'application.

Dans **Image**, choisissez un mode **Standard, Cinéma, Jeu, Dynamique ou Personnalisé**, comme dans le menu d'un écran ou d'une télé. Ajustez **Luminosité, Contraste, Couleur et Netteté** de 0 à 100, puis la température **Chaud / Neutre / Froid**. Les valeurs neutres sont 50 pour luminosité, contraste et couleur, et 0 pour la netteté. Chaque mode mémorise ses propres valeurs ; **Réinitialiser ce mode** restaure seulement le mode sélectionné.

**Voir l'image d'origine** ignore temporairement les réglages et les profils ICC. La molette fait défiler le panneau sur les petits écrans. Les menus de mode et de température se commandent aussi avec les flèches et Entrée ; Échap les ferme. Le bouton **Image** masque le panneau pour agrandir l'aperçu.

L'onglet **Avancé** regroupe gamma, teinte et balance Rouge/Vert/Bleu (50 = neutre). La **Gestion ICC** reste accessible dans cet onglet. Le profil source est sRGB par défaut et le profil de destination est celui de l'écran Windows. Les boutons **sRGB**, **Auto** et **Réinitialiser les profils** rétablissent ces valeurs. Quatre intentions de rendu sont disponibles. Attendez l'état **Conversion ICC prête** avant une capture d'image.

Ces commandes modifient l'image vidéo dans l'application. Elles ne règlent pas le rétroéclairage physique de l'écran. Le mode Jeu est un préréglage d'image et ne modifie pas la latence de capture. Les réglages de la 1.52.0 sont repris dans le mode Personnalisé.

La mire sert à vérifier le fonctionnement du logiciel. Elle ne calibre pas l'écran. Les réglages d'image précèdent la conversion ICC. Consultez le [guide Image et ICC](docs/PICTURE_SETTINGS_FR.md) pour les détails et limites.

## Tester avec le boîtier USB HDMI

Lancez `USBHDMIMonitor.exe` normalement, ou cliquez sur **Quitter la mire**. L'application recherche les périphériques et peut ouvrir automatiquement la source sélectionnée. Choisissez le bon boîtier dans **Source vidéo**, puis sa résolution et sa fréquence.

1. Vérifiez l'image et le son pendant au moins 15 minutes, puis le plein écran et le retour en fenêtre.
2. Testez une source noire, une scène sombre, des mouvements rapides et une mire de la console. Notez les niveaux de noir, la fluidité et le décalage audio éventuel.
3. Débranchez/rebranchez le boîtier, coupez/rallumez la source HDMI et changez de résolution. Vérifiez la reprise sans blocage.
4. Faites une capture PNG et une copie avec Ctrl+C ; ouvrez l'image enregistrée. Testez aussi le JPEG depuis les paramètres.
5. Enregistrez une vidéo avec le son, puis ouvrez le MP4. Attendez au moins 35 secondes et sauvegardez deux replays espacés de quelques secondes ; vérifiez leur durée et leur lecture.
6. Testez les réglages couleur et un profil ICC connu. Si plusieurs écrans ont des profils différents, déplacez la fenêtre entre eux et vérifiez la mise à jour du profil automatique.
7. Fermez puis relancez l'application : profils, intention et réglages doivent être conservés. Testez également la réduction dans la zone de notification et la restauration.

Pour un retour utile : modèle du boîtier, source HDMI, résolution/fréquence, version de Windows et étapes exactes du problème. Les journaux peuvent être exportés depuis **Paramètres > Avancé**.

## Raccourcis par défaut

- F2 : capture d'image ; Ctrl+C : copie de l'image.
- F9 : démarrer/arrêter un enregistrement ; F3 : sauvegarder un replay.
- F10 : paramètres ; F11 : plein écran ; Échap : retour en fenêtre.
- M : couper/rétablir le volume.

Les captures d'image sont converties vers sRGB, sans les notifications superposées. Les vidéos et les replays gardent les couleurs originales de la source. Le mode démo permet les captures d'image ; l'enregistrement et le replay nécessitent une vraie source vidéo.

La configuration est conservée dans `%APPDATA%\USB HDMI Monitor`, avec les couleurs dans `USBHDMIMonitor.ini.color.ini`. Les chemins des profils importés restent des références aux fichiers d'origine : conservez ces fichiers à leur emplacement. Les journaux se trouvent dans `%LOCALAPPDATA%\USB HDMI Monitor\Logs`.

## Validation de cette livraison

32 contrôles natifs automatisés et les contrôles de livraison sont fournis dans `VALIDATION_RESULTS.txt`. Ils couvrent notamment les médias synthétiques, les conversions ICC, le rendu GPU, les captures sRGB, les chemins Unicode et les anciens correctifs de stabilité.

L'interface a aussi été vérifiée sur la mire. La capture HDMI réelle, le monitoring audio matériel, les reconnexions physiques et les sessions prolongées restent à valider par le testeur. Aucune exactitude colorimétrique mesurée n'est revendiquée. Cette chaîne d'affichage est SDR 8 bits ; le HDR n'est pas implémenté.

L'installateur propose le français et l'anglais, les raccourcis, les mises à jour et la désinstallation. Les préférences sont conservées lors d'une mise à jour et d'une désinstallation. Les guides sont disponibles dans le dépôt public ; les résultats des contrôles et les sommes SHA-256 accompagnent la préversion.
