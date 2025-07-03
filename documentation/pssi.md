# **POLITIQUE DE SECURITE DES SYSTEMES D’INFORMATION ( PSSI )**

---

# **Sommaire**

1. Introduction
2. Gouvernance de la sécurité
3. Gestion des ressources
4. Sécurité humaine
5. Sécurité physique et environnementale
6. Sécurité logique et technique
7. Sécurité des communications
8. Analyse des risques
9. Gestion des incidents
10. Continuité d’activité
11. Conformité
12. Évolution de la PSSI

---

# **1. Introduction**

La PSSI (Politique de Sécurité des Systèmes d’Information) est indispensable dans un établissement médicale comme nôtre CHU en raison de la nature sensible des données de santé quelle héberge.

Les **données médicales** sont considérées comme **sensibles** par le RGPD et la législation française, leur collecte, stockage, traitement et transfert doivent faire l’objet de mesures de sécurité renforcées.

La présente politique a pour but de garantir la **confidentialité**, **intégrité**, **disponibilité** et **traçabilité**des données manipulées au sein de notre CHU. 

Cette politique s’applique à l’ensemble des employés, prestataires, utilisateurs temporaires, applications et réseaux du CHU ayant accès, direct ou indirect, au système d’information.

Elle est rédigée et maintenue à jour par le Responsable de la Sécurité des Systèmes d’Information (RSSI).

Références réglementaires et normatives :
- **ISO 27001** : Norme internationale pour la mise en œuvre d’un SMSI.
- **ISO 27799** : Application au domaine des données de santé personnelles.
- **RGPD** : Règlement général sur la protection des données (UE).
- **Code de la santé publique** : Textes législatifs et réglementaires français régissant le domaine de la santé.

---

# **2. Gouvernance de la sécurité**

## Rôles et responsabilités

**Le RSSI (Responsable de la Sécurité des Systèmes d’Information)** :
- Pilote la politique de sécurité du SI au sein du CHU.
- Évalue les risques et propose des mesures de sécurité adaptées.
- Coordonne les actions de sécurité avec les équipes techniques et les métiers.
- Assure la veille réglementaire et technologique.
- Supervise les audits, les tests d’intrusion, et les incidents de sécurité.

**Direction Générale** :
- Valide et soutient la stratégie de sécurité du SI.
- Alloue les ressources humaines et financières nécessaires.
- Intègre les enjeux de cybersécurité dans la gouvernance globale de l’établissement.
- Garantit la conformité avec la réglementation.

**Équipe IT (DSI, admin, techniciens)** :
- Implémente les solutions techniques de sécurité.
- Gère les comptes utilisateurs, les droits d’accès, les sauvegardes, la maintenance.
- Applique les procédures de sécurité établies.
- Réagit aux alertes et incidents en coordination avec le RSSI.

**Utilisateurs** :
- Respectent les règles définies dans la charte informatique.
- Signalent toute activité suspecte ou anomalie au support.
- Participent aux actions de sensibilisation et de formation.
- Utilisent les outils numériques dans le respect des bonnes pratiques.

## Organisation de la sécurité

Le **comité de sécurité**, composé du **RSSI**, du **DSI** et de la **direction générale**, est une instance de pilotage stratégique et opérationnelle de la sécurité du système d’information.

Il se réunit régulièrement pour :
- Suivre les plans d’actions de sécurité,
- Analyser les incidents majeurs,
- Valider les choix technologiques sensibles,
- Prioriser les investissements en cybersécurité.

| **Processus**                        | **Objectif**                                                                |
| ------------------------------------ | --------------------------------------------------------------------------- |
| Pilotage de la sécurité              | Définir les priorités, suivre les projets SSI, mesurer les indicateurs clés |
| Audit de sécurité interne et externe | Évaluer la conformité, détecter les vulnérabilités, vérifier les pratiques  |
| Revue périodique de la PSSI          | Adapter les règles de sécurité à l’évolution des menaces et du contexte     |
| Revue des droits d’accès             | Vérifier régulièrement les accès aux applications et aux données sensibles  |
| Gestion des incidents                | Identifier, traiter et documenter les incidents de sécurité                 |

---

# **3. Gestion des ressources**

La gestion rigoureuse des ressources est essentielle pour garantir la sécurité du SI de nôtre CHU. 
Cela inclut la classification, la propriété et le suivi des actifs matériels, logiciels et informationnels.

## Classification des actifs

### Actifs matériels

| Actif                  | Exemple                     | Sensibilité | Criticité | Remarques                            |
| ---------------------- | --------------------------- | ----------- | --------- | ------------------------------------ |
| Serveurs physiques     | Serveur LDAP, web, base DPI | Élevée      | Critique  | Hébergent des données vitales        |
| Postes de travail      | PC administratif, médical   | Moyenne     | Élevée    | Accès aux données patient            |
| Équipements réseau     | Pare-feu, switch, routeur   | Élevée      | Critique  | Élément essentiel à la connectivité  |
| Matériel de sauvegarde | Serveurs de backup          | Élevée      | Critique  | Protection contre perte de données   |
| Imprimantes/Scanner    | Périphériques réseau        | Faible      | Moyenne   | Peuvent stocker des traces sensibles |

### Actifs logiciels

