# ProGestion SaaS — Product Backlog V1

**Version :** 1.0  
**Statut :** Validé  
**Dernière mise à jour :** 26/10/2026  
**Product Owner :** Responsable ProGestion  
**Responsable technique :** Développeuse Full Stack  
**Périmètre :** Version 1 (V1)

---

## 1. Objectif du produit

### 1.1 Présentation

ProGestion est une application web SaaS destinée aux petites entreprises de services.

Elle permet de centraliser la gestion des clients et des rendez-vous dans une seule application.

La première entreprise utilisatrice compte 8 employés et environ 500 clients.

L'application sera développée avec :

- React et TypeScript pour le frontend.
- Symfony et API Platform pour le backend.
- PostgreSQL pour la base de données.
- Docker pour les environnements.
- Git pour le versioning.

### 1.2 Problèmes à résoudre

Actuellement, notre entreprise rencontre plusieurs difficultés :

- Les informations clients sont dispersées dans plusieurs fichiers Excel.
- Les employés perdent du temps à rechercher les coordonnées des clients.
- Certaines fiches clients sont dupliquées.
- Les rendez-vous sont organisés manuellement.
- Deux employés peuvent réserver le même créneau.
- Les plannings ne sont pas centralisés.
- Les droits d'accès aux informations sont mal définis.

### 1.3 Objectif principal

Permettre aux employés de gérer efficacement les clients et les rendez-vous depuis une application centralisée, sécurisée et simple d'utilisation.

### 1.4 Objectifs mesurables

| ID      | Objectif                 | Indicateur de réussite                                                         |
| ------- | ------------------------ | ------------------------------------------------------------------------------ |
| OBJ-001 | Centraliser les clients  | Toutes les nouvelles fiches sont créées dans ProGestion                        |
| OBJ-002 | Faciliter les recherches | 95 % des recherches simples répondent en moins de 2 secondes                   |
| OBJ-003 | Éviter les conflits      | Aucun chevauchement interdit entre rendez-vous confirmés                       |
| OBJ-004 | Améliorer les plannings  | Chaque employé peut consulter ses rendez-vous                                  |
| OBJ-005 | Sécuriser les données    | Aucun accès non autorisé entre entreprises                                     |
| OBJ-006 | Faciliter l'utilisation  | Les employés réalisent les actions principales sans assistance après formation |

### 1.5 Périmètre validé de la V1

La V1 comprend :

- Authentification des utilisateurs.
- Gestion des autorisations.
- Isolation des données des entreprises.
- Création des fiches clients.
- Recherche des clients.
- Consultation des fiches clients.
- Modification des fiches clients.
- Création des rendez-vous.
- Vérification des conflits de réservation.
- Consultation du planning personnel.
- Annulation des rendez-vous.

### 1.6 Hors périmètre V1

Les fonctionnalités suivantes seront étudiées pour la V2 :

- Consultation du planning global de l'équipe.
- Réservation directe par les clients.
- Notifications automatiques par SMS ou e-mail.
- Facturation.
- Paiement en ligne.
- Statistiques avancées.
- Export CSV.
- Gestion avancée des absences.
- Importation automatique des anciens fichiers Excel.

---

## 2. Epics

Une Epic représente un grand ensemble fonctionnel regroupant plusieurs User Stories.

### EPIC-01 — Gestion des clients

**Objectif :**

Permettre aux employés autorisés de centraliser et de gérer les informations clients.

**Valeur métier :**

- Réduire le temps de recherche.
- Améliorer la qualité des informations.
- Éviter la dispersion des données.
- Faciliter le suivi des clients.

**User Stories associées :**

- US-001 — Rechercher un client.
- US-002 — Créer un client.
- US-003 — Modifier un client.
- US-007 — Consulter une fiche client.

**Résultat attendu :**

Les employés disposent d'un référentiel client unique et sécurisé pour leur entreprise.

### EPIC-02 — Gestion des rendez-vous

**Objectif :**

Permettre aux employés d'organiser les rendez-vous sans créer de conflits de réservation.

**Valeur métier :**

- Réduire les erreurs de planning.
- Améliorer l'organisation quotidienne.
- Éviter les doubles réservations.
- Faciliter la consultation des rendez-vous.

