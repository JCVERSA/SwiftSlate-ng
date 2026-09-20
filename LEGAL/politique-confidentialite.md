# Politique de confidentialité

> **Version 1.0 — 20 septembre 2026**
> Ce document est la version qui fait foi. Traduction anglaise (non contraignante) : [privacy-policy.md](privacy-policy.md).
> Ce document complète, sans le remplacer, les [mentions légales](mentions-legales.md).

---

## 1. En une page

| Question | Réponse |
|:--|:--|
| L'application crée-t-elle un compte ? | **Non.** Aucun compte, aucune inscription, aucun identifiant utilisateur. |
| L'éditeur collecte-t-il vos données ? | **Non.** Il n'exploite aucun serveur, aucune base de données, aucun tableau de bord. Il n'a aucun moyen de savoir qui utilise l'application ni ce qui est tapé. |
| Y a-t-il des cookies, des traceurs, de la mesure d'audience ? | **Aucun.** Pas d'analytics, pas de pixel publicitaire, pas de rapport de plantage automatique. |
| Que devient le texte que vous faites réécrire ? | Il est envoyé **au fournisseur d'intelligence artificielle que vous avez vous-même configuré**, avec votre propre clé d'accès. C'est le seul traitement substantiel décrit ici. |
| Où vont mes données ? | Vers le fournisseur que vous choisissez : États-Unis pour la plupart, **Chine pour DeepSeek**. Section 6. |
| Que reste-t-il sur mon téléphone ? | Vos clés d'accès (chiffrées), vos préférences et, si vous l'activez, un historique local. Section 5. |
| Combien de temps ? | L'éditeur ne conserve rien. Les durées ci-dessous concernent votre appareil et les fournisseurs. Section 7. |
| Comment exercer mes droits ? | Par email à **jcversa16@gmail.com**. Section 9. |

---

## 2. Qui est responsable du traitement ?

**Responsable du traitement** : l'éditeur du service SwiftSlate, personne physique agissant à titre non professionnel, joignable à l'adresse **jcversa16@gmail.com**.

Conformément à l'article 6-III-2 de la LCEN, l'éditeur ne rend pas publiques son identité et ses coordonnées personnelles, qui ont été communiquées à l'hébergeur du service (GitHub B.V.). Cette même adresse email constitue le point de contact fonctionnel pour toute question relative aux données personnelles et pour l'exercice des droits décrits à la section 9.

**Pas de délégué à la protection des données (DPO)** : l'activité ne relève d'aucun des cas imposant cette désignation (art. 37 RGPD). Le contact ci-dessus en tient lieu.

### 2.1 Un point de vocabulaire important

Selon les traitements, le rôle de l'éditeur n'est pas le même :

| Traitement | Qui décide de la finalité et des moyens ? |
|:--|:--|
| Transmission du texte au fournisseur d'IA | **L'éditeur**, qui conçoit et décrit ce que fait l'application. Il est responsable de traitement pour cette transmission, dans les conditions de la section 5.1. |
| Choix du fournisseur, de la commande et du texte | **Vous.** L'application n'envoie rien sans que vous l'ayez explicitement déclenché. |
| Données stockées sur votre appareil (clés, historique, préférences, statistiques) | **Vous.** L'éditeur n'y a **aucun accès** : ces données ne quittent jamais le téléphone. |
| Fournisseur d'IA destinataire | **Le fournisseur** reçoit les données en qualité de responsable ou de sous-traitant distinct, selon ses propres conditions. Sa politique de confidentialité s'applique à partir du moment où il reçoit le texte. |

---

## 3. Principe de conception

L'application est conçue de telle sorte que l'éditeur **n'a besoin d'aucune donnée** pour fonctionner :

- pas de compte, pas de serveur applicatif, pas de base de données côté éditeur ;
- aucune bibliothèque d'analyse, de publicité ou de suivi de plantage n'est intégrée au logiciel (vérifiable dans les dépendances du projet) ;
- les sauvegardes automatiques Android vers le cloud sont **désactivées** pour les préférences sensibles ;
- le mode confidentialité, activable dans les réglages, **bloque tout envoi** : seules les commandes de remplacement local continuent de fonctionner.

