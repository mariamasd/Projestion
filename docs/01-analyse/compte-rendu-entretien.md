# ProGestion : Compte rendu d'entretien

**Projet :** ProGestion SaaS  
**Version :** 0.1  
**Date :** 26 octobre 2026  
**Statut :** Compte rendu d'entretien  
**Interlocuteur :** Responsable de l'entreprise cliente

## 1. Contexte du projet

Je suis responsable d'une petite entreprise de services qui compte actuellement 8 employés et environ 500 clients.

Notre activité consiste à proposer des prestations sur rendez-vous à des particuliers et à des professionnels.

Aujourd'hui, nous utilisons principalement des fichiers Excel, le téléphone et les e-mails pour gérer nos clients et organiser les rendez-vous.

Cette organisation fonctionnait lorsque notre entreprise était plus petite, mais elle devient difficile à gérer avec l'augmentation du nombre de clients.

Nous souhaitons donc mettre en place une application web centralisée appelée **ProGestion**.

L'objectif est de faciliter le travail quotidien de nos employés, d'améliorer le suivi de nos clients et d'éviter les erreurs de planification.

À terme, nous aimerions que cette application puisse également être utilisée par d'autres petites entreprises sous forme de logiciel SaaS.

## 2. Objectifs de l'entretien

En tant que client, je souhaite que cet entretien permette de :

- Présenter le fonctionnement actuel de notre entreprise.
- Expliquer les difficultés rencontrées par nos employés.
- Identifier les fonctionnalités indispensables.
- Définir les profils des futurs utilisateurs.
- Clarifier les règles de gestion des rendez-vous.
- Identifier les contraintes de notre activité.
- Déterminer les priorités de la première version.
- Préparer un cahier des charges fonctionnel.

Je souhaite surtout que l'équipe de développement comprenne nos problèmes avant de proposer des solutions techniques.

## 3. Participants

| Participant                 | Rôle                        | Responsabilité                                 |
| --------------------------- | --------------------------- | ---------------------------------------------- |
| Responsable de l'entreprise | Client / Responsable métier | Présenter les besoins et valider les décisions |
| Développeuse Full Stack     | Analyste fonctionnelle      | Recueillir, analyser et formaliser les besoins |
| Employé référent            | Futur utilisateur           | Expliquer le fonctionnement quotidien          |
| Responsable du projet       | Coordination                | Organiser les étapes et suivre l'avancement    |

**Remarque :** pour cet entretien pédagogique, les réponses sont principalement formulées du point de vue du responsable de l'entreprise.

## 4. Fonctionnement actuel

Actuellement, notre organisation fonctionne de la manière suivante.

### 4.1 Gestion des clients

Lorsqu'un nouveau client nous contacte, un employé récupère ses coordonnées.

Les informations sont ensuite enregistrées dans un fichier Excel.

Nous conservons généralement :

- Le nom du client.
- Son prénom.
- Son numéro de téléphone.
- Son adresse e-mail.
- Les informations nécessaires à la prestation.
- Certaines remarques utiles au suivi.

Cependant, plusieurs employés peuvent modifier les fichiers.

Il arrive donc que nous créions plusieurs fiches pour un même client.

### 4.2 Gestion des rendez-vous

Les clients prennent principalement rendez-vous par téléphone ou par e-mail.

L'employé vérifie les disponibilités dans un planning Excel.

Si le créneau semble disponible, il ajoute le rendez-vous.

Ensuite, il informe le client de la date et de l'heure retenues.

Le problème est que les plannings ne sont pas toujours actualisés immédiatement.

Deux employés peuvent parfois réserver le même créneau.

### 4.3 Consultation des informations

Lorsqu'un client nous appelle, nous devons rechercher ses informations dans les différents fichiers.

Si un employé est absent, ses collègues ne savent pas toujours où retrouver les dernières informations.

Cela entraîne des pertes de temps.

### 4.4 Organisation de l'équipe

Chaque employé possède son propre planning.

En tant que responsable, je souhaite avoir une meilleure visibilité sur l'activité de l'entreprise.

Aujourd'hui, je dois consulter plusieurs documents pour comprendre les rendez-vous programmés.

## 5. Problèmes identifiés

Pendant notre fonctionnement quotidien, nous rencontrons plusieurs difficultés.

