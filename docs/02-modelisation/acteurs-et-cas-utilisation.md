# ProGestion — Acteurs et cas d'utilisation

**Référence :** UML-PROGESTION-001  
**Version :** 1.0  
**Date :** 29/10/2026  
**Statut :** VALIDÉ — Référence fonctionnelle V1  
**Projet :** ProGestion SaaS  
**Entreprise de référence :** Atelier Horizon Services  
**Validation métier :** Product Owner ProGestion  
**Documents de référence :** Cahier des charges fonctionnel V1, Catalogue des exigences V1, Product Backlog V1, Priorisation MoSCoW V1

---

## 1. Objectif de la modélisation

Ce document identifie les acteurs qui interagissent avec ProGestion et les services qu'ils attendent du système.

Il délimite le périmètre fonctionnel de la V1 et décrit précisément le cas d'utilisation **UC-005 — Créer un rendez-vous**.

Les objectifs sont de :

- Définir qui utilise l'application et pour quelles actions.
- Associer chaque cas d'utilisation à une exigence et à une User Story.
- Décrire les échanges entre les acteurs et le système.
- Fournir une base stable aux diagrammes UML, aux scénarios de tests et à la conception.

**Décision métier :** La V1 couvre la gestion des clients, des rendez-vous, l'authentification et les autorisations, avec isolation des données entre entreprises.

---

## 2. Frontière du système

### 2.1 Dans le périmètre de ProGestion V1

Le système ProGestion prend en charge :

1. L'authentification et la déconnexion des utilisateurs.
2. La recherche, la création, la consultation et la modification des fiches clients.
3. La création de rendez-vous et le contrôle des conflits.
4. La consultation du planning personnel.
5. L'annulation des rendez-vous autorisés.
6. La vérification des autorisations et l'isolation des données de chaque entreprise.

Les utilisateurs interagissent avec ProGestion au moyen d'une application web.

Le contrôle des droits, la validation des données et la détection des conflits sont des responsabilités **internes au système**, et non des acteurs externes.

### 2.2 Hors périmètre V1

- Réservation autonome par les clients finaux.
- Notifications automatiques SMS ou e-mail.
- Vue consolidée du planning de l'équipe (US-008, reportée en V2).
- Facturation et paiement en ligne.
- Gestion avancée des absences.
- Importation automatique des fichiers Excel.
- Administration des comptes via une interface métier dédiée.

Les comptes sont provisionnés par un processus d'administration interne sécurisé pour la V1.

### 2.3 Frontière UML

Dans un diagramme de cas d'utilisation :

- Le rectangle représente **ProGestion SaaS — V1**.
- Les acteurs sont représentés à l'extérieur.
- Les cas d'utilisation sont représentés par des ovales à l'intérieur.
- Les associations relient les acteurs aux fonctionnalités qu'ils utilisent.

---

## 3. Acteurs identifiés

### ACT-001 — Employé

**Type :** Acteur humain principal.

L'employé travaille pour une entreprise cliente de ProGestion.

Il possède un compte individuel actif.

**Responsabilités :**

- Se connecter et se déconnecter.
- Rechercher un client.
- Créer une fiche client.
- Consulter une fiche client.
- Modifier une fiche client.
- Créer un rendez-vous.
- Consulter son propre planning.
- Annuler un rendez-vous qu'il a créé ou auquel il est affecté.

**Restrictions :**

- Il ne peut pas accéder aux données d'une autre entreprise.
- Il ne peut pas consulter le planning global de l'équipe en V1.
- Il ne peut pas annuler un rendez-vous sans autorisation.

### ACT-002 — Responsable

**Type :** Acteur humain principal.

Le Responsable est une spécialisation de l'acteur Employé.

Il possède toutes les possibilités de l'Employé.

**Responsabilités supplémentaires :**

- Annuler tout rendez-vous appartenant à son entreprise.
- Superviser les opérations métier selon les droits définis.

**Restrictions :**

- Il ne peut pas accéder aux données d'une autre entreprise.
- Le planning global de l'équipe reste exclu de la V1.

**Relation UML :**

Le Responsable hérite des cas d'utilisation de l'Employé.

Relation : `Responsable --|> Employé`

### ACT-003 — Administrateur de plateforme

**Type :** Acteur de support technique.

L'Administrateur de plateforme assure :

- L'exploitation technique de ProGestion.
- Le provisionnement sécurisé des comptes.
- La maintenance de la plateforme.
- La gestion technique des environnements.

