# Politique de Confidentialité et de Protection des Données

**Dernière mise à jour : 31 Janvier 2026**
**Version : 1.2**

## 1. Préambule et Engagement
La présente politique de confidentialité (ci-après la "Politique") détaille les modalités de collecte, de traitement et de protection des données personnelles par l'application **Listy** (ci-après l'"Application"), éditée par le Développeur, **Dorian Faye** (ci-après "Nous").

Nous nous engageons à respecter scrupuleusement le Règlement Général sur la Protection des Données (**RGPD**) de l'UE et le **CCPA** (California Consumer Privacy Act). Vos données sont stockées de manière sécurisée et isolée via des règles de sécurité strictes (Row Level Security).

## 2. Identité du Responsable du Traitement
Le responsable du traitement des données (Data Controller) est le développeur de l'Application.
Pour toute question relative à vos données, vous pouvez contacter le Délégué à la Protection des Données (DPO) à l'adresse suivante :
**fayedorian@gmail.com**

## 3. Nature des Données Collectées

Nous minimisons la collecte de données. Les données traitées se divisent en plusieurs catégories :

### 3.1. Données Personnelles (Stockage Sécurisé)
Ces données sont stockées dans votre espace dédié sur nos serveurs sécurisés (`Supabase`). L'accès est strictement limité à votre compte utilisateur via des règles de sécurité (RLS).
*   **Contenu :** Listes de courses, noms des articles, prix, budgets, participants aux listes, photos d'articles/reçus, historique de scans (code-barres, prix, devise, prix normalisé en EUR, date/heure, catégorie, indicateur de suspicion), données de profil (nom d'affichage, photo) et identifiants techniques d'authentification.
*   **Finalité :** Synchronisation entre vos appareils, partage avec vos proches, calculs budgétaires et maintien de l'historique.

Certaines préférences et informations de profil peuvent être synchronisées via **iCloud (NSUbiquitousKeyValueStore)** afin d'assurer une continuité entre vos appareils Apple.

### 3.2. Données Techniques et d'Utilisation (Analytique)
Nous collectons des données pseudonymisées pour comprendre l'utilisation de l'app, améliorer la qualité et corriger les bugs.
*   **Outil utilisé :** **PostHog** (Hébergé en Union Européenne).
*   **Données :** Identifiant unique d'installation (anonyme), pages vues (`screen_views`), interactions principales (ex : "reçu importé", "alerte prix inhabituel"), version de l'OS, modèle de l'appareil, événements techniques.
*   **Finalité :** Amélioration du produit, stabilité, détection de comportements anormaux.

### 3.3. Données Communautaires (Crowdsourcing)
Données que vous choisissez de rendre publiques pour aider la communauté.
*   **Stockage :** Base de données publique (`Supabase Public Tables`).
*   **Données :** Associations "Code-barres <-> Nom du produit <-> Catégorie", marques, images publiques, prix **agrégés** (moyenne, nombre de relevés, date de dernière observation).
*   **Finalité :** Alimenter la base de connaissances partagée de l'Application.

### 3.4. Données de Modération et Prévention des Abus
Pour protéger l'intégrité des données communautaires, nous appliquons des contrôles automatisés.
*   **Traitements :** Détection d'anomalies de prix, application de bornes par catégorie, marquage des contributions suspectes.
*   **Effets :** Les contributions suspectes peuvent être exclues des agrégats publics et utilisées pour limiter l'accès aux fonctionnalités communautaires en cas d'abus répétés.

## 4. Traitement des Données et Services Tiers

L'Application s'appuie sur des sous-traitants (Data Processors) rigoureusement sélectionnés.

