# Projet : IA éthique — cas pratiques sans réponses (pipeline ML & LLM)

## Objectif

Fournir des **contextes réalistes** et détaillés de déploiement d’IA. **Ne donnez pas les réponses** : pour chaque cas, vous devez (1) **identifier les problèmes éthiques potentiels** (il peut y en avoir plusieurs), (2) **les illustrer** avec un mini‑scénario ou des chiffres synthétiques, (3) **proposer une stratégie de mitigation**. À la fin, **rédigez une Charte d’éthique IA** adaptée au projet.

## Livrables 

* **Dossier d’analyse** — un sous‑chapitre par cas : problèmes • illustration • mitigation.
* **Charte d’éthique IA** — livrable séparé.

## Grille d’évaluation (20 pts)

* Pertinence de l’identification des problèmes (7 pts)
* Qualité & réalisme des illustrations (5 pts)
* Pertinence et faisabilité des mitigations (6 pts)
* Cohérence et applicabilité de la Charte (2 pts)

---

# Partie A — Cas par étape du pipeline ML (contexte enrichi)

> Pour chaque cas A1–A10 : **n’expliquez pas**, **analysez**. Tâches :
>
> 1. Identifier **tous** les problèmes éthiques/biais potentiels.
> 2. Illustrer chaque problème (scénario, exemple avec des données, etc.).
> 3. Proposer une stratégie de mitigation pour chaque problème.

## A1) Cadrage du problème & finalité — **NovaHire (RH)**

**Contexte** — NovaHire, cabinet de recrutement européen (5 pays), veut prédire le **« potentiel de performance à 12 mois »** pour des postes de support client. Sources envisagées : CV, tests de personnalité, transcription d’entretiens vidéo, données LinkedIn publiques. Les clients exigent des **listes courtes livrées en 24h** et un score de 0–100. KPI internes : taux de placement, satisfaction client, temps moyen de sourcing. Les pays appliquent des règles différentes (RGPD/obligations locales).

## A2) Collecte & échantillonnage — **EuroSure (Assurance)**

**Contexte** — EuroSure construit un modèle **anti‑fraude** auto pour l’UE. Données disponibles surtout **France & Benelux** via canal web ; les sinistres papier/centres d’appels d’Europe de l’Est sont peu numérisés. Les sinistres de petits montants (<500€) sont parfois exclus. Pression pour réduire le coût de fraude de **15%** en 6 mois.

## A3) Annotation & vérité terrain — **Chatterly (Réseau social)**

**Contexte** — Chatterly modère des contenus en **12 langues**. L’annotation est sous‑traitée à plusieurs prestataires avec **turnover élevé**. Le guide d’annotation fait 3 pages, les exemples limites sont rares, et les annotateurs disposent de **90 secondes** par item.

## A4) Prétraitement & features — **CrediNow (Fintech)**

**Contexte** — CrediNow développe un **score de crédit** pour micro‑prêts (300–3 000€). Variables candidates : historique de paiement, secteur d’activité, **code postal**, stabilité de logement, durée d’abonnement télécom, historique e‑commerce. Taux de **valeurs manquantes** élevé sur la stabilité de logement pour les jeunes.

## A5) Partitionnement & validation — **ShopBridge (Retail)**

**Contexte** — ShopBridge anticipe la **demande hebdomadaire** par magasin pour optimiser les stocks. Les data scientists utilisent un **split aléatoire** et des features contenant des **agrégations glissantes**. L’équipe ops a besoin d’un modèle robuste aux **pics saisonniers** (Noël, soldes).

## A6) Entraînement & tuning — **CVMatch (ATS)**

**Contexte** — CVMatch classe des candidatures pour des postes tech. Optimisation **quasi exclusive** de l’AUC. Classes très **déséquilibrées** (3% embauches). Les clients souhaitent un **tri automatique** top‑50 sans revue humaine initiale.

## A7) Évaluation & métriques — **MediSight (Santé)**

**Contexte** — MediSight assiste au **diagnostic d’imagerie** (radiologie thoracique). L’évaluation interne rapporte 90% d’exactitude **globale** sur un jeu multi‑hôpitaux, mais la distribution par **âge/sexes/comorbidités** n’a pas été étudiée. Les radiologues juniors s’appuient fortement sur l’outil.

## A8) Déploiement & UX — **JobNest (Place de marché d’emplois)**

**Contexte** — JobNest présente par défaut un **tri par “pertinence”** calculé par un modèle d’apprentissage par le **clic**. 70% des clics se concentrent sur les **3 premiers résultats**. Un badge “match fort” s’affiche en vert.

## A9) Monitoring & dérive — **OptiVision (Manufacturing)**

**Contexte** — OptiVision détecte des **défauts** sur une ligne de production. Changement récent de **caméra** et d’**éclairage** pour des raisons de maintenance. Il n’existe pas de **seuils d’alerte** ni de protocole de re‑validation avant mise en prod.

## A10) Gouvernance & documentation — **DataForge (Plateforme ML interne)**

