# ProGestion SaaS

## Catalogue des exigences — V1

**Version du document :** 0.1  
**Date :** 26 octobre 2026  
**Statut :** Brouillon — À valider avec le client  
**Projet :** ProGestion SaaS  
**Type de document :** Spécification des exigences fonctionnelles et non fonctionnelles  
**Responsable de rédaction :** Analyste fonctionnelle / Développeuse Full Stack  
**Source principale :** Compte rendu d'entretien client

---

## 1. Contexte métier

### 1.1 Présentation de l'entreprise

L'entreprise cliente est une petite structure de services composée de 8 employés et disposant d'environ 500 clients.

Elle propose des prestations sur rendez-vous à des particuliers et à des professionnels.

Actuellement, l'entreprise utilise principalement :

- Des fichiers Excel pour gérer les informations clients.
- Des fichiers Excel pour organiser les rendez-vous.
- Le téléphone pour communiquer avec les clients.
- Les e-mails pour confirmer certaines informations.
- Des échanges internes entre employés pour coordonner les activités.

Cette organisation devient difficile à maintenir avec l'augmentation du nombre de clients.

### 1.2 Problèmes identifiés

| ID     | Problème                         | Conséquence                              | Priorité |
| ------ | -------------------------------- | ---------------------------------------- | -------- |
| PB-001 | Informations clients dispersées  | Perte de temps lors des recherches       | Élevée   |
| PB-002 | Doublons dans les fiches clients | Risque d'informations contradictoires    | Élevée   |
| PB-003 | Conflits de rendez-vous          | Désorganisation et insatisfaction client | Critique |
| PB-004 | Absence de planning centralisé   | Difficulté à organiser les activités     | Élevée   |
| PB-005 | Informations clients obsolètes   | Erreurs de communication                 | Moyenne  |
| PB-006 | Nombreuses opérations manuelles  | Perte de productivité                    | Élevée   |
| PB-007 | Droits d'accès mal définis       | Risque d'accès non autorisé              | Élevée   |

### 1.3 Solution envisagée

Le projet ProGestion consiste à développer une application web SaaS permettant de centraliser les informations clients et de gérer les rendez-vous.

L'application sera accessible aux utilisateurs autorisés depuis un navigateur web.

À terme, plusieurs entreprises pourront utiliser ProGestion tout en conservant une séparation stricte de leurs données.

La première version devra se concentrer sur les fonctionnalités essentielles.

---

## 2. Objectifs du projet

### 2.1 Objectif général

Développer une application web simple, fiable et sécurisée permettant aux petites entreprises de gérer leurs clients et leurs rendez-vous depuis un outil centralisé.

### 2.2 Objectifs métier

| ID      | Objectif                             | Résultat attendu                                     |
| ------- | ------------------------------------ | ---------------------------------------------------- |
| OBJ-001 | Centraliser les informations clients | Disposer d'un référentiel unique                     |
| OBJ-002 | Faciliter la recherche des clients   | Réduire le temps nécessaire pour retrouver une fiche |
| OBJ-003 | Fiabiliser les réservations          | Empêcher les conflits de rendez-vous non autorisés   |
| OBJ-004 | Améliorer l'organisation             | Permettre aux employés de consulter leur planning    |
| OBJ-005 | Sécuriser les informations           | Contrôler les accès aux données                      |
| OBJ-006 | Préparer un fonctionnement SaaS      | Isoler les données de chaque entreprise              |

### 2.3 Indicateurs de réussite proposés

| Objectif                | Indicateur                                           | Cible proposée                |
| ----------------------- | ---------------------------------------------------- | ----------------------------- |
| Recherche client        | Temps moyen de recherche                             | Réduction de 30 %             |
| Gestion des rendez-vous | Nombre de conflits confirmés non autorisés           | 0                             |
| Centralisation          | Pourcentage de fiches actives intégrées              | 100 % après migration validée |
| Sécurité                | Accès inter-entreprises non autorisés lors des tests | 0                             |
| Utilisation             | Taux d'employés formés                               | 100 % avant déploiement       |

