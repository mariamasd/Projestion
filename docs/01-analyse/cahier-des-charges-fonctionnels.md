# ProGestion SaaS — Cahier des charges fonctionnel V1

**Référence :** CDCF-PROGESTION-001  
**Version :** 1.0  
**Date :** 26/10/2026  
**Statut :** VALIDÉ — Référence fonctionnelle V1  
**Entreprise cliente :** Atelier Horizon Services  
**Product Owner :** Responsable Atelier Horizon Services  
**Responsable de réalisation :** Développeuse Full Stack  
**Produit :** ProGestion SaaS

---

## 1. Présentation du projet

### 1.1 Contexte de l'entreprise

Atelier Horizon Services est une entreprise de prestations de services qui compte actuellement 8 employés et environ 500 clients.

L'entreprise reçoit des demandes de rendez-vous par téléphone et par e-mail.

Les informations clients sont enregistrées dans des fichiers Excel, tandis que les rendez-vous sont organisés dans différents plannings.

Cette organisation pose plusieurs difficultés :

- Les données clients sont dispersées.
- Certaines fiches sont enregistrées plusieurs fois.
- Les employés perdent du temps à rechercher les informations.
- Des rendez-vous peuvent être réservés sur des créneaux incompatibles.
- Les plannings ne sont pas centralisés.
- Les droits d'accès aux données ne sont pas suffisamment maîtrisés.

### 1.2 Présentation de la solution

ProGestion est une application web SaaS destinée aux petites entreprises de services.

Elle permettra de centraliser la gestion des clients et des rendez-vous.

Chaque entreprise disposera de ses propres utilisateurs et de ses propres données.

La V1 se concentrera sur trois domaines :

1. La gestion des clients.
2. La gestion des rendez-vous.
3. L'authentification et la sécurité.

### 1.3 Finalité du projet

Remplacer les fichiers Excel dispersés par une application centralisée, simple, fiable et sécurisée.

---

## 2. Objectifs du projet

### 2.1 Objectif principal

Permettre aux employés autorisés de gérer les clients et les rendez-vous de leur entreprise depuis une seule application web.

### 2.2 Objectifs métier

| ID      | Objectif                          | Résultat attendu                            |
| ------- | --------------------------------- | ------------------------------------------- |
| OBJ-001 | Centraliser les clients           | Un référentiel unique par entreprise        |
| OBJ-002 | Faciliter la recherche            | Retrouver rapidement une fiche client       |
| OBJ-003 | Fiabiliser les rendez-vous        | Aucun chevauchement interdit                |
| OBJ-004 | Améliorer l'organisation          | Chaque employé consulte son planning        |
| OBJ-005 | Maintenir les informations à jour | Les fiches clients sont modifiables         |
| OBJ-006 | Sécuriser les accès               | Les opérations non autorisées sont refusées |
| OBJ-007 | Isoler les entreprises            | Aucune fuite de données entre organisations |

### 2.3 Indicateurs de réussite

Les indicateurs suivants sont retenus pour la V1 :

- 100 % des nouvelles fiches clients sont enregistrées dans ProGestion après mise en service.
- 95 % des recherches simples répondent en moins de 2 secondes dans les conditions de test définies.
- Aucun rendez-vous confirmé incompatible n'est accepté.
- Aucun accès inter-entreprises non autorisé ne réussit lors des tests.
- Les 8 employés peuvent consulter leur planning personnel après formation.

---

## 3. Parties prenantes

| Partie prenante                      | Rôle                    | Responsabilité                                        |
| ------------------------------------ | ----------------------- | ----------------------------------------------------- |
| Responsable Atelier Horizon Services | Client / Product Owner  | Définir les priorités et accepter les fonctionnalités |
| Employés                             | Utilisateurs métier     | Gérer les clients et les rendez-vous                  |
| Développeuse Full Stack              | Réalisation             | Concevoir, développer et tester l'application         |
| Responsable technique                | Architecture et qualité | Garantir la cohérence technique et la sécurité        |

Dans le cadre de ce projet, les responsabilités de développement et d'architecture peuvent être assurées par la même personne.

---

## 4. Périmètre fonctionnel V1

