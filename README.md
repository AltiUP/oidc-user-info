# OIDC User Info

**OIDC User Info** est un module complémentaire pour Drupal qui étend les fonctionnalités du module [OpenID Connect (OIDC)](https://www.drupal.org/project/oidc). Ce module permet de récupérer et d'utiliser des informations supplémentaires sur les utilisateurs à partir du point de terminaison `userinfo` fourni par le fournisseur d'identité OIDC.

## 📌 Fonctionnalités

- **Récupération des informations utilisateur** : Après l'authentification via OIDC, le module interroge le point de terminaison `userinfo` pour obtenir des données supplémentaires sur l'utilisateur, telles que le nom complet, l'adresse e-mail, l'image de profil, etc.
- **Mise à jour du profil utilisateur Drupal** : Les informations récupérées peuvent être utilisées pour compléter ou mettre à jour le profil utilisateur dans Drupal, assurant ainsi une cohérence entre les données du fournisseur d'identité et votre site.
- **Compatibilité avec divers fournisseurs OIDC** : Testé avec des fournisseurs tels que Google, Azure AD, Keycloak, etc.

## ⚙️ Prérequis

- **Drupal 9 ou supérieur** : Assurez-vous que votre site utilise une version compatible de Drupal.
- **Module [OpenID Connect](https://www.drupal.org/project/oidc)** : Ce module doit être installé et configuré pour gérer l'authentification OIDC de base.

## 🚀 Installation

1. **Téléchargement du module** : Clonez le dépôt dans le répertoire `modules/custom/` de votre installation Drupal.

   ```bash
   cd modules/custom/
   git clone https://github.com/AltiUP/oidc-user-info.git
   ```

2. **Activation du module** : Activez le module via Drush ou l'interface d'administration de Drupal.

   Avec Drush :

   ```bash
   drush en oidc_user_info -y
   ```

   Ou via l'interface d'administration :

   - Accédez à **Extend** (Extension) dans le menu d'administration.
   - Recherchez **OIDC User Info**.
   - Cochez la case correspondante et cliquez sur **Install** (Installer).

## ⚙️ Configuration

1. **Mapper les claims aux champs utilisateur Drupal** : Associez les données reçues du point de terminaison `userinfo` aux champs correspondants dans le profil utilisateur Drupal. Par exemple :

   - `first_name` → Prénom
   - `last_name` → Nom de famille
   - `email` → Adresse e-mail

   Ces claims sont définis par le fournisseur d'identité et peuvent varier.

4. **Tester la configuration** : Après avoir enregistré les paramètres, effectuez une connexion avec un compte utilisateur via OIDC pour vérifier que les informations sont correctement récupérées et mappées.

## 🛠️ Personnalisation

Si vous souhaitez étendre ou modifier le comportement du module :

- **Hooks** : Utilisez les hooks Drupal disponibles pour intervenir lors de la récupération ou du mappage des données utilisateur.
- **Services** : Le module expose des services que vous pouvez remplacer ou étendre selon vos besoins spécifiques.

## 📑 Ressources supplémentaires

- **Spécifications OpenID Connect** : Pour une compréhension approfondie du fonctionnement de OIDC et du point de terminaison `userinfo`, consultez la [documentation officielle](https://openid.net/specs/openid-connect-core-1_0.html#UserInfo).

## 🛡️ Support

Si vous rencontrez des problèmes ou avez des questions :

- **Tickets GitHub** : Ouvrez une issue sur le [dépôt GitHub](https://github.com/AltiUP/oidc-user-info/issues).
- **Forum Drupal** : Rejoignez la communauté sur [Drupal.org](https://www.drupal.org/forum) pour des discussions et de l'aide supplémentaires.

## 📚 Licence

Ce projet est distribué sous la licence MIT. Veuillez consulter le fichier [LICENSE](LICENSE) pour plus de détails.

---

En intégrant **OIDC User Info** à votre site Drupal, vous enrichissez les profils utilisateurs avec des données précises et à jour provenant de votre fournisseur d'identité, améliorant ainsi l'expérience utilisateur et la cohérence des données.