**Important :** ces valeurs sont des propositions pédagogiques. Elles devront être confirmées avec le client et accompagnées d'une méthode de mesure.

---

## 3. Exigences fonctionnelles

Une exigence fonctionnelle décrit ce que le système doit permettre de faire.

Chaque exigence possède :

- Un identifiant unique.
- Une description claire.
- Un acteur concerné.
- Une priorité.
- Un statut de validation.

### 3.1 Gestion des clients

#### EF-001 — Créer une fiche client

**Description :** Le système doit permettre à un utilisateur autorisé de créer une fiche client dans son organisation.

**Acteur :** Employé autorisé.

**Priorité :** Must Have.

**Règles associées :**

- Le nom du client est obligatoire.
- Le prénom est facultatif pour permettre les clients professionnels.
- Au moins un moyen de contact est obligatoire.
- La fiche est associée à l'organisation de l'utilisateur.
- Les informations obligatoires doivent être vérifiées avant l'enregistrement.

**Résultat attendu :** Une nouvelle fiche client est enregistrée et devient consultable par les utilisateurs autorisés.

**Statut :** À valider.

#### EF-002 — Rechercher un client

**Description :** Le système doit permettre à un utilisateur autorisé de rechercher un client par son nom.

**Acteur :** Employé autorisé.

**Priorité :** Must Have.

**Règles associées :**

- La recherche porte uniquement sur les clients accessibles à l'utilisateur.
- Une recherche sans résultat affiche un message compréhensible.
- Les résultats présentent suffisamment d'informations pour identifier le client.

**Résultat attendu :** L'utilisateur peut retrouver une fiche client existante.

**Statut :** À valider.

#### EF-003 — Modifier une fiche client

**Description :** Le système doit permettre à un utilisateur autorisé de modifier les informations d'un client existant.

**Acteur :** Employé autorisé.

**Priorité :** Should Have.

**Règles associées :**

- Les champs obligatoires doivent rester valides.
- Les modifications doivent respecter les droits d'accès.
- Un utilisateur ne peut pas modifier une fiche appartenant à une autre organisation sans autorisation.

**Résultat attendu :** Les nouvelles informations remplacent les anciennes valeurs autorisées.

**Statut :** À valider.

#### EF-009 — Consulter une fiche client

**Description :** Le système doit permettre à un utilisateur autorisé de consulter les informations d'un client de son organisation.

**Acteur :** Employé autorisé.

**Priorité :** Must Have.

**Règles associées :**

- Seules les informations accessibles au rôle de l'utilisateur sont affichées.
- Une fiche inexistante ou inaccessible ne doit pas révéler des données confidentielles.

**Résultat attendu :** L'utilisateur peut consulter les informations nécessaires au suivi du client.

**Statut :** À valider.

### 3.2 Gestion des rendez-vous

#### EF-004 — Créer un rendez-vous

**Description :** Le système doit permettre à un utilisateur autorisé de créer un rendez-vous pour un client existant et accessible.

**Acteur :** Employé autorisé.

**Priorité :** Must Have.

**Règles associées :**

- Le client doit exister.
- Le rendez-vous doit être associé à une organisation.
- Un employé concerné doit être identifié.
- Une date, une heure de début et une durée doivent être renseignées.
- Le système doit vérifier les règles de disponibilité avant de confirmer.

**Résultat attendu :** Un rendez-vous valide est enregistré.

**Statut :** À valider.

#### EF-005 — Empêcher les conflits de rendez-vous

**Description :** Le système doit empêcher la confirmation de rendez-vous incompatibles pour un même employé.

**Acteur :** Employé autorisé.

**Priorité :** Must Have.

**Règles associées :**

- Deux rendez-vous confirmés d'un même employé ne peuvent pas se chevaucher.
- Une réservation incompatible doit être refusée.
- Le système doit afficher un message compréhensible.
- Le contrôle doit rester fiable lorsque plusieurs utilisateurs effectuent des réservations simultanément.

**Résultat attendu :** Aucun conflit de réservation interdit par les règles métier n'est confirmé.