Il reste néanmoins des traitements réels, décrits un par un ci-dessous. Ils sont peu nombreux, mais ils existent, et c'est l'objet de ce document que de les rendre lisibles.

---

## 4. À qui ce document s'applique

| | |
|:--|:--|
| **Base territoriale** | Le règlement (UE) 2016/679 (RGPD) s'applique parce que l'éditeur est établi en France (art. 3-1) **et** parce que le service est offert à des personnes se trouvant dans l'Union (art. 3-2), y compris lorsque vous résidez hors d'Europe. |
| **Droit français complémentaire** | Loi « Informatique et libertés » (loi n° 78-17 modifiée), y compris ses dispositions sur le consentement des mineurs. |
| **Public visé** | Utilisateurs particuliers. L'application n'est pas destinée aux enfants (voir section 11). |

---

## 5. Les traitements, un par un

### 5.1 Transmission du texte à un fournisseur d'intelligence artificielle

C'est le traitement central de l'application : sans lui, l'assistant de réécriture ne fait rien.

| | |
|:--|:--|
| **Données** | Le contenu du champ de texte auquel vous appliquez une commande (le texte visible, tronqué aux limites fixées par l'application) ; votre clé d'accès (API key) au fournisseur, transmise comme en-tête d'authentification ; les données techniques inhérentes à toute requête réseau (adresse IP, horodatage), traitées par le fournisseur. |
| **Personnes concernées** | Vous, et — si le texte que vous faites réécrire contient leurs informations — des tiers dont le texte parle. Voir l'avertissement ci-dessous. |
| **Finalité** | Exécuter la commande de réécriture que vous avez déclenchée ; renvoyer le texte transformé dans le champ de saisie. Aucune autre finalité : aucun profilage, aucune publicité, aucune constitution de base de données par l'éditeur. |
| **Base légale** | **Consentement** (art. 6-1-a RGPD). Vous ne déclenchez l'envoi qu'en tapant volontairement une commande de déclenchement, après avoir configuré vous-même un fournisseur et une clé. |
| **Comment retirer ce consentement** | N'utilisez plus les commandes IA ; activez le **mode confidentialité** (plus aucun envoi, le remplacement local reste disponible) ; supprimez la clé du fournisseur ; ou désinstallez l'application. |
| **Destinataires** | Le fournisseur que vous avez choisi, et lui seul. L'éditeur ne reçoit ni copie ni journal. |
| **Durée de conservation** | **Aucune conservation par l'éditeur.** Le texte n'est pas conservé après la réponse, sauf si vous avez activé l'historique local (section 5.4). Chez le fournisseur, la durée est celle décrite à la section 6. |
| **Transfert hors UE** | Oui, dans la plupart des configurations. Voir section 6. |
| **Mesures de sécurité** | HTTPS obligatoire, redirections HTTP désactivées (une clé ne peut pas être redirigée vers un autre hôte ni vers une connexion non chiffrée), clés chiffrées au repos, retrait des clés des messages d'erreur avant affichage. |

> ⚠️ **Avertissement — n'envoyez pas n'importe quel texte.** Le texte transmis est traité par un fournisseur tiers, sur une infrastructure que l'éditeur ne contrôle pas. N'y faites pas figurer de données sensibles au sens de l'article 9 du RGPD (santé, opinions politiques ou religieuses, orientation sexuelle, appartenance syndicale, données biométriques ou génétiques), de mots de passe, de numéros de carte bancaire, ni de données concernant des tiers qui ne s'attendent pas à ce traitement. Le fournisseur peut conserver les requêtes pendant la durée indiquée à la section 6, et **aucune revue humaine** de ces requêtes ne peut être exclue par l'éditeur.

### 5.2 Vérification quotidienne des mises à jour

| | |
|:--|:--|
| **Données** | Adresse IP, version de l'application installée, horodatage de la requête. |
| **Finalité** | Savoir si une version plus récente existe et vous prévenir par notification. Aucune donnée n'est extraite de votre texte. |
| **Base légale** | **Intérêt légitime** (art. 6-1-f RGPD) : vous informer d'une mise à jour, en particulier corrective de sécurité. L'impact sur votre vie privée est minimal et l'éditeur ne conserve rien. |
| **Fréquence** | Au maximum une fois par jour, en arrière-plan. |
| **Destinataire** | GitHub, Inc. / GitHub B.V. (appel à `api.github.com`). |
| **Durée** | L'éditeur ne conserve que la dernière version pour laquelle vous avez déjà été notifié, **sur votre appareil**. GitHub applique sa propre politique de journaux. |
| **Transfert hors UE** | Oui, vers GitHub (voir section 6). |
| **Comment y échapper** | Désactiver les notifications de l'application, ou restreindre son accès réseau au niveau du système. |

### 5.3 Clés d'accès aux fournisseurs (API keys)

| | |
|:--|:--|
| **Données** | Vos clés d'accès aux fournisseurs d'IA, et vos éventuels paramètres d'accès à un endpoint personnalisé. |
| **Finalité** | Authentifier vos requêtes auprès du fournisseur que vous avez configuré. Sans clé, l'application ne peut pas fonctionner. |
| **Base légale** | **Consentement** (art. 6-1-a RGPD), matérialisé par la saisie volontaire de la clé. |
| **Stockage** | **Uniquement sur votre appareil**, chiffré en AES-256-GCM au moyen d'une clé non exportable conservée par le magasin de clés sécurisé d'Android (Android Keystore). En cas d'échec du chiffrement, l'application refuse d'écrire plutôt que de dégrader la protection. |
| **Ce qui n'est jamais fait** | Aucun envoi des clés à l'éditeur ; aucune inclusion des clés dans les sauvegardes Android automatiques (fonction désactivée) ; aucune inclusion dans la sauvegarde manuelle des réglages. Une exportation chiffrée par phrase de passe existe, à votre initiative exclusive. |
| **Durée** | Jusqu'à ce que vous supprimiez la clé, ou jusqu'à la désinstallation de l'application. |
| **Transfert hors UE** | La clé n'est transmise qu'au fournisseur concerné, comme en-tête d'authentification de vos propres requêtes. Aucun transfert à un autre destinataire. |

### 5.4 Historique local des commandes — désactivé par défaut

| | |
|:--|:--|
| **Données** | Texte d'entrée, texte de sortie, nom de la commande utilisée, fournisseur associé, date. |
| **Finalité** | Vous permettre de retrouver et, le cas échéant, de revenir sur vos dernières réécritures. |
| **Base légale** | **Consentement** (art. 6-1-a RGPD). L'historique est **désactivé par défaut** : tant que vous ne l'activez pas, aucune entrée n'est écrite. |
| **Stockage** | Sur votre appareil uniquement, dans l'espace privé de l'application. Jamais transmis, jamais synchronisé, exclu des sauvegardes. |
| **Durée** | Durée que vous choisissez : **30 jours par défaut**, jusqu'à 365 jours au maximum. Le nombre d'entrées est plafonné (100). Vous pouvez effacer l'historique en une action, à tout moment, depuis les réglages. |
| **Retrait du consentement** | Désactiver l'historique ou le vider. La suppression est immédiate et définitive. |

### 5.5 Statistiques d'usage locales

| | |
|:--|:--|
| **Données** | Compteurs agrégés : nombre de commandes exécutées, répartition par commande, par jour et par mois. |
| **Finalité** | Afficher votre propre activité sur le tableau de bord de l'application. |
| **Base légale** | Ce traitement est **purement local** et n'est pas transmis à l'éditeur, qui n'y a aucun accès. Il ne permet pas de vous identifier. |
| **Durée** | Jusqu'à la désinstallation, ou jusqu'à la remise à zéro effectuée depuis l'application. |
| **Transfert** | Aucun. |

### 5.6 Correspondance par email

| | |
|:--|:--|
| **Données** | Votre adresse email, le contenu de votre message et, le cas échéant, les éléments que vous joignez (captures d'écran, extraits de journaux, informations sur votre appareil). |
| **Finalité** | Répondre à votre demande ; traiter les signalements de vulnérabilité ou d'abus ; assurer le suivi des incidents. |
| **Personnes concernées** | Vous, et toute personne que vous mentionnez dans votre message. |
| **Base légale** | **Intérêt légitime** (art. 6-1-f RGPD) : répondre à une demande et assurer la sécurité du service. Lorsque votre message tend à l'exercice d'un droit (section 9), le traitement est fondé sur l'**obligation légale** de l'article 6-1-c. |
| **Destinataire** | L'éditeur, sur sa boîte de courrier électronique (service d'hébergement de messagerie : **Google — Gmail**). |
| **Durée** | Conservation pendant le traitement de la demande, puis **12 mois** après la dernière réponse, puis suppression définitive. |
| **Transfert hors UE** | Oui, la messagerie utilisée étant hébergée par Google. Voir section 6. |
| **Avertissement** | N'envoyez ni mot de passe, ni clé d'accès (API key), ni donnée sensible dans un message ; si votre signalement en contient, elles peuvent être tronquées dans les échanges. |

### 5.7 Permissions Android et service d'accessibilité

L'application demande les permissions suivantes. Aucune n'est utilisée à d'autres fins que celles décrites ici.

| Permission | Pourquoi | Ce qui n'est pas fait |
|:--|:--|:--|
| **Service d'accessibilité** | Détecter une commande de déclenchement en fin de texte dans l'application au premier plan, puis remplacer le texte par le résultat. | Le texte n'est **pas** lu en continu : seuls les changements de texte sont examinés à la recherche d'une commande. Les champs de mot de passe sont ignorés. Aucun texte n'est transmis tant qu'aucune commande n'est reconnue. Rien n'est conservé par l'éditeur. |
| **Internet** | Joindre le fournisseur d'IA configuré et vérifier les mises à jour. | Aucun appel vers un serveur de l'éditeur : il n'en existe pas. |
| **Notifications** | Afficher la notification de mise à jour disponible. | Aucune notification publicitaire ou promotionnelle. |
| **Vibration** | Retour haptique lors des actions. | — |
| **Redémarrage** | Retrouver son état après un redémarrage du téléphone. | Aucune donnée transmise. |

Si vous refusez ou retirez l'autorisation d'accessibilité, l'application cesse de fonctionner dans les autres applications ; les autres fonctions restent disponibles.

---

## 6. Transferts hors de l'Union européenne

L'éditeur **ne transfère aucune donnée personnelle** : il n'en détient aucune. Les transferts décrits ici sont ceux que **votre propre configuration** déclenche, vers les fournisseurs que vous choisissez.

### 6.1 Le fournisseur d'IA que vous sélectionnez

| Fournisseur | Destination | Garanties connues au 20 septembre 2026 |
|:--|:--|:--|
| **Google — Gemini API** | États-Unis (cache possible dans tout pays où Google opère) | Google LLC est certifié au titre du **cadre de protection des données UE–États-Unis** (EU–US DPF). Le traitement relève du *Data Processing Addendum* de Google Cloud, qui intègre les **clauses contractuelles types** de la Commission. Pour les utilisateurs de l'EEE, du Royaume-Uni et de la Suisse, les conditions des « services payants » s'appliquent même au palier gratuit : **les textes ne servent pas à entraîner les modèles**. Les journaux techniques sont conservés environ **55 jours** pour la lutte contre les abus. |
| **Groq** | États-Unis (buckets Google Cloud) | L'accord de service de Groq **interdit contractuellement** l'entraînement sur vos entrées et sorties. Par défaut, Groq **ne conserve pas** les données d'inférence ; une journalisation limitée peut subsister jusqu'à **30 jours** en cas de dépannage ou d'enquête pour abus. Une option de **conservation nulle** (ZDR) est activable vous-même dans la console. Le DPA intègre les clauses contractuelles types de l'UE et l'addendum britannique. |
| **NVIDIA NIM** | États-Unis | **[À VÉRIFIER]** Reportez-vous au DPA et à la politique de confidentialité de NVIDIA avant d'envoyer des données personnelles. Ce document sera complété à la vérification. |
| **OpenRouter** | États-Unis (service de routage vers des fournisseurs tiers) | **[À VÉRIFIER]** OpenRouter route vers des fournisseurs dont les politiques diffèrent. Un réglage de compte permet de refuser l'entraînement sur les requêtes : **désactivez-le si vous ne l'avez pas déjà fait**. |
| **DeepSeek** | 🇨🇳 **Chine** | ⚠️ **Aucune décision d'adéquation, aucune clause contractuelle type publiée.** Le transfert vers la Chine ne dispose d'aucune garantie documentée au sens du chapitre V du RGPD, et les autorités de contrôle européennes ont ouvert des enquêtes sur ce service. **N'utilisez pas ce fournisseur pour un texte contenant des données personnelles**, les vôtres comme celles de tiers. |
| **Endpoint personnalisé (Custom)** | Là où **vous** l'hébergez : souvent un serveur sur votre propre réseau local (Ollama, LM Studio, vLLM) | Aucun transfert : les données restent sur votre réseau. En HTTP sur réseau local, le trafic n'est pas chiffré — l'application vous en avertit. |

### 6.2 L'hébergeur et la messagerie

| Destinataire | Destination | Garanties connues au 20 septembre 2026 |
|:--|:--|:--|
| **GitHub** (hébergement du service, releases, vérification de mise à jour) | États-Unis et Pays-Bas — GitHub B.V. est l'entité contractante pour l'Union européenne | GitHub déclare adhérer au **cadre de protection des données UE–États-Unis** et à son extension britannique, et s'appuie sur les clauses contractuelles types pour les autres transferts. |
| **Google — Gmail** (messagerie de contact) | États-Unis | Google LLC est certifié au titre du cadre de protection des données UE–États-Unis. |

---

## 7. Durées de conservation — vue d'ensemble

| Donnée | Où | Durée | Qui l'efface |
|:--|:--|:--|:--|
| Texte envoyé à un fournisseur | Chez le fournisseur | Jamais conservé par l'éditeur ; chez le fournisseur, selon la section 6.1 | Le fournisseur, selon sa politique |
| Texte d'entrée et de sortie (historique local) | Sur votre appareil | **Désactivé par défaut.** 30 jours par défaut si activé, 365 jours au maximum, 100 entrées au plus | Vous, en une action |
| Clés d'accès | Sur votre appareil, chiffrées | Jusqu'à votre suppression ou la désinstallation | Vous |
| Préférences, commandes personnalisées, choix de modèle | Sur votre appareil | Idem | Vous |
| Statistiques d'usage | Sur votre appareil | Jusqu'à la remise à zéro ou la désinstallation | Vous |
| Version déjà notifiée (mise à jour) | Sur votre appareil | Jusqu'à la prochaine notification | Vous, en désinstallant |
| Emails de contact | Sur la messagerie de l'éditeur | **12 mois** après la dernière réponse | L'éditeur |

---

## 8. Destinataires et sous-traitants

L'éditeur ne fait appel à **aucun sous-traitant** pour traiter vos données : il n'en traite aucune. Les seuls destinataires sont ceux que votre configuration détermine :

| Destinataire | Rôle | Données reçues |
|:--|:--|:--|
| Fournisseur d'IA sélectionné (Google, Groq, NVIDIA, OpenRouter, DeepSeek ou votre endpoint) | Fournir la réponse du modèle | Le texte que vous soumettez, votre clé d'accès, les données techniques de la requête |
| GitHub (hébergement, releases) | Distribuer l'application, héberger le code et les signalements | Les données de connexion à la plateforme lorsque vous la consultez ; l'adresse IP et la version lors de la vérification de mise à jour |
| Google (Gmail) | Réception des emails de contact | Votre adresse, le contenu de votre message |
| GitHub Sponsors | Traitement des dons volontaires, si vous en faites | Les données que **vous** fournissez à GitHub à cette occasion — l'éditeur ne reçoit que votre nom d'utilisateur public et le montant, jamais de données bancaires |

**Aucune donnée n'est vendue, louée, partagée à des fins publicitaires ou utilisée pour entraîner un modèle par l'éditeur.** Il n'a ni les moyens ni la volonté de le faire : il ne reçoit rien.

---

## 9. Vos droits et comment les exercer

### 9.1 Les droits

Vous disposez des droits suivants sur vos données personnelles :

| Droit | Ce qu'il signifie concrètement ici |
|:--|:--|
| **Accès** (art. 15) | Savoir si des données vous concernant sont traitées et en obtenir copie. Dans le cas présent : l'éditeur n'en détient aucune, sauf nos échanges par email. |
| **Rectification** (art. 16) | Corriger une donnée inexacte. |
| **Effacement** (art. 17) | Obtenir la suppression de vos données. Pour les données locales, l'effacement est **immédiat et vous appartient** : réglages, ou désinstallation. |
| **Opposition** (art. 21) | Vous opposer à un traitement fondé sur l'intérêt légitime — concrètement : désactiver les notifications, ou cesser d'utiliser les commandes IA. |
| **Limitation** (art. 18) | Geler l'utilisation de vos données pendant un désaccord. |
| **Portabilité** (art. 20) | Recevoir vos données dans un format lisible. Les données locales de l'application sont exportables par la fonction de sauvegarde intégrée (sans les clés d'accès, qui ne sont jamais exportées en clair). |
| **Retrait du consentement** (art. 7-3) | Retirer à tout moment un consentement donné, sans affecter la licéité des traitements antérieurs. |
| **Réclamation** (art. 77) | Saisir une autorité de contrôle. Voir section 15. |