**User Stories associées :**

- US-004 — Créer un rendez-vous.
- US-005 — Consulter son planning.
- US-006 — Annuler un rendez-vous.
- US-008 — Consulter le planning de l'équipe (V2).

**Résultat attendu :**

Les employés peuvent créer, consulter et annuler leurs rendez-vous selon leurs autorisations.

### EPIC-03 — Authentification et sécurité

**Objectif :**

Protéger l'application et garantir l'accès aux données uniquement aux utilisateurs autorisés.

**Valeur métier :**

- Protéger les informations clients.
- Séparer les données des entreprises.
- Empêcher les actions non autorisées.
- Fiabiliser l'utilisation de l'application.

**User Stories associées :**

- US-009 — Se connecter.
- US-010 — Accéder uniquement aux données autorisées.
- US-011 — Isoler les données des entreprises.

**Résultat attendu :**

Chaque utilisateur accède uniquement aux fonctionnalités et aux données autorisées de son entreprise.

---

## 3. Catalogue des User Stories

| ID     | Epic    | Titre                              | Exigence       | Priorité | Statut      |
| ------ | ------- | ---------------------------------- | -------------- | -------- | ----------- |
| US-001 | EPIC-01 | Rechercher un client               | EF-002         | Must     | Ready       |
| US-002 | EPIC-01 | Créer un client                    | EF-001         | Must     | Ready       |
| US-003 | EPIC-01 | Modifier un client                 | EF-003         | Should   | Ready       |
| US-004 | EPIC-02 | Créer un rendez-vous               | EF-004, EF-005 | Must     | Ready       |
| US-005 | EPIC-02 | Consulter son planning             | EF-006         | Must     | Ready       |
| US-006 | EPIC-02 | Annuler un rendez-vous             | EF-008         | Should   | Ready       |
| US-007 | EPIC-01 | Consulter une fiche client         | EF-009         | Must     | Ready       |
| US-008 | EPIC-02 | Consulter le planning de l'équipe  | EF-007         | Could    | Reportée V2 |
| US-009 | EPIC-03 | Se connecter                       | EF-010         | Must     | Ready       |
| US-010 | EPIC-03 | Contrôler les autorisations        | EF-011         | Must     | Ready       |
| US-011 | EPIC-03 | Isoler les données des entreprises | EF-012         | Must     | Ready       |

### Signification des priorités

**Must Have :** indispensable pour la V1.

**Should Have :** important et inclus dans le périmètre V1.

**Could Have :** utile, mais non indispensable pour la V1.

### Signification des statuts

**Ready :** User Story validée fonctionnellement et suffisamment détaillée pour être planifiée.

**In Progress :** développement en cours.

**Done :** développement terminé et critères d'acceptation satisfaits.

**Reportée V2 :** fonctionnalité exclue de la V1.

---

## 4. Détail des User Stories

### US-001 — Rechercher un client

**Epic :** EPIC-01  
**Priorité :** Must  
**Statut :** Ready

**Description :**

En tant qu'employé autorisé,  
Je veux rechercher un client par son nom,  
Afin de retrouver rapidement ses informations.

**Valeur métier :**

Réduire le temps nécessaire pour retrouver une fiche client.

**Exigence liée :** EF-002.

**Critères d'acceptation :**

- CA-001 : La recherche par nom retourne les clients correspondants.
- CA-002 : La recherche ne présente que les clients accessibles à l'utilisateur.
- CA-003 : Une recherche sans résultat affiche un message explicite.
- CA-004 : La recherche est insensible à la casse.
- CA-005 : Les résultats permettent d'accéder à la fiche du client.

**Décisions métier validées :**

- La recherche par nom est disponible dès la V1.
- La recherche ne doit pas révéler les clients d'une autre entreprise.
- Le système accepte une recherche partielle du nom.

---

### US-002 — Créer un client

**Epic :** EPIC-01  
**Priorité :** Must  
**Statut :** Ready

**Description :**

En tant qu'employé autorisé,  
Je veux créer une fiche client,  
Afin de centraliser ses informations.

**Valeur métier :**

Éviter la dispersion des données clients dans plusieurs fichiers.

**Exigence liée :** EF-001.