**Statut :** À valider.

#### EF-006 — Consulter son planning

**Description :** Le système doit permettre à un employé de consulter les rendez-vous auxquels il est autorisé à accéder.

**Acteur :** Employé.

**Priorité :** Must Have.

**Règles associées :**

- Le planning présente les rendez-vous selon une période sélectionnée.
- Chaque rendez-vous affiche les informations nécessaires à son identification.
- Les informations affichées respectent les autorisations.

**Résultat attendu :** L'employé peut consulter son planning.

**Statut :** À valider.

#### EF-007 — Consulter le planning de l'équipe

**Description :** Le système pourrait permettre à un responsable autorisé de consulter les rendez-vous de son équipe.

**Acteur :** Responsable.

**Priorité :** Could Have.

**Périmètre :** Hors V1 actuelle.

**Résultat attendu :** Le responsable pourrait disposer d'une vue d'ensemble des rendez-vous autorisés.

**Statut :** Reporté — À réévaluer.

#### EF-008 — Annuler un rendez-vous

**Description :** Le système doit permettre à un utilisateur autorisé d'annuler un rendez-vous.

**Acteur :** Employé autorisé.

**Priorité :** Should Have.

**Règles associées :**

- L'utilisateur doit disposer des droits nécessaires.
- Un rendez-vous annulé ne doit plus bloquer le créneau concerné.
- L'annulation doit être visible dans l'état du rendez-vous.
- Les règles de conservation de l'historique doivent être définies.

**Résultat attendu :** Le rendez-vous passe à l'état « Annulé ».

**Statut :** À valider.

### 3.3 Authentification et autorisations

#### EF-010 — S'authentifier

**Description :** Le système doit permettre aux utilisateurs disposant d'un compte actif de s'authentifier avant d'accéder aux fonctionnalités protégées.

**Acteurs :** Employé, responsable et administrateur.

**Priorité :** Must Have.

**Résultat attendu :** Un utilisateur authentifié accède uniquement aux fonctionnalités autorisées.

**Statut :** À valider.

#### EF-011 — Contrôler les autorisations

**Description :** Le système doit vérifier les droits d'accès avant toute opération protégée.

**Acteurs :** Tous les utilisateurs.

**Priorité :** Must Have.

**Règles associées :**

- Un utilisateur ne peut pas accéder à une fonctionnalité sans autorisation.
- Les autorisations sont contrôlées côté serveur.
- Les règles d'accès sont appliquées aux opérations de lecture et de modification.

**Résultat attendu :** Les opérations non autorisées sont refusées.

**Statut :** À valider.

#### EF-012 — Isoler les données des organisations

**Description :** Le système doit garantir qu'une organisation ne peut pas accéder aux données d'une autre organisation sans autorisation explicite.

**Acteurs :** Tous les utilisateurs.

**Priorité :** Must Have.

**Résultat attendu :** Les données clients et rendez-vous sont accessibles uniquement dans le périmètre autorisé.

**Statut :** À valider.

### 3.4 Tableau récapitulatif des exigences fonctionnelles

| ID     | Exigence                             | Priorité | User Story |
| ------ | ------------------------------------ | -------- | ---------- |
| EF-001 | Créer un client                      | Must     | US-002     |
| EF-002 | Rechercher un client                 | Must     | US-001     |
| EF-003 | Modifier un client                   | Should   | US-003     |
| EF-004 | Créer un rendez-vous                 | Must     | US-004     |
| EF-005 | Empêcher les conflits                | Must     | US-004     |
| EF-006 | Consulter son planning               | Must     | US-005     |
| EF-007 | Consulter le planning d'équipe       | Could    | US-008     |
| EF-008 | Annuler un rendez-vous               | Should   | US-006     |
| EF-009 | Consulter une fiche client           | Must     | US-007     |
| EF-010 | S'authentifier                       | Must     | SEC-001    |
| EF-011 | Contrôler les autorisations          | Must     | SEC-001    |
| EF-012 | Isoler les données des organisations | Must     | SEC-002    |

