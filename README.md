# TBad
#### Application de gestion de compétition de badminton

---

## Invariants
### Module Conception de compétition
- 1 compétition de badminton est composé d'un nombres de matchs limité. 
- 1 compétition se déroule sur plusieurs jours.
- La compétition se déroule dans un ou plusieurs gymnases. Ainsi il y a un nombre de terrains définis.


- Chaque match est intégré au sein d'un tableau
- Un tableau est composé par la discipline (SH, SD, DH, DD, DX) et par son niveau.
- La durée d'un match dépend du niveau et du tableau.
- 1 tableau peut avoir 
  - soit des phases en élimination directe, 
  - soit des phases de poules puis d'élimination directe.


- 1 joueur ne peut s'inscrire sur au maximum 2 tableaux
- Une inscription d'un joueur contient le classement du joueur, ainsi que les souhaits de tableaux du joueur


- Un match se déroule sur 2 sets gagnants de 21
- La gestion du Score doit être paramétrable.

### Module Génération échéancier
- 1 tableau peut être contraint de se dérouler que sur un jour
- 1 joueur ne peut faire plus de 8 matchs par jour
- Chaque joueur à droit à au minimum 20 minutes de temps de repos
- Un tableau est découpé en Tour (poules : Tour 1, Tour 2, Tour 3/KO : Quart de finale, Demi-Finale, Finale).
- Un match d'un Tour ne peut se dérouler que si les matchs du Tour précédent sont terminés

### Durée de matchs
|                | Simple Homme | Simple Dame | Double Homme | Double Dame | Double Mixte |
|:--------------:|:------------:|:-----------:|:------------:|:-----------:|:------------:|
| Promotionnelle |    29 min    |   27 min    |    27 min    |   27 min    |    27 min    |
| Départementale |    32 min    |   30 min    |    30 min    |   30 min    |    30 min    |
|   Régionale    |    35 min    |   33 min    |    33 min    |   33 min    |    33 min    |
|   Nationale    |    45 min    |   43 min    |    43 min    |   43 min    |    43 min    |


### Têtes de séries
#### Elimination directe
| Nombre de participants  | 15 ou moins | entre 16 à 31 | entre 32 à 63 | 64 ou plus |
|:-----------------------:|:-----------:|:-------------:|:-------------:|:----------:|
| Nombre de Tête de Série |      2      |       4       |       8       |     16     |

#### Poules + KO
| Nombre de participants  | 15 ou moins | entre 16 à 31 | entre 32 à 63 | 64 ou plus |
|:-----------------------:|:-----------:|:-------------:|:-------------:|:----------:|
| Nombre de Tête de Série |      2      |       4       |       8       |     16     |

Dans un tableau où les éliminatoires prennent la forme de poules, les mêmes proportions doivent
être respectées. Toutefois, elles peuvent être dépassées pour atteindre le chiffre de une tête de
série par poule.

Les têtes de série sont placées dans le tableau de la manière suivante :
- la tête de série n° 1 au début du demi-tableau supérieur
- la tête de série n° 2 à la fin du demi-tableau inférieur ;
- les têtes de série n° 3 et 4 au début du 2e quart de tableau et à la fin du 3e quart de tableau,
par tirage au sort ;
- les têtes de série n° 5, 6, 7 et 8 au début des 2e et 4e et à la fin des 5e et 7e huitièmes de
tableau.


## Fonctionnalités
- Dimensionnement de la compétition : Définition du nombre de matchs en fonction des contraintes 
  - créneaux horaires, 
  - taille des gymnases, 
  - discipline, 
  - découpage par niveau
- Concevoir une compétition : Proposition de format des tableaux (poules + KO ou K0) en fonction du nombre d'inscrit
- Tirage au sort et assignation des joueurs
- Générer un échéancier

## Contraintes techniques
- TDD (Diamond Outside in)
- DDD (context map à générer)
- BDD (tests d'acceptance)
- Clean code
- Architecture domaine centrique (clean architecture)
- Event sourcing ?
- Documentation vivante (génération de markdown, mermaid, ...)
- Code review / pull requests systématique
- CI (exécution des tests et affichage des tests d'acceptance)
- .NET C#
- Développé en français

## Workflow
1. Définition du besoin (Janvier 2023)
   1. via excalidraw
2. Introduire les scénarios/exemples (Example mapping) (Février 2023)
   1. via excalidraw
3. Automatiser ces scénarios/exemples sous forme de tests d'acceptance (gherkin ou non) (Mars 2023)
4. Réalisation (Mars 2023)


## Expression du besoin
![Conception de compétition](1_Definition_du_besoin/Expression_du_besoin.png)