| ID     | Problème                         | Conséquence                                        | Importance |
| ------ | -------------------------------- | -------------------------------------------------- | ---------- |
| PB-001 | Informations clients dispersées  | Perte de temps lors des recherches                 | Élevée     |
| PB-002 | Doublons dans les fiches clients | Risque d'erreurs et d'informations contradictoires | Élevée     |
| PB-003 | Conflits de rendez-vous          | Insatisfaction des clients et désorganisation      | Critique   |
| PB-004 | Absence de planning centralisé   | Difficulté à organiser le travail                  | Élevée     |
| PB-005 | Informations parfois obsolètes   | Mauvaise communication avec les clients            | Moyenne    |
| PB-006 | Gestion manuelle importante      | Perte de productivité                              | Élevée     |
| PB-007 | Droits d'accès mal définis       | Risque d'accès inapproprié aux informations        | Élevée     |

### Problème prioritaire

Pour moi, le problème le plus urgent concerne les conflits de rendez-vous.

Lorsqu'un client se présente et que deux réservations ont été effectuées au même moment pour le même employé, cela nuit directement à notre image.

Je souhaite donc que le futur système empêche les réservations incompatibles.

## 6. Besoins exprimés

Nous souhaitons disposer d'une application simple, accessible depuis un navigateur web et adaptée à notre organisation.

### BF-001 — Centraliser les informations clients

Je veux que les employés autorisés puissent retrouver les informations clients au même endroit.

Nous devons pouvoir créer, rechercher, consulter et modifier les fiches clients.

### BF-002 — Faciliter la recherche des clients

Je souhaite retrouver rapidement une fiche client à partir de son nom.

Nous pourrons étudier d'autres critères de recherche selon les besoins.

### BF-003 — Fiabiliser les rendez-vous

Je souhaite qu'un employé autorisé puisse créer un rendez-vous pour un client.

Le système doit vérifier la disponibilité du créneau et empêcher les conflits de réservation non autorisés.

### BF-004 — Consulter les plannings

Chaque employé doit pouvoir consulter les rendez-vous auxquels il est autorisé à accéder.

En tant que responsable, j'aimerais également consulter le planning global de l'équipe.

Cette dernière fonctionnalité pourra être étudiée pour une version ultérieure si elle ne rentre pas dans le périmètre de la V1.

### BF-005 — Modifier ou annuler les rendez-vous

Je souhaite que les utilisateurs autorisés puissent annuler un rendez-vous.

Nous devons également déterminer dans quelles conditions un rendez-vous peut être modifié.

### BF-006 — Sécuriser les accès

Chaque utilisateur doit disposer d'un compte personnel.

Les employés ne doivent pas pouvoir accéder à des informations sans autorisation.

Comme ProGestion pourrait être utilisé par plusieurs entreprises, les données de chaque organisation doivent être isolées.

### BF-007 — Faciliter l'utilisation

L'application doit être compréhensible par des employés qui ne sont pas informaticiens.

Nous souhaitons une interface simple, avec des formulaires clairs et des messages d'erreur faciles à comprendre.

### Priorités proposées pour la V1

| ID     | Fonctionnalité                    | Priorité |
| ------ | --------------------------------- | -------- |
| US-001 | Rechercher un client              | Must     |
| US-002 | Créer un client                   | Must     |
| US-003 | Modifier un client                | Should   |
| US-004 | Créer un rendez-vous              | Must     |
| US-005 | Consulter son planning            | Must     |
| US-006 | Annuler un rendez-vous            | Should   |
| US-007 | Consulter une fiche client        | Must     |
| US-008 | Consulter le planning de l'équipe | Could    |

L'authentification, les autorisations et l'isolation des données entre entreprises sont également indispensables.

Je préfère disposer d'une première version limitée mais fiable plutôt que d'une application contenant beaucoup de fonctionnalités incomplètes.

## 7. Hypothèses à valider

Certaines informations ont été évoquées, mais doivent encore être confirmées.

| ID    | Hypothèse                                                                  | Statut    |
| ----- | -------------------------------------------------------------------------- | --------- |
| H-001 | Chaque employé possédera un compte individuel                              | À valider |
| H-002 | Tous les rendez-vous seront associés à un client existant                  | À valider |
| H-003 | Un rendez-vous sera affecté à un seul employé dans la V1                   | À valider |
| H-004 | Deux rendez-vous confirmés d'un même employé ne pourront pas se chevaucher | À valider |
| H-005 | Les employés utiliseront principalement un ordinateur                      | À valider |
| H-006 | Les données clients existantes pourront être reprises depuis Excel         | À étudier |
| H-007 | Les clients ne prendront pas directement rendez-vous dans la V1            | À valider |
| H-008 | Les notifications automatiques seront reportées à une version ultérieure   | À valider |