| Service | Type de Données | Localisation | Finalité |
| :--- | :--- | :--- | :--- |
| **Supabase** | Contenu utilisateur, Auth, données communautaires | Monde (AWS) | Hébergement sécurisé, authentification et synchronisation. |
| **PostHog** | Analytique d'usage, télémétrie | **Union Européenne** (Francfort) | Analyse d'audience et amélioration produit. |
| **Open Food Facts** | Code-barres, adresse IP | Monde | Récupération des infos nutritionnelles. |
| **Open Beauty Facts** | Code-barres, adresse IP | Monde | Récupération des infos cosmétiques. |
| **Frankfurter API** | Codes devises, adresse IP | Monde | Récupération des taux de change. |
| **Apple Vision** | Images (Reçus) | **Local (On-Device)** | OCR et extraction de texte. Aucune image n'est envoyée dans le cloud pour ce traitement. |
| **Apple iCloud (KVS)** | Préférences, profil (nom/photo, devise) | Monde (Apple) | Synchronisation des préférences entre appareils Apple. |

**Note spécifique sur Open Food Facts / Open Beauty Facts :**
L'utilisation du scanner de code-barres implique l'envoi du code scanné à leurs API publiques. Cette requête expose transitoirement votre adresse IP à leurs serveurs pour l'acheminement de la réponse. **Aucun identifiant personnel (nom, e-mail, ID utilisateur) n'est transmis lors du scan.**

**Note spécifique sur Frankfurter API :**
Les conversions de devises utilisent des taux publiés par Frankfurter. Les taux sont indicatifs et peuvent différer des taux bancaires réels.

## 5. Bases Légales du Traitement (RGPD)

*   **Exécution du contrat (Art. 6.1.b) :** Pour la synchronisation, le partage et le fonctionnement de base de l'app.
*   **Intérêt légitime (Art. 6.1.f) :** Pour l'analyse d'audience (PostHog), la sécurité, la prévention des abus et la qualité des données communautaires.
*   **Consentement (Art. 6.1.a) :** Pour l'accès aux capteurs (Caméra, Photos) et l'envoi de rapports de bugs volontaires.

## 6. Transferts de Données Hors UE

*   **PostHog :** Les données analytiques sont hébergées au sein de l'UE (`eu.i.posthog.com`).
*   **Supabase :** Peut transférer des données via AWS (généralement Francfort ou USA). Ce transfert est couvert par les standards de sécurité de l'industrie.
*   **Apple iCloud :** Les données peuvent être traitées dans les centres de données d'Apple, conformément à leur politique.

## 7. Durée de Conservation

*   **Données utilisateur (Supabase) :** Conservées tant que vous ne supprimez pas votre compte ou vos données.
*   **Données analytiques (PostHog) :** Conservées pour une durée limitée, puis supprimées ou anonymisées.
*   **Rapports de bugs :** Conservés jusqu'à résolution du bug, maximum 6 mois.
*   **Données communautaires :** Les agrégats publics peuvent être conservés même après suppression du compte, sous forme non identifiante.

## 8. Vos Droits (RGPD & CCPA)

Vous disposez des droits suivants sur vos données :

1.  **Droit d'accès et de portabilité :** Vous pouvez demander une copie de vos données en nous contactant.
2.  **Droit de rectification :** Vous pouvez modifier vos listes directement dans l'application.
3.  **Droit à l'effacement ("Droit à l'oubli") :**
    *   **Contenu :** Vous pouvez utiliser le bouton "Supprimer mon compte" situé dans les réglages de l'application (Section "Mon Profil").
    *   **Analytique :** Contactez-nous pour demander la suppression de votre historique d'usage si vous n'utilisez plus l'application.
    *   **Note :** Certaines données communautaires agrégées peuvent subsister sous forme non identifiante.
4.  **Droit d'opposition :** Vous pouvez refuser le suivi analytique en nous contactant. **Note importante :** L'application n'utilise pas d'identifiant publicitaire (IDFA) et ne pratique pas de suivi publicitaire ("Tracking") au sens de la directive AppTrackingTransparency d'Apple.

## 9. Sécurité

Nous appliquons des mesures de sécurité strictes :
*   Utilisation exclusive de connexions chiffrées (HTTPS/TLS) pour toutes les communications externes.
*   L'authentification repose sur l'infrastructure Apple ID (MFA, Biométrie) et l'infrastructure Supabase Auth.
*   Accès restreint aux bases de données de développement.

## 10. Contact Juridique

Pour toute demande légale, demande d'exercice de droits ou question sur cette politique :
*   **Email :** fayedorian@gmail.com