**Restrictions :**

- Il ne dispose pas automatiquement d'un accès aux données métier des entreprises.
- Aucun cas d'utilisation d'administration des comptes par interface web n'est livré en V1.

### 3.4 Acteurs non retenus

**Client final**

Le client final contacte l'entreprise par téléphone ou par e-mail.

Il ne réserve pas directement dans ProGestion en V1.

**Service de notification**

Aucun service automatique SMS ou e-mail n'est intégré en V1.

**Système de paiement**

Aucun système de paiement n'est intégré en V1.

**Base de données**

La base de données est un composant interne de ProGestion et non un acteur UML.

---

## 4. Matrice acteurs / cas d'utilisation

### 4.1 Catalogue des cas d'utilisation

| ID     | Cas d'utilisation                 | Acteur principal     | User Story | V1       |
| ------ | --------------------------------- | -------------------- | ---------- | -------- |
| UC-001 | Se connecter                      | Employé, Responsable | US-009     | Oui      |
| UC-002 | Rechercher un client              | Employé, Responsable | US-001     | Oui      |
| UC-003 | Créer un client                   | Employé, Responsable | US-002     | Oui      |
| UC-004 | Consulter une fiche client        | Employé, Responsable | US-007     | Oui      |
| UC-005 | Créer un rendez-vous              | Employé, Responsable | US-004     | Oui      |
| UC-006 | Consulter son planning            | Employé, Responsable | US-005     | Oui      |
| UC-007 | Modifier un client                | Employé, Responsable | US-003     | Oui      |
| UC-008 | Annuler un rendez-vous            | Employé, Responsable | US-006     | Oui      |
| UC-009 | Se déconnecter                    | Employé, Responsable | US-009     | Oui      |
| UC-010 | Consulter le planning de l'équipe | Responsable          | US-008     | Non — V2 |

**Important :**

Les contrôles d'autorisation (US-010) et l'isolation des données (US-011) sont des exigences transversales.

Ils s'appliquent à tous les cas d'utilisation protégés.

### 4.2 Matrice des autorisations

| Cas d'utilisation                 | Employé                | Responsable                 | Administrateur       |
| --------------------------------- | ---------------------- | --------------------------- | -------------------- |
| Se connecter                      | Oui                    | Oui                         | Hors parcours métier |
| Rechercher un client              | Oui                    | Oui                         | Non par défaut       |
| Créer un client                   | Oui                    | Oui                         | Non par défaut       |
| Consulter une fiche client        | Oui                    | Oui                         | Non par défaut       |
| Créer un rendez-vous              | Oui                    | Oui                         | Non par défaut       |
| Consulter son planning            | Oui                    | Oui                         | Non par défaut       |
| Modifier un client                | Oui                    | Oui                         | Non par défaut       |
| Annuler un rendez-vous            | Si créateur ou affecté | Tous ceux de son entreprise | Non par défaut       |
| Se déconnecter                    | Oui                    | Oui                         | Hors parcours métier |
| Consulter le planning de l'équipe | Non                    | Non en V1                   | Non                  |

Toutes les autorisations métier sont limitées à l'entreprise de l'utilisateur.

### 4.3 Relations UML

**Généralisation**

Le Responsable est une spécialisation de l'Employé.

Il hérite des cas d'utilisation accessibles à l'Employé.

**Association**

Une association relie un acteur au cas d'utilisation qu'il peut déclencher.

**Inclusion (`<<include>>`)**

UC-005 — Créer un rendez-vous inclut obligatoirement le contrôle de disponibilité.

Ce contrôle peut être représenté par un sous-cas :

**Vérifier la disponibilité du créneau.**

**Extension (`<<extend>>`)**

Aucune extension n'est nécessaire dans la modélisation V1 retenue.

Les erreurs de saisie, les conflits et les refus d'autorisation sont décrits dans les scénarios alternatifs ou d'exception.

---

## 5. Traçabilité des exigences

