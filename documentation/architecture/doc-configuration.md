# Configuration détaillée

## Objectif

Cette documentation décrit en détail la configuration des éléments du SI pour le **CHU Ynov**, dans le cadre de sa sécurisation contre les cyberattaques.

---

### `fw-01` – Pare-feu externe (`192.168.1.2`)

| Élément        | Configuration appliquée                                                |
| -------------- | ---------------------------------------------------------------------- |
| Type           | iptables                                                               |
| Interface WAN  | Publique                                                               |
| NAT            | NAT vers `web-01` pour HTTPS                                           |
| Règles         | HTTPS autorisé depuis Internet, DNS autorisé, tout autre trafic bloqué |
| Journalisation | Logs envoyés vers `siem-01`                                            |

---

### `fw-02` – Pare-feu interne (`192.168.1.3`)

| Élément        | Configuration appliquée                      |
| -------------- | -------------------------------------------- |
| Type           | iptables                                     |
| Inter-VLAN     | Contrôle du trafic entre VLANs               |
| Filtrage       | VLAN 10 `GUEST` bloqué vers VLANs 20, 30, 40 |
| Journalisation | Logs envoyés vers `siem-01`                  |

---

### `sw-01` / `sw-02` – Switchs (`192.168.1.4`, `192.168.1.5`)

| Élément          | Configuration appliquée                                     |
| ---------------- | ----------------------------------------------------------- |
| VLANs configurés | 10 (Guest), 20 (Admin), 30 (Infra), 40 (Médical), 100 (DMZ) |
| Ports inutilisés | Désactivés                                                  |
| Accès management | Restreint à une connexion physique                          |

---

### `dns-01` – DNS externe (`192.168.100.4`)

| Élément    | Configuration appliquée                     |
| ---------- | ------------------------------------------- |
| Service    | BIND9                                       |
| Résolution | DNS publique uniquement                     |
| Accès      | Restreint aux serveurs internes via `fw-01` |

---

### `dns-dhcp-02` – DNS + DHCP interne (`192.168.30.2`)

| Élément  | Configuration appliquée           |
| -------- | --------------------------------- |
| DNS      | Résolution interne uniquement     |
| DHCP     | VLANs 20 plages définies par rôle |
| Sécurité | Journalisation vers `siem-01`     |

---

### `dhcp-01` – DHCP invité (`192.168.10.2`)

| Élément        | Configuration appliquée            |
| -------------- | ---------------------------------- |
| IP attribuées  | `192.168.10.10` à `192.168.10.240` |
| Réservation    | `192.168.10.2` + `192.168.10.3`    |
| Journalisation | Activée                            |

---

### `ldap-01` – Annuaire LDAP (`192.168.20.2`)

| Élément          | Configuration appliquée |
| ---------------- | ----------------------- |
| Service          | OpenLDAP                |
| Chiffrement      | LDAPS activé            |
| Authentification | Par groupe              |
| Journalisation   | Activée vers `siem-01`  |

---

### `srv-mail-01` – Serveur mail (`192.168.20.3`)

| Élément        | Configuration appliquée |
| -------------- | ----------------------- |
| Services       | Postfix, Dovecot        |
| Chiffrement    | TLS obligatoire         |
| Sécurité       | SPF + antivirus ClamAV  |
| Journalisation | Activée vers `siem-01`  |

---

### `srv-share-01` – Serveur de fichiers (`192.168.20.4`)

| Élément          | Configuration appliquée |
| ---------------- | ----------------------- |
| Service          | Samba                   |
| Authentification | Intégration LDAP        |
| Sécurité         | Chiffrement + ACL       |

---

### `siem-01` – Supervision (`192.168.30.3`)

| Élément  | Configuration appliquée                          |
| -------- | ------------------------------------------------ |
| Solution | Wazuh                                            |
| Collecte | Pare-feux, IDS, LDAP, serveurs, poste de travail |
| Alerting | Email + tableau de bord                          |

---

### `ids-01` – IDS / IPS (`192.168.100.3`)

| Élément  | Configuration appliquée             |
| -------- | ----------------------------------- |
| Solution | Snort                               |
| Mode     | Passif (interface SPAN sur `sw-01`) |
| Ciblage  | Web, DNS externe, DHCP externe      |

---

### `web-01` – Serveur web (`192.168.100.2`)

| Élément     | Configuration appliquée                     |
| ----------- | ------------------------------------------- |
| Services    | Apache                                      |
| Chiffrement | HTTPS activé                                |
| Sécurité    | HTTP headers, fail2ban, logs vers `siem-01` |

---

### `wifi-01` – Wi-Fi invité (`192.168.10.3`)

| Élément        | Configuration appliquée     |
| -------------- | --------------------------- |
| Accès          | Internet uniquement         |
| Isolation      | VLAN `GUEST` isolé du reste |
| Portail captif | Activé                      |
| DNS            | Résolution DNS via `dns-01` |

---

### `srv-backup-01` / `srv-backup-02` – Sauvegardes (`192.168.30.4`, `192.168.40.3`)

| Élément     | Configuration appliquée                         |
| ----------- | ----------------------------------------------- |
| Logiciel    | Bacula                                          |
| Sauvegardes | Quotidiennes (diff) + Hebdomadaires (complètes) |
| Chiffrement | Activé                                          |
| Réplicaion  | Restauration testée                             |

---

### `srv-bdd-01` – Base de données DPI (`192.168.40.2`)

| Élément          | Configuration appliquée      |
| ---------------- | ---------------------------- |
| Service          | MySQL                        |
| TLS              | Activé                       |
| Authentification | Fortifiée + 2FA              |
| Réplication      | Multi-instances              |
| Sauvegardes      | Activées via `srv-backup-02` |

---

### `pc-admin` – Poste d’administration

| Élément          | Configuration appliquée               |
| ---------------- | ------------------------------------- |
| Authentification | LDAP                                  |
| Antivirus        | EDR installé                          |
| Chiffrement      | Disque complet via LUKS               |
| Clé SSH          | Utilisée pour connexions aux machines |
| Restrictions     | Accès limité aux VLANs 30, 40         |




