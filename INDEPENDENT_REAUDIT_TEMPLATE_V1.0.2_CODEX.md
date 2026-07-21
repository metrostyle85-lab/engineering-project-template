# Revérification indépendante ciblée — Engineering Project Template v1.0.2

## A. Identification

| Élément | Valeur contrôlée |
|---|---|
| Nature | Revérification indépendante ciblée de MAJ-01, des scénarios S1 à S5, de la non-régression directe et de la discipline Git de la correction |
| Date du contrôle | 2026-07-21 (Europe/Brussels) |
| Dépôt audité | `C:/Users/doumo/Desktop/Dev/Engineering Project Template` |
| Remote attendu et observé | `https://github.com/metrostyle85-lab/engineering-project-template.git` |
| Branche | `docs/template-1.0.2-lot-level-fields` |
| Base du lot | `6d3382f4b276350e9b752a215bf1b1c89e075b24` |
| Sommet initial audité | `28159852d21d8a36bd7be6d0706017d9f8a0e880` |
| Sommet corrigé revérifié | `a31559fe1850851262d35201c1da6ff883bddb6f` |
| Référentiel normatif | `C:/Users/doumo/Desktop/Dev/Engineering Playbook V2`, version `2.3.0` |
| Références normatives examinées | `playbook/M03_QUALITY_GATES.md` et `playbook/M04_PROMPT_CONTRACT.md` |

La présente mission est une revérification ciblée. Elle n'est ni un nouvel audit complet du Template, ni une Validation d'Architecture, ni une autorisation de fusion ou de publication.

Les conclusions ci-dessous reposent sur l'inspection directe des objets Git et des fichiers aux deux sommets indiqués, après exécution de `git fetch origin --prune --tags`.

## B. Vérification Git

### B.1 État du dépôt et des références

| Contrôle | Résultat | Statut |
|---|---|---|
| Racine réelle | `C:/Users/doumo/Desktop/Dev/Engineering Project Template` | PASS |
| Remote `origin` | URL attendue en fetch et push | PASS |
| Branche locale | `docs/template-1.0.2-lot-level-fields` | PASS |
| Branche distante suivie | `origin/docs/template-1.0.2-lot-level-fields` | PASS |
| HEAD local | `a31559fe1850851262d35201c1da6ff883bddb6f` | PASS |
| Sommet distant vérifié par `git ls-remote` | `a31559fe1850851262d35201c1da6ff883bddb6f` | PASS |
| Divergence local/distant | `0 / 0` | PASS |
| `main` local | `6d3382f4b276350e9b752a215bf1b1c89e075b24` | PASS |
| `origin/main` local après fetch | `6d3382f4b276350e9b752a215bf1b1c89e075b24` | PASS |
| `main` distant vérifié par `git ls-remote` | `6d3382f4b276350e9b752a215bf1b1c89e075b24` | PASS |
| Working tree | aucune entrée dans `git status --porcelain=v1 --untracked-files=all` | PASS |

Git a émis un avertissement d'accès au fichier global `C:/Users/doumo/.config/git/ignore`. Cet avertissement n'invalide pas la conclusion de propreté : l'absence de ce filtre global ne peut pas masquer un fichier non suivi ; elle tend au contraire à en exposer davantage. Aucun fichier modifié, indexé ou non suivi n'a été rapporté.

### B.2 Structure et chronologie de la correction

Le commit corrigé présente exactement un parent :

```text
a31559fe1850851262d35201c1da6ff883bddb6f
└── 28159852d21d8a36bd7be6d0706017d9f8a0e880
```

Il ne s'agit donc pas d'un merge commit.

La plage exclusive `2815985..a31559f` contient exactement un commit :

| Ordre | Commit | Date auteur | Sujet |
|---|---|---|---|
| 1 | `a31559fe1850851262d35201c1da6ff883bddb6f` | `2026-07-21T19:14:40+02:00` | `docs: keep lot-level roadmap guidance visible` |

La correction modifie exactement un fichier :

```text
M  blueprints/project/ROADMAP.md
```

Statistique : `1 file changed, 2 insertions(+), 4 deletions(-)`. Aucun fichier n'est ajouté ni supprimé.

### B.3 Absence de publication et de fusion