---

## 4. Exigences non fonctionnelles

Une exigence non fonctionnelle décrit les qualités, contraintes de fonctionnement ou niveaux de service attendus.

### ENF-001 — Sécurité des accès

Le système doit protéger les fonctionnalités et les données contre les accès non autorisés.

**Critère de vérification proposé :** Les scénarios de tests d'autorisation doivent démontrer qu'un utilisateur ne peut pas consulter ou modifier une ressource interdite.

**Priorité :** Must Have.

### ENF-002 — Confidentialité et isolation

Les données appartenant à des organisations différentes doivent rester isolées.

**Critère de vérification proposé :** Les tests inter-organisations doivent refuser les accès non autorisés, y compris lorsque l'identifiant d'une ressource est connu.

**Priorité :** Must Have.

### ENF-003 — Performance

Les opérations courantes de consultation et de recherche doivent présenter des temps de réponse compatibles avec l'activité.

**Objectif pédagogique proposé :** 95 % des recherches simples en moins de 2 secondes, dans des conditions de charge à définir.

**Statut :** Seuil à valider avec le client.

### ENF-004 — Ergonomie

L'application doit être compréhensible par des utilisateurs non informaticiens.

**Critères proposés :**

- Les champs obligatoires sont identifiables.
- Les messages d'erreur indiquent comment corriger une saisie.
- Les principales actions sont clairement nommées.
- Les formulaires présentent une structure cohérente.

### ENF-005 — Accessibilité

Les principales fonctionnalités doivent être utilisables au clavier et présenter des libellés compréhensibles.

**Référence envisagée :** critères WCAG 2.2, niveau AA, sous réserve du périmètre d'accessibilité validé.

### ENF-006 — Disponibilité

Le service doit être accessible pendant les périodes d'utilisation convenues avec le client.

**Objectif :** taux de disponibilité à définir.

**Statut :** À valider.

### ENF-007 — Sauvegarde et restauration

Le système doit prévoir des sauvegardes des données nécessaires au fonctionnement de l'application.

Les procédures de restauration doivent pouvoir être vérifiées.

**Paramètres à définir :**

- Fréquence des sauvegardes.
- Durée de conservation.
- Perte maximale de données acceptable (RPO).
- Délai maximal de restauration acceptable (RTO).

### ENF-008 — Protection des données personnelles

Le système doit permettre la mise en œuvre des obligations applicables en matière de protection des données personnelles.

Les durées de conservation, les finalités des traitements et les modalités de gestion des droits des personnes doivent être définies avec les responsables concernés.

### ENF-009 — Compatibilité

L'application doit fonctionner sur les navigateurs et appareils retenus lors du cadrage.

**Liste des environnements :** À valider.

### ENF-010 — Maintenabilité

Le système doit pouvoir évoluer sans compromettre les fonctionnalités existantes.

**Mesures envisagées :**

- Documentation technique.
- Tests automatisés.
- Revue de code.
- Gestion des versions.
- Procédures de déploiement reproductibles.

**Remarque :** ces mesures seront précisées dans le plan qualité et les spécifications techniques.

---

## 5. Contraintes du projet

### C-001 — Architecture pédagogique

Dans le cadre du parcours de formation, le projet sera développé avec :

- React et TypeScript pour l'interface utilisateur.
- Symfony et API Platform pour les services backend.
- PostgreSQL pour le stockage des données.
- Docker pour les environnements.
- Git pour le versioning.

Ces technologies constituent des choix pédagogiques du projet et non des exigences métier exprimées par le client fictif.

### C-002 — Périmètre de la V1

La première version doit se concentrer sur la gestion des clients, des rendez-vous et des accès sécurisés.

Les fonctionnalités secondaires pourront être reportées.

### C-003 — Budget

Le budget de réalisation n'a pas encore été confirmé.

**Statut :** À définir.

### C-004 — Calendrier

Le calendrier de livraison de la V1 doit être établi à partir du périmètre validé et des estimations de réalisation.

**Statut :** À définir.

### C-005 — Reprise des données existantes

