# Registre des traitements

> **Version 1.0 — 20 septembre 2026** · Document interne, requis par l'article 30 du RGPD.
> Il n'a pas à être publié, mais **doit pouvoir être présenté à la CNIL en cas de contrôle**.
> Document de référence pour le public : [politique-confidentialite.md](politique-confidentialite.md).

---

## 1. Identification du responsable de traitement

| | |
|:--|:--|
| **Responsable** | L'éditeur du service SwiftSlate — personne physique agissant à titre non professionnel |
| **Contact** | jcversa16@gmail.com |
| **Identité complète** | Non publiée (art. 6-III-2 LCEN) ; communiquée à l'hébergeur GitHub B.V. |
| **DPO** | Sans objet — aucun des cas de l'article 37 n'est rempli |
| **Représentant dans l'UE (art. 27)** | Sans objet — le responsable est établi en France |
| **Sous-traitants** | Aucun sous-traitant pour le compte du responsable : il ne traite lui-même aucune donnée utilisateur |
| **Catégories d'activité** | Édition d'un logiciel grand public distribué gratuitement, sans compte ni serveur |

---

## 2. Vue d'ensemble des traitements

| N° | Traitement | Base légale | Données de catégorie particulière ? | Transfert hors UE |
|:--|:--|:--|:--|:--|
| 1 | Transmission du texte à un fournisseur d'IA | Consentement (art. 6-1-a) | **Possibles**, par le fait de l'utilisateur | Oui (US ; Chine si DeepSeek) |
| 2 | Vérification quotidienne des mises à jour | Intérêt légitime (art. 6-1-f) | Non | Oui (US / NL) |
| 3 | Stockage des clés d'accès (API keys) | Consentement (art. 6-1-a) | Non | Non (sauf en-tête vers le fournisseur) |
| 4 | Historique local des commandes (optionnel) | Consentement (art. 6-1-a) | Possibles, si l'utilisateur en saisit | Non |
| 5 | Statistiques d'usage locales | Hors champ du RGPD (traitement local, non identifiant) | Non | Non |
| 6 | Correspondance par email | Intérêt légitime (art. 6-1-f) ; obligation légale (art. 6-1-c) si exercice de droits | Possibles, si l'utilisateur en communique | Oui (US — hébergement de la messagerie) |
| 7 | Journalisation technique liée au service d'accessibilité | — (pas de conservation) | — | Non |

> **Aucun traitement** ne relève de la prospection commerciale, du profilage, de la décision automatisée, de la vidéosurveillance ou de la gestion de ressources humaines.

---

## 3. Fiches détaillées

### Traitement 1 — Transmission du texte à un fournisseur d'intelligence artificielle

| Champ (art. 30) | Contenu |
|:--|:--|
| **Finalité** | Exécuter la commande de réécriture déclenchée par la personne ; restituer le texte transformé dans le champ de saisie |
| **Base légale** | Consentement (art. 6-1-a) — déclenchement explicite par la personne, après configuration de son propre fournisseur et de sa propre clé |
| **Personnes concernées** | Utilisateurs de l'application ; tiers dont le texte soumis contient les informations |
| **Catégories de données** | Contenu du texte soumis ; clé d'accès (en-tête d'authentification) ; données techniques de la requête (IP, horodatage) traitées par le fournisseur |
| **Destinataires** | Fournisseur d'IA choisi par la personne : Google (Gemini), Groq, NVIDIA (NIM), OpenRouter, DeepSeek, ou endpoint personnalisé |
| **Transferts hors UE** | États-Unis (majorité) ; Chine (DeepSeek — **sans garantie documentée**). Voir fiche de transfert, section 4 |
| **Durée de conservation** | **Nulle côté responsable** (aucune copie, aucun journal). Côté fournisseur : 30 à 55 jours selon le fournisseur, ou selon sa politique |
| **Mesures de sécurité** | HTTPS obligatoire ; redirections désactivées ; clés chiffrées au repos (AES-256-GCM, Android Keystore) ; masquage des secrets dans les messages d'erreur |
| **Sort du traitement si refus** | La personne peut activer le mode confidentialité : plus aucun envoi, remplacement local uniquement |

### Traitement 2 — Vérification quotidienne des mises à jour