| Actif                   | Exemple                             | Sensibilité | Criticité | Remarques                               |
| ----------------------- | ----------------------------------- | ----------- | --------- | --------------------------------------- |
| Systèmes d’exploitation | Debian, Windows                     | Élevée      | Critique  | Cible fréquente                         |
| Logiciel médical        | DPI, DMP, imagerie, prescription    | Élevée      | Critique  | Contient des données de santé sensibles |
| Logiciel administratif  | Messagerie, dossier paratgé         | Moyenne     | Élevée    | Données RH, financières                 |
| Services réseau         | DNS, DHCP, LDAP, Mail, SIEM         | Élevée      | Critique  | Essentiels au bon fonctionnement du SI  |
| Logiciels de sécurité   | IDS/IPS, antivirus, pare-feu, Wazuh | Élevée      | Critique  | Protection et surveillance du SI        |
| Outils de sauvegarde    | rsync, Bacula                       | Élevée      | Critique  | Sauvegarde/restauration de données      |

### Actifs informationnels

| Type de données          | Exemple                            | Sensibilité | Criticité | Remarques                                 |
| ------------------------ | ---------------------------------- | ----------- | --------- | ----------------------------------------- |
| Données de santé         | DPI, DPM                           | Très élevée | Critique  | Données personnelles sensibles (RGPD)     |
| Données personnelles     | Identité des employés, patients    | Élevée      | Critique  | RGPD, confidentialité                     |
| Données administratives  | Données RH, financières            | Moyenne     | Élevée    | Données stratégiques internes             |
| Logs système et réseau   | Journaux, tentatives de connexions | Moyenne     | Moyenne   | Traçabilité                               |
| Données de configuration | Fichiers de configuration          | Élevée      | Élevée    | Nécessaires à la restauration             |
| Clés cryptographiques    | Certificats TLS, clés RSA          | Très élevée | Critique  | Doivent être stockées de manière sécurisé |

## Propriété des actifs

Chaque actif du système d’information doit être attribué à un propriétaire clairement identifié.

Le propriétaire est responsable de :
- La définition du niveau de sécurité requis,
- La gestion des droits d’accès,
- La conformité aux politiques internes et réglementaires,
- La mise à jour et la maintenance de l’actif.

## Inventaire et suivi des ressources

Un inventaire centralisé et à jour des actifs est tenu par la DSI en coordination avec le RSSI.

et inventaire vise à recenser l’ensemble des ressources physiques et logicielles utilisées au sein du CHU. 
Il doit inclure au minimum :
- Le nom de l’actif
- Son type
- Sa localisation
- Son propriétaire
- Sa classification 
- La date d’ajout ou de dernière modification.

L’accès à cet inventaire est restreint aux personnes habilitées. 
Des revues périodiques sont réalisées afin de garantir sa fiabilité, sa complétude et sa mise à jour continue.


---

# **4. Sécurité humaine**

La sécurité des systèmes d'information repose autant sur les comportements humains que sur les dispositifs techniques. 
La sensibilisation, la responsabilisation et la gestion rigoureuse des accès sont essentielles dans un environnement hospitalier manipulant des données de santé sensibles.

## Sensibilisation du personnel

Le CHU met en place un programme de sensibilisation à la sécurité informatique à destination de l’ensemble des utilisateurs ayant pour objectif de renforcer la culture de la sécurité, réduire les risques d'erreur humaine et garantir le respect des bonnes pratiques.

Les modalités sont les suivantes :
- Formation obligatoire à l’arrivée
- Sessions régulières de rappel
- Communication interne
- Mise en situation

## Charte informatique

Chaque utilisateur du système d’information du CHU doit lire et signer une charte informatique définissant ses droits, devoirs et responsabilités.
Cette charte précise :
- Les règles d’utilisation des équipements informatiques et réseaux
- Les restrictions liées aux données sensibles
- Les comportements interdits
- Les sanctions en cas de non-respect.

La signature de la charte conditionne la création d’un compte utilisateur. 
Un exemplaire est conservé par le DSI.

## Gestion des habilitations

Les accès aux ressources du SI sont strictement encadrés par un processus de gestion des habilitations basé sur les rôles et responsabilités.

**Création de comptes** :
- Demande écrite validée par un responsable
- Autorisée uniquement si la charte est signée
- Réalisée par l’équipe IT, avec un niveau d’accès minimal nécessaire au poste

**Droits d’accès** :
- Attribués selon le principe du moindre privilège
- Évolutifs selon le changement de fonction ou les besoins ponctuels
- Réévalués régulièrement

**Suppression de comptes** :
- Automatique en cas de départ d’un utilisateur
- Supprimée ou désactivée sans délai par la DSI

---

# **5. Sécurité physique et environnementale**

La sécurité du système d'information repose également sur la protection physique des infrastructures et des équipements informatiques. 
Un accès non autorisé à un local ou à un matériel peut compromettre la confidentialité, l’intégrité ou la disponibilité des données de santé.

## Contrôle d'accès aux locaux

**L’accès aux locaux sensibles est strictement limité et contrôlé**.

Moyens mis en place pour contrôler les accès :
- Accès réservé aux personnels habilités
- Badges nominatifs avec droits d’accès paramétrés
- Contrôle d’accès électronique
- Journalisation des accès physiques

