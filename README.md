# AI Hub

AI Hub est une application de bureau Windows (Electron) qui regroupe tes comptes web Claude, ChatGPT et Gemini comme des « clés ». Elle choisit la clé la plus adaptée, bascule toute seule sur une autre quand une limite est atteinte, et pilote le dossier d'un projet par de simples instructions.

## Installation

1. Lance AI-Hub-Setup.exe (installeur noir et blanc).
2. Ouvre AI Hub, ajoute tes comptes dans la zone « Clés » (la connexion se fait sur les vrais sites).
3. Crée un projet : un dossier de ton PC (mode local) ou une conversation en ligne.

Tes comptes, scripts et réglages sont stockés dans %APPDATA%\ai-hub et ne sont pas supprimés par la désinstallation.

## Mode local

L'IA lit et modifie le dossier choisi par des lignes qui commencent par @ (@read, @edit, @run, @task…). Chaque modification est sauvegardée avant d'être appliquée et peut être annulée (@undo, « Annuler ce tour », « Revenir ici »). Les commandes système demandent ta confirmation.

Commandes gratuites (0 crédit), à taper dans la barre de chat : tape / pour ouvrir le menu, /aide pour la liste complète. Exemples : /tree, /read, /grep, /ctx, /plan, /agents, /eco, /budget.

Dans le message, @fichier, @dossier/ ou @fichier:10-40 joignent du contexte du projet.

## Plans

/plan suivi d'un objectif crée le dossier .aihubplan et fait écrire à l'IA un plan au format AHP (une tâche par ligne : fichiers, dépendances, vérification, taille). /plan voir le contrôle, /plan executer le transforme en tâches partagées entre toutes les clés.

## Mises à jour

Les mises à jour sont des paquets .aihubupdate complets (4 fichiers, numéro de version strictement croissant). Elles s'installent depuis Paramètres > Mises à jour, avec retour automatique à la version précédente si elles ne démarrent pas. Avant de publier un paquet : python verify-update.py ai-hub-update-X.Y.Z.aihubupdate

## Contrôle à distance

Paramètres › Général › Contrôle à distance affiche un lien et un code. Ouvre le lien sur un téléphone ou un autre PC : la page docs/index.html (hébergée sur GitHub Pages) se connecte directement à AI Hub, qui doit rester ouvert sur le PC. Le lien contient un secret : ne le partage qu'avec tes propres appareils. « Générer un nouveau code » invalide les anciens liens.

## Développement

- Sources : work/src (main-core.js, preload.js, webview-preload.js, index.html).
- Tests : node --test work/tests/logic.test.js work/tests/audit.test.js
- Installeur : work/setup/Setup.cs.
- Le site distant : docs/index.html, à déposer dans le dépôt GitHub.

Voir CHANGELOG.md pour l'historique et MENTIONS-LEGALES.md pour les mentions légales.