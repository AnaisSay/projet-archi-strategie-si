# Cartographie cible du SI (to be) — M. Traiteur

> **Commanditaire** : Direction M. Traiteur (M. Traiteur père & fils)
> **Maîtrise d'ouvrage déléguée / AMOA** : équipe projet SI
> **Objet** : Cartographie du SI à l'état cible, à l'appui de la stratégie d'extension du réseau
> **Version** : 1.0 — document de cadrage

---

## 1. Objectif et périmètre

Cette cartographie décrit le SI **à l'état envisagé** (cible), tel qu'il doit soutenir le doublement du CA, l'extension hors région et les nouveaux services clients. Elle prolonge la cartographie de l'existant (as-is) et s'organise selon les quatre couches d'urbanisation : **métier, fonctionnelle, applicative, technique**.

Le principe directeur est le **découplage des domaines** : chaque domaine (socle de gestion, services clients, logistique, pilotage, extension) expose des **interfaces / API** stables, de sorte qu'un changement de prestataire ou d'outil ne remette pas en cause les processus.

---

## 2. Légende des flux

| Type de trait | Signification |
|---|---|
| Trait plein épais | Flux applicatif **temps quasi réel** (API / événementiel) |
| Trait pointillé | Flux différé ou périodique (consolidation, reporting) |
| Trait plein orange | Relation contractuelle (hébergement, infogérance, partenariat logistique) |
| Trait plein fin | Flux physique (livraison, retrait, livraison à domicile) |

---

## 3. Couche métier (processus cible)

```mermaid
flowchart TD
    classDef acteur fill:#e8eef7,stroke:#33558b,color:#1a2b4a;
    classDef proc fill:#ffffff,stroke:#5a5a5a,color:#222;
    classDef new fill:#e9f9ee,stroke:#1f9d55,color:#14532d;

    CLI([Client final]):::acteur
    FRA([Franchisé et personnel]):::acteur
    SIE([Siège M. Traiteur]):::acteur
    ACH([Acheteurs multi-régions]):::acteur
    LOG([Partenaire logistique national]):::acteur

    P1[Prise de commande<br/>web, app, tel, C&C < 1h]:::proc
    P2[Préparation des plats]:::proc
    P3[Encaissement caisse / TPE<br/>remontée temps réel]:::new
    P4[Approvisionnement<br/>sourcing multi-régions]:::proc
    P7[Livraison à domicile<br/>< 10 pers, en semaine]:::new
    P6[Support central<br/>RH, compta, marketing, qualité]:::proc
    P8[Pilotage consolidé<br/>BI, CRM, facturation 8%]:::new
    P9[Onboarding franchisé<br/>kit SI standardisé]:::new

    CLI --> P1 --> P2 --> P3
    P2 --> P7 --> CLI
    FRA --> P2
    FRA --> P4 --> ACH --> LOG --> FRA
    SIE --> P6
    SIE --> P8
    SIE --> P9 --> FRA
    P3 -.-> P8
```

Nouveaux processus (en vert) introduits par la cible : **encaissement temps réel**, **livraison à domicile de proximité**, **pilotage consolidé (BI/CRM + facturation 8 %)** et **onboarding SI standardisé** des franchisés.

---

## 4. Couche fonctionnelle & applicative (domaines cibles)