### 4.1 Fonctionnalités incluses

| ID     | Fonctionnalité                     | Priorité |
| ------ | ---------------------------------- | -------- |
| US-009 | Se connecter                       | Must     |
| US-010 | Contrôler les autorisations        | Must     |
| US-011 | Isoler les données des entreprises | Must     |
| US-002 | Créer un client                    | Must     |
| US-001 | Rechercher un client               | Must     |
| US-007 | Consulter une fiche client         | Must     |
| US-004 | Créer un rendez-vous               | Must     |
| US-005 | Consulter son planning             | Must     |
| US-003 | Modifier un client                 | Should   |
| US-006 | Annuler un rendez-vous             | Should   |

Ces 10 User Stories constituent le périmètre fonctionnel retenu pour la V1.

### 4.2 Fonctionnalités exclues

| Fonctionnalité                           | Décision     |
| ---------------------------------------- | ------------ |
| Planning global de l'équipe              | Reporté V2   |
| Réservation directe par les clients      | Reportée V2  |
| Notifications SMS et e-mail automatiques | Reportées V2 |
| Facturation                              | Hors V1      |
| Paiement en ligne                        | Hors V1      |
| Statistiques avancées                    | Reportées    |
| Export CSV                               | Reporté      |
| Importation automatique Excel            | Hors V1      |
| Gestion avancée des absences             | Reportée     |
| Historique complet des prestations       | Reporté      |

### 4.3 Limites de la V1

La V1 ne constitue pas un ERP complet.

Elle ne gère ni les paiements, ni la facturation, ni les ressources matérielles.

Elle se concentre sur les clients, les rendez-vous et les accès sécurisés.

---

## 5. Utilisateurs et droits d'accès

### 5.1 Acteurs

**Employé**

Utilisateur qui gère les clients et les rendez-vous dans son entreprise.

**Responsable**

Utilisateur disposant des droits métier nécessaires pour superviser les opérations de son entreprise.

**Administrateur de plateforme**

Acteur technique chargé de l'exploitation et de la configuration de la plateforme. Il ne bénéficie pas automatiquement d'un accès libre aux données métier des entreprises.

### 5.2 Matrice des autorisations V1

| Action                                     | Employé        | Responsable    |
| ------------------------------------------ | -------------- | -------------- |
| Se connecter                               | Oui            | Oui            |
| Créer un client                            | Oui            | Oui            |
| Rechercher un client                       | Oui            | Oui            |
| Consulter une fiche client                 | Oui            | Oui            |
| Modifier un client                         | Oui            | Oui            |
| Créer un rendez-vous                       | Oui            | Oui            |
| Consulter son planning                     | Oui            | Oui            |
| Annuler un rendez-vous autorisé            | Oui            | Oui            |
| Consulter le planning global               | Non disponible | Non disponible |
| Accéder aux données d'une autre entreprise | Non            | Non            |

### 5.3 Règles d'accès

- Chaque utilisateur possède un compte individuel.
- Chaque utilisateur est rattaché à une seule entreprise dans la V1.
- Toutes les opérations protégées nécessitent une authentification.
- Les autorisations sont contrôlées côté serveur.
- Aucun utilisateur ne peut consulter ou modifier les données d'une autre entreprise.
- Un employé peut créer un rendez-vous pour un collègue de la même entreprise.
- Un employé consulte uniquement son planning personnel.
- Un employé peut annuler un rendez-vous qu'il a créé ou qui lui est affecté.
- Le responsable peut annuler tout rendez-vous de son entreprise.
- La création, l'activation et la désactivation des comptes sont réalisées par un processus d'administration interne sécurisé dans la V1.

---

## 6. Gestion des clients

### 6.1 Création d'un client — EF-001

L'utilisateur autorisé doit pouvoir créer une fiche client.

#### Données de la fiche

