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

**Problème 1 — Proxy bias**
**Détection à mener**
Le préfixe de code postal et/ou le temps de trajet pourraient être des proxys du statut socio-éco ou grp.
Indices à regarder : forte mutual information/corrélation entre (zip/temps) et grp; écarts de TPR/FPR par grp quand ces features sont présentes; adversaire qui prédit grp à partir des features.

**Scénario**

Le modèle apprend qu’habiter loin d’une agence (ou dans des préfixes de code postal “X9”) est associé à plus de non-remboursements… mais ces variables capturent en fait des différences structurelles d’accès au système bancaire liées au groupe grp. Résultat : les candidats de grp=1 sont systématiquement sous-notés, même à revenu égal.

(...)