| Contrôle | Preuve directe | Statut |
|---|---|---|
| Tag local `v1.0.2` | `git tag --list` ne retourne que `v1.0.0` et `v1.0.1` | PASS |
| Tag distant `v1.0.2` | `git ls-remote --tags origin refs/tags/v1.0.2 refs/tags/v1.0.2^{}` ne retourne rien | PASS |
| Release GitHub `v1.0.2` | `gh release view v1.0.2 ...` retourne `release not found` | PASS |
| Correction fusionnée dans `main` | `git merge-base --is-ancestor a31559f main` retourne faux | PASS |
| Sommet initial fusionné dans `main` | `git merge-base --is-ancestor 2815985 main` retourne faux | PASS |
| Branches contenant `a31559f` | uniquement la branche candidate locale et sa branche distante | PASS |
| Base commune de `main` et `a31559f` | `6d3382f4b276350e9b752a215bf1b1c89e075b24` | PASS |

La branche candidate n'est pas fusionnée dans `main`. Aucun tag ni aucune Release `v1.0.2` n'existe au moment du contrôle.

## C. Limite liée au premier rapport absent

Le rapport complet du premier audit indépendant n'était pas matériellement disponible pour archivage ou comparaison. Aucun rapport d'audit ou de revérification propre à ce lot n'est présent dans le dépôt contrôlé. La présente revérification :

- ne reconstitue pas ce rapport depuis son résumé ;
- ne prétend pas en être une copie, verbatim ou autrement ;
- ne reprend pas de contenu détaillé qui ne peut pas être vérifié ;
- reproduit directement le défaut au commit `28159852d21d8a36bd7be6d0706017d9f8a0e880` ;
- contrôle directement la correction au commit `a31559fe1850851262d35201c1da6ff883bddb6f`.

**Qualification : limite documentaire compensée par la présente revérification autonome.**

Cette absence empêche uniquement d'archiver ou de comparer le texte intégral de l'ancien rapport. Elle n'empêche ni de reproduire le défaut initial, ni d'identifier le delta correctif, ni d'évaluer MAJ-01 et S1 à S5 sur les objets Git immuables désignés. Elle ne constitue donc ni un blocage ni une réserve résiduelle sur la conformité technique de la correction.

## D. Reproduction du défaut initial

Le fichier `blueprints/project/ROADMAP.md` a été lu directement au sommet `28159852d21d8a36bd7be6d0706017d9f8a0e880`.

Les seules indications selon lesquelles les trois champs :

- s'appliquaient exclusivement aux projets adoptant Engineering Playbook 2.3+ ;
- devaient rester inutilisés autrement ;
- portaient une information de planification ;
- ne remplaçaient pas le contrat de développement ;
- exigeaient une confirmation contractuelle avant Développement ;
- laissaient M03 seule autorité sur la classification ;

étaient réunies dans un unique commentaire HTML placé avant le bloc répétable.

Après suppression de tous les commentaires HTML, le contenu visible conservait notamment :

```text
Lot level: Standard

Level justification:

[Level justification]

Main risk factors: (optional)
```

mais ne conservait plus aucun contexte conditionnel ni aucune séparation durable entre planification et contrat.

Conséquences reproduites directement :

- un projet sans Playbook pouvait lire `Lot level: Standard` sans savoir que le champ devait rester inutilisé ;
- un projet sous Playbook 2.2 pouvait interpréter ce champ comme une règle applicable à cette version ;
- le caractère purement planificatoire de la Roadmap disparaissait autour de ces champs ;
- l'obligation de confirmation dans le contrat/prompt avant Développement disparaissait ;
- le fait que M03 soit l'autorité normative unique disparaissait.

Le défaut initial décrit par MAJ-01 est donc **confirmé et reproduit** depuis le commit initial, indépendamment du rapport absent.

## E. Analyse de la correction

Le fichier a été lu directement au sommet `a31559fe1850851262d35201c1da6ff883bddb6f`. La correction remplace le commentaire HTML normativement important par la note Markdown visible suivante, située dans le bloc répétable, entre `Expected outcome` et les trois champs :

> **Engineering Playbook 2.3+ only:** The fields below are planning aids. Leave them unused when the project does not adopt Engineering Playbook 2.3 or later. When the Playbook is adopted, confirm the lot level in the development contract or prompt before Development starts. This Roadmap does not replace that contract. M03 remains the sole authority for classification.