**Critères d'acceptation :**

- CA-001 : Un utilisateur autorisé peut créer un client.
- CA-002 : Le nom est obligatoire.
- CA-003 : Au moins un moyen de contact est obligatoire : téléphone ou e-mail.
- CA-004 : Les formats du téléphone et de l'e-mail sont vérifiés.
- CA-005 : Une fiche créée appartient à l'entreprise de l'utilisateur.
- CA-006 : Une confirmation apparaît après l'enregistrement.
- CA-007 : Une fiche contenant des informations obligatoires manquantes n'est pas enregistrée.

**Décisions métier validées :**

- Le prénom est facultatif.
- Le nom et un moyen de contact sont obligatoires.
- Les doublons potentiels sont signalés avant confirmation, sans blocage automatique.
- La suppression définitive des clients n'est pas incluse dans la V1.

---

### US-003 — Modifier un client

**Epic :** EPIC-01  
**Priorité :** Should  
**Statut :** Ready

**Description :**

En tant qu'employé autorisé,  
Je veux modifier les informations d'un client,  
Afin de maintenir sa fiche à jour.

**Valeur métier :**

Réduire les erreurs dues aux informations obsolètes.

**Exigence liée :** EF-003.

**Critères d'acceptation :**

- CA-001 : L'utilisateur autorisé peut modifier une fiche accessible.
- CA-002 : Les champs obligatoires restent valides.
- CA-003 : Les modifications sont enregistrées après confirmation.
- CA-004 : Une confirmation est affichée.
- CA-005 : Un utilisateur ne peut pas modifier une fiche d'une autre entreprise sans autorisation.
- CA-006 : En cas d'erreur, les données non valides ne sont pas enregistrées.

**Décisions métier validées :**

- Le nom, le prénom et les coordonnées peuvent être modifiés.
- L'identifiant du client ne peut pas être modifié.
- Le changement d'entreprise d'une fiche client est interdit dans la V1.

---

### US-004 — Créer un rendez-vous

**Epic :** EPIC-02  
**Priorité :** Must  
**Statut :** Ready

**Description :**

En tant qu'employé autorisé,  
Je veux créer un rendez-vous pour un client,  
Afin d'organiser les prestations et d'éviter les conflits de planning.

**Valeur métier :**

Fiabiliser les réservations et réduire les doubles rendez-vous.

**Exigences liées :** EF-004 et EF-005.

**Critères d'acceptation :**

- CA-001 : Un rendez-vous doit être associé à un client existant et accessible.
- CA-002 : Un rendez-vous doit être affecté à un employé de la même entreprise.
- CA-003 : La date, l'heure de début et la durée sont obligatoires.
- CA-004 : L'heure de fin doit être postérieure à l'heure de début.
- CA-005 : Deux rendez-vous confirmés du même employé ne peuvent pas se chevaucher.
- CA-006 : Une réservation incompatible est refusée avec un message explicite.
- CA-007 : Un rendez-vous valide est enregistré et confirmé.
- CA-008 : Deux demandes simultanées incompatibles ne peuvent pas créer deux réservations confirmées.
- CA-009 : Un utilisateur ne peut pas réserver pour une autre entreprise.

**Décisions métier validées :**

- Un rendez-vous est affecté à un seul employé en V1.
- Les rendez-vous sont créés par les employés autorisés.
- Les clients ne disposent pas de réservation directe en V1.
- Deux rendez-vous peuvent se suivre sans chevauchement.
- Les rendez-vous confirmés ne peuvent pas se chevaucher pour le même employé.
- Le créneau est libéré lorsqu'un rendez-vous est annulé.

---

### US-005 — Consulter son planning

**Epic :** EPIC-02  
**Priorité :** Must  
**Statut :** Ready

**Description :**

En tant qu'employé,  
Je veux consulter mon planning,  
Afin de connaître mes rendez-vous à venir.

**Valeur métier :**

Faciliter l'organisation du travail quotidien.

**Exigence liée :** EF-006.

**Critères d'acceptation :**

