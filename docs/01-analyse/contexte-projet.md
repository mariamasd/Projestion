# ProGestion : Analyse initiale du besoin métier

**Projet :** ProGestion SaaS  
**Document :** Analyse fonctionnelle initiale  
**Version :** 0.1  
**Statut :** Document de travail — à valider avec le client  
**Auteur :** Analyste développeuse Full Stack

---

## 1. Contexte du projet

ProGestion est un projet d'application SaaS destiné aux petites entreprises de services souhaitant centraliser la gestion de leurs clients et de leurs rendez-vous.

Dans notre cas pratique, l'entreprise cliente compte huit employés et environ 500 clients.

Actuellement, les informations clients sont enregistrées dans plusieurs fichiers Excel, tandis que les rendez-vous sont organisés par téléphone et par messagerie.

Cette organisation rend le suivi des informations difficile et peut provoquer des erreurs, des oublis ou des conflits de réservation.

L'entreprise souhaite disposer d'un outil centralisé afin de simplifier son organisation et d'améliorer la qualité de son service.

## 2. Problématique métier

L'entreprise rencontre trois difficultés principales.

### 2.1. Problème 1 : Informations clients dispersées

Les données clients sont enregistrées dans plusieurs fichiers Excel.

**Conséquences possibles :**

- Difficulté à retrouver rapidement une fiche client.
- Risque de doublons et d'informations contradictoires.
- Perte de temps lors de la recherche d'informations.

### 2.2. Problème 2 : Gestion manuelle des rendez-vous

Les rendez-vous sont organisés par téléphone et par messagerie, sans outil centralisé.

**Conséquences possibles :**

- Risque de doubles réservations.
- Oubli de certains rendez-vous.
- Difficulté à connaître les créneaux disponibles.

### 2.3. Problème 3 : Manque de visibilité sur l'activité

La direction ne dispose pas d'une vue centralisée de l'activité.

**Conséquences possibles :**

- Difficulté à suivre le nombre de rendez-vous.
- Manque de visibilité sur la charge de travail.
- Difficulté à identifier les périodes les plus chargées.

Ces conséquences sont des hypothèses à confirmer pendant les entretiens.

## 3. Objectifs métier

| Objectif                             | Résultat attendu                                 | Indicateur de suivi                                        |
| ------------------------------------ | ------------------------------------------------ | ---------------------------------------------------------- |
| Centraliser les informations clients | Disposer d'une source commune d'informations     | Pourcentage de fiches clients enregistrées dans ProGestion |
| Améliorer la gestion des rendez-vous | Réduire les erreurs et conflits de réservation   | Nombre de conflits de réservation constatés par mois       |
| Améliorer le suivi de l'activité     | Donner aux responsables une meilleure visibilité | Temps nécessaire pour obtenir un bilan d'activité          |

Les valeurs cibles seront définies avec le client après mesure de la situation actuelle.

## 4. Identification des acteurs

| Acteur         | Rôle                             | Besoins supposés                                          |
| -------------- | -------------------------------- | --------------------------------------------------------- |
| Administrateur | Gère les accès et les paramètres | Créer des comptes et attribuer des droits                 |
| Responsable    | Supervise l'activité             | Consulter les plannings et suivre les rendez-vous         |
| Employé        | Réalise les prestations          | Consulter son planning et gérer les rendez-vous autorisés |
| Client final   | Bénéficie des prestations        | Demander, consulter ou annuler un rendez-vous             |

Les droits et les responsabilités exacts devront être confirmés avec le client.

## 5. Besoins fonctionnels pressentis

### BF-01 : Gestion des clients

L'application devra permettre aux utilisateurs autorisés de créer, consulter, modifier et rechercher des fiches clients.

### BF-02 : Gestion des rendez-vous

L'application devra permettre d'enregistrer un rendez-vous en précisant au minimum le client, la date, l'heure et l'employé concerné, sous réserve de validation des informations nécessaires.

### BF-03 : Consultation des plannings

L'application devra permettre aux utilisateurs autorisés de consulter les rendez-vous dans un calendrier ou une liste.

### BF-04 : Modification et annulation

L'application devra permettre aux utilisateurs autorisés de modifier ou d'annuler un rendez-vous selon les règles définies par l'entreprise.