Ces hypothèses ne doivent pas être considérées comme des décisions définitives.

## 8. Questions ouvertes

Avant de commencer la conception détaillée, j'aimerais que nous clarifiions plusieurs points.

### Gestion des clients

**Q-001 :** Quels champs seront obligatoires pour créer un client ?

**Q-002 :** Comment détecter et traiter les doublons ?

**Q-003 :** Un employé pourra-t-il supprimer une fiche client ?

### Gestion des rendez-vous

**Q-004 :** Quelle sera la durée minimale et maximale d'un rendez-vous ?

**Q-005 :** Les employés pourront-ils créer des rendez-vous pour leurs collègues ?

**Q-006 :** Comment gérer les horaires de travail, les pauses et les absences ?

**Q-007 :** Que se passe-t-il lorsqu'un client annule son rendez-vous ?

**Q-008 :** Un rendez-vous annulé doit-il rester visible dans l'historique ?

### Utilisateurs et sécurité

**Q-009 :** Quels droits seront attribués aux employés, responsables et administrateurs ?

**Q-010 :** Qui pourra créer et désactiver les comptes utilisateurs ?

**Q-011 :** Quelles données personnelles devons-nous conserver et pendant combien de temps ?

### Organisation du projet

**Q-012 :** Devons-nous importer les données Excel existantes dès la V1 ?

**Q-013 :** Quel budget et quel calendrier peuvent être confirmés ?

**Q-014 :** Qui sera responsable de la validation fonctionnelle ?

**Q-015 :** Quels navigateurs et appareils devront être pris en charge ?

## 9. Matrice de traçabilité

Cette matrice permet de relier les problèmes métier aux besoins, aux exigences et aux fonctionnalités prévues.

| Problème | Besoin métier | Exigence                                       | User Story            |
| -------- | ------------- | ---------------------------------------------- | --------------------- |
| PB-001   | BF-001        | EF-001 — Créer un client                       | US-002                |
| PB-001   | BF-002        | EF-002 — Rechercher un client                  | US-001                |
| PB-002   | BF-001        | EF-003 — Modifier un client                    | US-003                |
| PB-003   | BF-003        | EF-004 — Créer un rendez-vous                  | US-004                |
| PB-003   | BF-003        | EF-005 — Empêcher les conflits                 | US-004                |
| PB-004   | BF-004        | EF-006 — Consulter son planning                | US-005                |
| PB-004   | BF-004        | EF-007 — Consulter le planning d'équipe        | US-008                |
| PB-006   | BF-005        | EF-008 — Annuler un rendez-vous                | US-006                |
| PB-007   | BF-006        | ENF-001 — Contrôler les accès                  | Exigence transversale |
| PB-007   | BF-006        | ENF-002 — Isoler les données des organisations | Exigence transversale |

**Remarque :** les identifiants et les correspondances devront être harmonisés avec le catalogue d'exigences et le backlog du projet.

## 10. Prochaines étapes

À la suite de cet entretien, je souhaite que l'équipe projet réalise les actions suivantes.

### Étape 1 — Formaliser les exigences

Transformer les besoins exprimés en exigences fonctionnelles et non fonctionnelles précises.

### Étape 2 — Clarifier les règles métier

Organiser un échange complémentaire sur les conflits de réservation, les droits d'accès, les horaires et les annulations.

### Étape 3 — Valider le périmètre V1

Identifier les fonctionnalités indispensables et celles qui pourront être reportées.

### Étape 4 — Préparer le cahier des charges fonctionnel

Rédiger un document présentant les objectifs, le périmètre, les exigences, les contraintes et les critères de validation.

### Étape 5 — Préparer la modélisation

Identifier les acteurs, les cas d'utilisation et les principaux scénarios métier.

### Étape 6 — Faire valider les documents

Présenter les documents au responsable métier afin de confirmer les besoins et de corriger les éventuelles incompréhensions.

## Conclusion de l'entretien

En tant que responsable de l'entreprise, ma priorité est de disposer d'un outil fiable et facile à utiliser.

Je souhaite que ProGestion nous permette de centraliser les informations clients, de mieux organiser les rendez-vous et de réduire les erreurs quotidiennes.

Je ne cherche pas nécessairement une application contenant toutes les fonctionnalités dès le départ.

Je préfère une première version qui répond correctement à nos besoins essentiels, puis des évolutions progressives.

**Le succès de ProGestion dépendra avant tout de sa capacité à résoudre nos problèmes métier.**

---

**Fin du compte rendu**