- CA-001 : L'employé connecté peut consulter ses rendez-vous.
- CA-002 : Les rendez-vous sont présentés par date et heure.
- CA-003 : L'utilisateur peut choisir une date.
- CA-004 : Les rendez-vous présentent les informations nécessaires : client, horaire et statut.
- CA-005 : L'employé ne voit pas les plannings auxquels il n'a pas accès.
- CA-006 : Une journée sans rendez-vous affiche un état vide compréhensible.

**Décisions métier validées :**

- Une vue journalière est disponible en V1.
- Les rendez-vous annulés restent visibles avec leur statut.
- La vue globale de l'équipe est reportée à la V2.

---

### US-006 — Annuler un rendez-vous

**Epic :** EPIC-02  
**Priorité :** Should  
**Statut :** Ready

**Description :**

En tant qu'employé autorisé,  
Je veux annuler un rendez-vous,  
Afin de libérer le créneau lorsqu'une prestation n'a plus lieu.

**Valeur métier :**

Maintenir un planning fiable et éviter les réservations inutiles.

**Exigence liée :** EF-008.

**Critères d'acceptation :**

- CA-001 : Un utilisateur autorisé peut demander l'annulation.
- CA-002 : Une confirmation est demandée avant l'annulation.
- CA-003 : Un rendez-vous annulé passe au statut « Annulé ».
- CA-004 : Un rendez-vous annulé ne bloque plus le créneau.
- CA-005 : L'annulation ne supprime pas définitivement le rendez-vous.
- CA-006 : Une nouvelle réservation peut utiliser le créneau libéré.
- CA-007 : Une annulation non autorisée est refusée.

**Décisions métier validées :**

- L'annulation est une modification du statut.
- L'historique des rendez-vous annulés est conservé.
- La notification automatique au client est reportée à la V2.

---

### US-007 — Consulter une fiche client

**Epic :** EPIC-01  
**Priorité :** Must  
**Statut :** Ready

**Description :**

En tant qu'employé autorisé,  
Je veux consulter la fiche d'un client,  
Afin de retrouver ses coordonnées et les informations utiles à son suivi.

**Valeur métier :**

Accéder rapidement aux informations clients.

**Exigence liée :** EF-009.

**Critères d'acceptation :**

- CA-001 : Un utilisateur autorisé peut ouvrir une fiche client accessible.
- CA-002 : La fiche présente les coordonnées enregistrées.
- CA-003 : Une fiche inexistante affiche un résultat approprié.
- CA-004 : Un utilisateur ne peut pas consulter les données d'une autre entreprise.
- CA-005 : Les informations affichées correspondent aux données enregistrées.

**Décisions métier validées :**

- La fiche présente le nom, le prénom, le téléphone et l'e-mail disponibles.
- La consultation de l'historique complet des prestations est reportée à la V2.

---

### US-008 — Consulter le planning de l'équipe

**Epic :** EPIC-02  
**Priorité :** Could  
**Statut :** Reportée V2

**Description :**

En tant que responsable,  
Je veux consulter le planning de mon équipe,  
Afin de mieux organiser les activités.

**Valeur métier :**

Disposer d'une vision globale des rendez-vous de l'entreprise.

**Exigence liée :** EF-007.

**Critères d'acceptation prévisionnels :**

- CA-001 : Le responsable autorisé peut consulter les plannings de son équipe.
- CA-002 : Les rendez-vous sont présentés par employé et par date.
- CA-003 : Les droits d'accès sont respectés.

**Décision métier validée :**

Cette fonctionnalité est exclue de la V1 et sera réétudiée pour la V2.

---

### US-009 — Se connecter

**Epic :** EPIC-03  
**Priorité :** Must  
**Statut :** Ready

**Description :**

En tant qu'utilisateur disposant d'un compte actif,  
Je veux me connecter à ProGestion,  
Afin d'accéder aux fonctionnalités qui me sont autorisées.

**Valeur métier :**

Sécuriser l'accès à l'application.

**Exigence liée :** EF-010.

**Critères d'acceptation :**

- CA-001 : Un utilisateur actif peut s'authentifier avec des identifiants valides.
- CA-002 : Des identifiants invalides entraînent un refus de connexion.
- CA-003 : Un compte désactivé ne peut pas se connecter.
- CA-004 : Les fonctionnalités protégées ne sont pas accessibles sans authentification.
- CA-005 : L'utilisateur peut se déconnecter.
- CA-006 : Les informations d'authentification sensibles ne sont pas exposées dans les réponses.

