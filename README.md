# BI — Onboarding Funnel

> **Projet personnel — données fictives.** Tous les chiffres du dashboard sont synthétiques et embarqués dans la page.

## Objectif

Rendre visible **où** un parcours d'onboarding digital perd ses utilisateurs : quelles étapes convertissent, lesquelles font abandonner, et si le phénomène dépend du canal (web / mobile).

Ce projet s'inspire d'une démarche réelle de construction d'un outil de pilotage : partir des besoins des utilisateurs, définir des indicateurs peu nombreux mais sans ambiguïté, puis seulement construire l'affichage.

## Contenu

| Fichier | Contenu |
|---|---|
| `docs/cadrage.md` | Cadrage complet : problème, utilisateurs, indicateurs retenus et écartés, règles de lecture |
| `dashboard/index.html` | Dashboard autonome (une page, aucune dépendance, données synthétiques embarquées) |

## Le dashboard

Ouvrir `dashboard/index.html` dans un navigateur — aucune installation, aucun serveur.

- **5 étapes du funnel** : parcours initié → identité vérifiée → contrat lu → consentement donné → signature complétée.
- **Par étape** : nombre de parcours, taux de conversion depuis l'étape précédente, taux d'abandon.
- **Filtres** : canal (tous / web / mobile) et période (deux mois d'exemple).
- **Alerte visuelle** : toute étape dont l'abandon dépasse **25 %** est signalée « à investiguer » (règle définie dans le cadrage).
- **Synthèse** : parcours initiés, parcours signés, taux de complétion global, étape la plus fragile.

## Choix de conception

- **Autonome plutôt que connecté** : pour une démonstration, une page sans dépendance vaut mieux qu'une maquette d'outil BI non reproductible. La structure de données (entrées par étape, canal, période) est exactement celle qu'alimenterait un export d'événements réel.
- **Peu d'indicateurs, bien définis** : le cadrage (`docs/cadrage.md`) explique pourquoi le temps par étape et les motifs d'abandon autodéclarés ont été écartés de la v1.
- **Des seuils avant des couleurs** : le seuil d'investigation (25 %) est une règle métier documentée, pas un choix graphique.

## Suite envisagée

- Temps médian par étape (exige une instrumentation horodatée)
- Vue « cohorte hebdomadaire » pour distinguer un incident ponctuel d'une dérive lente
- Export des définitions d'indicateurs en dictionnaire de données versionné

---

*Projet personnel de démonstration — toutes les données sont fictives.*
