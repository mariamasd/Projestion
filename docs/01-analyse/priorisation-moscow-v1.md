# ProGestion SaaS — Priorisation MoSCoW V1

**Version du document :** 1.0  
**Date :** 26/10/2026  
**Statut :** VALIDÉ  
**Projet :** ProGestion SaaS  
**Product Owner :** Responsable ProGestion  
**Responsable de réalisation :** Développeuse Full Stack  
**Référence :** Product Backlog V1 — Version 1.0

---

## 1. Contexte du projet

ProGestion SaaS est une application web destinée aux petites entreprises de services.

Notre première entreprise utilisatrice compte 8 employés et environ 500 clients.

Actuellement, nous utilisons principalement des fichiers Excel, des appels téléphoniques et des e-mails pour gérer nos clients et nos rendez-vous.

Cette organisation entraîne plusieurs difficultés :

- Informations clients dispersées.
- Perte de temps lors des recherches.
- Doublons dans les fiches clients.
- Conflits de rendez-vous.
- Absence de planning centralisé.
- Manque de visibilité sur les activités.
- Risques liés aux accès non autorisés.

Nous souhaitons remplacer cette organisation par une application web centralisée, fiable et sécurisée.

Cependant, nous ne pouvons pas développer toutes les fonctionnalités dès la première version.

Nous devons donc définir les fonctionnalités indispensables, importantes et secondaires.

La méthode MoSCoW nous permet de prioriser le périmètre de la V1.

---

## 2. Objectifs métier

### Objectif principal

Livrer une première version de ProGestion permettant de gérer les clients et les rendez-vous sans conflits de réservation et dans un environnement sécurisé.

### Objectifs détaillés

| ID      | Objectif métier                                   | Priorité |
| ------- | ------------------------------------------------- | -------- |
| OBJ-001 | Centraliser les informations clients              | Critique |
| OBJ-002 | Rechercher rapidement un client                   | Élevée   |
| OBJ-003 | Empêcher les conflits de rendez-vous              | Critique |
| OBJ-004 | Permettre aux employés de consulter leur planning | Élevée   |
| OBJ-005 | Contrôler les accès aux données                   | Critique |
| OBJ-006 | Garantir l'isolation des entreprises              | Critique |
| OBJ-007 | Faciliter la mise à jour des informations clients | Moyenne  |
| OBJ-008 | Permettre l'annulation des rendez-vous            | Élevée   |

### Critères de réussite

La V1 sera considérée comme satisfaisante si :

- Un employé autorisé peut créer et rechercher un client.
- Un employé peut consulter les informations clients autorisées.
- Un rendez-vous valide peut être enregistré.
- Deux rendez-vous confirmés incompatibles ne peuvent pas être enregistrés pour le même employé.
- Chaque employé peut consulter son planning.
- Un utilisateur non autorisé ne peut pas accéder aux données protégées.
- Les données des différentes entreprises restent isolées.

---

## 3. Contraintes de livraison

### 3.1 Capacité disponible

Pour notre exercice de planification, nous retenons une capacité globale de **35 unités d'effort**.

Une unité d'effort représente une estimation relative de la complexité, du travail et de l'incertitude.

Elle ne correspond pas automatiquement à une journée de travail.

**Capacité totale : 35 unités.**

### 3.2 Réserve pour les imprévus

Nous conservons une réserve de 20 % afin de gérer :

- Les anomalies découvertes pendant les tests.
- Les difficultés d'intégration.
- Les ajustements nécessaires.
- Les problèmes de sécurité.
- Les imprévus techniques.

Calcul :

35 × 20 % = 7 unités.

**Réserve : 7 unités.**

### 3.3 Capacité réellement planifiable

Capacité totale : 35 unités.

Réserve : 7 unités.

Capacité planifiable : 35 - 7 = **28 unités**.

Les fonctionnalités sélectionnées pour la V1 doivent respecter cette limite.

### 3.4 Contraintes fonctionnelles

Les contraintes suivantes sont obligatoires :

- L'application doit être accessible via un navigateur web.
- Les utilisateurs doivent être authentifiés.
- Les autorisations doivent être contrôlées.
- Les données des entreprises doivent être isolées.
- Les conflits de rendez-vous doivent être empêchés.
- Les fonctionnalités livrées doivent respecter leurs critères d'acceptation.

### 3.5 Contraintes techniques

Le parcours de réalisation utilisera :

- React.
- TypeScript.
- Symfony.
- API Platform.
- PostgreSQL.
- Docker.
- Git.

Ces technologies constituent les choix techniques du projet de formation.

---