| Champ                      | Obligatoire  | Règle                                  |
| -------------------------- | ------------ | -------------------------------------- |
| Identifiant                | Automatique  | Unique, non modifiable                 |
| Nom                        | Oui          | Texte non vide, maximum 150 caractères |
| Prénom                     | Non          | Maximum 150 caractères                 |
| Téléphone                  | Conditionnel | Au moins un contact obligatoire        |
| E-mail                     | Conditionnel | Au moins un contact obligatoire        |
| Entreprise de rattachement | Automatique  | Déduite du contexte authentifié        |
| Date de création           | Automatique  | Enregistrée par le système             |
| Date de modification       | Automatique  | Mise à jour lors des modifications     |

Au moins un téléphone ou un e-mail doit être renseigné.

Un e-mail fourni doit respecter un format valide.

Le téléphone doit respecter les formats acceptés par l'application.

#### Déroulement

1. L'utilisateur ouvre le formulaire de création.
2. Il renseigne les informations.
3. Le système vérifie les données.
4. Le système recherche les doublons potentiels.
5. L'utilisateur confirme la création.
6. La fiche est enregistrée.
7. Une confirmation est affichée.

#### Gestion des doublons

Un doublon potentiel est signalé lorsqu'une fiche de la même entreprise possède :

- Le même e-mail normalisé ; ou
- Le même numéro de téléphone normalisé.

Le système affiche un avertissement et permet de consulter les fiches correspondantes.

L'utilisateur peut confirmer la création malgré l'avertissement.

Aucun doublon n'est supprimé ou fusionné automatiquement.

### 6.2 Recherche d'un client — EF-002

L'utilisateur peut rechercher un client par son nom.

Règles :

- La recherche accepte un nom partiel.
- Elle est insensible aux majuscules et minuscules.
- Elle est limitée à l'entreprise de l'utilisateur.
- Les résultats sont affichés dans une liste.
- Une recherche sans résultat affiche un message explicite.
- La liste est paginée lorsque le nombre de résultats est important.

### 6.3 Consultation d'une fiche — EF-009

L'utilisateur peut consulter une fiche client autorisée.

La fiche affiche :

- Nom.
- Prénom.
- Téléphone.
- E-mail.
- Date de création.
- Date de dernière modification.

Les données d'une autre entreprise ne sont jamais affichées.

### 6.4 Modification d'un client — EF-003

L'utilisateur peut modifier :

- Le nom.
- Le prénom.
- Le téléphone.
- L'e-mail.

Les règles de validation sont identiques à celles de la création.

L'identifiant et l'entreprise de rattachement ne peuvent pas être modifiés.

La suppression définitive d'un client n'est pas disponible en V1.

---

## 7. Gestion des rendez-vous

### 7.1 Création d'un rendez-vous — EF-004

L'utilisateur autorisé peut créer un rendez-vous pour un client de son entreprise.

#### Données du rendez-vous

| Champ                  | Obligatoire | Règle                                 |
| ---------------------- | ----------- | ------------------------------------- |
| Identifiant            | Automatique | Unique                                |
| Client                 | Oui         | Client existant de la même entreprise |
| Employé affecté        | Oui         | Employé actif de la même entreprise   |
| Date et heure de début | Oui         | Date future                           |
| Date et heure de fin   | Calculée    | Strictement après le début            |
| Durée                  | Oui         | 30, 60, 90 ou 120 minutes             |
| Statut                 | Automatique | Confirmé à la création                |
| Entreprise             | Automatique | Entreprise du contexte authentifié    |
| Créateur               | Automatique | Utilisateur ayant créé le rendez-vous |

#### Règles horaires

- Fuseau horaire métier : Europe/Paris.
- Les rendez-vous peuvent être créés du lundi au samedi.
- Plage autorisée : de 08 h 00 à 19 h 00.
- Aucun rendez-vous ne peut commencer avant 08 h 00.
- Aucun rendez-vous ne peut se terminer après 19 h 00.
- Les rendez-vous ne peuvent pas être créés dans le passé.
- Les rendez-vous ne peuvent pas traverser deux journées.

La gestion détaillée des congés, pauses et absences est exclue de la V1.

### 7.2 Vérification des conflits — EF-005

Deux rendez-vous confirmés affectés au même employé ne peuvent pas se chevaucher.

#### Exemple

Rendez-vous existant :

10 h 00 à 11 h 00.

