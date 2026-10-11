# AI Hub (mode local) vs Cursor : comparatif honnête

Prix Cursor relevés le 11/10/2026 (cursor.com/fr/pricing et guides tiers, les sources divergent sur les crédits inclus) : Hobby gratuit, Pro 20 $/mois, Pro+ 60 $/mois, Ultra 200 $/mois, Teams à partir de 40 $/utilisateur. Depuis peu, les limites sont en calcul facturé aux tarifs API (au moins 20 $ de calcul sur Pro), et le mode Auto n'est plus illimité d'après une source. Vérifie la page officielle avant de t'engager.

| Critère | Cursor | AI Hub (4.4.0) |
|---|---|---|
| Coût | 20 à 200 $/mois, dépassement facturé au tarif API | Les abonnements/comptes gratuits que tu as déjà (Claude, ChatGPT, Gemini) : 0 $ en plus, mais limites par compte |
| Vitesse d'un tour | Rapide : appel API direct, streaming, plusieurs outils en parallèle | Plus lent : AI Hub pilote les pages web (collage, attente, lecture), quelques secondes de plus par tour |
| Contexte du code | Index du projet (embeddings), sait retrouver le bon fichier seul | CARTE + @outline + @grep + @read fn:nom : correct, mais l'IA doit chercher elle-même et chaque tour coûte un message |
| Édition | Diffs natifs dans l'éditeur, Tab, agents en arrière-plan et en parallèle | @edit/@replace avec contrôle syntaxe, diff, annulation par tour, commit git ; un seul agent à la fois |
| Gros projets (heures) | Agents longs, reprise propre | @task : plan de 15 à 60 tâches partagé entre toutes les clés, rotation des clés, jusqu'à 400 tours, commit git après chaque tâche, attente automatique quand toutes les clés sont en limite |
| Qualité du modèle | Modèles de pointe au choix + modèles maison | Celui de la page web de chaque compte (souvent très bon, mais pas toujours le même d'un compte à l'autre) |
| Fiabilité | Produit commercial, support | Dépend de l'interface web des sites : une mise à jour de leur page peut casser la lecture/écriture |
| Conditions d'utilisation | Prévu pour cet usage | Automatiser des comptes grand public et en multiplier peut contredire les conditions des sites : risque de limitation ou de blocage de compte |

## Verdict
- Petite et moyenne tâche : Cursor est plus rapide et plus confortable.
- Très gros projet à budget quasi nul (par exemple un mod Minecraft complet) : AI Hub est faisable parce que le travail est découpé (PLAN.md + @task), sauvegardé (git) et repris par n'importe quelle clé, mais compte plusieurs heures, sans garantie de qualité sans boucle de compilation.
- Pour un mod Minecraft : installe JDK et Gradle, et demande à l'IA de lancer la compilation (@run gradle build) après chaque tâche, c'est ce qui fait la différence entre « beaucoup de code » et « code qui marche ».

## Limites connues d'AI Hub
Pas d'index sémantique, pas d'agents parallèles, pas d'autocomplétion, et chaque tour passe par une page web.