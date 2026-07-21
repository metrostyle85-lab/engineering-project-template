# Validation d'Architecture — Engineering Project Template v1.0.2

## A. Identification

| Élément | Valeur |
|---|---|
| Nature | Validation d'Architecture du lot « lot-level planning fields » v1.0.2 |
| Rôle | Architecte du Template |
| Date | 2026-07-21 (Europe/Brussels) |
| Dépôt | `C:/Users/doumo/Desktop/Dev/Engineering Project Template` |
| Remote | `https://github.com/metrostyle85-lab/engineering-project-template.git` |
| Branche | `docs/template-1.0.2-lot-level-fields` |
| Base du lot | `6d3382f4b276350e9b752a215bf1b1c89e075b24` |
| Sommet initial (défaut MAJ-01) | `28159852d21d8a36bd7be6d0706017d9f8a0e880` |
| Sommet corrigé | `a31559fe1850851262d35201c1da6ff883bddb6f` |
| Commit d'archivage du rapport Codex | `7c2b70a0cf4199137a352331f18f1a0064b107cc` |
| Autorité normative référencée | Engineering Playbook, module M03 (classification) et M04 (contrat/prompt) |

Cette Validation d'Architecture ne recopie pas le verdict de la revérification Codex. Elle vérifie directement les objets Git immuables et les fichiers du lot, puis statue sur l'architecture. Elle n'est ni une fusion, ni un tag, ni une Release.

---

## B. Périmètre évalué

Périmètre couvert :

- cohérence des responsabilités documentaires du lot ;
- correction de MAJ-01 (visibilité durable des garde-fous dans `ROADMAP.md`) ;
- séparation entre planification (Roadmap) et contrat (prompt/M04) ;
- légèreté du Template et respect du Single Source of Truth ;
- compatibilité avec les quatre profils de projet ;
- adéquation de la version cible 1.0.2 à la convention réelle du dépôt ;
- qualification de la limite documentaire liée au premier rapport absent ;
- invariants du Template.

Hors périmètre :

- ré-audit exhaustif de tous les blueprints ;
- audit du contenu interne de M03/M04 (autorités externes, versionnées à part) ;
- toute opération de publication (fusion, tag, Release) ou de Documentation pré-fusion.

---

## C. Sources et preuves

Toutes les preuves ci-dessous proviennent d'une inspection directe du dépôt après `git fetch origin --prune --tags`.

### C.1 État Git et références

| Contrôle | Preuve directe | Statut |
|---|---|---|
| HEAD local = distant branche | `7c2b70a0cf4199137a352331f18f1a0064b107cc` (local et `git ls-remote origin refs/heads/…`) | PASS |
| Divergence local/distant | `0 / 0` | PASS |
| `main` local = `origin/main` = distant | `6d3382f4b276350e9b752a215bf1b1c89e075b24` | PASS |
| Working tree | propre (`git status --porcelain=v1` vide) | PASS |
| Tag `v1.0.2` | absent en local (`git tag -l` → `v1.0.0`, `v1.0.1`) et à distance (`git ls-remote --tags` vide) | PASS |
| Release `v1.0.2` | absente (`gh release list` → `v1.0.1`, `v1.0.0`) | PASS |
| Fusion dans `main` | base commune de `main` et `a31559f` = `6d3382f` ; lot non fusionné | PASS |

### C.2 Périmètre du lot et delta correctif

- Lot complet `6d3382f..a31559f` : 4 fichiers, `37 insertions(+), 1 deletion(-)`.

  | Fichier | Nature du changement |
  |---|---|
  | `CHANGELOG.md` | entrée `[1.0.2]` (+22) |
  | `README.md` | version `1.0.1` → `1.0.2` (±1) |
  | `blueprints/core/AI_CONTEXT.md` | guidage agents vers le champ Lot level (+2) |
  | `blueprints/project/ROADMAP.md` | champs de planification + note (+12) |