### BF-05 : Gestion des utilisateurs

L'application devra permettre de gérer les comptes et les droits d'accès selon les rôles validés.

## 6. Besoins non fonctionnels pressentis

### BNF-01 : Sécurité

Les données clients devront être accessibles uniquement aux utilisateurs autorisés.

### BNF-02 : Ergonomie et accessibilité

L'interface devra être simple à utiliser sur ordinateur et sur téléphone, avec des exigences d'accessibilité à préciser.

### BNF-03 — Performance

La consultation des fiches clients et des plannings devra offrir des temps de réponse acceptables.

Les seuils de performance seront définis ultérieurement.

## 7. Règles métier à valider

### RM-01 : Conflits de réservation

Un employé ne devrait pas pouvoir avoir deux rendez-vous confirmés qui se chevauchent, sauf exception métier explicitement définie.

### RM-02 : Annulation

Seuls les utilisateurs disposant des autorisations nécessaires pourront annuler un rendez-vous.

### RM-03 — Disponibilité

Un rendez-vous ne devrait être confirmé que si l'employé concerné est disponible sur le créneau demandé.

Ces règles sont proposées pour discussion et ne sont pas encore validées.

## 8. Questions à poser au client

1. Comment gérez-vous actuellement les informations de vos clients ?
2. Comment les rendez-vous sont-ils enregistrés et confirmés ?
3. Quelles difficultés rencontrez-vous le plus souvent ?
4. Comment gérez-vous les doubles réservations ?
5. Qui utilisera l'application au quotidien ?
6. Quels utilisateurs pourront créer, modifier ou annuler un rendez-vous ?
7. Chaque employé possède-t-il son propre planning ?
8. Quelles informations clients sont indispensables ?
9. Quelles fonctionnalités sont prioritaires pour la première version ?
10. Disposez-vous d'un budget, d'un délai ou de contraintes particulières ?

## 9. Hypothèses à confirmer

- Les employés disposeront d'un compte individuel.
- Les rendez-vous seront associés à un client et à un employé.
- Les responsables pourront consulter les plannings des employés.
- L'application sera accessible depuis un navigateur web.
- Les fonctionnalités seront déployées progressivement.

Aucune de ces hypothèses ne doit être considérée comme définitivement acceptée sans validation.

## 10. Périmètre envisagé de la V1

Sous réserve de validation avec le client, la première version pourrait comprendre :

- L'authentification des utilisateurs.
- La gestion des fiches clients.
- La création et la consultation des rendez-vous.
- La modification et l'annulation des rendez-vous.
- La consultation des plannings.
- Une première gestion des rôles et des autorisations.

Les fonctionnalités de facturation, les notifications avancées et les tableaux de bord détaillés pourront être étudiés pour les versions suivantes.

## 11. Risques et points de vigilance

| Risque                            | Conséquence possible                      | Mesure envisagée                                  |
| --------------------------------- | ----------------------------------------- | ------------------------------------------------- |
| Besoins mal définis               | Développement de fonctionnalités inutiles | Organiser des entretiens et valider les exigences |
| Conflits de réservation           | Erreurs dans les plannings                | Clarifier les règles métier et prévoir des tests  |
| Mauvaise gestion des accès        | Consultation non autorisée de données     | Définir une matrice des droits                    |
| Données Excel de mauvaise qualité | Erreurs lors de la migration              | Analyser et nettoyer les données avant import     |

## 12. Prochaines étapes

1. Organiser un entretien avec le responsable de l'entreprise.
2. Interroger les futurs utilisateurs.
3. Confirmer les problèmes métier.
4. Valider les objectifs et les règles métier.
5. Prioriser les fonctionnalités de la V1.
6. Rédiger les exigences fonctionnelles détaillées.
7. Faire valider le périmètre par le client.

## 13. Conclusion

L'analyse initiale montre que ProGestion pourrait répondre à un besoin de centralisation des informations clients et de meilleure organisation des rendez-vous.

Cependant, plusieurs éléments restent à confirmer, notamment les droits des utilisateurs, les règles de réservation, les priorités et les contraintes du projet.

La prochaine étape consiste à recueillir et à valider les besoins auprès des parties prenantes avant de commencer la conception fonctionnelle et technique.