| Cas d'utilisation                   | Exigence       | User Story | Règles métier                                                             |
| ----------------------------------- | -------------- | ---------- | ------------------------------------------------------------------------- |
| UC-001 — Se connecter               | EF-010         | US-009     | Compte actif                                                              |
| UC-002 — Rechercher un client       | EF-002         | US-001     | RM-006, RM-007                                                            |
| UC-003 — Créer un client            | EF-001         | US-002     | RM-005, RM-007, RM-009                                                    |
| UC-004 — Consulter une fiche client | EF-009         | US-007     | RM-006, RM-007                                                            |
| UC-005 — Créer un rendez-vous       | EF-004, EF-005 | US-004     | RM-001, RM-002, RM-003, RM-006 à RM-008, RM-010 à RM-012, RM-014 à RM-016 |
| UC-006 — Consulter son planning     | EF-006         | US-005     | RM-006, RM-007                                                            |
| UC-007 — Modifier un client         | EF-003         | US-003     | RM-005 à RM-007                                                           |
| UC-008 — Annuler un rendez-vous     | EF-008         | US-006     | RM-004, RM-006, RM-007, RM-013                                            |
| UC-009 — Se déconnecter             | EF-010         | US-009     | Gestion de session                                                        |
| UC-010 — Planning de l'équipe       | EF-007         | US-008     | Hors V1                                                                   |

### 5.1 Exigences transversales

**EF-011 — Contrôler les autorisations**

Liée à US-010.

Elle s'applique à tous les cas d'utilisation protégés.

**EF-012 — Isoler les données des entreprises**

Liée à US-011.

Elle garantit qu'un utilisateur ne peut pas accéder aux ressources d'une autre entreprise sans autorisation.

---

## 6. Description UC-005 : créer un rendez-vous

### 6.1 Fiche d'identification

| Élément           | Description                                               |
| ----------------- | --------------------------------------------------------- |
| Identifiant       | UC-005                                                    |
| Nom               | Créer un rendez-vous                                      |
| Objectif          | Enregistrer un rendez-vous confirmé sans conflit interdit |
| Acteur principal  | Employé                                                   |
| Acteur secondaire | Responsable                                               |
| Déclencheur       | L'utilisateur sélectionne « Nouveau rendez-vous »         |
| Priorité          | Must Have                                                 |
| Exigences         | EF-004, EF-005                                            |
| User Story        | US-004                                                    |
| Statut            | Validé pour V1                                            |

### 6.2 Préconditions

Avant de créer un rendez-vous :

1. L'utilisateur est authentifié.
2. Son compte est actif.
3. Il possède le droit de créer un rendez-vous.
4. Le client sélectionné existe dans son entreprise.
5. L'employé affecté est actif.
6. L'employé affecté appartient à la même entreprise.

### 6.3 Données d'entrée

L'utilisateur doit renseigner :

- Le client.
- L'employé affecté.
- La date du rendez-vous.
- L'heure de début.
- La durée.

**Durées autorisées :**

- 30 minutes.
- 60 minutes.
- 90 minutes.
- 120 minutes.

L'entreprise et le créateur du rendez-vous sont automatiquement déterminés à partir du compte connecté.

### 6.4 Scénario nominal

**Objectif : créer un rendez-vous valide.**

1. L'utilisateur ouvre le formulaire « Nouveau rendez-vous ».
2. Le système affiche les champs de création.
3. L'utilisateur sélectionne un client de son entreprise.
4. L'utilisateur sélectionne un employé actif de son entreprise.
5. L'utilisateur renseigne la date.
6. L'utilisateur renseigne l'heure de début.
7. L'utilisateur sélectionne la durée.
8. L'utilisateur confirme la création.
9. Le système vérifie les autorisations.
10. Le système vérifie que le client et l'employé appartiennent à la bonne entreprise.
11. Le système vérifie les informations saisies.
12. Le système calcule l'heure de fin.
13. Le système vérifie que le rendez-vous respecte les horaires autorisés.
14. Le système vérifie l'absence de conflit avec un rendez-vous confirmé du même employé.
15. Le système enregistre le rendez-vous de manière sûre.
16. Le système attribue le statut « Confirmé ».
17. Le système affiche un message de confirmation.

**Résultat :**

Le rendez-vous est créé et apparaît dans le planning de l'employé affecté.

### 6.5 Scénarios alternatifs

#### A1 — Créneaux consécutifs

**Situation :**

Un rendez-vous existe de 10 h 00 à 11 h 00.

L'utilisateur souhaite créer un rendez-vous de 11 h 00 à 12 h 00.

**Comportement attendu :**

Le système autorise le nouveau rendez-vous si toutes les autres règles sont respectées.

**Résultat :** Rendez-vous créé.

#### A2 — Même horaire, employés différents

**Situation :**

L'employé A possède un rendez-vous de 10 h 00 à 11 h 00.