Les données clients sont actuellement conservées dans des fichiers Excel.

Une étude devra déterminer :

- Les formats disponibles.
- La qualité des données.
- La présence de doublons.
- Les règles de nettoyage.
- Les modalités d'importation.

La migration des données n'est pas automatiquement incluse dans la V1.

### C-006 — Multi-entreprises

L'application est destinée à pouvoir être utilisée par plusieurs organisations.

Chaque organisation doit disposer d'un périmètre de données isolé.

### C-007 — Validation métier

Les exigences et les règles métier doivent être revues avec un responsable habilité avant d'être considérées comme validées.

---

## 6. Règles métier

Les règles métier décrivent les conditions de fonctionnement propres à l'activité.

Elles doivent être distinguées des décisions techniques.

### RM-001 — Conflits de rendez-vous

Deux rendez-vous confirmés affectés au même employé ne peuvent pas se chevaucher.

**Exemple :**

Un rendez-vous existe de 10 h à 11 h.

Une réservation de 10 h 30 à 11 h est incompatible.

Une réservation de 11 h à 12 h pourrait être autorisée, sous réserve des autres règles de disponibilité.

**Statut :** À valider.

### RM-002 — Association à un client

Chaque rendez-vous doit être associé à un client existant et accessible dans l'organisation concernée.

**Statut :** À valider.

### RM-003 — Affectation à un employé

Chaque rendez-vous doit être affecté à un employé dans la V1.

**Statut :** À valider.

### RM-004 — Annulation

Un rendez-vous annulé ne bloque plus le créneau de l'employé concerné.

L'historique de l'annulation doit être conservé selon des règles à définir.

**Statut :** À valider.

### RM-005 — Données obligatoires d'un client

La création d'une fiche client nécessite au minimum les informations obligatoires définies par le métier.

**Proposition :** nom et au moins un moyen de contact.

**Statut :** À valider.

### RM-006 — Contrôle des autorisations

Seuls les utilisateurs autorisés peuvent créer, consulter, modifier ou annuler les données concernées.

**Statut :** À valider.

### RM-007 — Isolation des organisations

Les opérations sur les clients et les rendez-vous doivent respecter l'organisation à laquelle les données appartiennent.

**Statut :** À valider.

### RM-008 — Validité des horaires

Un rendez-vous doit posséder une heure de fin strictement postérieure à son heure de début.

Les durées minimales, maximales et les horaires autorisés restent à définir.

**Statut :** À valider.

### RM-009 — Prévention des doublons

Le système doit prévoir un mécanisme de détection ou de signalement des doublons clients.

La stratégie exacte reste à définir : avertissement, blocage ou rapprochement manuel.

**Statut :** À étudier.

---

## 7. Critères d'acceptation

Les critères d'acceptation permettent de vérifier qu'une exigence est satisfaite.

Ils doivent être précis et testables.

### CA-001 — Création d'un client

**Exigence :** EF-001.

**Étant donné** qu'un utilisateur autorisé est connecté à son organisation,

**Quand** il renseigne les informations obligatoires valides et confirme la création,

**Alors** une nouvelle fiche client est enregistrée dans son organisation,

**Et** une confirmation est présentée.

### CA-002 — Recherche d'un client

**Exigence :** EF-002.

**Étant donné** qu'un client nommé « Dupont » existe dans l'organisation de l'utilisateur,

**Quand** un utilisateur autorisé recherche « Dupont »,

**Alors** le client apparaît dans les résultats accessibles.

### CA-003 — Modification d'un client

**Exigence :** EF-003.

**Étant donné** qu'un utilisateur autorisé consulte une fiche client accessible,

**Quand** il modifie une information autorisée avec une valeur valide,

**Alors** la nouvelle information est enregistrée.

### CA-004 — Création d'un rendez-vous

**Exigence :** EF-004.

**Étant donné** qu'un utilisateur autorisé est connecté,

**Et** qu'un client accessible existe,

**Et** que le créneau demandé est disponible,

**Quand** l'utilisateur confirme une réservation valide,