| Champ (art. 30) | Contenu |
|:--|:--|
| **Finalité** | Informer la personne qu'une version plus récente — notamment corrective de sécurité — est disponible |
| **Base légale** | Intérêt légitime (art. 6-1-f) : sécurité et maintien à jour du logiciel installé |
| **Personnes concernées** | Utilisateurs de l'application |
| **Catégories de données** | Adresse IP ; version de l'application ; horodatage |
| **Destinataires** | GitHub, Inc. / GitHub B.V. (`api.github.com`) |
| **Transferts hors UE** | États-Unis / Pays-Bas — GitHub déclare adhérer au cadre de protection des données UE–États-Unis |
| **Durée de conservation** | Côté responsable : la seule dernière version notifiée, sur l'appareil. Côté GitHub : selon sa propre politique de journaux |
| **Mesures de sécurité** | HTTPS obligatoire ; aucune donnée issue du texte de la personne |
| **Test de mise en balance** | Intérêt légitime retenu : information de sécurité, données minimales, aucun profilage, possibilité de neutraliser les notifications |

### Traitement 3 — Stockage des clés d'accès

| Champ (art. 30) | Contenu |
|:--|:--|
| **Finalité** | Authentifier les requêtes de la personne auprès du fournisseur qu'elle a configuré |
| **Base légale** | Consentement (art. 6-1-a), matérialisé par la saisie volontaire |
| **Personnes concernées** | Utilisateurs de l'application |
| **Catégories de données** | Clés d'accès (API keys) ; paramètres d'accès à un endpoint personnalisé |
| **Destinataires** | Aucun — stockage strictement local. Transmission au seul fournisseur concerné, comme en-tête d'authentification |
| **Transferts hors UE** | Aucun stockage hors UE ; la clé accompagne la requête vers le fournisseur choisi |
| **Durée de conservation** | Jusqu'à suppression par la personne ou désinstallation |
| **Mesures de sécurité** | AES-256-GCM, clé non exportable via Android Keystore ; refus d'écriture en cas d'échec du chiffrement ; exclusion des sauvegardes automatiques et de la sauvegarde manuelle des réglages |

### Traitement 4 — Historique local des commandes

| Champ (art. 30) | Contenu |
|:--|:--|
| **Finalité** | Permettre à la personne de retrouver ses dernières réécritures |
| **Base légale** | Consentement (art. 6-1-a) — fonction **désactivée par défaut** |
| **Personnes concernées** | Utilisateurs de l'application ; tiers mentionnés dans les textes conservés |
| **Catégories de données** | Texte d'entrée ; texte de sortie ; nom de commande ; fournisseur ; date |
| **Destinataires** | Aucun — stockage local, jamais synchronisé |
| **Transferts hors UE** | Aucun |
| **Durée de conservation** | 30 jours par défaut, 365 jours maximum ; 100 entrées au plus ; effacement immédiat à la demande |
| **Mesures de sécurité** | Espace privé de l'application ; exclusion des sauvegardes cloud et du transfert d'appareil |

### Traitement 5 — Statistiques d'usage locales

| Champ (art. 30) | Contenu |
|:--|:--|
| **Finalité** | Afficher à la personne sa propre activité sur le tableau de bord |
| **Base légale** | Traitement local sur l'appareil de la personne, sans transmission ni identification — hors champ du RGPD |
| **Catégories de données** | Compteurs agrégés (nombre de commandes, par commande, par jour, par mois) |
| **Destinataires / transferts** | Aucun |
| **Durée** | Jusqu'à remise à zéro ou désinstallation |

### Traitement 6 — Correspondance par email