**Contexte** — DataForge héberge **40 modèles** utilisés par plusieurs BU. Pas de **Data Cards/Model Cards** standardisées ; retraits de variables sensibles non **tracés** ; pas de **comité** de revue éthique. Délais time‑to‑market privilégiés sur la conformité.

---

# Partie B — Cas IA générative / LLM (contexte enrichi)

> Pour chaque cas G1–G7 : identifiez tous les problèmes, illustrez‑les, puis proposez une mitigation. **Pas de réponses toutes faites dans ce document.**

## G1) Hallucinations factuelles — **LexiAssist (Juridique)**

**Contexte** — LexiAssist génère des **mémos** et suggère des **références** (arrêts, doctrine). Des collaborateurs juniors copient‑collent les résultats dans des dossiers. Les clients exigent des délais **très courts**.

## G2) Biais stéréotypés & toxicité — **TalentGen (RH)**

**Contexte** — TalentGen rédige des **annonces d’emploi** multilingues et des messages de sourcing. L’outil est **fine‑tuné** sur l’historique des textes internes.

## G3) Prompt injection & données sensibles — **HelpDeskGPT (IT interne)**

**Contexte** — Le chatbot HelpDeskGPT peut **lire des pages intranet** et exécuter des **outils** (tickets, logs). Des pages contiennent des **instructions cachées**.

## G4) Propriété intellectuelle & training data — **Artify (Génération d’images)**

**Contexte** — Artify permet des rendus proches de **styles d’artistes vivants**. Les marketeurs créent des visuels “inspirés de…”.

## G5) Confidentialité & fuite de données — **CodePilot (Assist Dev)**

**Contexte** — CodePilot aide au **debug** et à la **revue**. Les développeurs collent des extraits **propriétaires** ; les journaux sont utilisés pour **améliorer** le modèle.

# Partie C — Charte d’éthique IA (à réaliser **après** les cas)

Rédigez une **Charte d’éthique IA** (2–3 pages) s’appliquant aux cas étudiés. Elle doit préciser :

1. **Principes** (finalité, équité, explicabilité, sécurité, confidentialité, durabilité, gouvernance/responsabilité).
2. **Engagements** (ce que vous ferez systématiquement ; pratiques interdites ; seuils d’acceptation).
3. **Rôles & processus** (revues, audits, gestion d’incidents, décision/arrêt, fréquence).
4. **Documentation** (Data Cards, Model Cards, registres, journal des décisions).
5. **Monitoring & amélioration continue** (indicateurs, seuils, boucle utilisateur, re‑entrainement).
6. **Mécanisme de recours** (canaux, délais, arbitrage humain).

> Livrer la charte en document séparé et référencer explicitement A1–A10 et G1–G5.

[Exemple Chart Ethique IA](https://www.capgemini.com/wp-content/uploads/2021/06/Capgemini_Code_of_Ethics_for_AI_2021_EN.pdf)

*Consigne finale : n’apportez **aucune réponse** dans ce document — produisez vos analyses, illustrations et mitigations. La Charte d’éthique IA est **obligatoire**.*

# Exemple 

**Cas d’étude : Micro-crédit « QuickLoan »**
**Contexte général**
QuickLoan propose des micro-prêts (300–2 000 €). Un modèle ML prédit la probabilité de remboursement à 12 mois pour pré-filtrer les demandes.
Variables candidates : revenus, âge, code postal (préfixe), temps de trajet domicile-agence, historique e-commerce, stabilité d’emploi.
Attribut sensible (audit-only) : grp (0/1), collecté avec base légale pour audit d’équité (pas utilisé en production).
Labels historiques : approuve (décision humaine passée) et rembourse (observé seulement si approuvé ⇒ « selective labels »).


## 2) Problème A — **Proxy bias**

### Détection (à mener)
- `zip_pref` et `trajet_min` peuvent servir de **proxys** de `grp` (statut socio-éco/zone).  
- Indices :  
  - forte corrélation / MI entre (`zip_pref`, `trajet_min`) et `grp`;  
  - **écarts TPR/FPR** par `grp` quand ces features sont incluses ;  
  - **classifieur adversarial** prédisant `grp` à partir des features.

### Scénario
À revenu et score historique comparables, les dossiers venant des **préfixes X9** (zones éloignées, bancarisées différemment) sont **sous-notés**. Le modèle a appris le **proxy** (X9 / trajet long) plutôt que le vrai signal de risque → **sous-approbation systématique** de `grp=1`.

### Mini-jeu de données (10 lignes) — *détection proxy*

| id | grp (audit) | revenu_k€ | age | zip_pref | trajet_min | score_hist | approuve | rembourse_obs |
|---:|:-----------:|----------:|----:|:--------:|-----------:|-----------:|:--------:|:-------------:|
|  1 |      0      |    24     | 28  |   X1     |     15     |    0.6     |    1     |       1       |
|  2 |      1      |    24     | 29  |   X9     |     55     |    0.6     |    0     |      NA       |
|  3 |      0      |    19     | 22  |   X1     |     20     |    0.4     |    1     |       1       |
|  4 |      1      |    26     | 31  |   X9     |     60     |    0.7     |    0     |      NA       |
|  5 |      1      |    22     | 27  |   X9     |     50     |    0.5     |    0     |      NA       |
|  6 |      0      |    21     | 24  |   X1     |     18     |    0.5     |    1     |       0       |
|  7 |      1      |    24     | 26  |   X9     |     58     |    0.6     |    0     |      NA       |
|  8 |      0      |    25     | 30  |   X1     |     12     |    0.7     |    1     |       1       |
|  9 |      1      |    25     | 30  |   X9     |     57     |    0.7     |    0     |      NA       |
| 10 |      0      |    23     | 25  |   X1     |     16     |    0.5     |    1     |       1       |

> **Lecture** : les observations X9/trajet long (souvent `grp=1`) sont refusées malgré des profils comparables → suspicion de **proxy**.

## 3) Problème B — **Biais de labels** (sélectivité + sévérité inégale)

### Deux sources
1) **Sélectivité des labels** : `rembourse_obs` n’existe **que** pour `approuve=1` → on n’observe jamais l’issue pour les refusés (biais d’échantillonnage de label).  
2) **Biais de décision historique** : pour des X proches, `grp=1` a **moins d’approbations** (label `approuve` **biaisé**).

