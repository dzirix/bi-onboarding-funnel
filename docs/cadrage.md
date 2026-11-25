# Cadrage — Dashboard de suivi du funnel d'onboarding

> **Projet personnel — données fictives.** Le contexte, les utilisateurs et les chiffres sont synthétiques. Ce document illustre une démarche de cadrage d'un outil de pilotage.

## 1. Problème

Les équipes qui opèrent un parcours d'onboarding digital (création de compte, vérification d'identité, signature) savent combien de dossiers aboutissent chaque semaine — mais pas **où** les utilisateurs abandonnent, ni **pourquoi**. Les relances sont donc génériques et les améliorations du parcours sont décidées à l'intuition.

## 2. Utilisateurs et besoins

| Utilisateur | Besoin exprimé | Décision que l'outil doit éclairer |
|---|---|---|
| Responsable onboarding | « Je veux voir en 30 secondes si le funnel se dégrade. » | Faut-il alerter, et sur quelle étape ? |
| Product Owner du parcours | « Je veux comparer les canaux : le mobile convertit-il moins bien que le web ? » | Où investir l'effort produit ? |
| Support / opérations | « Je veux savoir si les abandons viennent de l'étape d'identité ou de la signature. » | Où porter l'assistance et les relances ? |

## 3. Indicateurs retenus — et pourquoi

| Indicateur | Définition | Pourquoi celui-ci |
|---|---|---|
| Entrées par étape | Nombre de parcours ayant atteint chaque étape du funnel | La base de tout le reste ; sans dénominateur fiable, les taux ne valent rien |
| Taux de conversion d'étape | Entrées de l'étape N+1 ÷ entrées de l'étape N | Localise précisément l'étape qui « fuit » |
| Taux d'abandon d'étape | 1 − taux de conversion | Formulation orientée action : c'est sur l'abandon qu'on agit |
| Taux de complétion global | Parcours signés ÷ parcours initiés | L'indicateur de synthèse pour le management |
| Répartition par canal | Mêmes mesures, filtrées web / mobile | Évite de « réparer » le mauvais canal |

**Indicateurs écartés** (et pourquoi) : le temps moyen par étape (utile, mais exige une instrumentation horodatée fiable qui n'existait pas au départ — prévu en v2) ; le motif d'abandon autodéclaré (taux de réponse trop faible pour être décisionnel).

## 4. Règles de lecture

- Un taux d'abandon d'étape supérieur à **25 %** déclenche une investigation.
- Toute comparaison entre canaux exige au moins **100 entrées** par canal sur la période, sinon l'écart n'est pas interprétable.
- Les données sont **synthétiques** dans ce projet de démonstration ; la structure (étapes, définitions, seuils) est celle qui serait branchée sur les événements réels du parcours.

## 5. Périmètre de la v1

- Une page autonome, lisible sans formation.
- Filtres : canal (tous / web / mobile) et période (deux jeux de données d'exemple).
- Hors v1 : alertes automatiques, export, temps par étape.

## 6. Ce que ce cadrage m'a appris

La difficulté n'est pas technique : c'est de **définir chaque étape sans ambiguïté** (à quel événement exact un parcours « entre » dans l'étape identité ?) et de résister à la demande d'indicateurs supplémentaires tant que les définitions de base ne sont pas stabilisées.
