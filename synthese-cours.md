# Synthèse — Stratégie des Systèmes d'Information
> Formateur : Bruno PIANGERELLI — Architecte des Systèmes d'Information

---

## 1. Le Système d'Information (SI)

### Définition
Ensemble organisé de ressources permettant de **collecter, stocker, traiter et distribuer** de l'information.  
Composé de deux sous-systèmes :
- **Social** : structure organisationnelle et personnes
- **Technique** : technologies (hardware, software, télécoms) et processus métiers

### Bref historique
| Période | Contexte |
|---------|----------|
| Années 60–70 | Entreprises monolithiques, pas de SI structuré |
| Années 80 | Démocratisation de l'ordinateur, Internet → naissance de l'architecture SI |
| Aujourd'hui | Organisations en réseau, flux temps réel |
| Demain | Mobilité, agilité, IA pour orchestrer l'information |

### Les 4 fonctions du SI
1. **Collecte** — saisie d'informations internes (comptabilité, RH…) et externes (clients, fournisseurs…)
2. **Stockage** — fichiers, BDD, NAS, cloud ; organisation, archivage, protection
3. **Traitement** — nettoyage, structuration, mise à jour, production de nouvelles informations
4. **Diffusion** — postes de travail, réseau, email, papier, vocal…

### Des fonctions aux services
Un **service SI** répond à un besoin métier spécifique (ex. : la paye, la gestion des commandes).  
→ On parle de **SIRH** (Ressources Humaines), **SIC** (Comptable/Commercial), etc.  
⚠️ Le découpage par services ne doit pas nuire à la cohérence globale du système.

---

## 2. La Direction du Système d'Information (DSI)

Rôle **plus large** que le simple service informatique :

| Rôle opérationnel | Rôle stratégique |
|---|---|
| Continuité du service technique | Veille technologique et métier |
| Amélioration des performances | Anticipation du changement |
| Réduction des coûts d'exploitation | Alignement SI / stratégie d'entreprise |

La DSI s'appuie sur un **Comité de Pilotage (COPIL)** regroupant les décideurs des différentes BUs → notion de **gouvernance du SI**.

---

## 3. Gouvernance du SI

### Définition
Système d'entités décisionnelles qui dirige et contrôle le SI en s'appuyant sur une **approche systémique**.

### Enjeux clés
- Création de valeur ajoutée
- Gestion des risques
- Alignement stratégique SI ↔ entreprise
- Mesure des performances
- Gestion des ressources

### Architecture d'Entreprise (EA)
> Démarche visant à aligner la stratégie d'entreprise avec toutes les couches (Métier, Fonctionnelle, Applicative, Technique).

Référentiel de référence : **COBIT V5** (normes ISO 20xx, ITIL…)

---

## 4. Définir une stratégie du SI

### Alignement bidirectionnel
- Le SI doit être **au service des métiers** → il s'adapte à l'organisation
- **L'évolution technologique** influe en retour sur la stratégie de l'organisation

### Thématiques à couvrir
Marketing, finances, relations externes, RH, veille technologique, gestion des risques, gestion des référentiels…

### Nouveaux enjeux transversaux
- **Cloud & micro-services** pour la flexibilité
- **IA & data** pour l'automatisation et l'analyse
- **Cybersécurité** intégrée dès la conception
- **Sobriété numérique** : code optimisé, data centers verts, open source, indicateurs RSE

### Outil d'analyse : le modèle SWOT
Analyse des **Forces / Faiblesses / Opportunités / Menaces** appliquée au projet SI pour cadrer la stratégie avant de lancer un SDSI.

**Structure de la matrice :**

