---
name: architecte-si-traiteur
description: >
  Skill à activer pour tout travail d'architecture SI sur l'étude de cas M. Traiteur
  (réseau de franchise de traiteur). Déclenche ce skill dès qu'une demande porte sur :
  cartographie SI, analyse SWOT, schéma directeur (SDSI), processus métier, choix
  d'architecture applicative ou technique, analyse de risques, cahier des charges SI,
  ou tout livrable de transformation du SI dans ce contexte. Ce skill encode les
  conventions de modélisation, les données de référence du cas, et les bonnes pratiques
  issues du cours « Stratégie des Systèmes d'Information ».
---

# Skill : Architecte SI — Étude de cas M. Traiteur

## Données de référence du cas (à ne jamais réinventer)

| Donnée | Valeur |
|---|---|
| Franchisés actifs | 25 (+ 3 magasins propres hors franchise) |
| Employés total | 230 |
| CA siège | 1 M€/an |
| CA franchisé estimé (après 2 ans) | 600 K€ HT/an |
| Objectif CA (5 ans) | Doubler |
| Droit d'entrée franchise | 35 000 € HT |
| Frais de gestion actuels | 3 000 € HT/mois (fixes) |
| Frais de gestion cibles (nouveaux contrats) | 8% du CA annuel |
| Coût ERP infogéré actuel | 16 000 € HT/an (10 postes) |
| Coût logistique « Je livre » | 150 000 €/an |
| Coût site web + app | 1 500 €/an |
| Coût caisse par franchisé | 5 000 €/an (matériel inclus) |
| Carte : nombre de plats | ~30 plats en rotation |
| Ventes déjeuner | ~10% du CA franchisé |
| Commande minimum pour livraison | 10 personnes, weekend uniquement |
| Horaires 75% des franchisés | 13h–21h |
| Délai commande click & collect | 3h minimum (hors vitrine) |
| Contrat franchise | 8 ans |
| Surface locale minimum | 60–100 m² |
| Équipe minimum par franchisé | 7 personnes (5 préparateurs + 2 vendeurs) |

---

## Acteurs du SI (au sens UML)