**Alors** un rendez-vous est enregistré,

**Et** une confirmation est présentée.

### CA-005 — Refus d'un conflit de rendez-vous

**Exigence :** EF-005.

**Étant donné** qu'un employé possède un rendez-vous confirmé de 10 h à 11 h,

**Quand** un utilisateur tente de confirmer un autre rendez-vous de 10 h 30 à 11 h pour ce même employé,

**Alors** la nouvelle réservation est refusée,

**Et** aucun rendez-vous incompatible n'est enregistré.

### CA-006 — Consultation du planning

**Exigence :** EF-006.

**Étant donné** qu'un employé autorisé est connecté,

**Quand** il consulte son planning,

**Alors** le système affiche les rendez-vous auxquels il est autorisé à accéder.

### CA-007 — Annulation d'un rendez-vous

**Exigence :** EF-008.

**Étant donné** qu'un utilisateur autorisé consulte un rendez-vous annulable,

**Quand** il confirme son annulation,

**Alors** le rendez-vous passe à l'état « Annulé »,

**Et** le créneau n'est plus bloqué par ce rendez-vous.

### CA-008 — Accès refusé

**Exigence :** EF-011.

**Étant donné** qu'un utilisateur ne possède pas l'autorisation de modifier un client,

**Quand** il tente de modifier cette fiche,

**Alors** le système refuse l'opération,

**Et** les données restent inchangées.

### CA-009 — Isolation entre entreprises

**Exigence :** EF-012.

**Étant donné** qu'un utilisateur appartient à l'organisation A,

**Et** qu'un client appartient à l'organisation B,

**Quand** cet utilisateur tente d'accéder directement à la fiche du client B sans autorisation,

**Alors** l'accès est refusé,

**Et** aucune information confidentielle du client B n'est divulguée.

### CA-010 — Réservations simultanées

**Exigence :** EF-005.

**Étant donné** qu'un employé dispose d'un créneau libre,

**Et** que deux utilisateurs autorisés préparent des réservations incompatibles,

**Quand** les deux demandes de confirmation sont envoyées simultanément,

**Alors** le système ne confirme pas les deux réservations incompatibles,

**Et** au plus une réservation est enregistrée pour ce créneau.

### 7.1 Matrice exigences / critères d'acceptation

| Exigence | Critère d'acceptation |
| -------- | --------------------- |
| EF-001   | CA-001                |
| EF-002   | CA-002                |
| EF-003   | CA-003                |
| EF-004   | CA-004                |
| EF-005   | CA-005, CA-010        |
| EF-006   | CA-006                |
| EF-008   | CA-007                |
| EF-011   | CA-008                |
| EF-012   | CA-009                |

**Remarque :** cette matrice n'est pas encore exhaustive. Les autres exigences devront également disposer de critères d'acceptation avant leur validation définitive.

---

## 8. Hypothèses à valider

Les hypothèses correspondent aux informations supposées mais non confirmées.

| ID    | Hypothèse                                                      | Impact si incorrecte       | Statut    |
| ----- | -------------------------------------------------------------- | -------------------------- | --------- |
| H-001 | Chaque employé possède un compte individuel                    | Gestion des utilisateurs   | À valider |
| H-002 | Un rendez-vous est associé à un client existant                | Modèle métier              | À valider |
| H-003 | Un rendez-vous concerne un seul employé en V1                  | Modèle des rendez-vous     | À valider |
| H-004 | Les chevauchements sont interdits pour un même employé         | Règles de réservation      | À valider |
| H-005 | Les employés utilisent principalement un ordinateur            | Conception des interfaces  | À valider |
| H-006 | Les données Excel peuvent être reprises                        | Migration                  | À étudier |
| H-007 | Les clients ne réservent pas directement dans la V1            | Gestion des acteurs        | À valider |
| H-008 | Les notifications automatiques sont reportées                  | Périmètre V1               | À valider |
| H-009 | Un rendez-vous annulé libère immédiatement le créneau          | Gestion des disponibilités | À valider |
| H-010 | Les responsables peuvent consulter certains plannings d'équipe | Autorisations              | À valider |

