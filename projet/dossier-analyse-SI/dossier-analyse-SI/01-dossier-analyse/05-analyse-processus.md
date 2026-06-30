# Analyse des Processus Métier
## Réseau de Franchise M. Traiteur — Processus à améliorer / processus manquants

**Version :** 1.0 
**Date :** 30 Juin 2026
**Auteures :** Florian, Anaïs et Anthony les GOAT (pronocer "goatte" en Français)

---

## 1. Méthode

Cette analyse se place au niveau **métier** (couche processus), indépendamment des outils qui les supportent.

Elle distingue deux catégories :

- **Processus à améliorer** : processus qui existent et sont documentés, mais qui présentent une friction freinant un ou plusieurs des 7 objectifs stratégiques.
- **Processus manquants** : processus qui n'existent pas aujourd'hui, ou dont l'existence n'est pas démontrée — y compris les flux précédemment traités comme hypothèses lors de la cartographie (publication du catalogue, transmission des commandes vers « Je livre »).

Chaque processus est relié à un ou plusieurs des **7 objectifs stratégiques** de la fiche contexte, et, lorsque pertinent, à une **tension par partie prenante** identifiée dans la fiche correspondante.

---

## 2. Rappel des 7 objectifs stratégiques (fiche contexte)

| N° | Objectif |
|---|---|
| 1 | Doubler le CA d'ici la reprise |
| 2 | Étendre le réseau à d'autres régions |
| 3 | Changer d'ERP |
| 4 | Mettre en place la livraison à domicile (y compris < 10 personnes, en semaine) |
| 5 | Indexer les frais de gestion sur le CA (8%) pour les nouveaux contrats |
| 6 | Assouplir les conditions pour le click & collect accéléré |
| 7 | Revoir la logistique (« Je livre » sans antenne hors région) |

## 3. Rappel des acteurs et tensions (parties prenantes)

| Acteur | Tension identifiée |
|---|---|
| Direction & comptabilité | Besoin d'un pilotage temps réel impossible avec la remontée batch actuelle |
| Franchisés & clients | Attentes non couvertes : livraison de proximité, click & collect rapide |
| Acheteurs | Sourcing à étendre hors de la zone du prestataire actuel |
| Éditeur ERP & « Je livre » | Deux dépendances externes critiques pour la stratégie d'extension |

> Point structurel à retenir : les **magasins propres (×3)** ont une gestion financière intégrée directement au siège — pas de facturation franchisé, droits d'accès SI distincts. Plusieurs processus liés au modèle économique (frais de gestion, facturation) ne concernent donc que les 25 franchisés, pas les magasins propres.

---

## 4. Processus à améliorer

| Réf. | Processus | État actuel | Problème identifié                                                                                                                                                                              | Objectif(s) concerné(s) | Tension partie prenante | Priorité |
|---|---|---|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---|---|---|
| PA-01 | Remontée des ventes vers l'ERP | Batch nocturne, transmission après fermeture | Aucune vision temps réel pour le siège ; les écarts ou anomalies ne sont détectés qu'a posteriori                                                                                               |  1 | Direction & comptabilité | **Haute** |
| PA-02 | Prise de commande / délai de retrait | Délai minimum de 3h avant retrait, uniforme | Frein direct aux ventes du déjeuner (~10% du CA), qui nécessitent un retrait rapide                                                                                                             |  6 | Franchisés & clients | **Haute** |
| PA-03 | Livraison des commandes clients | Réservée aux commandes > 10 personnes, week-end uniquement | Possibilité de croissance du CA non exploitée pour les segments de ventes individuelles en semaine                                                                                              |  4 | Franchisés & clients | **Haute** |
| PA-04 | Approvisionnement / supply chain | Mono-prestataire (« Je livre »), sans antenne hors région | Bloque structurellement toute extension géographique du réseau                                                                                                                                                |  2,  7 | Acheteurs · Éditeur ERP & Je livre | **Haute** |
| PA-05 | Calcul des frais de gestion | Modèle fixe (3 000 €/mois), pas de mécanisme variable | Le passage au modèle indexé (8%) nécessite un processus de calcul et facturation — concerne les 25 franchisés, pas les 3 magasins propres dont la gestion financière est déjà intégrée au siège |  5,  1 | Direction & comptabilité | **Moyenne** |
| PA-06 | Sourcing producteurs locaux | Limité à la zone régionale actuelle, via les 2 acheteurs | L'extension multi-régions suppose un sourcing élargi, non préparé aujourd'hui                                                                                                                   |  2,  7 | Acheteurs | Moyenne |

---

## 5. Processus manquants

| Réf. | Processus | Constat | Objectif(s) concerné(s) | Tension partie prenante | Priorité |
|---|---|---|---|---|---|
| PM-01 | Onboarding SI d'un nouveau franchisé | Aucun processus décrit pour le paramétrage des accès, la formation, l'intégration d'un point de vente — a fortiori hors région |  2 | — | **Haute** |
| PM-02 | Gestion et publication du catalogue (~30 plats) | Le principe de rotation est connu (2 plats ajoutés/retirés par mois) mais aucun processus de gestion ou de publication n'est documenté |  6,  1 | Marketing / Veille qualité (parties prenantes) | **Haute** |
| PM-03 | Transmission des commandes groupées vers « Je livre » | Le rôle des acheteurs est décrit mais aucun canal n'est documenté ; reclassé ici depuis l'hypothèse posée lors de la cartographie |  7 | Acheteurs | Moyenne |
| PM-04 | Livraison à domicile (< 10 personnes, en semaine) | N'existe pas aujourd'hui ; nécessite un processus complet |  4,  1 | Franchisés & clients | **Haute** |
| PM-05 | Click & collect structuré (plats déjeuner) | N'existe pas tel que souhaité par M. Traiteur fils ; intention, pas processus en place |  6,  1 | Franchisés & clients | **Haute** |
| PM-06 | Pilotage consolidé / reporting siège | Aucun processus de consolidation des données réseau (ventes, stocks, performance par franchisé) |  1,  2 | Direction & comptabilité | **Haute** |
| PM-07 | Gestion multi-prestataires logistiques | Un seul prestataire décrit ; aucun processus de sélection ou de répartition entre plusieurs prestataires |  7,  2 | Éditeur ERP & Je livre | Moyenne |
| PM-08 | Différenciation de gestion magasins propres / franchisés | Les magasins propres (×3) ont des besoins SI distincts (pas de facturation franchisé, droits d'accès différents) mais aucun processus ni paramétrage différencié n'est décrit |  1,  5 | Direction & comptabilité | Moyenne |
| PM-09 | Communication structurée siège ↔ franchisés | Aucun canal ni processus de communication formel au-delà de la consultation des commandes | Transverse | — | Faible à moyenne |

---

## 6. Synthèse

Trois constats se dégagent de cette analyse.

**Le batch/traitement de nuit est la racine commune de plusieurs frictions.** PA-01 n'est pas un problème isolé : il bloque mécaniquement PM-06 (reporting siège) et complique PA-05 (calcul des frais au % CA, qui suppose une donnée de CA fiable et récente). Résoudre PA-01 a un effet de levier sur au moins deux autres processus.

**Les processus manquants à forte priorité sont tous liés aux nouveaux canaux de vente.** PM-04 (livraison à domicile) et PM-05 (click & collect) sont les deux relais de croissance identifiés par M. Traiteur fils.

**L'onboarding (PM-01) est un prérequis silencieux à l'extension géographique.** Sans ce processus, l'objectif N°2 (Étendre le réseau à d'autres régions) ne peut pas être totalement mis en œuvre, quel que soit le SI choisi.