| Nouveau rendez-vous | Résultat |
| ------------------- | -------- |
| 09 h 00 à 10 h 00   | Autorisé |
| 09 h 30 à 10 h 30   | Refusé   |
| 10 h 00 à 11 h 00   | Refusé   |
| 10 h 30 à 11 h 30   | Refusé   |
| 11 h 00 à 12 h 00   | Autorisé |

Deux rendez-vous de deux employés différents peuvent avoir lieu au même moment.

Le système doit également empêcher les doubles réservations incompatibles lorsque plusieurs utilisateurs confirment simultanément.

### 7.3 Consultation du planning — EF-006

Chaque employé peut consulter son planning personnel.

La V1 propose une vue journalière.

Le planning présente :

- La date.
- L'heure de début.
- L'heure de fin.
- Le nom du client.
- Le statut du rendez-vous.

L'utilisateur peut sélectionner une autre date.

Les rendez-vous annulés restent visibles avec un statut distinct.

Un jour sans rendez-vous affiche un message adapté.

### 7.4 Annulation — EF-008

Un utilisateur autorisé peut annuler un rendez-vous confirmé.

#### Déroulement

1. L'utilisateur ouvre le rendez-vous.
2. Il sélectionne « Annuler ».
3. Le système demande une confirmation.
4. L'utilisateur confirme.
5. Le rendez-vous passe au statut « Annulé ».
6. Le créneau devient disponible.
7. Le système affiche une confirmation.

Le rendez-vous n'est pas supprimé définitivement.

L'annulation conserve :

- L'identifiant du rendez-vous.
- La date et l'heure initiales.
- Le client concerné.
- L'employé affecté.
- La date d'annulation.
- L'utilisateur ayant effectué l'annulation.

Un rendez-vous déjà annulé ne peut pas être annulé une seconde fois.

La modification ou le déplacement d'un rendez-vous confirmé est exclu de la V1. Pour changer un créneau, l'utilisateur annule le rendez-vous puis en crée un nouveau.

---

## 8. Authentification et sécurité

### 8.1 Authentification — EF-010

Chaque utilisateur possède :

- Un identifiant de connexion : adresse e-mail.
- Un mot de passe.
- Un statut de compte : actif ou désactivé.
- Un rôle métier.
- Une entreprise de rattachement.

#### Fonctionnement

1. L'utilisateur accède à la page de connexion.
2. Il saisit son e-mail et son mot de passe.
3. Le système vérifie les informations.
4. Si elles sont valides et que le compte est actif, l'accès est autorisé.
5. Sinon, la connexion est refusée.

Un message d'erreur ne doit pas révéler si l'adresse e-mail existe.

L'utilisateur peut se déconnecter.

### 8.2 Autorisations — EF-011

Les droits d'accès sont vérifiés sur chaque opération protégée.

Une interface qui masque un bouton ne suffit pas à sécuriser une action.

Le backend doit refuser toute opération non autorisée.

### 8.3 Isolation des entreprises — EF-012

Chaque entreprise possède son propre périmètre de données.

Les clients et les rendez-vous sont rattachés à une entreprise.

Un utilisateur de l'entreprise A ne peut pas consulter, modifier ou annuler les ressources de l'entreprise B.

Cette règle s'applique notamment :

- Aux listes.
- Aux recherches.
- Aux consultations directes par identifiant.
- Aux créations.
- Aux modifications.
- Aux annulations.

L'identifiant de l'entreprise utilisé pour les contrôles ne doit pas être accepté aveuglément depuis les données envoyées par le navigateur.

---

## 9. Règles métier