- Delta correctif MAJ-01 `2815985..a31559f` : un seul fichier `blueprints/project/ROADMAP.md`, `2 insertions(+), 4 deletions(-)`.

### C.3 Blobs de contrôle (au sommet corrigé `a31559f`)

| Fichier | Blob |
|---|---|
| `blueprints/project/ROADMAP.md` @ `2815985` | `66a4fb90f2554195a3e2632bfd6cfc4b2eaa093c` |
| `blueprints/project/ROADMAP.md` @ `a31559f` | `ba23fda073239e167f3415280c21ff81f3ec70b3` |
| `blueprints/core/AI_CONTEXT.md` @ `a31559f` | `6841381080554d3e2c8815d66da719f392b68e0b` |
| `README.md` @ `a31559f` | `9730e3da949967a27bebfccf1e8b4eee1b22ab4a` |
| `CHANGELOG.md` @ `a31559f` | `334ade1c53681a53762e595f994b59c8cc84c865` |
| Rapport Codex archivé (blob dans l'arbre `7c2b70a`) | `a08ec89af13baf596a655db6be97ecb9a192d131` |

Le blob du rapport Codex archivé est identique au `git hash-object` de la source Desktop (`a08ec89…`), avec SHA256 `cbc7f3f733ee5a9978e7c30d27817b5aa54c354029e843057056efce0e7bbb23` et comparaison `cmp` byte-à-byte concluante.

### C.4 Recherche de duplication normative

`git grep` sur l'ensemble du dépôt suivi (rapport Codex exclu) : les seules mentions de `M03` sont trois références en déférence, et aucune définition de niveaux, critères, effets ou règles de reclassement n'est recopiée. La seule occurrence d'un « niveau » est la valeur de planification `Lot level: Standard`. La mention `Critical` de `blueprints/project/TECH_DEBT.md` est un champ de priorité de dette technique sans lien avec la classification M03.

---

## D. Cohérence architecturale

Vérification directe de la propriété des responsabilités :

| Responsabilité | Propriétaire attendu | Constat direct | Statut |
|---|---|---|---|
| Planification de l'évolution | `blueprints/project/ROADMAP.md` | « It is a planning document. » (ligne 13) ; les champs sont qualifiés de `planning aids` | PASS |
| Référence officielle du lot (Playbook 2.3+) | Contrat / prompt (M04) | ROADMAP et AI_CONTEXT renvoient au contrat/prompt et déclarent que la Roadmap ne le remplace pas | PASS |
| Navigation documentaire | `AI_CONTEXT.md` (racine) | reste l'« Official AI entry point », sans changement | PASS |
| Statut et version | `README.md` | section `Status` : `Current Version = 1.0.2`, `Status = Stable` | PASS |
| Historique des versions | `CHANGELOG.md` | entrée `[1.0.2] - 2026-07-21` présente | PASS |
| Classification (niveaux, critères, effets, reclassement) | M03 (Playbook) | trois références déclarent M03 seule autorité et interdisent de recopier ses règles | PASS |

Aucune responsabilité n'est déplacée ni dédoublée. Le guidage ajouté dans `blueprints/core/AI_CONTEXT.md` respecte la règle « Authority » de la Documentation Grammar (« A document may complement a higher authority, but it must never redefine or contradict it. ») : il oriente vers le champ de planification tout en désignant M03 comme propriétaire.

---

## E. Séparation planification / contrat

Vérification directe de la note corrigée (ROADMAP.md, ligne 73) et du guidage (AI_CONTEXT core, ligne 50) :

- `Lot level: Standard` est présenté comme une **valeur de planification** initialisée, sous une note qui qualifie explicitement les champs de `planning aids` ;
- le niveau contractuel confirmé reste celui du contrat/prompt : « confirm the lot level in the development contract or prompt before Development starts » ;
- en cas de divergence, le contrat et le Playbook gouvernent : « This Roadmap does not replace that contract » ;
- aucune seconde norme n'est créée : la note ne définit aucun niveau, aucun critère, aucun effet, aucun mécanisme de reclassement, et défère à M03 ;
- la Roadmap n'est pas transformée en registre complet de reclassement : rien n'impose ni ne bloque un tel registre, propriété de M03 et du contrat.

La séparation planification / contrat est architecturalement nette et alignée sur la relation Template ↔ Playbook énoncée dans `philosophy.md` (« Engineering Playbook defines how projects are developed. Engineering Project Template defines how project knowledge is organized. »).

---

## F. Compatibilité

Évaluation des quatre profils :

| Profil | Comportement attendu | Constat | Statut |
|---|---|---|---|
| Projet sans Playbook | champs laissés inutilisés | note visible : « Leave them unused when the project does not adopt Engineering Playbook 2.3 or later » ; aucune adoption implicite | PASS |
| Projet Playbook 2.0–2.2 | non soumis à la classification | en-tête « Engineering Playbook 2.3+ only » ; un projet 2.2 entre dans le cas « does not adopt … 2.3 or later » | PASS |
| Projet Playbook 2.3+ | niveau lisible mais confirmé au contrat | note et guidage exigent la confirmation dans le contrat/prompt avant Développement, M03 restant l'autorité | PASS |
| Projet déjà initialisé (version antérieure) | aucune migration imposée | CHANGELOG `[1.0.2]` : « No new blueprint is added and no migration is required » ; champs additifs et optionnels | PASS |

La compatibilité avec Engineering Playbook 2.3+ est confirmée, et la compatibilité ascendante des projets existants est préservée.

---

## G. Légèreté et Single Source of Truth

| Critère de légèreté | Constat | Statut |
|---|---|---|
| Aucun nouveau blueprint | 0 fichier ajouté dans le lot | PASS |
| Aucun nouveau document universel obligatoire | aucun | PASS |
| Fichiers fonctionnels du lot | quatre uniquement (CHANGELOG, README, AI_CONTEXT core, ROADMAP) | PASS |
| Correction ciblée dans ROADMAP.md | `2 insertions(+), 4 deletions(-)` | PASS |
| Aucun scoring | absent | PASS |
| Aucune matrice | absente | PASS |
| Aucun champ concurrent (ex. `Expected validation depth`) | absent | PASS |
| Aucune duplication de M03 | trois références en déférence, aucune règle recopiée | PASS |
| Aucune migration obligatoire | confirmée par le CHANGELOG | PASS |

Le Single Source of Truth est préservé et même renforcé : la classification reste la propriété exclusive de M03, la Roadmap se limitant à une aide de planification renvoyant au contrat. Les principes `Simple by Default`, `Progressive Growth` et `Single Source of Truth` de `philosophy.md` sont respectés.

---

## H. Traitement de MAJ-01

Vérification directe du delta `28159852…` → `a31559fe…` sur `blueprints/project/ROADMAP.md` :

- le contexte essentiel n'est plus dans un commentaire HTML : le bloc `<!-- The Lot level, Level justification … -->` est **supprimé** ;
- la note visible appartient au bloc répétable : le blockquote « **Engineering Playbook 2.3+ only:** … » est inséré (ligne 73) entre `Expected outcome` et `Lot level: Standard`, à l'intérieur du bloc `## [ID] — …` copié pour chaque work package ;
- elle survit au retrait des commentaires HTML : c'est du Markdown visible, non un commentaire HTML ;
- projets sans Playbook : la note dit de laisser les champs inutilisés ;
- projets Playbook 2.0–2.2 : exclus par « 2.3+ only » ;
- projets Playbook 2.3+ : le niveau doit être confirmé dans le contrat/prompt ;
- la Roadmap ne remplace pas le contrat : « This Roadmap does not replace that contract » ;
- M03 reste la seule autorité : « M03 remains the sole authority for classification ».

Le commentaire HTML général d'organisation (« Organize work … Copy the block below … ») subsiste, mais il ne porte plus aucun garde-fou normatif. La correction restaure la visibilité durable sans créer de seconde source de vérité.

**MAJ-01 — corrigé, vérifié directement en architecture.**

---

## I. Limite documentaire liée au premier audit

Le rapport complet du premier audit indépendant n'était pas matériellement disponible.

- Il ne doit pas être recréé et ne l'a pas été : aucun rapport historique n'a été fabriqué.
- La revérification Codex archivée reproduit le défaut directement depuis le commit `28159852…` et contrôle la correction directement au commit `a31559fe…`.
- La présente Validation d'Architecture s'appuie elle aussi sur l'inspection directe des objets Git immuables, indépendante du rapport absent.

Cette limite empêche uniquement d'archiver ou de comparer le texte intégral de l'ancien rapport. Elle n'empêche ni de reproduire le défaut, ni d'identifier le delta correctif, ni d'évaluer l'architecture. **Elle reste non bloquante pour l'Architecture et sans réserve résiduelle sur le périmètre vérifié.**

---

## J. Invariants

| Invariant | Constat | Statut |
|---|---|---|
| Aucun changement de philosophie | `philosophy.md` hors du lot et inchangé ; les changements respectent tous ses principes | PASS |
| Aucune responsabilité documentaire déplacée | propriété inchangée (section D) | PASS |
| Aucune modification nécessaire de la Documentation Grammar | `docs/documentation-grammar.md` hors du lot ; la règle « Authority » couvre déjà la note | PASS |
| Aucun changement nécessaire du Document Catalog | `docs/document-catalog.md` hors du lot | PASS |
| Aucun changement nécessaire du Blueprint Guide | `docs/blueprint-guide.md` hors du lot | PASS |
| Aucune modification d'IPTVApp ou de P06 | hors dépôt ; aucun impact | PASS |
| Aucune fusion, aucun tag, aucune Release | vérifié en section C.1 | PASS |

---

## K. Décision de l'Architecte

# GO

- **État de MAJ-01 : corrigé.** Les garde-fous sont visibles, intégrés au bloc répétable, résistants au retrait des commentaires HTML, et alignés sur M03/M04 sans duplication.
- **Absence du premier rapport : acceptable.** Limite documentaire compensée par la reproduction directe du défaut et le contrôle direct de la correction sur les objets Git ; non bloquante, sans réserve résiduelle.
- **Compatibilité Playbook 2.3+ : confirmée.** Le niveau de planification est lisible et sa confirmation contractuelle avant Développement est exigée ; les profils sans Playbook et 2.0–2.2 laissent les champs inutilisés ; aucune migration n'est imposée.
- **Seconde source de vérité : absente.** La classification demeure la propriété exclusive de M03 ; la Roadmap se limite à une aide de planification déférant au contrat.
- **État Git : conforme.** Correction linéaire (un commit, un fichier pour MAJ-01), branche locale et distante synchronisées (`7c2b70a`, 0/0), `main` inchangée sur `6d3382f`, aucun tag ni Release `v1.0.2`, aucune fusion, aucun force-push.

Observations non bloquantes :

- la version `1.0.2` est conforme à la convention réelle du dépôt, qui traite les alignements documentaires comme des correctifs (le `1.0.1` était un « Documentation alignment ») ; sous une lecture SemVer stricte, l'ajout de champs optionnels pourrait être un incrément mineur, mais le changement est additif, optionnel et sans rupture, donc `1.0.2` reste adapté ;
- le rapport Codex archivé conserve, comme prévu, sa propre déclaration relative au premier rapport absent.

---

## L. Prochaine étape autorisée

**Documentation pré-fusion.**

Ne sont pas autorisées à ce stade et ne doivent pas être exécutées : la fusion, le tag `v1.0.2`, la Release `v1.0.2`, le nettoyage de branche. L'exécution s'arrête après le commit et le push de la présente Validation d'Architecture.