## 4. Backlog priorisé

| ID     | Fonctionnalité                     | MoSCoW | Effort | Justification                                             |
| ------ | ---------------------------------- | ------ | -----: | --------------------------------------------------------- |
| US-009 | Se connecter                       | Must   |      3 | Sécuriser l'accès à l'application                         |
| US-010 | Contrôler les autorisations        | Must   |      3 | Empêcher les opérations non autorisées                    |
| US-011 | Isoler les données des entreprises | Must   |      3 | Garantir la confidentialité SaaS                          |
| US-002 | Créer un client                    | Must   |      3 | Constituer le référentiel client                          |
| US-001 | Rechercher un client               | Must   |      2 | Retrouver rapidement les informations                     |
| US-007 | Consulter une fiche client         | Must   |      2 | Accéder aux coordonnées clients                           |
| US-004 | Créer un rendez-vous               | Must   |      5 | Fonctionnalité métier centrale et contrôle des conflits   |
| US-005 | Consulter son planning             | Must   |      2 | Organiser les rendez-vous de l'employé                    |
| US-003 | Modifier un client                 | Should |      2 | Maintenir les informations à jour                         |
| US-006 | Annuler un rendez-vous             | Should |      2 | Libérer les créneaux inutilisés                           |
| US-008 | Consulter le planning de l'équipe  | Could  |      3 | Améliorer la supervision, sans être indispensable à la V1 |

### Lecture du tableau

Les fonctionnalités Must sont indispensables au fonctionnement de la V1.

Les fonctionnalités Should sont importantes, mais peuvent faire l'objet d'un arbitrage en cas de difficulté.

Les fonctionnalités Could apportent de la valeur supplémentaire, mais ne sont pas retenues dans le périmètre de livraison actuel.

---

## 5. Fonctionnalités Must Have

Les fonctionnalités Must Have sont celles sans lesquelles la V1 ne répondrait pas correctement à nos besoins essentiels.

### Liste des Must Have

| ID        | Fonctionnalité                     | Effort |
| --------- | ---------------------------------- | -----: |
| US-009    | Se connecter                       |      3 |
| US-010    | Contrôler les autorisations        |      3 |
| US-011    | Isoler les données des entreprises |      3 |
| US-002    | Créer un client                    |      3 |
| US-001    | Rechercher un client               |      2 |
| US-007    | Consulter une fiche client         |      2 |
| US-004    | Créer un rendez-vous               |      5 |
| US-005    | Consulter son planning             |      2 |
| **TOTAL** |                                    | **23** |

### Justification métier

**Authentification et sécurité**

L'application manipule des informations clients.

Nous devons empêcher les accès non autorisés et protéger les données des entreprises.

**Gestion des clients**

Les employés doivent pouvoir créer, rechercher et consulter les fiches clients.

Sans ces fonctionnalités, la centralisation n'apporte pas suffisamment de valeur.

**Gestion des rendez-vous**

La création des rendez-vous et la prévention des conflits constituent le besoin principal de notre entreprise.

**Consultation du planning**

Un rendez-vous enregistré doit pouvoir être retrouvé facilement par l'employé concerné.

### Décision du Product Owner

Les 8 fonctionnalités Must sont obligatoires pour la livraison de la V1.

---

## 6. Fonctionnalités Should Have

Les fonctionnalités Should Have apportent une valeur importante, mais ne sont pas aussi critiques que les Must.

| ID        | Fonctionnalité         | Effort |
| --------- | ---------------------- | -----: |
| US-003    | Modifier un client     |      2 |
| US-006    | Annuler un rendez-vous |      2 |
| **TOTAL** |                        |  **4** |

### US-003 — Modifier un client

Cette fonctionnalité permet de corriger les coordonnées et de maintenir les informations clients à jour.

Sans elle, les employés devraient utiliser une procédure manuelle pour corriger certaines données.

Elle reste donc importante pour la qualité du service.

### US-006 — Annuler un rendez-vous

Cette fonctionnalité permet de libérer un créneau lorsqu'une prestation n'a plus lieu.

Elle contribue directement à la fiabilité du planning.

### Décision du Product Owner

Les deux fonctionnalités Should sont incluses dans la V1, car elles apportent une valeur importante et leur effort estimé reste compatible avec la capacité disponible.

En cas de dépassement important, elles pourront faire l'objet d'un nouvel arbitrage.

---

## 7. Fonctionnalités Could Have

Les fonctionnalités Could Have sont utiles, mais ne sont pas indispensables au fonctionnement de la V1.