| Exigence ciblée | Analyse | Statut |
|---|---|---|
| Le commentaire HTML général d'organisation peut rester | Le commentaire `Organize work... Copy the block below...` reste présent et n'est pas porteur des garde-fous essentiels | PASS |
| Garde-fous en Markdown visible | La note est un blockquote Markdown visible, hors commentaire HTML | PASS |
| Note dans le bloc répétable | Elle se situe sous le titre, le statut, l'objectif, le scope et l'outcome du work package, avant ses champs de classification | PASS |
| Note copiée avec le bloc | Copier le bloc de `## [ID]` jusqu'au séparateur `---` emporte la note et les champs | PASS |
| Résistance à la suppression des commentaires HTML | Après retrait de tous les commentaires HTML, la note reste présente à l'identique | PASS |
| Portée Playbook 2.3+ | L'en-tête dit explicitement `Engineering Playbook 2.3+ only` | PASS |
| Champs inutilisés sans adoption 2.3+ | La note exige explicitement de les laisser inutilisés | PASS |
| Valeur de planification | Les champs sont explicitement qualifiés de `planning aids` | PASS |
| Confirmation avant Développement | La confirmation dans le contrat ou prompt avant le début du Développement est explicite | PASS |
| Roadmap distincte du contrat | `This Roadmap does not replace that contract` est explicite | PASS |
| Autorité normative de M03 | `M03 remains the sole authority for classification` est explicite | PASS |
| Aucune définition locale des niveaux | Aucun niveau n'est défini dans la note | PASS |
| Aucune duplication normative détaillée | Aucun critère, effet, invariant, mécanisme de reclassement ou logique de maximum n'est recopié | PASS |
| Aucun mécanisme concurrent | Aucun score, matrice ni champ `Expected validation depth` n'est ajouté | PASS |

La correction restaure donc la visibilité durable recherchée sans transformer la Roadmap en seconde source normative.

## F. Séparation planification / contrat

La comparaison directe avec M03 et M04 v2.3.0 établit les points suivants :

1. M03 §2.3 déclare que M03 est propriétaire de la classification et que les niveaux, critères, effets et règles de reclassement ne sont définis que dans ce module.
2. M03 précise que le niveau est proposé pendant la Définition et confirmé au plus tard dans le contrat de développement, avant le Développement.
3. M04 §3 déclare que le prompt constitue la référence officielle du lot de travail.
4. M04 §4.1 rend le niveau obligatoire dans tout contrat et exige au minimum le niveau, une justification synthétique et les principaux facteurs de risque ; la profondeur attendue est ajoutée lorsqu'elle apporte une information utile.
5. M04 §4.1 renvoie à M03 pour les définitions, critères, effets et règles de reclassement.

La note corrigée est cohérente avec cette répartition :

- la Roadmap conserve une valeur de planification ;
- le prompt/contrat reste la référence officielle du lot ;
- le niveau contractuel doit être confirmé avant Développement ;
- `ROADMAP.md` ne satisfait pas à lui seul M04 §4.1, car une aide de planification n'est pas le contrat officiel exigé par M04 ;
- en cas de divergence entre une valeur de Roadmap et le contrat, le contrat et les règles de M03 gouvernent l'exécution ;
- aucune seconde source normative n'est créée.

La Roadmap n'a pas à devenir un historique complet des reclassements. La correction n'impose pas cette fonction et ne bloque aucun mécanisme de reclassement appartenant à M03 et au contrat.

## G. Non-régression

### G.1 Immutabilité des trois autres fichiers initiaux

Les blobs sont identiques entre `2815985` et `a31559f` :

| Fichier | Blob à `2815985` | Blob à `a31559f` | Statut |
|---|---|---|---|
| `README.md` | `9730e3da949967a27bebfccf1e8b4eee1b22ab4a` | identique | PASS |
| `CHANGELOG.md` | `334ade1c53681a53762e595f994b59c8cc84c865` | identique | PASS |
| `blueprints/core/AI_CONTEXT.md` | `6841381080554d3e2c8815d66da719f392b68e0b` | identique | PASS |

### G.2 Contrôles directs sur la Roadmap et le delta