| ID     | Règle métier                                                                 | Décision |
| ------ | ---------------------------------------------------------------------------- | -------- |
| RM-001 | Deux rendez-vous confirmés du même employé ne se chevauchent pas             | Validée  |
| RM-002 | Chaque rendez-vous est associé à un client existant                          | Validée  |
| RM-003 | Chaque rendez-vous est affecté à un employé                                  | Validée  |
| RM-004 | Un rendez-vous annulé libère son créneau                                     | Validée  |
| RM-005 | Le nom et un moyen de contact sont obligatoires pour un client               | Validée  |
| RM-006 | Seuls les utilisateurs autorisés peuvent effectuer des opérations protégées  | Validée  |
| RM-007 | Les données de deux entreprises sont isolées                                 | Validée  |
| RM-008 | L'heure de fin est strictement postérieure à l'heure de début                | Validée  |
| RM-009 | Les doublons potentiels sont signalés                                        | Validée  |
| RM-010 | Un rendez-vous commence entre 08 h et 19 h et se termine au plus tard à 19 h | Validée  |
| RM-011 | Les rendez-vous sont possibles du lundi au samedi                            | Validée  |
| RM-012 | Un rendez-vous créé possède le statut « Confirmé »                           | Validée  |
| RM-013 | Les rendez-vous annulés sont conservés                                       | Validée  |
| RM-014 | Un utilisateur appartient à une seule entreprise dans la V1                  | Validée  |
| RM-015 | Un rendez-vous ne peut pas être créé dans le passé                           | Validée  |
| RM-016 | Un rendez-vous ne peut pas traverser deux journées                           | Validée  |

---

## 10. Exigences non fonctionnelles

### ENF-001 — Performance

Dans l'environnement de recette défini pour la V1 :

- 95 % des recherches simples doivent répondre en moins de 2 secondes.
- Les principales opérations doivent fournir un retour utilisateur compréhensible.
- Les tests de performance doivent être réalisés avec un jeu de données représentatif d'au moins 500 clients par entreprise.

### ENF-002 — Sécurité

- Les communications doivent être protégées par HTTPS en production.
- Les mots de passe ne doivent jamais être stockés en clair.
- Les mots de passe doivent être protégés par un mécanisme de hachage adapté.
- Les opérations protégées doivent vérifier les autorisations.
- Les accès inter-entreprises non autorisés doivent être refusés.
- Les messages d'erreur ne doivent pas exposer d'informations sensibles.
- Les données saisies doivent être validées côté serveur.

### ENF-003 — Ergonomie

L'interface doit :

- Être claire et cohérente.
- Présenter des libellés compréhensibles.
- Identifier les champs obligatoires.
- Afficher les erreurs près des champs concernés lorsque cela est pertinent.
- Confirmer les opérations réussies.
- Demander confirmation avant une annulation.

### ENF-004 — Accessibilité

Les parcours principaux doivent être utilisables au clavier.

Les formulaires doivent comporter des libellés accessibles.

Les contrastes et les états de focus doivent être vérifiés selon les critères WCAG 2.2 niveau AA applicables au périmètre.

### ENF-005 — Compatibilité

La V1 doit être utilisable sur les versions récentes de :

- Google Chrome.
- Mozilla Firefox.
- Microsoft Edge.

L'interface doit être utilisable sur ordinateur et tablette.

### ENF-006 — Disponibilité et sauvegardes

Pour le lancement de la V1, les objectifs d'exploitation sont :

- Disponibilité mensuelle cible : 99,5 %, hors maintenance annoncée.
- Sauvegarde quotidienne des données.
- RPO cible : 24 heures.
- RTO cible : 8 heures.
- Vérification périodique de la restauration.

Ces objectifs doivent être pris en compte dans la conception de l'exploitation et testés avant mise en production.

### ENF-007 — Protection des données personnelles

Les données personnelles doivent être traitées selon les finalités définies pour ProGestion.

Le système et les procédures d'exploitation doivent permettre :

- De limiter les données collectées.
- De contrôler les accès.
- De gérer les demandes relatives aux droits des personnes.
- D'appliquer les durées de conservation prévues.
- De sécuriser les sauvegardes.

Les durées de conservation et les responsabilités de traitement seront documentées dans la politique de protection des données avant toute exploitation réelle.

### ENF-008 — Maintenabilité

Le projet doit disposer :

- D'un dépôt Git.
- D'une documentation fonctionnelle.
- D'une documentation technique.
- De tests automatisés.
- D'une procédure de déploiement.
- D'une gestion des versions.

---

## 11. Contraintes du projet

### 11.1 Contraintes fonctionnelles

- Le périmètre V1 comprend 10 User Stories.
- Les fonctionnalités hors périmètre ne sont pas nécessaires à la recette V1.
- Les règles de sécurité sont obligatoires.
- Les règles de conflit sont obligatoires.