### Gestion des hypothèses

Chaque hypothèse importante doit être confirmée, rejetée ou reformulée.

Lorsqu'une hypothèse est validée, les exigences concernées doivent être mises à jour si nécessaire.

---

## 9. Questions ouvertes

Les questions suivantes devront être posées au responsable métier.

### 9.1 Gestion des clients

**Q-001 :** Quels champs sont obligatoires pour créer une fiche client ?

**Q-002 :** Comment doit-on détecter les doublons ?

**Q-003 :** Les employés peuvent-ils supprimer les fiches clients ?

**Q-004 :** Faut-il distinguer les clients particuliers des clients professionnels ?

### 9.2 Gestion des rendez-vous

**Q-005 :** Quelle est la durée minimale et maximale d'un rendez-vous ?

**Q-006 :** Les rendez-vous peuvent-ils être créés en dehors des horaires habituels ?

**Q-007 :** Un employé peut-il réserver un créneau pour un collègue ?

**Q-008 :** Comment gérer les pauses, les absences et les jours non travaillés ?

**Q-009 :** Un rendez-vous peut-il être déplacé après sa création ?

**Q-010 :** Les rendez-vous annulés doivent-ils rester visibles ?

**Q-011 :** Quel fuseau horaire doit être utilisé ?

**Q-012 :** Deux rendez-vous peuvent-ils se suivre sans intervalle ?

### 9.3 Utilisateurs et sécurité

**Q-013 :** Quels rôles doivent exister dans la V1 ?

**Q-014 :** Quels droits possède chaque rôle ?

**Q-015 :** Qui peut créer ou désactiver un compte utilisateur ?

**Q-016 :** Quelles informations personnelles sont réellement nécessaires ?

**Q-017 :** Quelles durées de conservation doivent être appliquées ?

### 9.4 Organisation du projet

**Q-018 :** Quel budget est disponible ?

**Q-019 :** Quelle est la date cible de mise en service ?

**Q-020 :** La migration des données Excel est-elle obligatoire pour la V1 ?

**Q-021 :** Quels navigateurs et appareils doivent être pris en charge ?

**Q-022 :** Qui validera officiellement les exigences ?

### 9.5 Priorités de clarification

Les questions les plus urgentes concernent :

1. Les règles de conflit de rendez-vous.
2. Les autorisations des utilisateurs.
3. Les champs obligatoires des clients.
4. Les horaires et durées des rendez-vous.
5. Le périmètre réel de la V1.
6. Le calendrier et les contraintes de livraison.

Ces réponses devront être obtenues avant de figer la conception détaillée.

---

## 10. Historique des modifications

| Version | Date       | Auteur                 | Modification                           | Statut    |
| ------- | ---------- | ---------------------- | -------------------------------------- | --------- |
| 0.1     | 26/10/2026 | Analyste fonctionnelle | Création du catalogue des exigences V1 | Brouillon |

### Règles de gestion documentaire

- Toute modification importante doit être tracée.
- Les exigences validées doivent être identifiables.
- Les changements de périmètre doivent être discutés avec le responsable métier.
- Les identifiants des exigences doivent rester stables.
- Les critères d'acceptation doivent évoluer avec les exigences concernées.
- Les documents liés doivent rester cohérents.

---

## Conclusion

Ce catalogue constitue la première base structurée des exigences du projet ProGestion SaaS.

Il décrit les principales fonctionnalités attendues, les qualités du système, les contraintes, les règles métier et les critères de validation.

Il servira de référence pour :

- La rédaction et l'affinage du Product Backlog.
- La priorisation du périmètre V1.
- La modélisation UML.
- La conception fonctionnelle et technique.
- La réalisation avec React, TypeScript, Symfony et API Platform.
- La conception de la base PostgreSQL.
- La préparation des tests.
- Les évolutions futures du produit.

**Statut final du document : Brouillon à valider avec le client fictif.**

**Fin du catalogue des exigences — ProGestion SaaS V1.**
