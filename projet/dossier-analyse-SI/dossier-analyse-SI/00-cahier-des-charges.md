# Cahier des charges sommaire — Transformation du SI : M. Traiteur

> **Commanditaire** : Direction M. Traiteur (M. Traiteur père & fils)
> **Maîtrise d'ouvrage déléguée / AMOA** : équipe projet SI
> **Objet** : Cadrage des besoins, des éléments stratégiques et des principes retenus pour la transformation du SI à l'appui de la stratégie d'extension du réseau
> **Horizon** : 5 ans (aligné sur l'échéance de reprise / succession)
> **Version** : 1.0 — document de cadrage

---

## 1. Contexte et finalité

M. Traiteur exploite un réseau de traiteur haut de gamme composé de **3 magasins en propre** et de **25 franchisés** répartis sur 3 départements, pour **230 personnes** et un **CA siège de 1 M€/an**. La direction prépare la succession (père → fils) dans un horizon de 5 ans et engage à cette occasion une **stratégie d'extension** : doublement du CA, ouverture hors région, modernisation du SI et de la logistique, nouveaux services clients.

Le SI actuel — ERP infogéré vieillissant, caisses et TPE mutualisés, site/app de commande, prestataire logistique mono-régional « Je livre » — constitue une base homogène mais arrive à ses limites : remontées des ventes en **batch nocturne**, absence de **livraison à domicile de proximité**, **click & collect** contraint (3 h), dépendances externes fortes (éditeur ERP, logisticien).

Le présent cahier des charges définit les **besoins**, les **éléments stratégiques** structurants et les **principes** qui encadrent la cible et sa feuille de route.

---

## 2. Objectifs stratégiques de référence

| N° | Objectif stratégique |
|---|---|
| O1 | Doubler le CA d'ici la reprise |
| O2 | Étendre le réseau à d'autres régions (produits et plats locaux) |
| O3 | Remplacer l'ERP (solution chère et vieillissante) |
| O4 | Mettre en place la livraison à domicile (y compris < 10 pers., en semaine) |
| O5 | Indexer les frais de gestion sur le CA (8 %) pour les nouveaux contrats |
| O6 | Assouplir les conditions pour le click & collect accéléré (ventes déjeuner) |
| O7 | Revoir la logistique (« Je livre » sans antenne hors région) |

---

## 3. Expression des besoins

### 3.1 Besoins fonctionnels

| Réf. | Besoin fonctionnel | Objectif(s) servi(s) |
|---|---|---|
| BF-1 | Disposer d'un **socle de gestion (ERP) moderne, SaaS et API-first**, à coût maîtrisé et évolutif | O3, O1 |
| BF-2 | **Remonter les ventes et encaissements en temps quasi réel** (caisse → socle), en remplacement du batch nocturne | O1, O5 |
| BF-3 | **Calculer et facturer les frais indexés à 8 % du CA** pour les nouveaux contrats franchisés | O5, O1 |
| BF-4 | **Différencier la gestion** des 3 magasins propres et des 25 franchisés (droits, facturation) | O1, O5 |
| BF-5 | Offrir un **click & collect accéléré** (délai 3 h → < 1 h) pour capter les ventes du déjeuner | O6, O1 |
| BF-6 | **Refondre le site et l'application** (commande, paiement, parcours client) | O1, O6 |
| BF-7 | **Gérer et publier le catalogue** (~30 plats en rotation) depuis une source unique | O6, O1 |
| BF-8 | Mettre en place la **livraison à domicile** de proximité (< 10 pers., en semaine) | O4, O1 |
| BF-9 | Sélectionner un **partenaire logistique à couverture nationale** et ouvrir le SI au **multi-prestataires** | O7, O2 |
| BF-10 | Étendre le **sourcing producteurs multi-régions** | O2, O7 |
| BF-11 | **Piloter le réseau** (tableaux de bord consolidés : ventes, stocks, performance par franchisé) | O1, O2 |
| BF-12 | Déployer un **CRM et un programme de fidélité** (exploitation des données clients) | O1 |
| BF-13 | Industrialiser l'**onboarding SI d'un nouveau franchisé** (kit de déploiement) | O2 |

### 3.2 Besoins non fonctionnels

| Réf. | Besoin | Exigence |
|---|---|---|
| BNF-1 | **Sécurité** | Authentification forte (MFA), droits par rôle (siège / franchisé / acheteur), chiffrement des flux, journalisation |
| BNF-2 | **Conformité RGPD** | Gestion des consentements, minimisation, registre des traitements, désignation d'un référent / DPO |
| BNF-3 | **Disponibilité & continuité** | Sauvegardes, plan de reprise (PRA/PCA), tolérance aux pannes sur les flux critiques de vente |
| BNF-4 | **Scalabilité** | Capacité à absorber le doublement du CA et l'arrivée de franchises hors région sans refonte |
| BNF-5 | **Interopérabilité** | API ouvertes entre domaines (socle, caisse, e-commerce, logistique) ; pas de couplage fort |
| BNF-6 | **Performance** | Remontée des ventes < 5 min ; parcours client fluide (web/app) |
| BNF-7 | **Éco-conception** | Mutualisation des ressources, hébergement sobre, optimisation des tournées de livraison |
| BNF-8 | **Réversibilité** | Possibilité de changer de prestataire (ERP, logisticien) sans remettre en cause les processus |

---

## 4. Éléments stratégiques structurants

- **Succession à 5 ans** : la feuille de route est bornée par l'échéance de reprise ; le jalon final (A5) prépare la transmission.
- **Doublement du CA** : les investissements SI sont gagés sur la croissance (nouveaux services + extension).
- **Modèle économique en évolution** : passage de frais fixes (3 000 €/mois) à un modèle **indexé 8 % du CA** pour les nouveaux contrats, qui suppose une donnée de CA fiable et récente (d'où le temps réel).
- **Atouts relationnels** : réseaux du père (grands chefs) et du fils (traiteurs d'autres régions) comme leviers d'extension.
- **Continuité d'exploitation** : le SI actuel doit rester opérationnel pendant toute la migration (coexistence ancien / nouveau).

---

## 5. Principes et concepts retenus

1. **Découplage des domaines (Clean Architecture appliquée au SI)** — les règles métier (commande, franchise, supply chain, facturation) sont indépendantes des outils. Un changement de prestataire ne doit pas remettre en cause les processus → interfaces / API clairement définies entre domaines.
2. **Source unique de vérité** — pas de duplication de données entre ERP et caisse ; le CA, le catalogue et les référentiels franchisés ont chacun un propriétaire unique.
3. **Temps quasi réel sur les flux critiques** — sortie du batch nocturne pour les ventes (effet de levier sur le pilotage et la facturation au % du CA).
4. **Sécurité & RGPD by design** — droits par rôle, chiffrement, gestion des consentements dès la conception.
5. **Évolution progressive, pas rupture** — remplacement par étapes (siège → magasins pilotes → réseau) et coexistence temporaire de l'ancien et du nouveau.
6. **Sobriété (« on ne conçoit pas ce dont on n'a pas besoin »)** — livraison à domicile et BI sont des domaines à part entière, pas des greffes sur l'existant.
7. **Gouvernance projet** — comité de pilotage trimestriel, jalons go/no-go, conduite du changement continue.

---

## 6. Périmètre et exclusions

- **Inclus** : socle ERP & finance, services numériques clients (C&C, site/app, livraison), logistique & supply chain, pilotage (BI/CRM), extension & gouvernance, sécurité.
- **Exclus à ce stade** : refonte du matériel de caisse (maintenu), changement de banque/TPE (mutualisé, maintenu), développement d'une flotte de livraison en propre (recours à un partenaire privilégié).
- **Hypothèses de cadrage à valider en comité de pilotage** : volumétrie cible post-extension, budget annuel d'investissement, calendrier contractuel de sortie de « Je livre ».

---

## 7. Livrables du dossier

Ce cahier des charges ouvre le dossier d'analyse, qui comprend : l'analyse stratégique (SWOT), la cartographie du SI actuel, l'analyse des processus, les préconisations priorisées, le schéma directeur à 5 ans, l'analyse des risques, la cartographie cible, les préconisations architecturales et l'estimation chiffrée.