Tout accès non autorisé ou tentative d’intrusion doit être immédiatement signalé au RSSI et à la direction.

## Protection des équipements

Les équipements informatiques doivent être protégés contre tout dommage, vol ou accès non autorisé.

Les équipements informatiques critiques sont hébergés dans des locaux physiquement sécurisés, avec accès restreint, vidéosurveillance, alimentation électrique de secoure et systèmes de détection d’incendie. 

Les postes de travail sont configurés pour se verrouiller automatiquement après quelques minutes d’inactivité, réduisant ainsi les risques de compromission en cas d’absence temporaire du personnel.

Les dispositifs médicaux connectés sont stockés dans des armoires fermées à clé lorsqu’ils ne sont pas utilisés.

## Surveillance

Des dispositifs de surveillance physique et d’alerte sont déployés dans les zones critiques.

Éléments de sécurité installés :
- Systèmes d’alarme anti-intrusion et anti-incendie
- Caméras de vidéosurveillance
- Badges personnalisés avec contrôle de présence
- Détecteurs de fumée et systèmes de détection d’eau

Les événements détectés par ces systèmes sont enregistrés, consultables en cas d’incident, et analysés régulièrement par l’équipe de sécurité.

Tout visiteur ou prestataire doit être accompagné, inscrit dans un registre et muni d’un badge visiteur.

---

# **6. Sécurité logique et technique**

La sécurité logique vise à protéger les systèmes, applications, réseaux et données contre les accès non autorisés, les malwares et les fuites d’information. 
Elle repose sur des mécanismes techniques robustes et des politiques rigoureuses.

## Contrôle des accès

L’accès aux systèmes d’information est restreint et sécurisé selon les principes du moindre privilège.

Les journaux d’accès physique sont croisés ponctuellement avec les accès logiques pour détecter toute incohérence.

Mesures mises en place :
- Authentification forte à double facteur
- Comptes nominatifs pour assurer la traçabilité
- Sessions verrouillées automatiquement après inactivité

Des règles strictes sont définies pour la gestion des mots de passe :
- Complexité obligatoire
- Durée de validité limitée
- Historique empêchant la réutilisation des anciens mots de passe
- Stockage chiffré et non réversible

## Protection

Le CHU déploie des outils de protection contre les menaces internes et externes :
-  Pare-feux multiples
- Segmentation réseau
- Antivirus et antimalwares
- IDS / IPS
- SIEM
- Filtrage web et messagerie

## Journalisation et supervision

Toutes les activités critiques sont journalisées afin de détecter les anomalies et assurer la traçabilité des actions.

Les logs enregistrés sont :
- Les logs d'accès 
- Les logs de modification 
- Les logs d'administration
- Les logs système

Les journaux sont conservés pendant une durée minimale de 1 an conformément au RGPD.
Une supervision centralisée des logs via un SIEM pour corrélation et alertes en temps réel.
Le RSSI effectue des revues régulières des logs.

## Chiffrement des données sensibles

Les données médicales et personnelles sensibles sont protégées par chiffrement, à la fois au repos et en transit.
Un chiffrement automatique des sauvegardes est effectué de manière régulière. 
Les données sont chiffrées avec des algorithmes robustes ( AES-256 ).

Les protocoles de sécurité utilisés sont :
- HTTPS
- TLS
- SFTP

## Sécurisation des postes et serveurs

Tous les postes de travail et serveurs sont configurés selon une politique de durcissement.
Une suppression des services inutiles hebdomadaire est mise en place.
Les droits administratifs sont strictement limités.
Les périphériques sont désactivés si non justifiés.
Des sauvegardes régulières sont mises en place et testées périodiquement.
Les images systèmes sont standardisées et vérifiées via des checksums avant déploiement.
Des mises à jour de sécurité régulières sont automatisées via un outil centralisé. Les correctifs critiques sont appliqués dès leur publication, après validation.

## Sécurité réseau

Le réseau du CHU est segmenté pour limiter la propagation d’éventuelles attaques.
Les VLANs permettent de séparer les services critiques selon leur sensibilité.
Un filtrage du trafic entrant et sortant entre segments critiques est effectuée. 
Une surveillance du réseau en temps réel est mise en place.

---

# **7. Sécurité des communications**

Les communications électroniques constituent un vecteur critique d’attaque. 
Le CHU met en œuvre des mesures de contrôle, de chiffrement et de restriction afin de garantir la confidentialité, l’intégrité et la traçabilité des échanges.

## Politique d’usage des emails et d’Internet

L’usage des messageries électroniques et de l’accès à Internet est encadré par la charte informatique.

**Emails** :
- Utilisation exclusivement professionnelle.
- Interdiction d’envoyer des données de santé par email
- Détection et filtrage des pièces jointes malveillantes, des liens suspects et des spams
- Obligation de chiffrer les emails contenant des informations sensibles

**Internet** :
- Navigation filtrée via un proxy et blocage des sites à risque
- Trafic analysé pour détecter des comportements anormaux
- Surveillance de l’usage personnel dans la limite du RGPD

## Chiffrement des communications

Toutes les communications internes et externes transportant des données sensibles sont protégées par des protocoles de chiffrement :
- Connexions aux services web internes et externes en HTTPS
- Transferts de fichiers via SFTP
- Outils de visioconférence approuvés par la DSI et conformes aux règles de confidentialité