### 11.2 Contraintes de réalisation

Les technologies retenues pour le projet sont :

| Couche          | Technologie         |
| --------------- | ------------------- |
| Frontend        | React et TypeScript |
| Backend         | Symfony             |
| API             | API Platform        |
| Base de données | PostgreSQL          |
| Environnements  | Docker              |
| Versioning      | Git                 |

Les détails d'architecture seront documentés séparément.

### 11.3 Contraintes de capacité

La priorisation MoSCoW a retenu :

| Élément                      | Unités d'effort |
| ---------------------------- | --------------: |
| Capacité totale de référence |              35 |
| Réserve pour imprévus        |               7 |
| Capacité planifiable         |              28 |
| Must Have                    |              23 |
| Should Have                  |               4 |
| Effort V1 retenu             |              27 |
| Marge de planification       |               1 |

Les unités d'effort sont des estimations relatives, et non des jours calendaires.

### 11.4 Contraintes de migration

L'importation automatique des anciens fichiers Excel est exclue de la V1.

Les nouveaux clients seront enregistrés directement dans ProGestion.

Les données historiques ne seront pas considérées comme intégralement reprises au lancement.

---

## 12. Parcours utilisateurs principaux

### 12.1 Parcours A — Créer un client

1. L'employé se connecte.
2. Il ouvre la gestion des clients.
3. Il sélectionne « Nouveau client ».
4. Il renseigne les informations.
5. Le système vérifie les champs.
6. Le système signale les éventuels doublons.
7. L'employé confirme.
8. Le client est enregistré.

**Résultat :** une nouvelle fiche client est disponible.

### 12.2 Parcours B — Rechercher un client

1. L'employé se connecte.
2. Il ouvre la liste des clients.
3. Il saisit une partie du nom.
4. Le système affiche les résultats accessibles.
5. L'employé sélectionne une fiche.

**Résultat :** la fiche client est consultable.

### 12.3 Parcours C — Créer un rendez-vous

1. L'employé se connecte.
2. Il sélectionne « Nouveau rendez-vous ».
3. Il choisit un client existant.
4. Il sélectionne l'employé concerné.
5. Il renseigne la date, l'heure et la durée.
6. Le système vérifie les règles métier.
7. Le système vérifie les conflits.
8. Si le créneau est disponible, le rendez-vous est confirmé.
9. Sinon, un message de refus est affiché.

**Résultat :** un rendez-vous valide est créé sans conflit interdit.

### 12.4 Parcours D — Consulter son planning

1. L'employé se connecte.
2. Il ouvre son planning.
3. Il sélectionne une date.
4. Le système affiche ses rendez-vous.

**Résultat :** l'employé visualise ses rendez-vous.

### 12.5 Parcours E — Annuler un rendez-vous

1. L'utilisateur autorisé ouvre un rendez-vous.
2. Il sélectionne « Annuler ».
3. Il confirme son choix.
4. Le système change le statut.
5. Le créneau est libéré.

**Résultat :** le rendez-vous reste enregistré avec le statut « Annulé ».

---

## 13. Critères d'acceptation V1

### CA-001 — Création d'un client valide

**Étant donné** un employé connecté,

**Quand** il saisit un nom et au moins un moyen de contact valide,

**Alors** le système crée la fiche dans son entreprise.

### CA-002 — Refus d'un client invalide

**Étant donné** un employé connecté,

**Quand** il tente de créer un client sans nom,

**Alors** le système refuse l'enregistrement,

**Et** affiche une erreur compréhensible.

### CA-003 — Recherche d'un client

**Étant donné** un client nommé « Dupont »,

**Quand** l'employé recherche « dup »,

**Alors** le client apparaît dans les résultats autorisés.

### CA-004 — Modification d'une fiche

**Étant donné** une fiche client accessible,

**Quand** un utilisateur autorisé modifie le téléphone avec une valeur valide,

**Alors** la nouvelle valeur est enregistrée.

### CA-005 — Création d'un rendez-vous

**Étant donné** un client existant,

**Et** un employé disponible,

**Quand** un utilisateur autorisé crée un rendez-vous valide,