| ID        | Fonctionnalité                    | Effort |
| --------- | --------------------------------- | -----: |
| US-008    | Consulter le planning de l'équipe |      3 |
| **TOTAL** |                                   |  **3** |

### US-008 — Consulter le planning de l'équipe

Cette fonctionnalité permettrait au responsable de visualiser les rendez-vous de tous les employés de son équipe.

Elle faciliterait l'organisation globale.

Cependant, les employés peuvent déjà consulter leur propre planning.

Cette fonctionnalité n'est donc pas indispensable pour lancer la V1.

### Décision du Product Owner

US-008 est reportée à la V2.

Elle n'est pas incluse dans les 27 unités d'effort retenues pour la V1.

---

## 8. Fonctionnalités Won't Have

Les fonctionnalités Won't Have sont explicitement exclues du périmètre V1.

Elles pourront être réétudiées pour une version ultérieure.

| ID     | Fonctionnalité                             | Justification                                           |
| ------ | ------------------------------------------ | ------------------------------------------------------- |
| WH-001 | Notifications automatiques par SMS         | Coûts et complexité supplémentaires                     |
| WH-002 | Notifications automatiques par e-mail      | Non indispensable au fonctionnement initial             |
| WH-003 | Réservation directe par les clients        | Nécessite un parcours public supplémentaire             |
| WH-004 | Facturation                                | Hors objectif principal de la V1                        |
| WH-005 | Paiement en ligne                          | Nécessite une gestion financière et des intégrations    |
| WH-006 | Statistiques avancées                      | Valeur secondaire pour le lancement                     |
| WH-007 | Export CSV                                 | Non indispensable au périmètre initial                  |
| WH-008 | Importation automatique des fichiers Excel | Nécessite un chantier spécifique de reprise des données |
| WH-009 | Gestion avancée des absences               | Reportée pour limiter la complexité                     |
| WH-010 | Historique complet des prestations         | Reporté à une version ultérieure                        |

### Décision du Product Owner

Aucune fonctionnalité Won't Have ne sera développée dans la V1.

Ces fonctionnalités ne seront réintroduites que dans le cadre d'une nouvelle priorisation.

---

## 9. Calcul de la capacité

### 9.1 Capacité totale

35 unités d'effort.

### 9.2 Réserve

7 unités d'effort.

### 9.3 Capacité planifiable

35 - 7 = 28 unités.

### 9.4 Effort des Must Have

3 + 3 + 3 + 3 + 2 + 2 + 5 + 2 = **23 unités**.

### 9.5 Effort des Should Have

2 + 2 = **4 unités**.

### 9.6 Effort total de la V1

23 + 4 = **27 unités**.

### 9.7 Capacité restante

28 - 27 = **1 unité**.

### 9.8 Bilan

| Élément                         | Effort |
| ------------------------------- | -----: |
| Capacité totale                 |     35 |
| Réserve imprévus                |      7 |
| Capacité planifiable            |     28 |
| Must Have                       |     23 |
| Should Have                     |      4 |
| Effort V1 retenu                |     27 |
| Marge de planification restante |      1 |
| Could Have reportés             |      3 |

### Conclusion

La V1 respecte la capacité disponible.

L'effort planifié est de 27 unités sur 28.

La réserve de 7 unités est conservée pour les imprévus.

La marge de planification restante est de 1 unité.

La capacité globale non affectée directement aux fonctionnalités est donc de 8 unités, dont 7 réservées aux imprévus.

---

## 10. Périmètre proposé pour la V1

### Périmètre fonctionnel retenu

La V1 comprend les fonctionnalités suivantes :

**Sécurité :**

- US-009 — Se connecter.
- US-010 — Contrôler les autorisations.
- US-011 — Isoler les données des entreprises.

**Gestion des clients :**

- US-002 — Créer un client.
- US-001 — Rechercher un client.
- US-007 — Consulter une fiche client.
- US-003 — Modifier un client.

**Gestion des rendez-vous :**

- US-004 — Créer un rendez-vous.
- US-005 — Consulter son planning.
- US-006 — Annuler un rendez-vous.

### Résultat attendu

À la fin de la V1, un employé autorisé pourra :

1. Se connecter à ProGestion.
2. Créer une fiche client.
3. Rechercher un client.
4. Consulter ses informations.
5. Modifier ses coordonnées.
6. Créer un rendez-vous.
7. Consulter son planning.
8. Annuler un rendez-vous.

Le système devra également empêcher les conflits de réservation interdits et garantir l'isolation des données.

### Décision du Product Owner

Le périmètre V1 est validé pour un effort estimé de 27 unités.

---

