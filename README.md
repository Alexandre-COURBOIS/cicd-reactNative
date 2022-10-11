# Projet initialisé sous React Native.

Le projet peut-être trouvé sur Github à cette adresse : `https://github.com/Alexandre-COURBOIS/cicd-reactNative.git`

## Prise en main du projet :

Une fois le projet cloné via Github depuis l'adresse renseignée ci-dessus :

## Commandes executables : 

### Executer un `npm install`

Permet la mise en place des packets dont le projet à besoin pour fonctionner

### Generer l'apk se placer dans le dossier `/android`

- Utiliser la commande ./gradlew assembleRelease

### Github Action dans le fichier workflows :
`update_on_push.yaml`

- Ce github action ne s'execute que sur la branche master
- L'objectif de celui ci est d'installer le projet, ainsi que de générer l'apk android grace aux commandes :
````
- cd android
- ./gradlew assembleRelease
````
- En dernier lieu celui-ci se connecte au serveur via différentes Github actions secret key qui sont elles à définir sur github :

Variables à définir : Votre NomUtilisateur & NomDuProjet :

`https://github.com/VotreNomUtilisateur/NomDuProjet/settings/secrets/actions`

Différentes clées sont à définirs sur l'url adaptée précèdement renseignée en cliquant sur :
`New Repository Secret`

Créer :
```
- HOST : L'IP du remote server
- KEY  : Votre clé privé correspondant à la clé public renseignée sur le host server
- PORT : Port par défaut de la connexion ssh sur le server
- USERNAME : Votre nom d'utilisateur sur le server
```

Penser également à modifier dans le target path le nom d'utilisateur qui correspondra au votre sur le remote server

Une fois fait, chaque push sur votre dépot permettra la génération d'une version de l'apk automatisée et déposera celle-ci à la racine de votre utilisateur dans le fichier mobile.