L'utilisateur souhaite créer un rendez-vous de 10 h 00 à 11 h 00 pour l'employé B.

**Comportement attendu :**

Le système autorise le nouveau rendez-vous.

**Résultat :** Rendez-vous créé.

#### A3 — Créneau libéré par une annulation

**Situation :**

Un rendez-vous de 10 h 00 à 11 h 00 a été annulé.

**Comportement attendu :**

Le système considère le créneau comme disponible.

**Résultat :** Un nouveau rendez-vous peut être créé.

### 6.6 Scénarios d'exception

#### E1 — Champs manquants ou invalides

**Situation :**

L'utilisateur oublie un champ obligatoire ou renseigne une valeur invalide.

**Comportement attendu :**

- Le système refuse l'enregistrement.
- Il affiche les erreurs à corriger.
- Aucun rendez-vous n'est créé.

#### E2 — Créneau déjà occupé

**Situation :**

Un rendez-vous confirmé existe de 10 h 00 à 11 h 00.

L'utilisateur tente de créer un rendez-vous de 10 h 30 à 11 h 30 pour le même employé.

**Comportement attendu :**

- Le système détecte le conflit.
- Il refuse la réservation.
- Il affiche un message d'indisponibilité.
- Aucun rendez-vous incompatible n'est enregistré.

#### E3 — Date ou horaire non autorisé

**Situation :**

L'utilisateur choisit :

- Une date passée.
- Un dimanche.
- Un horaire avant 08 h 00.
- Un rendez-vous se terminant après 19 h 00.
- Un rendez-vous traversant deux journées.

**Comportement attendu :**

Le système refuse la création et explique la règle non respectée.

#### E4 — Client ou employé d'une autre entreprise

**Situation :**

L'utilisateur tente de créer un rendez-vous avec un client ou un employé appartenant à une autre entreprise.

**Comportement attendu :**

- Le système refuse la création.
- Aucune donnée confidentielle n'est divulguée.
- Aucun rendez-vous n'est enregistré.

#### E5 — Session expirée ou droit insuffisant

**Situation :**

L'utilisateur n'est plus authentifié ou ne possède pas les droits nécessaires.

**Comportement attendu :**

Le système refuse la création.

#### E6 — Réservations simultanées

**Situation :**

Deux utilisateurs tentent de réserver simultanément des créneaux incompatibles pour le même employé.

**Comportement attendu :**

- Le système garantit qu'au plus une réservation est confirmée.
- L'autre demande est refusée.
- Aucun chevauchement interdit n'est enregistré.

#### E7 — Erreur technique

**Situation :**

Une erreur survient pendant l'enregistrement.

**Comportement attendu :**

- Le système n'annonce pas une création réussie.
- Aucune réservation partielle n'est enregistrée.
- Un message compréhensible est affiché.

### 6.7 Postconditions

#### En cas de succès

- Le rendez-vous est enregistré.
- Son statut est « Confirmé ».
- Il est associé à un client existant.
- Il est affecté à un employé actif.
- Il appartient à la bonne entreprise.
- Il apparaît dans le planning de l'employé affecté.
- Aucun conflit interdit n'est créé.

#### En cas d'échec

- Aucun rendez-vous invalide n'est confirmé.
- Les données existantes restent cohérentes.
- Un message adapté est affiché.

### 6.8 Critères d'acceptation — Gherkin

```gherkin
Fonctionnalité: Créer un rendez-vous

  Scénario: Création réussie
    Étant donné un employé autorisé et connecté
    Et un client de son entreprise
    Et un employé affecté actif de cette entreprise
    Et un créneau futur autorisé et disponible
    Quand il confirme un rendez-vous de 60 minutes
    Alors le rendez-vous est enregistré avec le statut "Confirmé"
    Et il apparaît dans le planning de l'employé affecté

  Scénario: Refus d'un chevauchement
    Étant donné un rendez-vous confirmé de 10:00 à 11:00 pour un employé
    Quand un utilisateur tente de créer un rendez-vous de 10:30 à 11:30 pour cet employé
    Alors la création est refusée
    Et aucun rendez-vous incompatible n'est enregistré

  Scénario: Créneaux consécutifs
    Étant donné un rendez-vous confirmé de 10:00 à 11:00 pour un employé
    Quand un utilisateur crée un rendez-vous de 11:00 à 12:00 pour cet employé
    Alors la création est autorisée si les autres règles sont respectées

  Scénario: Isolation des entreprises
    Étant donné un utilisateur de l'entreprise A
    Et un client appartenant à l'entreprise B
    Quand il tente de créer un rendez-vous pour ce client
    Alors la création est refusée
    Et aucune donnée confidentielle de l'entreprise B n'est divulguée

  Scénario: Réservations simultanées
    Étant donné un créneau libre pour un employé
    Quand deux utilisateurs demandent simultanément deux réservations incompatibles
    Alors au plus une réservation est confirmée
```