## 11. Fonctionnalités reportées

Les fonctionnalités suivantes ne seront pas développées pendant la V1.

| Fonctionnalité                      | Version envisagée  | Motif                          |
| ----------------------------------- | ------------------ | ------------------------------ |
| Planning global de l'équipe         | V2                 | Non indispensable au lancement |
| Notifications automatiques          | V2                 | Complexité et coûts            |
| Réservation directe par les clients | V2                 | Nouveau parcours utilisateur   |
| Facturation                         | Version ultérieure | Hors périmètre                 |
| Paiement en ligne                   | Version ultérieure | Intégrations supplémentaires   |
| Statistiques avancées               | V2                 | Priorité secondaire            |
| Export CSV                          | V2                 | Non indispensable              |
| Importation automatique Excel       | À replanifier      | Chantier spécifique            |
| Gestion avancée des absences        | V2                 | Complexité supplémentaire      |

Le report d'une fonctionnalité ne signifie pas qu'elle sera automatiquement développée en V2.

Elle devra être réévaluée selon les besoins et les moyens disponibles.

---

## 12. Risques et dépendances

### 12.1 Risques identifiés

| ID    | Risque                                     | Impact | Mesure prévue                          |
| ----- | ------------------------------------------ | ------ | -------------------------------------- |
| R-001 | Sous-estimation de la sécurité             | Élevé  | Prévoir des tests d'autorisation       |
| R-002 | Complexité des conflits de rendez-vous     | Élevé  | Définir précisément les règles métier  |
| R-003 | Réservations simultanées                   | Élevé  | Prévoir des tests de concurrence       |
| R-004 | Dépassement de capacité                    | Élevé  | Conserver la réserve de 7 unités       |
| R-005 | Problèmes de qualité des données           | Moyen  | Valider les données saisies            |
| R-006 | Difficultés d'intégration frontend/backend | Moyen  | Réaliser des intégrations progressives |
| R-007 | Retard de développement                    | Moyen  | Prioriser les Must Have                |

### 12.2 Dépendances fonctionnelles

| Fonctionnalité              | Dépendance                              |
| --------------------------- | --------------------------------------- |
| Rechercher un client        | Disposer de données clients             |
| Modifier un client          | Disposer d'une fiche client             |
| Créer un rendez-vous        | Disposer d'un client et d'un employé    |
| Consulter son planning      | Disposer de rendez-vous                 |
| Annuler un rendez-vous      | Disposer d'un rendez-vous existant      |
| Contrôler les autorisations | Identifier l'utilisateur                |
| Isoler les données          | Identifier l'entreprise de rattachement |

### 12.3 Ordre de réalisation

**Lot 1 — Sécurité et fondations**

- Authentification.
- Autorisations.
- Isolation des données.

**Lot 2 — Gestion des clients**

- Création.
- Recherche.
- Consultation.
- Modification.

**Lot 3 — Gestion des rendez-vous**

- Création.
- Vérification des conflits.
- Consultation du planning.
- Annulation.

**Lot 4 — Tests et livraison**

- Tests fonctionnels.
- Tests de sécurité.
- Tests de concurrence.
- Corrections.
- Documentation.
- Déploiement.

---

## 13. Questions à valider avec le client

### 13.1 Décisions métier confirmées

En tant que Product Owner, je confirme les décisions suivantes :

| Question                                                 | Décision                                               |
| -------------------------------------------------------- | ------------------------------------------------------ |
| Les employés doivent-ils se connecter ?                  | Oui                                                    |
| Chaque employé possède-t-il un compte individuel ?       | Oui                                                    |
| Un rendez-vous est-il associé à un client ?              | Oui                                                    |
| Un rendez-vous est-il affecté à un seul employé ?        | Oui, en V1                                             |
| Les chevauchements sont-ils autorisés ?                  | Non, pour un même employé et des rendez-vous confirmés |
| Peut-on annuler un rendez-vous ?                         | Oui                                                    |
| L'annulation libère-t-elle le créneau ?                  | Oui                                                    |
| Les données des entreprises doivent-elles être isolées ? | Oui                                                    |
| Les clients peuvent-ils réserver directement ?           | Non, pas en V1                                         |
| Les notifications sont-elles incluses ?                  | Non                                                    |
| Le planning global est-il inclus ?                       | Non, reporté à la V2                                   |

### 13.2 Questions restantes

Aucune question de priorisation métier ne bloque le périmètre V1.

Les décisions de conception technique, les estimations détaillées et l'organisation des livraisons seront traitées dans les phases suivantes.

### Statut

Arbitrages métier validés par le Product Owner.