**Aucune décision entièrement automatisée** produisant des effets juridiques ou significatifs n'est mise en œuvre (art. 22) : il n'existe ni profilage, ni notation, ni tri automatisé. Voir section 12.

### 9.2 Comment les exercer

Écrivez à **jcversa16@gmail.com**, en précisant l'objet de votre demande. Les demandes sont traitées dans un délai d'**un mois** (prorogeable de deux mois pour les demandes complexes, avec information de votre part dans ce cas).

Une précision importante, par honnêteté : pour les données transmises à un fournisseur d'IA, **l'éditeur n'en détient aucune copie** et ne peut donc ni les consulter, ni les supprimer. Une demande portant sur ces données doit être adressée **directement au fournisseur concerné**, qui en est le destinataire et applique sa propre politique. Sur simple demande, l'éditeur vous indiquera où adresser votre demande.

---

## 10. Sécurité

Mesures techniques effectivement en place (vérifiables dans le code source, publié sous licence MIT) :

| Mesure | Détail |
|:--|:--|
| Chiffrement des clés | AES-256-GCM, clé non exportable détenue par l'Android Keystore. Un échec de chiffrement provoque un refus d'écriture, jamais un repli en clair. |
| Transport | HTTPS exigé pour tout fournisseur distant. Les redirections HTTP automatiques sont désactivées, pour qu'une clé ne puisse être redirigée vers un autre hôte ni vers une connexion non chiffrée. |
| Réseau local | HTTP toléré uniquement vers des adresses privées de réseau local, avec avertissement explicite de l'absence de chiffrement. |
| Fuite de secrets | Les clés sont masquées dans les messages d'erreur avant tout affichage. |
| Sauvegardes | Sauvegardes automatiques Android (cloud et transfert d'appareil) désactivées pour les préférences sensibles. La sauvegarde manuelle exclut les clés et l'historique. |
| Télémétrie | Aucune. Ni analyse d'audience, ni rapport de plantage automatique. |

**Violation de données** : si une violation susceptible d'engendrer un risque élevé pour vos droits était portée à la connaissance de l'éditeur, elle serait notifiée à la CNIL dans les 72 heures (art. 33) et, si nécessaire, aux personnes concernées (art. 34), par les moyens disponibles — l'application n'étant pas connectée à un serveur de l'éditeur, l'information devrait passer par le dépôt public et les notes de version.

---

## 11. Mineurs

Le service **n'est pas destiné aux enfants**. Il n'est pas conçu pour eux, ne leur adresse aucune communication et ne collecte aucune donnée les concernant — l'éditeur ne collecte d'ailleurs aucune donnée, quel que soit l'âge.

En France, le consentement d'un mineur de moins de **15 ans** est requis du titulaire de l'autorité parentale pour s'inscrire à un service de la société de l'information (art. 45 de la loi n° 78-17). Aucune inscription n'étant proposée, cette situation ne se présente pas.

Si vous êtes parent et constatez que votre enfant utilise l'application, vous pouvez la désinstaller : aucune donnée n'est détenue par l'éditeur, aucune suppression à distance n'est nécessaire.

---

## 12. Cookies, traceurs et décisions automatisées

- **Cookies** : l'application n'en utilise aucun. Elle n'embarque aucun navigateur, aucune régie publicitaire, aucun script tiers.
- **Traceurs et identification** : aucun identifiant publicitaire, aucun identifiant d'appareil n'est collecté ni transmis.
- **Stockage local** : l'application écrit des données dans son espace privé (clés chiffrées, préférences, historique si activé). Ce stockage est **strictement nécessaire au fonctionnement du service que vous demandez** et ne requiert, à ce titre, aucun consentement préalable au sens de l'article 82 de la loi « Informatique et libertés ».
- **Décisions automatisées et profilage** : aucun (art. 22 RGPD). Aucune décision vous concernant n'est prise par un algorithme.

---

## 13. Absence de télémétrie, de publicité et de revente

- **Aucune mesure d'audience.** L'éditeur ne sait pas combien de personnes utilisent l'application, ni comment elles l'utilisent.
- **Aucun rapport de plantage automatique.** Un dysfonctionnement n'est connu que si vous le signalez.
- **Aucune publicité**, aucun partage de données à des fins publicitaires.
- **Aucune vente ni location de données.**
- Les statistiques de téléchargement et d'étoiles visibles sur GitHub sont des **données agrégées fournies par la plateforme** à l'éditeur ; elles ne contiennent pas de donnée personnelle vous concernant.

---

## 14. Modifications de cette politique

Toute modification est publiée dans le dépôt du projet, avec un incrément de version et de date en tête de ce document, et un report dans l'historique ci-dessous.

Une modification **substantielle** (nouveau fournisseur, nouveau traitement, changement de base légale, transfert vers un pays supplémentaire) sera signalée dans les notes de version de l'application, afin que vous puissiez la constater avant de mettre à jour.

En cas de désaccord avec une version modifiée, vous pouvez désinstaller l'application : aucune donnée n'étant détenue par l'éditeur, il n'y a rien à supprimer à distance.

---

## 15. Réclamation

Si vous estimez que vos données sont traitées en violation du RGPD, vous pouvez adresser une réclamation à l'éditeur (**jcversa16@gmail.com**), puis, sans attendre, à l'autorité de contrôle compétente.

**En France :**

> Commission nationale de l'informatique et des libertés (CNIL)
> 3 place de Fontenoy, TSA 80715, 75334 Paris Cedex 07
> Site de déclaration en ligne : `cnil.fr`
> Téléphone : +33 1 53 73 22 22

Si vous résidez dans un autre État de l'Union, vous pouvez saisir l'autorité de contrôle de votre pays de résidence habituelle ou de votre lieu de travail.

---

## 16. Historique des versions

| Version | Date | Modification |
|:--|:--|:--|
| 1.0 | 20 septembre 2026 | Création du document. Sept traitements décrits (transmission au fournisseur d'IA, vérification de mise à jour, clés d'accès, historique local optionnel, statistiques locales, correspondance email, permissions), bases légales, durées, destinataires, transferts hors UE, droits et sécurité. |