- **Client final** : passe commande (téléphone, web, app), retire ou se fait livrer
- **Franchisé** : consulte commandes, gère stock local, encaisse, remonte données
- **Siège M. Traiteur** : pilote RH, compta, marketing, achats, supply chain, formation
- **Acheteurs (x2)** : sourcing producteurs locaux, commandes groupées, suivi livraisons
- **Commercial (x1)** : relation franchisés, recrutement nouveaux franchisés
- **M. Traiteur fils** : direction stratégique, relais tech et commercial
- **« Je livre »** : prestataire logistique supply chain (local uniquement aujourd'hui)
- **Centrale d'achats « Je livre »** : agrégation des commandes fournisseurs
- **Banque partenaire** : TPE imposé, gestion flux interbancaires

---

## Cartographie SI actuel (as is) — couches d'urbanisation

### Couche Métier (processus)
- Prise de commande client (tel / web / app)
- Préparation des plats en franchisé
- Encaissement (caisse → TPE)
- Gestion des commandes d'approvisionnement (franchisé → acheteurs → Je livre)
- Livraison produits frais (2×/semaine)
- Gestion RH centralisée (paye, recrutement)
- Comptabilité centralisée
- Marketing & veille qualité
- Formation franchisés

### Couche Fonctionnelle (services SI)
- Prise de commande en ligne (site web + app mutualisés)
- Gestion de caisse (système unifié par franchisé)
- ERP central : RH, compta, marketing
- Remontée des encaissements (fin de journée → ERP)
- Application franchisé (consultation commandes)
- Pas de BI / reporting en temps réel
- Pas de livraison à domicile < 10 personnes
- Pas de click & collect structuré

### Couche Applicative (logiciels)
| Application | Rôle | Statut |
|---|---|---|
| ERP infogéré (éditeur stagnant) | RH, compta, marketing | À remplacer |
| Système de caisse unifié | Encaissement + remontée données | Maintenu |
| Site web + app mobile | Commandes clients | Maintenu |
| App franchisé | Consultation commandes | Maintenu |
| TPE bancaire | Paiement | Maintenu (banque imposée) |

### Couche Technique (infrastructure)
- ERP : hébergement infogéré externe (SaaS / hébergé chez l'éditeur)
- Site web / app : hébergement mutualisé externe
- Caisses : équipements locaux chez chaque franchisé (connexion soir → ERP)
- Pas d'architecture temps réel, synchronisation en batch nuitée
- Pas de mention de sécurité particulière dans le cas

---

## Processus manquants ou à améliorer

### Manquants
- Livraison à domicile (< 10 personnes, en semaine)
- Click & collect structuré (plats déjeuner, délai court)
- BI / tableau de bord consolidé pour le siège
- Onboarding SI nouveaux franchisés hors région
- Gestion multi-prestataires logistiques (remplacement ou complément à « Je livre »)
- Gestion de la facturation franchisés au % CA (nouveau modèle)

### À améliorer
- Remontée des ventes : batch nocturne → temps quasi-réel
- Commande d'approvisionnement : processus manuel → automatisation partielle
- Gestion de la carte (30 plats en rotation) : actuellement non détaillée dans le SI
- Suivi qualité / traçabilité : mentionné contractuellement mais non décrit en SI
- Communication siège ↔ franchisés : canaux non définis dans le SI actuel

---

## Analyse des risques — grille de référence

| Risque | Domaine | Criticité estimée |
|---|---|---|
| Dépendance à un ERP vieillissant (éditeur stagnant) | Applicatif | Élevée |
| Dépendance exclusive à « Je livre » (pas d'antenne hors région) | Logistique / SI | Élevée |
| Absence de données temps réel (batch nuitée) | Fonctionnel | Moyenne |
| Sécurité des données (RH, compta, données clients) | Sécurité | Moyenne à élevée |
| Scalabilité du SI si doublement du réseau | Technique | Élevée |
| Perte de maîtrise SI en cas d'infogérance totale | Gouvernance | Moyenne |
| Résistance au changement des franchisés existants | Conduite du changement | Moyenne |
| Obsolescence de l'app franchisé / site web | Applicatif | Faible à moyenne |
| Risque RGPD (données clients, employés) | Juridique / Sécurité | Moyenne |

---

## Principes architecturaux à retenir pour la cible

1. **Découplage progressif** : ne pas repartir de zéro. L'ERP actuel est à remplacer, pas tout le SI.
2. **Architecture n-tiers ou SOA légère** adaptée à la taille de l'organisation (PME / réseau franchise), pas de micro-services complets.
3. **API-first** pour permettre l'intégration futurs franchisés, futurs prestataires logistiques, et livraison à domicile (partenaires tiers type Uber Eats ou solution propre).
4. **Cloud hybride** : hébergement SaaS pour l'ERP (réduire les coûts de maintien), données sensibles potentiellement en cloud privé ou souverain.
5. **Temps réel ou quasi-réel** pour les commandes (exit le batch nuitée pour les flux critiques).
6. **Éco-conception** : mutualisation des hébergements, éviter la duplication de données, privilégier l'open source quand pertinent.
7. **Sécurité by design** : RGPD, droits d'accès par rôle (franchisé / siège / acheteur), chiffrement des flux.

---

## Éléments financiers de cadrage pour l'analyse coûts/bénéfices

**Coûts SI actuels estimés (siège)**
- ERP : 16 000 €/an
- Site web + app : 1 500 €/an
- Logistique « Je livre » : 150 000 €/an
- Caisses (à la charge des franchisés) : 5 000 €/franchisé/an × 25 = 125 000 €/an (hors siège)

**Indicateurs à mobiliser pour le ROI**
- Hausse des ventes déjeuner : si click & collect → de 10% à 15-20% du CA franchisé = +30 à +60 K€/franchisé/an
- Livraison à domicile : nouveau flux de CA non capté aujourd'hui
- Réduction des coûts ERP : migration vers solution moderne potentiellement moins chère et plus scalable
- Réduction des erreurs de remontée de caisse (batch → temps réel)
- ROI = (gains estimés – coût du projet) / coût du projet

---

## Conventions de modélisation à respecter

- **Cartographies** : utiliser des diagrammes Mermaid (flowchart ou C4 simplifié) ou des représentations tabulaires par couche
- **SWOT** : tableau 2×2 avec Forces / Faiblesses / Opportunités / Menaces, suivi d'une synthèse narrative
- **SDSI** : feuille de route sous forme de tableau temporel (T0 à T+5 ans) ou diagramme de Gantt macro
- **Risques** : matrice probabilité × impact, ou tableau avec colonnes Risque / Domaine / Criticité / Mesure corrective
- **Processus** : notation textuelle structurée ou diagramme BPMN simplifié en Mermaid

---

## Ce que ce skill ne couvre pas

- La modélisation détaillée des données (MCD / MLD)
- Le développement applicatif (code, API, schémas de base de données)
- Les appels d'offres ou comparatifs détaillés d'éditeurs ERP (Sage, SAP Business One, Odoo, etc.) — à traiter séparément si demandé