### 6.9 Règle de détection des conflits

Deux rendez-vous se chevauchent lorsque :

`début_nouveau < fin_existant ET fin_nouveau > début_existant`

**Exemple :**

Rendez-vous existant : 10 h 00 à 11 h 00.

| Nouveau créneau   | Résultat |
| ----------------- | -------- |
| 09 h 00 à 10 h 00 | Autorisé |
| 09 h 30 à 10 h 30 | Refusé   |
| 10 h 00 à 11 h 00 | Refusé   |
| 10 h 30 à 11 h 30 | Refusé   |
| 11 h 00 à 12 h 00 | Autorisé |

Seuls les rendez-vous au statut « Confirmé » bloquent un créneau.

La vérification doit être fiable même si plusieurs utilisateurs créent des rendez-vous simultanément.

---

## 7. Hypothèses et questions ouvertes

### 7.1 Décisions métier validées

| ID    | Décision                                                                                   | Statut  |
| ----- | ------------------------------------------------------------------------------------------ | ------- |
| D-001 | Chaque utilisateur possède un compte individuel et appartient à une seule entreprise en V1 | Validée |
| D-002 | Deux rôles métier : Employé et Responsable                                                 | Validée |
| D-003 | Le Responsable hérite des droits de l'Employé                                              | Validée |
| D-004 | Chaque rendez-vous concerne un client et un employé de la même entreprise                  | Validée |
| D-005 | Deux rendez-vous confirmés du même employé ne peuvent pas se chevaucher                    | Validée |
| D-006 | Durées autorisées : 30, 60, 90 ou 120 minutes                                              | Validée |
| D-007 | Créneaux du lundi au samedi, de 08 h 00 à 19 h 00, fuseau Europe/Paris                     | Validée |
| D-008 | Un rendez-vous annulé libère son créneau mais reste conservé                               | Validée |
| D-009 | Le planning global est reporté en V2                                                       | Validée |
| D-010 | Les clients finaux ne réservent pas directement en V1                                      | Validée |
| D-011 | Les données sont isolées entre entreprises et les droits sont vérifiés côté serveur        | Validée |
| D-012 | La gestion des comptes utilise un processus interne sécurisé en V1                         | Validée |

### 7.2 Questions ouvertes

**Aucune question métier bloquante.**

Les choix techniques suivants seront définis pendant la conception :

- Structure de la base de données.
- Gestion des transactions.
- Stratégie de verrouillage.
- Organisation des API.
- Architecture frontend.
- Organisation des tests automatisés.

Ces choix ne modifient pas les décisions métier validées.

### 7.3 Points de vigilance

- Vérifier les droits d'accès à chaque opération.
- Ne jamais faire confiance à un identifiant d'entreprise fourni librement par le navigateur.
- Tester les créneaux consécutifs.
- Tester les limites horaires.
- Tester les réservations simultanées.
- Maintenir la cohérence entre les diagrammes UML, les exigences, les User Stories et les tests.

---

## 8. Historique des modifications

| Version | Date       | Auteur                   | Modification                                                             | Statut    |
| ------- | ---------- | ------------------------ | ------------------------------------------------------------------------ | --------- |
| 0.1     | 22/10/2026 | Analyste fonctionnelle   | Création de la structure initiale                                        | Brouillon |
| 1.0     | 29/10/2026 | Product Owner ProGestion | Validation des acteurs, du périmètre, des cas d'utilisation et de UC-005 | Validé    |

---

## Approbation

**Décision du Product Owner : APPROUVÉ POUR LA V1.**

Le présent document constitue la référence de modélisation des acteurs et des cas d'utilisation du projet ProGestion SaaS V1.

Il servira de base pour :

- Les diagrammes UML de cas d'utilisation.
- Les descriptions détaillées des scénarios.
- La modélisation des activités.
- La conception fonctionnelle et technique.
- La préparation des tests.

**Statut final : VALIDÉ — VERSION 1.0**

**FIN DU DOCUMENT — PROGESTION SAAS**