**Décisions métier validées :**

- Chaque utilisateur possède un compte individuel.
- L'adresse e-mail est utilisée comme identifiant de connexion.
- La connexion repose sur un mot de passe.
- La création et l'administration des comptes seront traitées dans un lot technique distinct avant la mise en service.

---

### US-010 — Contrôler les autorisations

**Epic :** EPIC-03  
**Priorité :** Must  
**Statut :** Ready

**Description :**

En tant que responsable de l'entreprise,  
Je veux que les actions sensibles soient réservées aux utilisateurs autorisés,  
Afin de protéger les informations et les opérations de l'entreprise.

**Valeur métier :**

Réduire les risques de modification ou de consultation non autorisée.

**Exigence liée :** EF-011.

**Critères d'acceptation :**

- CA-001 : Une opération protégée vérifie l'autorisation de l'utilisateur.
- CA-002 : Une action non autorisée est refusée.
- CA-003 : Un utilisateur non autorisé ne peut pas contourner les règles en appelant directement l'API.
- CA-004 : Une opération refusée ne modifie pas les données.
- CA-005 : Les droits s'appliquent à la consultation, à la création, à la modification et à l'annulation.

**Décisions métier validées :**

- Deux rôles métier sont retenus pour la V1 : Employé et Responsable.
- Un Responsable dispose des droits nécessaires à la supervision des utilisateurs de son entreprise.
- Les opérations de gestion des comptes seront précisées dans le lot d'administration.
- Aucun rôle ne permet d'accéder librement aux données d'une autre entreprise.

---

### US-011 — Isoler les données des entreprises

**Epic :** EPIC-03  
**Priorité :** Must  
**Statut :** Ready

**Description :**

En tant que responsable d'une entreprise utilisant ProGestion,  
Je veux que les données de mon entreprise soient séparées de celles des autres entreprises,  
Afin de garantir leur confidentialité.

**Valeur métier :**

Permettre un fonctionnement SaaS multi-entreprises sécurisé.

**Exigence liée :** EF-012.

**Critères d'acceptation :**

- CA-001 : Un utilisateur de l'entreprise A ne peut pas consulter les clients de l'entreprise B.
- CA-002 : Un utilisateur de l'entreprise A ne peut pas modifier les rendez-vous de l'entreprise B.
- CA-003 : Les recherches ne retournent que les données autorisées.
- CA-004 : La connaissance d'un identifiant de ressource ne permet pas de contourner l'isolation.
- CA-005 : Les opérations de création associent les données à la bonne entreprise.
- CA-006 : Les tests d'accès inter-entreprises non autorisés sont refusés.

**Décisions métier validées :**

- Chaque utilisateur appartient à une entreprise dans la V1.
- Chaque client et rendez-vous appartient à une entreprise.
- Les données des entreprises sont isolées logiquement.
- Les contrôles sont appliqués côté backend.

---

## 5. Vérification INVEST

INVEST permet d'évaluer la qualité d'une User Story.

### 5.1 Signification

**I — Independent :** la Story doit pouvoir être réalisée avec un minimum de dépendances inutiles.

**N — Negotiable :** les détails de réalisation peuvent être discutés sans remettre en cause la valeur métier.

**V — Valuable :** la Story apporte une valeur identifiable.

**E — Estimable :** l'équipe peut estimer l'effort nécessaire.

**S — Small :** la Story est suffisamment petite pour être réalisée et testée.

**T — Testable :** la Story possède des critères d'acceptation vérifiables.

### 5.2 Évaluation des User Stories