---

## 14. Décisions d'arbitrage

### DEC-001 — Report des notifications

**Contexte :**

Les notifications automatiques peuvent améliorer la communication avec les clients, mais elles nécessitent des fonctionnalités et des intégrations supplémentaires.

**Décision :**

Les notifications SMS et e-mail sont exclues de la V1.

**Justification :**

La priorité est de fiabiliser la gestion des clients et des rendez-vous.

**Conséquences :**

Les confirmations et changements de rendez-vous devront être communiqués aux clients par les moyens habituels de l'entreprise.

**Statut :** Validé.

---

### DEC-002 — Report du planning global

**Contexte :**

Le responsable souhaite consulter les plannings de toute son équipe.

**Décision :**

La fonctionnalité US-008 est reportée à la V2.

**Justification :**

La consultation du planning individuel suffit pour répondre aux besoins essentiels du lancement.

**Conséquences :**

Le responsable ne disposera pas d'une vue consolidée de l'équipe en V1.

**Statut :** Validé.

---

### DEC-003 — Inclusion de la modification des clients

**Contexte :**

Les coordonnées clients peuvent changer régulièrement.

**Décision :**

US-003 est incluse dans la V1.

**Justification :**

Une application de gestion des clients doit permettre de corriger les informations existantes.

**Conséquences :**

2 unités d'effort sont allouées à cette fonctionnalité.

**Statut :** Validé.

---

### DEC-004 — Inclusion de l'annulation des rendez-vous

**Contexte :**

Les clients peuvent annuler leurs prestations.

**Décision :**

US-006 est incluse dans la V1.

**Justification :**

L'annulation permet de maintenir un planning fiable et de libérer les créneaux.

**Conséquences :**

2 unités d'effort sont allouées à cette fonctionnalité.

**Statut :** Validé.

---

### DEC-005 — Sécurité obligatoire

**Contexte :**

ProGestion est une application SaaS destinée à plusieurs entreprises.

**Décision :**

L'authentification, les autorisations et l'isolation des données sont obligatoires dès la V1.

**Justification :**

La confidentialité et la protection des données ne peuvent pas être reportées.

**Conséquences :**

9 unités d'effort sont allouées aux fonctionnalités de sécurité du backlog.

**Statut :** Validé.

---

### DEC-006 — Conservation de la réserve

**Contexte :**

Le développement peut rencontrer des imprévus.

**Décision :**

Une réserve de 7 unités est conservée.

**Justification :**

Elle permet de limiter les risques de dépassement et de traiter les difficultés imprévues.

**Conséquences :**

La capacité planifiable est limitée à 28 unités.

**Statut :** Validé.

---

### DEC-007 — Validation du périmètre V1

**Contexte :**

Le backlog contient des fonctionnalités indispensables, importantes et secondaires.

**Décision :**

La V1 comprend les 8 Must Have et les 2 Should Have.

**Justification :**

Cet ensemble couvre les besoins métier prioritaires tout en respectant la capacité planifiable.

**Conséquences :**

- 10 User Stories retenues.
- 27 unités d'effort planifiées.
- 7 unités réservées aux imprévus.
- 1 unité de marge de planification.
- Les Could Have et Won't Have sont exclus du périmètre.

**Statut :** Validé.

---

## 15. Historique des modifications

| Version | Date       | Auteur                   | Modification                                                | Statut    |
| ------- | ---------- | ------------------------ | ----------------------------------------------------------- | --------- |
| 0.1     | 23/10/2026 | Analyste fonctionnelle   | Création de la structure du document                        | Brouillon |
| 1.0     | 26/10/2026 | Product Owner ProGestion | Validation des priorités, de la capacité et du périmètre V1 | Validé    |

---

## Conclusion

La méthode MoSCoW a permis de définir un périmètre réaliste pour la première version de ProGestion SaaS.

### Bilan final

- Capacité totale : 35 unités.
- Réserve pour imprévus : 7 unités.
- Capacité planifiable : 28 unités.
- Must Have : 23 unités.
- Should Have : 4 unités.
- Effort total V1 : 27 unités.
- Marge de planification : 1 unité.

Le périmètre retenu permet de répondre aux besoins essentiels de gestion des clients et des rendez-vous tout en intégrant les exigences de sécurité.

Les fonctionnalités secondaires sont reportées afin de maîtriser la complexité et de concentrer les efforts sur la qualité de la première version.

**Décision finale du Product Owner : PÉRIMÈTRE V1 VALIDÉ.**

**Fin du document — ProGestion SaaS — Priorisation MoSCoW V1**
