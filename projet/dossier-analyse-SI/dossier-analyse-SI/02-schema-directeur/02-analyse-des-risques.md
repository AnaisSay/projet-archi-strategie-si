## Analyse des risques (version améliorée)

| Évolution                                          | Risque identifié                                                                                                                          | Probabilité |   Impact   |   Criticité  | Mesures de prévention / remédiation                                                                                                    |
| -------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | :---------: | :--------: | :----------: | -------------------------------------------------------------------------------------------------------------------------------------- |
| **Migration vers un nouvel ERP**                   | Perte ou corruption des données lors de la migration                                                                                      |    Élevée   | Très élevé |  🔴 Critique | Sauvegardes complètes, migration pilote, validation des données avant mise en production.                                              |
|                                                    | Interruption d'activité pendant la bascule                                                                                                |   Moyenne   | Très élevé |  🔴 Critique | Migration pendant les périodes creuses, plan de retour arrière (rollback), maintien temporaire de l'ancien ERP.                        |
|                                                    | **Erreurs de calcul des redevances ou fraude sur la déclaration du chiffre d'affaires des franchisés avec le nouveau modèle (8 % du CA)** |   Moyenne   |    Élevé   | 🟠 Important | Interconnexion automatique des caisses avec l'ERP, contrôle des ventes en temps réel, audits réguliers et traçabilité des opérations.  |
|                                                    | Dépassement du budget ou du calendrier du projet                                                                                          |   Moyenne   |    Élevé   | 🟠 Important | Gouvernance de projet, suivi budgétaire et jalons de validation.                                                                       |
| **Synchronisation temps réel ERP / Caisses**       | Incompatibilité entre les équipements existants et le nouvel ERP                                                                          |   Moyenne   |    Élevé   | 🟠 Important | Vérification des compatibilités, développement d'API et tests d'intégration.                                                           |
| **Refonte du site Web et de l'application mobile** | Dysfonctionnements lors de la mise en production                                                                                          |   Moyenne   |    Élevé   | 🟠 Important | Déploiement progressif, environnement de recette, tests utilisateurs.                                                                  |
| **Click & Collect accéléré**                       | Mauvaise estimation des délais de préparation                                                                                             |   Moyenne   |    Élevé   | 🟠 Important | Ajustement dynamique des créneaux de retrait selon la charge de production.                                                            |
| **Livraison à domicile**                           | Retards ou erreurs de livraison                                                                                                           |   Moyenne   |    Élevé   | 🟠 Important | Contrat avec indicateurs de performance (SLA), suivi des livraisons et notifications clients.                                          |
|                                                    | **Incapacité du prestataire logistique actuel à couvrir les nouvelles régions lors de l'extension nationale**                             |    Élevée   | Très élevé |  🔴 Critique | Lancer un appel d'offres national ou mettre en place un modèle multi-prestataires régionaux afin de garantir la continuité de service. |
|                                                    | Dépendance à un prestataire unique                                                                                                        |   Moyenne   |    Élevé   | 🟠 Important | Prévoir plusieurs partenaires logistiques et des contrats de secours.                                                                  |
| **Déploiement du CRM**                             | Non-respect du RGPD                                                                                                                       |    Faible   | Très élevé |  🔴 Critique | Désignation d'un DPO, gestion des consentements, minimisation des données collectées et audits réguliers.                              |
| **Cybersécurité**                                  | Cyberattaque (ransomware, phishing)                                                                                                       |   Moyenne   | Très élevé |  🔴 Critique | Authentification multifacteur (MFA), EDR, sauvegardes hors ligne, PRA/PCA et sensibilisation des utilisateurs.                         |
|                                                    | Fuite de données clients                                                                                                                  |    Faible   | Très élevé |  🔴 Critique | Chiffrement des données, contrôle des accès, journalisation et surveillance continue.                                                  |
| **Formation des utilisateurs**                     | Résistance au changement des franchisés                                                                                                   |   Moyenne   |    Moyen   |   🟡 Modéré  | Accompagnement au changement, formations et support technique.                                                                         |
| **Extension nationale**                            | Difficulté d'intégration des nouvelles franchises                                                                                         |   Moyenne   |    Élevé   | 🟠 Important | Standardisation des procédures, documentation et accompagnement des nouveaux franchisés.                                               |

---

# Cartographie des risques (mise à jour)

| Domaine                       | Niveau de risque |
| ----------------------------- | :--------------: |
| Migration ERP                 |   🔴 Très élevé  |
| Logistique nationale          |   🔴 Très élevé  |
| Cybersécurité                 |   🔴 Très élevé  |
| Facturation des redevances    |     🟠 Élevé     |
| Refonte Web / Mobile          |     🟠 Élevé     |
| Synchronisation ERP / Caisses |     🟠 Élevé     |
| Déploiement CRM (RGPD)        |     🟠 Élevé     |
| Formation des utilisateurs    |     🟡 Moyen     |
| Extension nationale           |     🟠 Élevé     |

---

# Matrice Probabilité / Impact

| **Impact**  | **Faible** | **Moyen**                    | **Élevé**                                                                                                                         | **Très élevé**                                                                                     |
| ----------- | ---------- | ---------------------------- | --------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| **Élevée**  |            |                              |                                                                                                                                   | **Incapacité du prestataire logistique à couvrir les nouvelles régions**, **Perte de données ERP** |
| **Moyenne** |            | **Résistance au changement** | **Erreurs de facturation des redevances**, **Retards de livraison**, **Incompatibilité ERP / caisses**, **Dépassement de budget** | **Cyberattaque**, **Interruption d'activité**                                                      |
| **Faible**  |            |                              |                                                                                                                                   | **Fuite de données**, **Non-conformité RGPD**                                                      |
 