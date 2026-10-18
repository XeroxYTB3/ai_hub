# Changelog

Les paquets de mise à jour sont complets : installer la dernière version suffit.

## 10.0.63 (à venir)
- Version finale de la série de revues : sécurité, robustesse, tests, installeur, documentation.

## 10.0.5x à 10.0.62
- Routage des clés par type de tâche, avec raison affichée (10.0.54).
- Index sémantique pondéré par la rareté des mots (10.0.55).
- Contrôle de syntaxe étendu après écriture : CSS, TOML, YAML (10.0.58).
- Budget de tokens par conversation : /budget N (10.0.60).
- Audits : sécurité Electron et instructions IA (SSRF, ouverture d'URL), vérification obligatoire des empreintes des mises à jour, écritures atomiques, tests (12 puis 16 tests).

## 10.0.46 à 10.0.49
- Contrôle à distance : actions et fichiers joints affichés comme dans l'app (Télécharger, Aperçu, Tout télécharger).
- Lignes de réflexion doublées (Ruminant, Fixing…) masquées dans les réponses lues.
- /plan : plans AHP dans le dossier .aihubplan (voir, exécuter).
- Points de restauration, terminal intégré, verrous par fichier, client MCP minimal, reprise après un plantage.

## 10.0.42 à 10.0.45
- Contrôle à distance par site web (PeerJS), code de connexion copiable.
- Plus aucun survol sur les cartes de Paramètres.

## 10.0.29 et 10.0.30
- Correction de la lecture des réponses (erreur d'échappement dans l'extraction) et lecture des blocs de code CodeMirror de ChatGPT.

## 10.0.15 à 10.0.19
- @tool : outils persistants de l'IA et paquets npm/pip, avec confirmation.
- Animations unifiées, bouton « Signaler un bug », focus du chat au retour de fenêtre.
- Notifications Windows sous le nom « AI Hub », nouvelle icône noir et blanc.

## Dette connue
- index.html contient 15 blocs de style empilés (le dernier surclasse les autres) et des fonctions de dessin de la bibliothèque définies deux fois puis neutralisées. À nettoyer dans une version dédiée, avec un test visuel.
- Le sandbox Electron des fenêtres n'est pas activé faute de test réel.