## Utilisation des réseaux Wi-Fi

Le Wi-Fi est déployé de manière sécurisée et segmentée, selon les usages et profils d’accès.

Les VLANs associés aux SSID permettent une isolation stricte des flux entre les différentes catégories d’utilisateurs

**Règles appliquées** :
- SSID séparés pour les invités, pour le personnel, et pour les équipements médicaux
- Chiffrement en WPA3 pour les accès internes
- Authentification via certificat ou portail captif sécurisé pour le personnel
- Aucun accès au SI interne depuis le VLAN invité

Une supervision continue du réseau Wi-Fi est assurée pour détecter les points d'accès non autorisés ou les comportements suspects.

---

# **8. Analyse des risques**

L’analyse des risques permet d’identifier les menaces, évaluer les vulnérabilités et prioriser les actions de sécurité selon l’impact potentiel sur les activités critiques du CHU.
## Menaces

| Menace                          | Description                                                             |
| ------------------------------- | ----------------------------------------------------------------------- |
| Phishing                        | Phishing et connexion réseau interne                                    |
| Malveillance Interne            | Employé malveillant cherchant à nuire par plusieurs moyens              |
| Panne matérielle                | Défaillance des équipements                                             |
| Risques Externes                | Incendie, tsunami ou encore tornades                                    |
| Ransomware                      | Logiciel malveillant bloquant les systèmes en échange d'une rançon      |
| Intrusion réseau malveillant    | Accès non autorisé au réseau interne                                    |
| Déni de service (DDoS)          | Attaque pirate pour surcharger un service                               |
| Mauvaise configuration          | Failles introduites par erreur lors d'une installation                  |
| Escroquerie au faux fournisseur | Fausse facture ou changement de RIB frauduleux envoyé à la comptabilité |
| Équipements médicaux            | Exploitation d'une faille sur un appareil connecté (IRM)                |
| Défaut d'alimentation           | Coupure de courant affectant les systèmes critiques                     |
| Infection par clé USB           | Clé contaminée branchée sur un PC interne                               |

## Vulnérabilité

| Vulnérabilité                              | Description                                                              |
| ------------------------------------------ | ------------------------------------------------------------------------ |
| Absence de mot de passe fort               | Manque de sensibilisation des utilisateurs                               |
| Poste non verrouillé                       | Manque de sensibilisation des utilisateurs                               |
| Mauvaise formation cyber                   | Manque de discipline quant à la formation cyber                          |
| Accès sans contrôle                        | Pas de restriction sur les accès réseau                                  |
| Phishing                                   | Manque de sensibilisation des utilisateurs                               |
| Sauvegarde irrégulière                     | Mauvais paramétrage de la BACKUP                                         |
| MAJ irrégulières                           | Potentielle nouvelle faille de sécurité                                  |
| Social engineering                         | Exploitation de l'humain pour contourner la sécurité                     |
| Applications web                           | Potentielles failles au niveau du portail web                            |
| Aucune politique d’usage du SI             | Pas de charte informatique donc pas de règles à suivre                   |
| Pas de gestion des habilitations sensibles | Droits différents non maîtrisés selon les besoins                        |
| Postes non sécurisés dans les services     | PC à disposition de toute personne                                       |
| Accès libre aux salles serveurs            | Un accès restreint est nécessaire                                        |
| Badge laissé sans surveillance             | Badge d’un personnel sans surveillance                                   |
| Logiciels médicaux non certifiés           | Utilisation de logiciels non conformes au RGPD                           |
| Prestataires sans clause de sécurité       | Aucun engagement contractuel sur la confidentialité des données patients |

## Matrices des Risques

| Risque                     | Impact (1-5) | Probabilité (1-5) | Niveau de Risque (Impact × Probabilité) |
| -------------------------- | ------------ | ----------------- | --------------------------------------- |
| Sinistre physique          | 5            | 1                 | 5                                       |
| Non-respect des procédures | 5            | 2                 | 10                                      |
| Panne matérielle           | 5            | 3                 | 15                                      |
| Déni de service (DDoS)     | 5            | 4                 | 20                                      |
| Intrusion physique         | 4            | 3                 | 12                                      |
| Erreur humaine             | 4            | 4                 | 16                                      |
| Ingénierie sociale         | 5            | 5                 | 25                                      |
| Grève ou indisponibilité   | 3            | 2                 | 6                                       |
| Manque de sensibilisation  | 3            | 3                 | 9                                       |

## Tableau de criticité
  

![img](tableau-criticité.png])

  

Cartographie des risques pour le CHU Ynov.

Elle distingue les risques selon leur **probabilité** et leur **impact** :
- **Zone rouge** : Risques critiques nécessitant des actions immédiates
- **Zone orange** : Risques importants à traiter rapidement
- **Zone jaune** : Risques modérés, à surveiller
- **Zone verte** : Risques faibles

  

## Mesures de traitement des risques