|  | Positif | Négatif |
|---|---|---|
| **Interne** (ce que l'organisation maîtrise) | **Forces** (Strengths) | **Faiblesses** (Weaknesses) |
| **Externe** (ce que l'organisation ne maîtrise pas) | **Opportunités** (Opportunities) | **Menaces** (Threats) |

**Exemples appliqués à un projet SI :**

| Quadrant | Exemples concrets |
|---|---|
| **Forces** | SI existant solide, équipes DSI compétentes, budget dédié, bonne couverture fonctionnelle |
| **Faiblesses** | Systèmes legacy obsolètes, dette technique, silos entre services, documentation insuffisante, manque de compétences |
| **Opportunités** | Nouvelles technologies (Cloud, IA, microservices), nouveaux marchés, évolutions réglementaires favorables, partenariats |
| **Menaces** | Cyber-attaques, concurrence technologique accrue, contraintes réglementaires (RGPD), obsolescence rapide, réductions budgétaires |

**Comment exploiter les résultats ?**

- **Forces × Opportunités (SO)** → Stratégie offensive : capitaliser sur les atouts pour saisir les opportunités
- **Forces × Menaces (ST)** → Stratégie défensive : utiliser les forces pour contrer les menaces
- **Faiblesses × Opportunités (WO)** → Stratégie de rattrapage : corriger les faiblesses pour profiter des opportunités
- **Faiblesses × Menaces (WT)** → Stratégie de survie : réduire l'exposition en éliminant les faiblesses critiques

> ⚠️ Le SWOT n'est pas une fin en soi : il doit déboucher sur des **actions concrètes** intégrées au SDSI.

---

## 5. Le Schéma Directeur du Système d'Information (SDSI)

### Définition
Document de référence (« feuille de route ») décrivant comment la stratégie s'applique au SI, **à horizon 3–5 ans**.

### Objectifs
- Planifier les projets et investissements structurants
- Distinguer projets cruciaux et projets périphériques
- Équilibrer **moyens** (humains + financiers) et **objectifs**

### Structure type
1. Contexte et état des lieux (as is)
2. Vision cible (to be)
3. Analyse des écarts
4. Plan de migration (Gantt)
5. Budget et ressources

### Règles de réussite
- Guidé par les enjeux **stratégiques** de l'entreprise
- Proposer des **scénarios alternatifs** (might be)
- Collaborer avec toutes les parties prenantes
- Document **vivant, itératif** (jamais figé)
- Communication permanente pour assurer l'adhésion

---

## 6. La Transformation du SI : as is → to be

```
AS IS  →  (analyse)  →  AS WISHED (idéal, souvent irréaliste)
                              ↓
                         MIGHT BE (intermédiaire réaliste)
                              ↓
                          TO BE  (nouveau as is)
```

La transformation procède par **priorisation et hiérarchisation** des étapes, en validant à chaque stade que les fonctionnalités et les coûts sont raisonnables.

---

## 7. Les Types d'Architecture

| Architecture | Caractéristiques | Avantages | Inconvénients | Cas d'usage |
|---|---|---|---|---|
| **Monolithique** | Un seul bloc applicatif | Simplicité, rapidité de dev | Faible scalabilité, maintenance lourde | Prototypes, petites applis |
| **N-tiers** | Présentation / logique métier / données | Maintenabilité, modularité | Rigidité, dépendances | ERP, CRM, SI classiques |
| **SOA** | Services indépendants via ESB | Interopérabilité, réutilisation | Complexité, lourdeur de l'ESB | Grands systèmes hétérogènes |
| **Micro-services** | Services indépendants + API Gateway | Scalabilité fine, agilité | Supervision et déploiement complexes | E-commerce, SaaS |
| **Événementielle** | Échanges asynchrones via bus d'événements | Découplage, temps réel | Gestion complexe des événements | IoT, streaming, big data |
| **Serverless (FaaS)** | Exécution à la demande | Pas d'infra à gérer, coût à l'usage | Dépendance fournisseur, cold start | API légères, batches ponctuels |

> **Pas d'architecture idéale** : le choix dépend du contexte (simplicité, scalabilité, coûts, pérennité).

---

## 8. L'Urbanisation du SI

Inspirée de la métaphore de la **cité** (C. Longépé, 2001) : le SI est découpé en zones et quartiers soumis à des règles d'urbanisme.

**4 couches de l'urbanisation :**
1. Couche **Métier** (processus business)
2. Couche **Fonctionnelle** (services SI)
3. Couche **Applicative** (logiciels)
4. Couche **Technique** (infrastructure)

---

## 9. Conduire un Projet SI

### Exigences
- Définir les **besoins métiers** (business requirements)
- Définir les **aspects fonctionnels** (fonctionnalités attendues)
- Définir les **besoins applicatifs** (outils informatiques)
- Mettre en œuvre les **moyens techniques**

### Gouvernance du projet
- **COPIL** composé des représentants de toutes les entités (niveau N-2/N-3 minimum)
- Matrice **RACI** pour définir rôles et responsabilités (Responsible / Accountable / Consulted / Informed)

### Rôle de l'Architecte SI
Chef d'orchestre transverse :
- Architecte technique **et** applicatif
- **Médiateur** entre MOA et MOE (AMOA / Business Analyst)
- Garant de la stratégie, des engagements économiques et de la cohérence globale

### Étapes clés d'un projet
1. Préparation (sur la base du SDSI)
2. Définition et modélisation
3. Plan d'exécution
4. Exécution et pilotage
5. Mise en exploitation / déploiement
6. Clôture et bilan

### Indicateurs de suivi
Principal indicateur : la **synergie** entre parties prenantes.  
⚠️ Risque d'euphorie collective → dérive vers des objectifs irréalistes → recadrage régulier indispensable.

---

## 10. Démarches et Méthodes

### TOGAF (The Open Group Architecture Framework)
Le référentiel le plus complet et le plus utilisé dans les grandes organisations (depuis 1995).

**3 concepts de base :**
- **Cycle ADM** (Architecture Development Method) — roue itérative en 8 phases (A→H) :
  - A : Vision de l'architecture
  - B : Architecture business
  - C : Architecture des SI
  - D : Architecture technologique
  - E : Opportunités et solutions
  - F : Planning de migration
  - G : Gestion de l'implémentation
  - H : Gestion du changement d'architecture
- **Architecture Content Framework** (métamodèle des livrables)
- **Cadre de capacité** (organisation de l'architecture d'entreprise)

### Cycle en V
Méthode traditionnelle : descente (spécifications → réalisation) + remontée (tests → validation).

### Démarche Agile
- Équipes **pluridisciplinaires** (MOA + MOE) qui interagissent régulièrement
- Objectif : détecter les dérives **au plus tôt**, itérations courtes
- Principalement orientée **développements informatiques**

---

## 11. Modélisation du SI

### Pourquoi modéliser ?
Identifier toutes les dépendances inter-entités, anticiper les impacts, réduire les risques de mauvais choix → **cartographie / diagramme de contexte**.

### Langages de modélisation

| Langage | Usage |
|---|---|
| **Archimate** (TOGAF) | Modélisation globale de l'EA (métier, application, technologie, stratégie) |
| **BPMN** | Processus métiers et techniques, enchaînements, déclenchements |
| **UML** | Use Cases, séquences, classes, activités, états, composants… |

### Outils recommandés
- **draw.io** (app.diagrams.net) — gratuit, en ligne
- **Visual Paradigm** — complet
- **Modelio** / **Archi** — UML, BPMN, TOGAF/Archimate
- **GenMyModel** — cloud, français, Archimate inclus

---

## 12. Gestion des Risques

### Nature des risques
Humaine, technique, juridique, budgétaire, temporelle, intrinsèque au projet.

### Processus (continu tout au long du projet)
1. Planifier la gestion des risques
2. **Qualifier et évaluer** les risques
3. **Quantifier** (donner un poids, une priorité)
4. **Surveiller** (désigner des responsables)
5. **Analyser** régulièrement

> ⚠️ Distinguer **risque** (anticipé) et **problème** (constaté).

**Outil** : tableau de suivi (Excel ou autre) avec colonnes : description, probabilité, impact, priorité, responsable, statut.

---

## 13. Conduite du Changement

### Objectif principal
**Adhésion** des parties prenantes : collaborateurs, clients, fournisseurs, prestataires.

### Clés de réussite
- Communication, support, conseils, implication (facteurs humains avant tout)
- Fixer des **objectifs clairs** et mettre en avant les résultats attendus
- **Plan de communication** (interne et externe)
- **Plan de formation**

### Le projet latéral
Assurer la **coordination et la synchronisation** des acteurs, gérer les conflits, maintenir la cohésion → dimension presque « psychologique ».

---

## 14. Informatique Décisionnelle (Business Intelligence)

Adressée aux **décideurs** (dirigeants, marketing, DRH, comptabilité…) :
- Présentation de données **agrégées et structurées** sous forme de rapports
- Statistiques **prévisionnelles** basées sur des données historiques internes
- Métiers associés : **Data Engineer, Data Analyst, Data Scientist**

---

## 15. Intégration des SI — ERP / PGI

**PGI (Progiciel de Gestion Intégré)** = ensemble logiciel intégrant tout ou partie des SI d'une organisation (ex. : SAP).

| | |
|---|---|
| ✅ Avantages | Intégration et partage des données, moins de développements spécifiques |
| ❌ Inconvénients | Coût élevé, ressources spécialisées nécessaires pour le paramétrage |

---

## 16. Infogérance

Externalisation des SI vers des prestataires (tout ou partie), matérialisée par un **contrat de service**.

| ✅ Avantages | ❌ Inconvénients |
|---|---|
| Coûts mutualisés et mieux maîtrisés | Perte de maîtrise du SI |
| Concentration sur le cœur de métier | Risque de dépendance (réversibilité coûteuse) |
| Flexibilité et réactivité accrues | Risques de sécurité (hébergement mutualisé) |
| | Risques liés à la propriété des logiciels |

> Le **Cloud** s'apparente en grande partie à de l'infogérance.

---

## 17. Performance et Coûts du SI

### Indicateurs de performance
- **Temps de réponse**
- **Disponibilité** (ressources suffisantes, 7j/7 24h/24)
- **Bande passante** et capacité de stockage
- **Scalabilité** (coût et rapidité de mise à l'échelle)

### Structure des coûts
| Catégorie | Exemples |
|---|---|
| Coûts évidents | Matériel, licences |
| Coûts moins visibles | Maintenance, électricité, ressources humaines |
| Coûts cachés | Pannes, sécurité, évolutions, coûts humains sous-jacents |

**Calcul du ratio** : coûts SI / charges salariales (rapporté au nombre de collaborateurs).

### ROI (Return On Investment)
$$ROI = \frac{\text{Gain} - \text{Coût d'investissement}}{\text{Coût d'investissement}}$$

*Exemple : investissement 100 000 € → retour 150 000 € → ROI = 50 %*

### Critères non financiers
Performance, qualité perçue, risque maîtrisé, sécurité de l'information (référentiels ITIL / COBIT V5).

---

## 18. Sécurité du SI

### Les 4 critères fondamentaux
| Critère | Description |
|---|---|
| **Confidentialité** | Information accessible aux seuls destinataires désignés |
| **Intégrité** | Données modifiables uniquement par des personnes/traitements autorisés |
| **Traçabilité** | Historique des modifications, connexions et consultations |
| **Disponibilité** | Information accessible au moment voulu, dans le respect de la confidentialité |

### Actifs à protéger
Supports de stockage, canaux de communication, moyens informatiques/humains, environnement physique (locaux, sites de backup).

### Principales menaces
Cyber-attaques, dégradations volontaires, catastrophes naturelles, grèves, pannes d'infrastructure.

### Politique de sécurité
- **Évaluer et budgéter** le risque sécurité comme un projet à part entière
- **Sensibiliser** l'ensemble des collaborateurs
- Mettre en place des **cellules de prévention et de surveillance**

---

## 19. Audit du SI

### Objectifs
- Évaluer l'efficacité et la performance du SI par rapport à la stratégie
- Évaluer les risques et la sécurité
- Formuler des **recommandations d'amélioration**
- Assurer la **conformité** (RGPD, normes, évolutions technologiques)

### Outils et référentiels
- Cartographie du SI, cahier des charges
- **COBIT V5**, **ITIL**
- **ISO 27000** (sécurité de l'information)
- Audit interne en préalable, puis externe (organisme indépendant) recommandé

### Le rapport d'audit
Document **clair et didactique** (non technique) comprenant :
- Contexte et attentes de départ
- Limites de l'audit
- Faiblesses constatées et leur importance relative
- Solutions et recommandations

---

## Récapitulatif visuel

```
Stratégie d'entreprise
        │
        ▼
   Gouvernance SI (COPIL, COBIT)
        │
        ▼
   SDSI — Schéma Directeur (3–5 ans)
        │
        ▼
   Transformation : AS IS → MIGHT BE → TO BE
        │
   ┌────┴────────────────────────┐
   ▼                             ▼
Architecture du SI          Conduite de projet
(Monolithique / N-tiers /   (MOA / MOE / RACI /
 SOA / Micro-services /      TOGAF / Agile)
 Event / Serverless)
        │
   ┌────┴──────────────────────────────┐
   ▼             ▼                     ▼
Modélisation  Gestion des risques  Conduite du changement
(UML/BPMN/   (anticiper, prioriser,  (communication,
 Archimate)   surveiller)             formation, adhésion)
        │
   ┌────┴──────────────────────────────┐
   ▼             ▼                     ▼
Sécurité SI   Performance & Coûts   Audit SI
(CIDT)        (ROI, KPI, ITIL)      (COBIT, ISO 27k)
```

---

*Synthèse réalisée à partir du cours "Stratégie des Systèmes d'Information" — Bruno PIANGERELLI*