| Contrôle | Résultat | Statut |
|---|---|---|
| `Lot level:` présent | une occurrence | PASS |
| `Level justification:` présent | une occurrence | PASS |
| `Main risk factors:` présent | une occurrence | PASS |
| Valeur initiale | `Lot level: Standard` est conservé | PASS |
| Nouveau fichier | aucun | PASS |
| Autre fichier modifié | aucun | PASS |
| Liens Markdown | aucun lien Markdown n'existe dans le fichier corrigé et aucun lien n'est ajouté ou modifié par le patch ; aucune régression directe de lien | PASS |
| Section `Related` | aucun ajout ni changement dans le patch | PASS |
| Version | aucune ligne de version n'est ajoutée ou modifiée par la correction | PASS |

La correction est strictement circonscrite à la visibilité et au placement des garde-fous de `ROADMAP.md`.

## H. Scénarios S1 à S5

| Scénario | Résultat | Justification |
|---|---|---|
| S1 — Projet sans Playbook | **PASS** | Après suppression de tous les commentaires HTML, la note visible dit encore de laisser les champs inutilisés lorsque le projet n'adopte pas Playbook 2.3 ou ultérieur. Aucune adoption implicite n'est créée. |
| S2 — Projet Playbook 2.2 | **PASS** | `2.3+ only` exclut explicitement 2.2 ; un projet 2.2 entre dans le cas « does not adopt Engineering Playbook 2.3 or later » et laisse les champs inutilisés. `Standard` n'est donc pas présenté comme une règle 2.2. |
| S3 — Projet Playbook 2.3+ | **PASS** | Le niveau planifié reste lisible ; la note exige sa confirmation dans le contrat/prompt avant Développement et identifie M03 comme seule autorité de classification. |
| S4 — Roadmap Standard / contrat Critique | **PASS** | La Roadmap est explicitement une aide de planification et ne remplace pas le contrat. M04 fait du prompt la référence officielle ; le contrat Critique gouverne donc l'exécution, sous les règles de M03. |
| S5 — montée contractuelle Standard vers Critique | **PASS** | La note ne fige pas la valeur de Roadmap et ne définit aucun reclassement local. M03, autorité unique, permet la montée de niveau à tout moment ; le Playbook et le contrat gouvernent. |

## I. Constats

### Suivi de MAJ-01

**MAJ-01 — corrigé.**

Les garde-fous essentiels ne dépendent plus d'un commentaire HTML. Ils sont visibles, intégrés au bloc répétable, conservés après retrait des commentaires et alignés sur M03/M04 sans duplication normative.

### Nouveaux constats

| Classe | Nombre |
|---|---:|
| Bloquant | 0 |
| Majeur | 0 |
| Mineur | 0 |
| Observation | 0 |

Aucun nouveau constat n'est relevé dans le périmètre ciblé.

## J. Limites

- Le premier rapport complet n'était pas disponible ; cette revérification ne l'archive pas et ne le reconstitue pas.
- La mission est limitée à MAJ-01, S1 à S5, à la non-régression directe des fichiers désignés et à la discipline Git de la correction.
- Il ne s'agit pas d'un nouvel audit exhaustif de tous les blueprints ou de l'ensemble du Template.
- Le contrôle des liens porte sur la régression directe : le fichier corrigé ne contient aucun lien Markdown et le patch n'en ajoute ni n'en modifie.
- L'absence de tag et de Release décrit l'état distant observé au moment de la vérification du 2026-07-21.
- Aucune Validation d'Architecture n'est réalisée dans le présent rapport.

Ces limites n'empêchent pas de statuer sur la correction ciblée.

## K. Verdict final

# GO

- **MAJ-01 : corrigé.**
- **S1 à S5 : PASS.**
- **Nouveaux constats : aucun bloquant, majeur, mineur ou observation.**
- **Premier rapport complet absent : limite documentaire compensée par la reproduction directe du défaut et le contrôle direct de la correction ; non bloquante et sans réserve résiduelle sur le périmètre vérifié.**
- **État Git : conforme ; correction linéaire, un commit, un fichier, branche locale et distante synchronisées, `main` inchangée sur la base, aucune fusion ni publication v1.0.2.**

**Prochaine étape autorisée : Validation d'Architecture.**

Aucune nouvelle correction ni nouvelle revérification ciblée n'est requise sur la base des éléments contrôlés ici.