| Risque                     | Mesure proposée                                                      |
| -------------------------- | -------------------------------------------------------------------- |
| Fuite de données clients   | Sensibilisation + MFA                                                |
| Ingénierie sociale         | Formation cyber + limitation des actions sensibles                   |
| Blocage serveur            | Sauvegarde + pare-feu                                                |
| Intrusion réseau           | Pare-feu + monitoring                                                |
| Perte de matériel          | Authentification forte + chiffrement des disques                     |
| Intrusion physique         | Badge + agent de sécurité + caméra                                   |
| Panne matérielle           | Redondance électrique / réseau                                       |
| Poste non verrouillé       | Verrouillage automatique + sensibilisation utilisateurs              |
| MAJ présentant des failles | Tests sur machine de test + pentest avant déploiement                |
| Non-respect des procédures | Sanctions adaptées selon le type de non-respect                      |
| Applications web           | Pentest + chiffrement SSL                                            |
| Infection par clé USB      | Blocage des périphériques (hors demande au RSSI)                     |
| Déni de service (DDoS)     | Redirection de flux si activité suspecte détectée                    |
| Erreur humaine             | Contrôle systématique par plusieurs personnes pour actions critiques |

---

# **9. Gestion des incidents**


## Procédure de gestion des incidents

| **Étape**                  | **Description**                                                                               |
| -------------------------- | --------------------------------------------------------------------------------------------- |
| **1. Détection**           | Surveillance continue via SIEM (`siem-01`), alertes IDS/IPS (`ids-01`), logs système          |
| **2. Signalement**         | Par les utilisateurs ou via alertes automatiques<br>**Tout signalement est transmis au RSSI** |
| **3. Qualification**       | Le RSSI analyse et catégorise l’incident                                                      |
| **4. Réponse**             | Contention (isoler machine), éradication (nettoyage), récupération (restauration)             |
| **5. Communication**       | Le RSSI informe la direction, le DSI et les utilisateurs concernés                            |
| **6. Journalisation**      | L’ensemble des actions est documenté                                                          |
| **7. Retour d'expérience** | Revue post-incident pour améliorer procédures et sécurité                                     |

## Journalisation et traçabilité

Tous les composants critiques génèrent des logs centralisés dans `siem-01`.
Conservation légale des journaux : **minimum 1 an**, conformément aux recommandations de l'ANSSI.
Les journaux sont horodatés, signés, et accessibles uniquement aux personnels autorisés.
Les actions administratives sensibles sont tracées et contrôlées.

## Notification aux autorités

En cas de violation de données à caractère personnel, une notification à la **CNIL** est effectuée :
 - Dans un délai de 72h après la découverte de l'incident
 - Par le RSSI, en lien avec la Direction Générale
 
 Les personnes concernées sont informées individuellement si l’incident est susceptible d'engendrer un risque élevé pour leurs droits et libertés.

---

# **10. Continuité d’activité**

La continuité d'activité a pour objectif de garantir le maintien ou le rétablissement rapide des activités critiques du CHU en cas de cyberattaque ou autre crise affectant le système d’information.

La continuité d’activité repose sur deux volets essentiels :
- PRA : rétablir le SI après un incident
- PCA : maintenir une activité pendant l’incident

## Périmètre d'action

| Domaine          | Éléments concernés        | Machine                                                      |
| ---------------- | ------------------------- | ------------------------------------------------------------ |
| Données patient  | DPI, DMP, base de données | `srv-bdd-01`                                                 |
| Communication    | Mail, DNS, DHCP, LDAP     | `srv-mail-01`, `dns-01`, `dhcp-01`, `dns-dhcp-02`, `ldap-01` |
| Sécurité         | Pare-feux , IDS, SIEM     | `fw-01/02`, `ids-01`, `siem-01`                              |
| Infrastructure   | Switchs                   | `sw-01/02`                                                   |
| Sauvegarde       | Serveurs de backup        | `srv-backup-01/02`                                           |
| Authentification | Serveur LDAP              | `ldap-01`                                                    |

## Plan de Continuité d’Activité (PCA)

Le PCA à pour objectif de :
- Assurer la continuité des services critiques durant un incident
- Minimiser l’impact sur les soins, la sécurité des patients et la confidentialité des données
- Maintenir un niveau minimal d’opération jusqu’au retour à la normale
- Compléter le PRA par des procédures opérationnelles et organisationnelles

La redondance assurée dans le cadre du PCA permet d’éviter une bascule immédiate vers le PRA. Le PRA est déclenché uniquement si la panne dépasse la capacité de résilience.
### Mesures de continuité

**Redondance et tolérance aux pannes** :
- Sauvegardes automatisées sur site
- Virtualisation et réplication des serveurs

**Organisation et personnel** :
- Mise en place d’une **cellule de crise** avec RSSI et DSI
- Formation des équipes sur les procédures d’urgence
- Mise en place de postes de travail de secours pour accès aux systèmes essentiels

**Procédures de travail alternatives** : 
- En cas d’indisponibilité du SI, recours à des processus papier temporaires
- Utilisation de moyens de communication alternatifs
- Planification de rotation du personnel sur site pour assurer la continuité

**Communication** : 
- Plan de communication interne et externe
- Mise à jour régulière des informations sur l’état du système via intranet, mails et SMS

### Délais de reprise des activités

| Service / Ressource          | Priorité | Délai        |
| ---------------------------- | -------- | ------------ |
| Messagerie et alertes        | Critique | < 30 minutes |
| Dossier Patients Informatisé | Critique | < 1 heure    |
| Réseau interne et accès      | Critique | < 2 heures   |
| Supervision de sécurité      | Haute    | < 4 heures   |