| User Story | I       | N   | V   | E         | S       | T   |
| ---------- | ------- | --- | --- | --------- | ------- | --- |
| US-001     | Oui     | Oui | Oui | Oui       | Oui     | Oui |
| US-002     | Oui     | Oui | Oui | Oui       | Oui     | Oui |
| US-003     | Oui     | Oui | Oui | Oui       | Oui     | Oui |
| US-004     | Partiel | Oui | Oui | Partiel   | Partiel | Oui |
| US-005     | Oui     | Oui | Oui | Oui       | Oui     | Oui |
| US-006     | Oui     | Oui | Oui | Oui       | Oui     | Oui |
| US-007     | Oui     | Oui | Oui | Oui       | Oui     | Oui |
| US-008     | Oui     | Oui | Oui | À estimer | Oui     | Oui |
| US-009     | Oui     | Oui | Oui | Oui       | Oui     | Oui |
| US-010     | Partiel | Oui | Oui | Partiel   | Partiel | Oui |
| US-011     | Partiel | Oui | Oui | Partiel   | Partiel | Oui |

### 5.3 Analyse des Stories complexes

**US-004 — Créer un rendez-vous**

Cette Story est relativement complexe car elle comprend :

- La sélection du client.
- La sélection de l'employé.
- La saisie des horaires.
- La vérification des règles métier.
- La gestion des conflits.
- La gestion des demandes simultanées.

Elle pourra être découpée en tâches techniques ou en Stories plus petites si l'estimation l'exige.

**US-010 — Contrôler les autorisations**

Cette Story est transversale.

Elle concerne plusieurs fonctionnalités.

Les contrôles devront être définis pour chaque opération protégée.

**US-011 — Isoler les données des entreprises**

Cette Story est également transversale.

Elle devra être prise en compte dès la conception des données et des API.

### 5.4 Conclusion INVEST

Le backlog est validé fonctionnellement.

Les Stories US-004, US-010 et US-011 devront faire l'objet d'un affinage technique avant leur planification détaillée.

---

## 6. Dépendances identifiées

### 6.1 Dépendances fonctionnelles

| User Story | Dépend de                            | Justification                                        |
| ---------- | ------------------------------------ | ---------------------------------------------------- |
| US-001     | US-002 ou données clients existantes | Il faut des clients à rechercher                     |
| US-003     | US-002                               | Il faut une fiche à modifier                         |
| US-004     | US-002, US-009, US-010, US-011       | Il faut un client et des accès sécurisés             |
| US-005     | US-004, US-009                       | Il faut des rendez-vous et un utilisateur identifié  |
| US-006     | US-004, US-010                       | Il faut un rendez-vous et les droits d'annulation    |
| US-007     | US-002                               | Il faut une fiche à consulter                        |
| US-008     | US-004, US-010                       | Il faut des rendez-vous et des droits de supervision |
| US-010     | US-009                               | Il faut identifier l'utilisateur                     |
| US-011     | Identification de l'entreprise       | Il faut déterminer le périmètre des données          |

### 6.2 Ordre de réalisation proposé

**Lot 1 — Fondations**

- Structure du projet.
- Identification des entreprises.
- Authentification.
- Autorisations.
- Isolation des données.

**Lot 2 — Gestion des clients**

- Création d'un client.
- Recherche d'un client.
- Consultation d'une fiche.
- Modification d'une fiche.

**Lot 3 — Gestion des rendez-vous**

- Création d'un rendez-vous.
- Vérification des conflits.
- Consultation du planning.
- Annulation d'un rendez-vous.

**Lot 4 — Qualité et livraison**

- Tests fonctionnels.
- Tests de sécurité.
- Tests de concurrence.
- Tests d'intégration.
- Documentation.
- Préparation du déploiement.

### 6.3 Dépendances techniques

Les dépendances techniques seront détaillées pendant la conception et l'architecture.

Elles concernent notamment :

- La gestion des identités.
- Le modèle de données.
- Les règles d'autorisation.
- La validation des données.
- Les contrôles de concurrence.
- La configuration des environnements.

---

## 7. Hypothèses validées et décisions de périmètre

Les hypothèses métier suivantes sont considérées comme validées pour le périmètre de référence de la V1.