### Scénario
Les décideurs passés, plus stricts pour `grp=1` et X9, ont rarement approuvé ces dossiers. Le modèle ne voit donc **aucun remboursement** chez eux (car jamais exposés au prêt), et « apprend » à continuer de les refuser.

### Mini-jeu de données (10 lignes) — *sélectivité/annotation*
| id | grp (audit) | revenu_k€ | age | zip_pref | score_hist | approuve (label hist.) | rembourse_obs |
|---:|:-----------:|----------:|----:|:--------:|-----------:|:----------------------:|:-------------:|
|  1 |      0      |    22     | 27  |   X1     |    0.5     |           1            |       1       |
|  2 |      1      |    22     | 27  |   X9     |    0.5     |           0            |      NA       |
|  3 |      0      |    24     | 29  |   X1     |    0.6     |           1            |       1       |
|  4 |      1      |    24     | 29  |   X9     |    0.6     |           0            |      NA       |
|  5 |      0      |    23     | 26  |   X1     |    0.5     |           1            |       0       |
|  6 |      1      |    23     | 26  |   X9     |    0.5     |           0            |      NA       |
|  7 |      0      |    25     | 31  |   X1     |    0.7     |           1            |       1       |
|  8 |      1      |    25     | 31  |   X9     |    0.7     |           0            |      NA       |
|  9 |      0      |    21     | 24  |   X1     |    0.4     |           1            |       1       |
| 10 |      1      |    21     | 24  |   X9     |    0.4     |           0            |      NA       |

> **Lecture** : paires presque identiques {1–2, 3–4, …} mais **approbation refusée** pour `grp=1` → **biais de label** + **labels manquants non aléatoires**.

## 4) Stratégies ML & process

### A) Atténuer le **proxy bias**
- **Audit de proxys**  
  - Mesurer corrélation/MI entre (`zip_pref`, `trajet_min`) et `grp`.  
  - **Classifieur adversarial** prédisant `grp` à partir de X → viser **AUC≈0,5** après mitigation.
- **Pré-traitement**  
  - Retrait/agrégation prudente des variables spatiales (binning, distances généralisées).  
  - **Reweighing** (Kamiran–Calders) pour équilibrer la distribution conditionnelle par `grp`.  
  - **Disparate Impact Remover** / normalisation par groupe (si juridiquement admis).
- **Validation**  
  - Rapporter **TPR/FPR/PPV/Calibration** par `grp` et par **sous-groupes intersectionnels**.  
  - **Tests contre-factuels** (X1↔X9, même X autrement).

### B) Corriger le **biais de labels** (sélectivité + annotation)
- **Sélectivité (labels manquants pour refusés)**  
  - **Inverse Propensity Scoring (IPS)** avec modèle `P(approuve|X)`.  
  - **PU Learning** (Positive-Unlabeled) pour apprendre `rembourse` quand seuls les approuvés sont labellisés.  
  - **Reject Inference** (EM, parcelling, fuzzy augmentation) pour estimer l’issue latente des refusés.  
  - **Expérimentation contrôlée** : approuver aléatoirement une petite fraction borderline (cadre éthique & légal) pour **révéler** l’issue réelle.
- **Biais d’annotation/décision**  
  - **Relabellisation** aveugle d’un échantillon, appariement X proche X1/X9.  
  - **Loss robustes au bruit** (Generalized Cross-Entropy, Co-teaching, Bootstrap).  
  - **Calibration** par groupe + contrôle de **disparate mistreatment**.
- **Gouvernance & documentation**  
  - Interdire l’usage direct d’attributs sensibles (sauf **audit**).  
  - **Data Card / Model Card** avec métriques d’équité et limites d’usage.  
  - **Canaux de recours** utilisateur, **monitoring** continu (TPR/FPR/PPV/Calib, drift).