```mermaid
flowchart LR
    classDef acteur fill:#eef2ff,stroke:#818cf8,color:#1a2b4a;
    classDef app fill:#ffffff,stroke:#444,color:#222,stroke-width:1.5px;
    classDef new fill:#e9f9ee,stroke:#1f9d55,color:#14532d,stroke-width:1.5px;
    classDef presta fill:#fff7ed,stroke:#fb923c,color:#5a4410;

    CLI([Client final]):::acteur
    FRA([Franchisé]):::acteur

    subgraph SI[SI cible M. Traiteur]
        direction TB
        subgraph BUS[Bus d'intégration / API Gateway]
            BUS0[API Gateway & événements]:::new
        end
        subgraph DA[A · Socle gestion & finance]
            ERP[ERP SaaS API-first<br/>compta, RH, achats]:::new
            FAC[Module facturation<br/>8% du CA]:::new
        end
        subgraph DB[B · Services numériques clients]
            WEB[Site & app refondus<br/>commande, paiement]:::new
            CAT[Gestion catalogue<br/>source unique]:::new
            CC[Click & collect < 1h]:::new
            CAI[Caisses unifiées<br/>remontée temps réel]:::app
        end
        subgraph DC[C · Logistique & supply chain]
            LOGm[Module logistique<br/>multi-prestataires]:::new
        end
        subgraph DD[D · Pilotage & relation client]
            BI[BI / tableaux de bord]:::new
            CRM[CRM & fidélité]:::new
        end
        subgraph DE[E · Extension & gouvernance]
            ONB[Onboarding SI<br/>kit franchise]:::new
            IAM[IAM / droits par rôle<br/>MFA]:::new
        end
    end

    HEB[Hébergeur cloud]:::presta
    LOGN[Partenaire logistique national]:::presta
    LIV[Partenaire livraison domicile]:::presta
    BAN[Banque / TPE]:::presta

    CLI ==> WEB
    CLI ==> CC
    FRA ==> WEB
    WEB ==> BUS0
    CAI ==> BUS0
    CC ==> BUS0
    BUS0 ==> ERP
    BUS0 ==> LOGm
    BUS0 ==> BI
    BUS0 ==> CRM
    ERP ==> FAC
    CAT ==> WEB
    LOGm ==> LOGN
    LOGm ==> LIV
    CAI ==> BAN
    HEB --> SI
    IAM -.-> BUS0
```

### Lecture des domaines cibles

| Domaine | Composants cibles | Évolution vs as-is |
|---|---|---|
| **A — Socle gestion & finance** | ERP SaaS API-first, module facturation 8 % | Remplacement de l'ERP infogéré ; nouvelle facturation indexée |
| **B — Services numériques clients** | Site/app refondus, gestion catalogue, C&C < 1 h, caisses temps réel | Refonte ; sortie du batch ; nouveau C&C accéléré |
| **C — Logistique & supply chain** | Module logistique multi-prestataires | Sortie du mono-prestataire « Je livre » ; ouverture nationale |
| **D — Pilotage & relation client** | BI, CRM & fidélité | Création (inexistant en as-is) |
| **E — Extension & gouvernance** | Onboarding SI, IAM/MFA, droits par rôle | Industrialisation et sécurisation |
| **Intégration** | API Gateway / bus d'événements | Découplage généralisé entre domaines |

---

## 5. Couche technique (infrastructure cible)

| Composant | Hébergement / infrastructure cible |
|---|---|
| ERP | SaaS, hébergé par l'éditeur, exposé via API |
| Site / app | Hébergement cloud mutualisé, dimensionnement élastique |
| Caisses | Équipements locaux conservés, synchronisation temps réel via le bus |
| Intégration | API Gateway + bus d'événements (temps quasi réel) |
| Sécurité | IAM centralisé, MFA, chiffrement des flux, sauvegardes, PRA/PCA |
| Données | Source unique par référentiel (CA, catalogue, franchisés) |

---

## 6. Synthèse — du as-is au to-be

La cible lève les quatre verrous du SI actuel :

1. **Batch → temps réel** : les ventes remontent en continu, condition du pilotage et de la facturation 8 %.
2. **Dépendances externes → interfaces ouvertes** : ERP SaaS API-first et logistique multi-prestataires réduisent l'effet de verrouillage.
3. **Services absents → domaines dédiés** : livraison à domicile, click & collect accéléré, BI et CRM existent comme domaines à part entière.
4. **Réseau régional → extension industrialisée** : onboarding SI standardisé et sécurité by design rendent l'ouverture hors région réplicable.

> Cette cartographie cible est l'aboutissement de la feuille de route à 5 ans (schéma directeur). Les jalons, dépendances et risques associés sont détaillés dans les dossiers correspondants.