| ID    | Décision validée                                                         | Statut  |
| ----- | ------------------------------------------------------------------------ | ------- |
| H-001 | Chaque utilisateur possède un compte individuel                          | Validée |
| H-002 | Chaque rendez-vous est associé à un client existant                      | Validée |
| H-003 | Un rendez-vous concerne un seul employé en V1                            | Validée |
| H-004 | Les rendez-vous confirmés d'un même employé ne peuvent pas se chevaucher | Validée |
| H-005 | L'application est accessible depuis un navigateur web                    | Validée |
| H-006 | L'importation automatique des anciens fichiers Excel est exclue de la V1 | Validée |
| H-007 | Les clients ne prennent pas directement rendez-vous dans la V1           | Validée |
| H-008 | Les notifications automatiques sont reportées à la V2                    | Validée |
| H-009 | Un rendez-vous annulé libère son créneau                                 | Validée |
| H-010 | La vue globale du planning d'équipe est reportée à la V2                 | Validée |
| H-011 | Deux rôles métier sont retenus : Employé et Responsable                  | Validée |
| H-012 | Chaque utilisateur appartient à une entreprise dans la V1                | Validée |
| H-013 | Chaque client et rendez-vous appartient à une entreprise                 | Validée |

### 7.1 Décisions complémentaires

**Gestion des clients :**

- Le nom est obligatoire.
- Le prénom est facultatif.
- Au moins un moyen de contact est obligatoire.
- Les doublons potentiels sont signalés.
- La suppression définitive est exclue de la V1.

**Gestion des rendez-vous :**

- Une date, une heure de début et une durée sont obligatoires.
- L'heure de fin doit être postérieure à l'heure de début.
- Les chevauchements confirmés sont interdits pour un même employé.
- Deux rendez-vous peuvent se suivre immédiatement.
- Une annulation libère le créneau.
- Les rendez-vous annulés restent consultables.

**Sécurité :**

- Les utilisateurs doivent être authentifiés.
- Les opérations sont soumises aux autorisations.
- Les contrôles de sécurité sont appliqués côté backend.
- Les données sont isolées entre entreprises.

### 7.2 Règle de gestion des changements

Toute évolution de ces décisions après le démarrage de la réalisation fera l'objet :

1. D'une description du changement demandé.
2. D'une analyse de son impact fonctionnel.
3. D'une estimation de son impact technique.
4. D'une décision de priorisation.
5. D'une mise à jour du backlog et des documents concernés.

---

## 8. Historique des modifications

| Version | Date       | Auteur                   | Modification                                                              | Statut    |
| ------- | ---------- | ------------------------ | ------------------------------------------------------------------------- | --------- |
| 0.1     | 22/10/2026 | Analyste fonctionnelle   | Création de la structure initiale                                         | Brouillon |
| 1.0     | 26/10/2026 | Product Owner ProGestion | Validation du périmètre, des Epics, des User Stories et des règles métier | Validé    |

---

## 9. Definition of Ready (DoR)

Une User Story peut entrer en développement lorsqu'elle respecte les conditions suivantes :

- Sa description est claire.
- Sa valeur métier est identifiée.
- Ses critères d'acceptation sont testables.
- Ses dépendances sont identifiées.
- Ses règles métier sont documentées.
- Son périmètre est compris.
- Son effort est estimé par l'équipe.
- Les conditions nécessaires à sa réalisation sont réunies.

**Décision :** la validation fonctionnelle du backlog ne remplace pas l'estimation et l'affinage nécessaires avant chaque développement.

---

## 10. Definition of Done (DoD)

Une User Story est considérée comme terminée lorsque :

- La fonctionnalité est développée.
- Les règles métier sont respectées.
- Les critères d'acceptation sont satisfaits.
- Les contrôles d'autorisation sont appliqués.
- Les tests nécessaires sont exécutés avec succès.
- Le code a été relu.
- La documentation concernée est mise à jour.
- La fonctionnalité est intégrée dans l'environnement de validation.
- Les anomalies bloquantes sont corrigées.
- Le résultat est accepté par le Product Owner.

---

## Conclusion

Le Product Backlog V1 de ProGestion est validé.

Il comprend :

- 3 Epics.
- 10 User Stories incluses dans le périmètre V1.
- 1 User Story reportée à la V2.
- Des exigences de sécurité transversales.
- Des critères d'acceptation vérifiables.
- Des dépendances fonctionnelles identifiées.
- Des décisions métier stabilisées.

Ce backlog constitue la référence fonctionnelle pour préparer la conception, les estimations et la réalisation de la V1.

**Validation métier : Responsable ProGestion / Product Owner**

**Statut final : VALIDÉ — VERSION 1.0**