| Champ (art. 30) | Contenu |
|:--|:--|
| **Finalité** | Répondre aux demandes ; traiter les signalements de vulnérabilité et d'abus ; assurer le suivi des incidents et l'exercice des droits |
| **Base légale** | Intérêt légitime (art. 6-1-f) pour la réponse et la sécurité ; obligation légale (art. 6-1-c) pour le traitement des demandes d'exercice de droits |
| **Personnes concernées** | Toute personne écrivant à l'adresse de contact |
| **Catégories de données** | Adresse email ; contenu du message ; pièces jointes éventuelles (captures, journaux, informations d'appareil) |
| **Destinataires** | Le responsable, sur sa boîte de messagerie hébergée par Google (Gmail) |
| **Transferts hors UE** | États-Unis — Google LLC certifié au titre du cadre de protection des données UE–États-Unis |
| **Durée de conservation** | Conservation pendant le traitement de la demande, puis **12 mois** après la dernière réponse, puis suppression définitive. |
| **Mesures de sécurité** | Accès restreint au seul responsable ; consigne de ne pas conserver les secrets communiqués ; invitation à ne pas envoyer de données sensibles |
| **Sort du traitement** | Réponse à la demande ; suppression à l'échéance ci-dessus |

### Traitement 7 — Service d'accessibilité (absence de conservation)

| Champ (art. 30) | Contenu |
|:--|:--|
| **Finalité** | Détecter une commande de déclenchement dans le champ de texte au premier plan et y réinsérer le résultat |
| **Base légale** | Consentement de la personne, matérialisé par l'activation du service d'accessibilité dans les réglages Android ; autorisation système explicite |
| **Catégories de données** | Événements de modification de texte, examinés en mémoire ; champs de mot de passe ignorés |
| **Destinataires / transfert** | Aucun hors le fournisseur d'IA, et uniquement après reconnaissance d'une commande |
| **Durée de conservation** | **Aucune** — traitement en mémoire, sans écriture disque, sans journal |
| **Point de vigilance** | C'est le traitement le plus intrusif en apparence (accès au texte des autres applications). Il est donc décrit explicitement dans le document public et l'utilisateur est renvoyé à l'auteur du texte : ne pas s'en servir sur des données de tiers sans motif |

---

## 4. Fiche de transfert hors Union européenne

| Destinataire | Pays | Nature | Garantie | Statut |
|:--|:--|:--|:--|:--|
| Google (Gemini API) | États-Unis | Texte, clé | Certification EU–US DPF de Google LLC ; *Data Processing Addendum* intégrant les clauses contractuelles types ; conditions « services payants » appliquées à l'EEE | Documenté |
| Groq | États-Unis | Texte, clé | Interdiction contractuelle d'entraînement ; DPA intégrant les clauses contractuelles types UE et l'addendum britannique | Documenté |
| NVIDIA (NIM) | États-Unis | Texte, clé | — | **[À VÉRIFIER]** |
| OpenRouter | États-Unis | Texte, clé | Routage vers des fournisseurs tiers ; réglage de refus d'entraînement à désactiver côté compte | **[À VÉRIFIER]** |
| DeepSeek | **Chine** | Texte, clé | **Aucune décision d'adéquation, aucune clause contractuelle type publiée** | ⚠️ **Risque non couvert** |
| GitHub | États-Unis / Pays-Bas | IP, version de l'application | Adhésion déclarée au cadre de protection des données UE–États-Unis ; clauses contractuelles types | Documenté |
| Google (Gmail) | États-Unis | Adresse, message | Certification EU–US DPF | Documenté |

**Mesure d'atténuation retenue pour DeepSeek** : le fournisseur reste sélectionnable — l'application ne peut pas retirer une intégration documentée sans casser une fonctionnalité existante — mais le risque est **signalé explicitement** dans la politique de confidentialité publique, avec recommandation de ne pas l'utiliser pour des données personnelles. La suppression pure et simple de ce fournisseur reste une option à trancher par le responsable.

---

## 5. Analyse d'impact (AIPD / DPIA)

Une analyse d'impact est requise lorsque le traitement est susceptible d'engendrer un risque élevé (art. 35).

| Critère | Constat |
|:--|:--|
| Évaluation ou notation de personnes | Non |
| Décision automatisée aux effets juridiques | Non |
| Surveillance systématique d'une zone accessible au public | Non |
| Données sensibles ou hautement personnelles | **Possibles**, par le fait de l'utilisateur, sans que le responsable les collecte |
| Traitement à grande échelle | Non — aucune donnée détenue par le responsable |
| Croisement de données de plusieurs sources | Non |
| Personnes vulnérables | Non — service non destiné aux enfants |

**Conclusion : AIPD non requise à ce jour.** À réexaminer si un serveur, un compte utilisateur ou une collecte de données était introduit.

---

## 6. Violations de données

Aucune violation constatée à la date du présent registre.

Procédure retenue, le cas échéant : notification à la CNIL dans les 72 heures (art. 33) si un risque est susceptible d'être engendré ; information des personnes concernées si le risque est élevé (art. 34). L'éditeur ne détenant aucune donnée utilisateur, les violations envisageables concernent la boîte de messagerie de contact, ou une vulnérabilité du logiciel elle-même — auquel cas l'information passerait par le dépôt public, une note de version et, le cas échéant, l'avis de sécurité du projet.

---

## 7. Points à mettre à jour

Le registre doit être révisé avant toute mise en service si :

- un fournisseur d'IA est ajouté ou retiré (traitement 1 et fiche de transfert) ;
- un serveur, un compte utilisateur, un paiement ou un outil de mesure d'audience est introduit (nouveau traitement) ;
- l'éditeur change de statut juridique (l'identification du responsable change) ;
- les durées de conservation sont modifiées — en particulier le **[À VALIDER]** de la section 3, traitement 6 ;
- l'application est publiée sur le Google Play Store (la fiche « Sécurité des données » doit être cohérente avec ce registre).
