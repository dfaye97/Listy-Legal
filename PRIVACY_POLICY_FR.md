# Politique de Confidentialité et de Protection des Données

**Dernière mise à jour : 23 Janvier 2026**
**Version : 1.1**

## 1. Préambule et Engagement
La présente politique de confidentialité (ci-après la "Politique") détaille les modalités de collecte, de traitement et de protection des données personnelles par l'application **Listy** (ci-après l'"Application"), éditée par le Développeur, **Dorian Faye** (ci-après "Nous").

Nous nous engageons à respecter scrupuleusement le Règlement Général sur la Protection des Données (**RGPD**) de l'UE et le **CCPA** (California Consumer Privacy Act). Notre architecture est fondée sur le principe du **Privacy-First** : vos données sensibles sont stockées dans votre espace privé iCloud, auquel nous n'avons pas accès.

## 2. Identité du Responsable du Traitement
Le responsable du traitement des données (Data Controller) est le développeur de l'Application.
Pour toute question relative à vos données, vous pouvez contacter le Délégué à la Protection des Données (DPO) à l'adresse suivante :
**fayedorian@gmail.com**

## 3. Nature des Données Collectées

Nous minimisons la collecte de données. Les données traitées se divisent en trois catégories :

### 3.1. Données "Zero-Knowledge" (Stockage Privé iCloud)
Ces données sont stockées exclusivement dans votre base de données privée iCloud (`CloudKit Private Database`). Nous (le développeur) n'avons **aucun moyen technique** de les lire ou de les déchiffrer.
*   **Contenu :** Listes de courses, noms des articles, prix, photos de reçus, budget, participants aux listes.
*   **Finalité :** Synchronisation entre vos appareils et partage avec vos proches.

### 3.2. Données Techniques et d'Utilisation (Analytique)
Nous collectons des données pseudonymisées pour comprendre l'utilisation de l'app et corriger les bugs.
*   **Outil utilisé :** **PostHog** (Hébergé en Union Européenne).
*   **Données :** Identifiant unique d'installation (anonyme), pages vues (`screen_views`), interactions principales (ex: "reçu importé"), version de l'OS, modèle de l'appareil.
*   **Finalité :** Amélioration du produit, détection des fonctionnalités peu utilisées, stabilité.

### 3.3. Données Communautaires (Crowdsourcing)
Données que vous choisissez de rendre publiques pour aider la communauté.
*   **Stockage :** Base de données publique iCloud (`CloudKit Public Database`).
*   **Données :** Associations "Code-barres ↔ Nom du produit ↔ Catégorie", Prix (Moyenne et Dernier relevé).
*   **Finalité :** Alimenter la base de connaissances partagée de l'application.

## 4. Traitement des Données et Services Tiers

L'Application s'appuie sur des sous-traitants (Data Processors) rigoureusement sélectionnés.

| Service | Type de Données | Localisation | Finalité |
| :--- | :--- | :--- | :--- |
| **Apple iCloud** | Contenu utilisateur, Sauvegardes | Monde (USA/EU) | Hébergement sécurisé et synchronisation. |
| **PostHog** | Analytique d'usage, Télémétrie | **Union Européenne** (Francfort) | Analyse d'audience et amélioration produit. |
| **Open Food Facts** | Code-barres, Adresse IP | Monde | Récupération des infos nutritionnelles. |
| **Apple Vision** | Images (Reçus) | **Local (On-Device)** | OCR et extraction de texte. Aucune image n'est envoyée dans le cloud pour ce traitement. |

**Note spécifique sur Open Food Facts :**
L'utilisation du scanner de code-barres implique l'envoi du code scanné à l'API publique d'Open Food Facts. Cette requête expose transitoirement votre adresse IP à leurs serveurs pour l'acheminement de la réponse. **Aucun identifiant personnel (nom, e-mail, ID utilisateur) n'est transmis à Open Food Facts lors du scan.**

## 5. Bases Légales du Traitement (RGPD)

*   **Exécution du contrat (Art. 6.1.b) :** Pour la synchronisation iCloud et le fonctionnement de base de l'app.
*   **Intérêt Légitime (Art. 6.1.f) :** Pour l'analyse d'audience (PostHog) visant à améliorer l'Application et la sécurité (détection de crashs).
*   **Consentement (Art. 6.1.a) :** Pour l'accès aux capteurs (Caméra, Photos) et l'envoi de rapports de bugs volontaires.

## 6. Transferts de Données Hors UE

*   **PostHog :** Les données analytiques sont hébergées au sein de l'UE (`eu.i.posthog.com`).
*   **Apple iCloud :** Apple peut transférer des données aux USA. Ce transfert est couvert par les Clauses Contractuelles Types (CCT) et le Data Privacy Framework.

## 7. Durée de Conservation

*   **Données iCloud (Privé) :** Conservées tant que vous ne les supprimez pas de votre compte Apple ou de l'application.
*   **Données Analytiques (PostHog) :** Conservées pour une durée glissante de 12 mois, puis supprimées ou anonymisées.
*   **Rapports de Bugs :** Conservés jusqu'à résolution du bug, maximum 6 mois.

## 8. Vos Droits (RGPD & CCPA)

Vous disposez des droits suivants sur vos données :

1.  **Droit d'accès et de portabilité :** Vous pouvez demander une copie brute de vos données via Apple (Privacy Portal) ou nous contacter pour les données analytiques liées à votre ID anonyme (si disponible).
2.  **Droit de rectification :** Vous pouvez modifier vos listes directement dans l'application.
3.  **Droit à l'effacement ("Droit à l'oubli") :**
    *   **Contenu :** Vous pouvez utiliser le bouton "Supprimer mon compte" situé dans les réglages de l'application (Section "Mon Profil"). Cette action supprime immédiatement votre profil de la base de données privée iCloud et envoie un signal de suppression à notre service analytique (PostHog) avant de réinitialiser tous les identifiants locaux.
    *   **Analytique :** Contactez-nous pour demander la suppression de votre historique d'usage si vous n'utilisez plus l'application.
4.  **Droit d'opposition :** Vous pouvez refuser le suivi analytique en nous contactant. **Note importante :** L'application n'utilise pas d'identifiant publicitaire (IDFA) et ne pratique pas de suivi publicitaire ("Tracking") au sens de la directive AppTrackingTransparency d'Apple.

## 9. Sécurité

Nous appliquons des mesures de sécurité strictes :
*   Utilisation exclusive de connexions chiffrées (HTTPS/TLS) pour toutes les communications externes.
*   L'authentification repose entièrement sur l'infrastructure Apple ID (MFA, Biométrie).
*   Accès restreint aux bases de données de développement.

## 10. Contact Juridique

Pour toute demande légale, demande d'exercice de droits ou question sur cette politique :
*   **Email :** fayedorian@gmail.com