### Processus de validation et tests

Chaque trimestre, un test de basculement vers la solution de secours est effectué afin de garantir la disponibilité et la fiabilité des systèmes en cas d’incident. 

Des exercices de simulation d’incident majeur sont réalisés chaque année, en prévenant au préalable la direction de l’établissement, afin de préparer l’ensemble des équipes à gérer efficacement ces situations critiques. 

Une revue annuelle des procédures du PCA est également menée par le RSSI, garantissant ainsi que les protocoles restent adaptés aux besoins et aux contraintes de l’organisation. 

Le plan fait l’objet de mises à jour régulières, tenant compte des évolutions techniques et organisationnelles, pour assurer sa pertinence et son efficacité en permanence.

## Plan de Reprise d’Activité (PRA)

Le PRA à pour objectif de :
- Assurer la continuité des soins en cas d’incident majeur affectant le SI
- Réduire au minimum les interruptions de service
- Restaurer rapidement les systèmes critiques
- Limiter les pertes de données et garantir la conformité réglementaire

### Typologie des incidents couverts

| Type d'incident        | Exemples                                           |
| ---------------------- | -------------------------------------------------- |
| Panne réseau           | Switch/routeur/pare-feu en panne                   |
| Cyberattaque           | Pare-feu compromis, attaques réseau                |
| Panne matérielle       | Serveur de fichiers, stockage HS                   |
| Sinistre physique      | Salle serveur sinistrée                            |
| Erreur humaine         | Mauvaise configuration sur routeur/switch/firewall |
| Défaillance logicielle | Crash ou bug logiciel                              |

### Organisation et responsabilités

| Rôle                  | Responsable       |
| --------------------- | ----------------- |
| Coordinateur PRA      | RSSI              |
| Responsable réseau    | DSI               |
| Responsable sécurité  | RSSI / DSI        |
| Équipe d’intervention | Technicien réseau |

### Procédures de reprise

Un déclenchement du PRA est obligatoire en cas de détection de panne via le SIEM.
Elle est suivie d'une évaluation de l'impact sur le SI.
L'activation du PRA se fait exclusivement par le RSSI et une notification est envoyé à la direction.

#### Priorité de reprise

| Composant       | Priorité | Délai |
| --------------- | -------- | ----- |
| Pare-feu        | Critique | < 2h  |
| Switch          | Critique | < 2h  |
| VLANs sensibles | Critique | < 4h  |
| IDS / IPS       | Critique | < 4h  |
| Routeur FAI     | Haute    | < 6h  |
| SIEM            | Haute    | < 12h |

#### Procédures de reprise par composant

**Pare-feu** (Critique – < 2h) :
- Si panne matérielle, remplacement par un pare-feu de secours
- Restauration de la configuration depuis backup chiffré
- Redémarrage des règles de filtrage
- Vérification des services

**Switch** (Critique – < 2h) :
- Si panne matérielle, remplacement par switch de secours
- Téléversement manuel de la configuration
- Validation du routage inter-VLAN
- Test de la connectivité réseau entre segments.

**VLANs sensibles** (Critique – < 4h) :
- Vérification des switchs et configuration VLAN
- Contrôle des affectations de ports
- Recréation des VLANs en cas de corruption
- Surveillance du trafic rétabli via IDS/SIEM.
- Tests d’accès aux ressources critiques

**IDS / IPS** (Critique – < 4h) :
- Redémarrage des services IDS
- Restauration de la configuration depuis snapshot
- Synchronisation avec le SIEM pour reprise de la détection
- Vérification des règles et des mises à jour de signatures
- Validation de l'analyse en temps réel des flux

**Routeur FAI** (Haute – < 6h) :
- Diagnostic de la panne avec le fournisseur
- Si matériel HS, remplacement par routeur de secours
- Test de la connectivité Internet entrante/sortante

**SIEM*** (Haute – < 12h) : 
- Reboot du serveur SIEM
- Vérification du service de collecte de logs
- Reconnexion aux équipements réseau
- Chargement des règles de corrélation d’alertes
- Vérification du tableau de bord et des alertes actives

#### Tests et maintenance

Des tests de continuité sont réalisés annuellement pour chacun des scénarios de panne identifiés, afin de valider l’efficacité des procédures de reprise.

Une sauvegarde quotidienne automatisée est effectuée en heures creuses pour l’ensemble des équipements du système d’information, via les serveurs de sauvegarde dédiés.

Un exemplaire de secours de chaque composant critique du SI est conservé dans une salle sécurisée et contrôlée, permettant une remise en service rapide en cas de défaillance matérielle.

Enfin, la supervision en temps réel du réseau assure une remontée automatique des alertes critiques vers le RSSI et la DSI par SMS et e-mail, garantissant une réactivité immédiate face aux incidents. 

#### Communication

En cas de crise informatique, une notification immédiate est transmise au RSSI, à la DSI, ainsi qu’à la direction de l’établissement.

Conformément au RGPD et aux directives de la CNIL, les autorités compétentes sont informées si la situation le requiert.

Un affichage en temps réel de la situation est diffusé sur l’intranet du CHU, si celui-ci demeure opérationnel, afin de tenir les utilisateurs informés de l’évolution et des consignes éventuelles.

