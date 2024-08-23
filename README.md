# Déployer une Application Streamlit sur Heroku

Ce guide vous expliquera comment déployer une application Streamlit à partir de ce dépôt GitHub sur Heroku.

## Prérequis

Avant de commencer, assurez-vous d'avoir les éléments suivants :

- [Git](https://git-scm.com/)
- [Python 3.11.3](https://www.python.org/downloads/)
- Un compte [Heroku](https://signup.heroku.com/)


## Étape 1 : Cloner le Dépôt

1. Clonez ce dépôt GitHub sur votre machine locale.

```bash
git clone https://github.com/bertrandfournel/heroku-test-bertrand.git
```

2.	Connectez-vous à votre compte GitHub.
3.	Créez un nouveau dépôt en cliquant sur le bouton “New repository”.
4.	Donnez un nom à votre nouveau dépôt et configurez les autres options selon vos besoins.
5.	Ne cochez pas l’option “Initialize this repository with a README”

```bash
cd heroku-test-bertrand
```

```bash
git remote set-url origin https://github.com/votre-nom-utilisateur/nom-du-nouveau-repo.git
```

6. Optionnel : La version Python est 3.11.3, installez un environnement virtuel avec venv (dans le dossier parent) : 

```bash
python -m venv ../env
```

7. Optionnel : Activez l'environnement (pour Linux et MacOS): 

```bash
. ../env/bin/activate
```


## Étape 2 : Créer une application sur Heroku

Pour créer une application sur Heroku, suivez les étapes suivantes :

1. Connectez-vous à votre compte Heroku sur le site [Heroku](https://www.heroku.com/).
2. Une fois connecté, cliquez sur le bouton "Create new app" pour créer une nouvelle application.
3. Donnez un nom à votre application et sélectionnez la région où vous souhaitez la déployer.
4. Cliquez sur le bouton "Create app" pour créer votre application sur Heroku.
5. Choisissez la méthode de déploiement avec Github dans Deployment method
6. Dans Connect to GitHub, choisissez votre repo personnel (préalablement, connectez votre compte github à votre compte Heroku)

## Étape 3 : Configurer l'application Heroku

1. Créez et récupérez votre clé API HEROKU (account settings)
2. Choisissez le Buildpack Python dans les settings de l'application
3. Dans Automatic deploys de l'onglet Deploy, cliquez sur Enable "Automatic Deploys"

## Étape 4 : Configurer le déploiement depuis Github

1. Dans le fichier workflows/main.yml, modifiez "heroku_app_name" par le nom de votre application Heroku, pushez les modifications
2. Allez dans les Settings de votre repo Github, puis "Secrets and variables" et "Actions" et rajouter deux repository secrets :
    * HEROKU_API_KEY, votre clé API heroku
    * HEROKU_EMAIL l'email qui vous avez renseigné pour créer votre compte Heroku


## Étape 5 : Déployez :

1. Faites les modifications sur le fichier app.py pour mettre en forme votre application. Pushez cette nouvelle version sur votre compte personnel github.

```bash
git add .
```

```bash
git commit -m "first deploy"
```

```bash
git push -u origin main
```

Les modifications sont en ligne quelques minutes après, pour les voir, cliquez sur "Open app" dans votre dahsboard Heroku
