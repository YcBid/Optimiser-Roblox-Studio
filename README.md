# PerfMonitor

Moniteur de performances et analyseur d'optimisation pour Roblox, en un seul LocalScript. Il affiche les FPS en direct, détecte ce qui alourdit un modèle ou une map, et propose des correctifs applicables en un clic.

Interface noir transparent, sans animation, déplaçable et redimensionnable.

## Fonctionnalités

### Barre FPS
- FPS et temps de frame en direct, mini-graphique des dernières secondes
- Alerte visuelle (contour rouge + notification) quand les FPS restent sous un seuil réglable
- Mode compact

### Analyse de modèle
- Ciblage 3D : survolez et cliquez un modèle du monde, navigation parent / enfant (Q / E)
- Score d'optimisation sur 100 avec verdict (Optimisé, Moyen, Non optimisé)
- Plus de 15 métriques : pièces, MeshParts, unions CSG, MeshIds uniques, CastShadow, collisions Precise, pièces non ancrées, Touch/Query inutiles, transparence, lumières avec ombres, effets, scripts, SurfaceGuis, joints, decals
- Liste des problèmes triés par gravité, avec conseil pour chacun
- Clic sur un problème : les pièces concernées sont surlignées en 3D
- Test d'impact : mesure en ms/frame le coût de rendu réel du modèle (visible vs masqué)
- Rapport texte copiable

### Correctifs en un clic
- Bouton Corriger par problème, ou Tout corriger
- Correctifs : CastShadow, CanTouch/CanQuery, CollisionFidelity, RenderFidelity, ombres des lumières, effets
- Annulation complète avec Annuler
- Les changements ne touchent que le client : à reporter ensuite dans Studio

### Classement de la map
- Scan de tous les modèles, classés par pire score ou par nombre de pièces
- Filtre par nom ou chemin
- Clic sur un modèle pour le détailler

### Profileur
- Enregistrement (F8) : FPS moyen, 1 % bas, temps de frame p50 / p95 / p99, pire frame, frames de plus de 33 ms et 50 ms, verdict
- Détecteur de pics de frame avec horodatage
- Heartbeat, pas physique, débit réseau, mémoire par catégorie

### Système
- Graphique FPS, moyenne, 1 % bas, min / max, ping, mémoire client, instances, primitives, qualité graphique

### Réglages
- Taille et opacité de l'interface, couleur d'accent
- Sévérité des seuils : Strict, Normal, Souple
- Surlignage au survol et à la sélection, exclusion des personnages
- Niveau de qualité graphique pour comparer les FPS

## Installation

1. Dans Roblox Studio, ajoutez un `ScreenGui` dans `StarterGui`.
2. Ajoutez un `LocalScript` enfant de ce `ScreenGui`.
3. Collez le contenu de `PerfMonitor.lua` dans le LocalScript.
4. Lancez une partie (Play). La barre FPS apparaît en haut à droite.

Si le script n'est pas enfant d'un ScreenGui, il en crée un automatiquement dans `PlayerGui`.

## Raccourcis

| Touche | Action |
|---|---|
| F6 | Ouvrir / fermer le panneau |
| F7 | Ré-analyser la sélection |
| F8 | Démarrer / arrêter l'enregistrement |
| Q / E | Niveau parent / enfant du modèle ciblé |
| Glisser | Déplacer la barre ou l'en-tête |

## Notes

- Pensé pour être utilisé en développement et en test. Retirez-le de la version publiée de votre jeu.
- Le test d'impact et le masquage sont locaux et temporaires.
- Les seuils du score sont des repères génériques ; ajustez la sévérité selon votre type de jeu.
- Compatible clavier / souris et tactile.

## Licence

À choisir (MIT recommandé).