**Alors** le rendez-vous est enregistré avec le statut « Confirmé ».

### CA-006 — Refus d'un chevauchement

**Étant donné** un rendez-vous confirmé de 10 h à 11 h pour un employé,

**Quand** un utilisateur tente de confirmer un rendez-vous de 10 h 30 à 11 h 30 pour ce même employé,

**Alors** la création est refusée,

**Et** aucun rendez-vous incompatible n'est enregistré.

### CA-007 — Créneaux consécutifs

**Étant donné** un rendez-vous confirmé de 10 h à 11 h,

**Quand** un utilisateur crée un rendez-vous de 11 h à 12 h pour le même employé,

**Alors** le système accepte le nouveau rendez-vous si toutes les autres règles sont respectées.

### CA-008 — Consultation du planning

**Étant donné** un employé connecté,

**Quand** il ouvre son planning,

**Alors** ses rendez-vous autorisés sont affichés.

### CA-009 — Annulation

**Étant donné** un rendez-vous confirmé,

**Quand** un utilisateur autorisé confirme son annulation,

**Alors** le rendez-vous passe au statut « Annulé »,

**Et** le créneau est libéré.

### CA-010 — Refus d'accès inter-entreprises

**Étant donné** un utilisateur de l'entreprise A,

**Quand** il tente d'accéder à une fiche client de l'entreprise B,

**Alors** l'accès est refusé,

**Et** aucune donnée confidentielle n'est divulguée.

### CA-011 — Réservations simultanées

**Étant donné** un créneau libre pour un employé,

**Quand** deux utilisateurs tentent simultanément de confirmer des rendez-vous incompatibles,

**Alors** le système n'enregistre pas deux rendez-vous confirmés incompatibles.

### CA-012 — Connexion invalide

**Étant donné** un utilisateur non authentifié,

**Quand** il fournit des identifiants incorrects,

**Alors** l'accès est refusé,

**Et** aucune session authentifiée n'est créée.

### CA-013 — Annulation répétée

**Étant donné** un rendez-vous déjà annulé,

**Quand** un utilisateur tente de l'annuler à nouveau,

**Alors** le système refuse cette opération,

**Et** le rendez-vous conserve son état.

---

## 14. Matrice de traçabilité

| Objectif | Exigence | User Story | Critère d'acceptation   |
| -------- | -------- | ---------- | ----------------------- |
| OBJ-001  | EF-001   | US-002     | CA-001, CA-002          |
| OBJ-002  | EF-002   | US-001     | CA-003                  |
| OBJ-001  | EF-009   | US-007     | CA-010 pour l'isolation |
| OBJ-005  | EF-003   | US-003     | CA-004                  |
| OBJ-003  | EF-004   | US-004     | CA-005                  |
| OBJ-003  | EF-005   | US-004     | CA-006, CA-007, CA-011  |
| OBJ-004  | EF-006   | US-005     | CA-008                  |
| OBJ-004  | EF-008   | US-006     | CA-009, CA-013          |
| OBJ-006  | EF-010   | US-009     | CA-012                  |
| OBJ-006  | EF-011   | US-010     | CA-010                  |
| OBJ-007  | EF-012   | US-011     | CA-010                  |

Les critères d'acceptation détaillés de chaque User Story restent également applicables.

---

## 15. Risques du projet

| ID    | Risque                                   | Impact   | Mesure retenue                            |
| ----- | ---------------------------------------- | -------- | ----------------------------------------- |
| R-001 | Double réservation simultanée            | Critique | Contrôle atomique et tests de concurrence |
| R-002 | Accès aux données d'une autre entreprise | Critique | Contrôles d'isolation systématiques       |
| R-003 | Erreurs dans les fiches clients          | Élevé    | Validation et signalement des doublons    |
| R-004 | Dépassement de l'effort prévu            | Élevé    | Réserve et priorisation MoSCoW            |
| R-005 | Problèmes d'intégration                  | Moyen    | Tests progressifs frontend/backend        |
| R-006 | Difficultés d'utilisation                | Moyen    | Tests des parcours métier                 |
| R-007 | Perte de données                         | Élevé    | Sauvegardes et tests de restauration      |