Par ailleurs, une journalisation complète de toutes les actions menées durant l’incident est exigée. Ce rapport doit être structuré, horodaté, et transmis au RSSI pour analyse et archivage.

## Contacts d’urgence

Une liste à jour des contacts internes est maintenue, incluant le RSSI et le DSI, afin de garantir une communication rapide et efficace en cas d'incident. 

Cette liste est complétée par les coordonnées des fournisseurs et partenaires techniques, essentiels au bon fonctionnement et au rétablissement des services en situation de crise. 

Les services de secours externes, tels que les pompiers, la police ou les services d’urgence médicale, sont également référencés pour permettre une réactivité optimale face aux situations les plus critiques.

---

## **11. Conformité**


Le CHU Ynov appuie sa réglementation par rapport aux grandes réglementations obligatoires. Nous voulons que notre SI puisse présenter le minimum de failles possibles, que ce soit au niveau physique, humain ou encore virtuel.

Des audits de conformité sont réalisés régulièrement pour évaluer la conformité du CHU, il existe 2 types d'audits.
Le premier est réalisé par le DSI ( Audit Interne) et le second est réalisé par un prestataire externe.
L'Audit peut donner lieu à des plans d'actions correctifs mis en place par le RSSI.

Le DPO (Délégué à la Protection des Données) sera la personne choisi pour garantir la conformité des réglementations du RGPD.

- **ISO 27001** : Norme internationale pour la mise en œuvre d’un SMSI.

| Référence | Contrôle                               | Description                                                                                       | Conformité |
| --------- | -------------------------------------- | ------------------------------------------------------------------------------------------------- | ---------- |
| A.5.1     | Politique de sécurité de l'information | Établir une politique de sécurité claire, adaptée aux enjeux du CHU.                              | CONFORME   |
| A.5.8     | Gestion des incidents                  | Détecter, signaler et traiter efficacement les incidents de sécurité                              | CONFORME   |
| A.6.3     | Sensibilisation et formation           | Former le personnel hospitalier aux bonnes pratiques de cybersécurité.                            | CONFORME   |
| A.7.1     | Contrôle d'accès physique              | Restreindre l’accès aux zones sensibles comme les salles serveurs                                 | CONFORME   |
| A.8.2     | Contrôle des accès                     | Gérer finement les droits d’accès aux SI selon les fonctions (soignant, administratif, etc.).     | CONFORME   |
| A.8.3     | Cryptographie                          | Chiffrer les données sensibles                                                                    | CONFORME   |
| A.8.6     | Sauvegardes                            | Effectuer des sauvegardes régulières et stockées de manière sécurisée.                            | CONFORME   |
| A.8.7     | Journalisation et surveillance         | Collecter les journaux d’activité pour identifier les comportements anormaux.                     | CONFORME   |
| A.8.8     | Sécurité réseau                        | Séparer les réseaux critiques (biomédical, administratif) et les protéger activement.             | CONFORME   |
| A.8.9     | Sécurité dans le développement         | Intégrer la sécurité dès la conception des logiciels ou applications santé.                       | CONFORME   |
| A.10.1    | Sécurité des communications            | Assurer la confidentialité et l'intégrité des données échangées entre services ou établissements. | CONFORME   |
| A.12.6    | Conformité avec les exigences légales  | Respecter les lois et règlements comme le RGPD                                                    | CONFORME   |

- **ISO 27799** : Application au domaine des données de santé personnelles.

| Référence | Contrôle                                     | Description                                                                                       | CONFORMITE |
| --------- | -------------------------------------------- | ------------------------------------------------------------------------------------------------- | ---------- |
| 5.1       | Politique de sécurité de l'information       | Définir une politique spécifique pour la protection des données de santé personnelles.            | CONFORME   |
| 5.2       | Organisation de la sécurité de l'information | Responsabilités claires pour la gestion de la sécurité des données de santé.                      | CONFORME   |
| 6.1       | Gestion des risques                          | Identification et traitement des risques liés à la confidentialité, intégrité et disponibilité.   | CONFORME   |
| 7.1       | Sensibilisation et formation                 | Formation du personnel sur la protection des données de santé et les exigences légales associées. | CONFORME   |
| 8.1       | Contrôle des accès                           | Limiter l’accès aux dossiers médicaux aux seules personnes autorisées.                            | CONFORME   |
| 8.2       | Authentification et gestion des identités    | Mise en place de mécanismes forts d’authentification (ex : MFA) pour accès aux données sensibles. | CONFORME   |
| 9.1       | Protection des communications                | Assurer la confidentialité et l’intégrité des échanges d’informations de santé.                   | CONFORME   |
| 10.1      | Gestion des incidents de sécurité            | Processus pour détecter, rapporter et gérer les violations ou incidents concernant les données.   | CORFORME   |
| 11.1      | Surveillance et audit                        | Enregistrer et contrôler les accès et modifications sur les données de santé.                     | CONFORME   |
| 12.1      | Continuité d’activité                        | Prévoir des mesures pour assurer la disponibilité des données en cas de sinistre ou panne.        | CONFORME   |
| 13.1      | Conformité légale                            | Respecter la législation sur la protection des données de santé (ex : RGPD, lois nationales).     | CONFORME   |