---

## 16. Recette fonctionnelle

### 16.1 Objectif

Vérifier que les fonctionnalités livrées répondent aux exigences du présent cahier des charges.

### 16.2 Environnement

Les tests fonctionnels seront réalisés dans un environnement de recette distinct de la production.

### 16.3 Jeux de données

La recette utilisera notamment :

- Deux entreprises distinctes.
- Plusieurs utilisateurs avec des rôles différents.
- Des clients appartenant à chaque entreprise.
- Des rendez-vous confirmés.
- Des rendez-vous annulés.
- Des créneaux disponibles et occupés.
- Des tentatives d'accès non autorisées.

### 16.4 Conditions d'acceptation

La V1 sera acceptée lorsque :

1. Les 10 User Stories retenues seront réalisées.
2. Leurs critères d'acceptation seront satisfaits.
3. Aucun défaut critique ou bloquant ne restera ouvert.
4. Les tests de conflits simultanés seront réussis.
5. Les tests d'isolation entre entreprises seront réussis.
6. Les principaux parcours seront utilisables.
7. Les exigences de sécurité obligatoires seront satisfaites.
8. Les procédures de sauvegarde et de restauration auront été vérifiées.
9. La documentation nécessaire à l'exploitation sera disponible.

### 16.5 Livrables attendus

- Application frontend.
- API backend.
- Base de données et migrations.
- Tests automatisés.
- Documentation fonctionnelle.
- Documentation technique.
- Guide de démarrage.
- Procédure de déploiement.
- Compte rendu de recette.
- Version Git identifiée pour la livraison.

---

## 17. Évolutions envisagées

### V2

Les évolutions candidates sont :

- Planning global de l'équipe.
- Réservation directe par les clients.
- Notifications automatiques.
- Gestion des absences.
- Export CSV.
- Statistiques.
- Historique complet des prestations.

### Versions ultérieures

- Facturation.
- Paiement en ligne.
- Gestion de ressources.
- Tableaux de bord avancés.
- Intégrations externes.

Ces évolutions feront l'objet de nouveaux arbitrages et de nouvelles spécifications.

---

## 18. Historique des modifications

| Version | Date       | Auteur                   | Modification                                    | Statut    |
| ------- | ---------- | ------------------------ | ----------------------------------------------- | --------- |
| 0.1     | 26/10/2026 | Analyste fonctionnelle   | Première rédaction du cahier des charges        | Brouillon |
| 1.0     | 26/10/2026 | Product Owner ProGestion | Validation du périmètre et des règles métier V1 | Validé    |

---

## 19. Validation du cahier des charges

### Décision du Product Owner

En tant que responsable d'Atelier Horizon Services et Product Owner de ProGestion, j'approuve :

- Les objectifs métier.
- Le périmètre V1.
- Les 10 User Stories retenues.
- Les fonctionnalités exclues.
- Les règles de gestion des clients.
- Les règles de gestion des rendez-vous.
- Les rôles et les autorisations.
- Les exigences de sécurité.
- Les critères d'acceptation.
- Les conditions de recette.

Le présent cahier des charges constitue la référence fonctionnelle pour la conception et le développement de ProGestion V1.

Toute modification du périmètre devra être documentée et faire l'objet d'un nouvel arbitrage.

**Décision : APPROUVÉ**

**Version de référence : 1.0**

**Statut : VALIDÉ**

---

## Conclusion

Le projet ProGestion SaaS V1 vise à fournir une application de gestion des clients et des rendez-vous fiable, sécurisée et simple d'utilisation.

Le périmètre retenu privilégie les fonctionnalités essentielles.

La V1 doit permettre de :

- Centraliser les informations clients.
- Rechercher, consulter et modifier les fiches.
- Créer des rendez-vous sans conflit interdit.
- Consulter les plannings personnels.
- Annuler les rendez-vous.
- Contrôler les accès.
- Garantir l'isolation des données entre entreprises.

Ce document servira de référence pour la modélisation UML, la conception de l'architecture, le développement, les tests et la recette.

**FIN DU CAHIER DES CHARGES FONCTIONNEL — PROGESTION SAAS V1**