- **RGPD** : Règlement général sur la protection des données (UE).

| Article     | Intitulé / Principe      | Description  | CONFORMITE |
|-------------|----|---------|----|
| Art. 5      | Principes relatifs au traitement des données     | Les données doivent être traitées de manière licite, loyale, transparente, et pour un but précis.|CONFORME |
| Art. 6      | Licéité du traitement  | Le traitement est justifié par une base légale |CONFORME |
| Art. 9      | Données sensibles  | Les données de santé sont des données sensibles, nécessitant une protection renforcée.    |CONFORME |
| Art. 12-14  | Information des personnes concernées | Les patients doivent être informés de l’usage de leurs données et de leurs droits.  |CONFORME |
| Art. 15     | Droit d'accès  | Tout patient peut demander l’accès à ses données médicales détenues par l’hôpital.   |CONFORME |
| Art. 16     | Droit de rectification| Permet au patient de faire corriger des données de santé inexactes. | CONFORME |
| Art. 17     | Droit à l’effacement (« droit à l’oubli »)    | Limité dans le secteur hospitalier| CONFORME |
| Art. 25     | Protection des données dès la conception  | Les systèmes du CHU doivent intégrer la sécurité et la confidentialité dès leur développement.  |CONFORME |
| Art. 30     | Registre des activités de traitement | Le CHU doit documenter tous les traitements de données (patients, RH, recherche, etc.). |CONFORME |
| Art. 32     | Sécurité du traitement  | Imposer des mesures techniques et organisationnelles pour garantir la sécurité des données.  |CONFORME |
| Art. 33-34  | Notification des violations de données  | En cas de fuite de données, obligation de notifier la CNIL et les personnes concernées. |CONFORME |
| Art. 35     | Analyse d'impact  | Obligatoire pour les traitements de santé à risque |CONFORME |
| Art. 37-39  | Délégué à la protection des données (DPO) | Le CHU doit désigner un DPO qui veille au respect du RGPD. |CONFORME |

- **Code de la santé publique** : Textes législatifs et réglementaires français régissant le domaine de la santé.

| Article         | Intitulé / Principe | Description | CONFORMITE |
|-----------------|--------|---------------|---|
| L1110-4         | Secret médical / confidentialité           | Oblige la mise en œuvre de protections informatiques pour garantir la confidentialité des données. | CONFORME |
| L1111-7         | Accès aux informations de santé  | Nécessite un SIH (système d'information hospitalier) permettant l’accès sécurisé aux dossiers médicaux. | CONFORME |
| L1111-8         | Hébergement des données de santé           | Impose l’usage d’un hébergeur certifié HDS pour toute solution de stockage externalisé. | CONFORME |
| L1111-8-1       | Certification HDS  | Obligation de recourir à des prestataires informatiques certifiés pour l’hébergement ou le traitement. | CONFORME |
| L1111-17        | Cybersécurité dans les SI de santé   | Oblige les établissements à adopter des mesures de cybersécurité adaptées aux risques numériques. | CONFORME |
| R1111-1 à R1111-9| Dossier médical du patient  | Fixe les conditions de constitution, conservation, sécurité et accès aux dossiers numérisés.   | CONFORME |
| L1460-1         | Système National des Données de Santé (SNDS)| Réglemente l’intégration et l’usage des données issues des systèmes hospitaliers dans le SNDS. | CONFORME |
| L1111-2         | Information du patient   | Implique des interfaces numériques ou systèmes pour informer le patient sur l’usage de ses données. | CONFORME |


---
# **12. Évolution de la PSSI**

La politique de sécurité des systèmes d’information du CHU est un document vivant, amené à évoluer en fonction des menaces, des technologies, de l'organisation interne et des obligations réglementaires.

## Mise à jour régulière

La PSSI fait l’objet d’une revue annuelle systématique, pilotée par le RSSI en collaboration avec le DSI. 
Des mises à jour ponctuelles peuvent également être réalisées à la suite :
- D’un audit de sécurité avec test d’intrusion
- D’un incident majeur ou d’une cyberattaque
- D’une évolution réglementaire
- De l’introduction de nouvelles technologies ou d’un changement d’infrastructure

## Processus de révision

Le processus de révision de la PSSI suit les étapes suivantes :
1. Collecte des retours d’expérience des utilisateurs, techniciens, RSSI et auditeurs
2. Évaluation de la pertinence des mesures existantes
3. Proposition de modifications, validées par le RSSI
4. Diffusion de la version mise à jour auprès des utilisateurs
5. Archivage des anciennes versions pour traçabilité

Chaque modification est **documentée, horodatée**, et validée par la direction.

## Suivi des évolutions technologiques et réglementaires

Le CHU assure une veille technologique et réglementaire continue afin d’anticiper les nouvelles menaces et les exigences légales. 

Cette veille repose sur :
- La consultation régulière des publications de l’ANSSI, du CERT-FR, et de la CNIL
- La participation à des groupes de travail cybersécurité hospitaliers
- L’analyse des bulletins de sécurité des éditeurs logiciels et matériels utilisés

 Les évolutions identifiées sont analysées en termes d’impact sur le SI, et intégrées à la PSSI lors des mises à jour exceptionnelles.
