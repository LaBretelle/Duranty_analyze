# Objectif de l'analyse des 22 pièces pour marionnettes de Duranty #

Ce programme permet de faire de l'analyse textuelle à partir des textes pour marionnettes de Louis-Edmond Duranty. 

L'arborescence fonctionne comme cela :
* 2 fichiers nommés "1862" et "1864" contenant les textes océrisés à partir de deux éditions numérisées sur Gallica
* un fichier "1864_segmente" contenant le texte de l'année 1864 océrisé divisé en 1 fichier.txt par texte de l'anthologie.
* un fichier "resultat" contenant quelques graphiques et données intéressantes prélevées ensuite
* un fichier "traitement" contenant toutes les analyses du texte faite avec Python

## IMPORTANT : où installer l'environnement virtuel ? ##

L'analyse est dans des jupyter notebook. Il faut aller dans : **./traitement/1864/** pour trouver l'endroit où il faut créer le fichier /env/.

# Installation de Ant Apache #

**IMPORTANT** : Il faut installer le compilateur Ant Apache.

Pour l'étape de Topic Modelling, nous utiliserons deux algorithmes : l'algorithme intégré de Gensim en python et l'algorithme de Mallet. L'algorithme de Mallet est téléchargé via l'application, mais étant écrit en java, il nécessite d'être compilé avant d'être utilisé.

Une case est dédiée à la compilation via Ant. Cependant, **il faut installer Ant Apache sur votre ordinateur pour que la compilation fonctionne**. En effet, j'utilise Ant Apache pour compiler l'algorithme de Mallet avant de l'utiliser.

Pour installer Ant Apache sur la distribution Ubuntu, il faut simplement taper en ligne de commande " sudo apt-get ant ".

# Fonctionnement #

## Installation de l'environnement virtuel ##

Il faut installer votre environnement virtuel dans le dossier "1864" (./traitement/1864), là où se trouve le requirements.txt, avec la commande :  virtualenv -p python3 venv 

Ensuite, il faut installer toutes les dépendances mentionnées dans le dossier requirements.txt grâce à la commande " pip install -r requirements.txt ".

## Problème à l'installation du corpus d'entraînement de spaCy ##

***IMPORTANT***

Le corpus d'entraînement pour la lemmatisation de spacy peut ne pas s'installer via le requirements (temps d'attente trop long), il faudra donc si besoin ajouter en outre dans votre terminal, une fois votre environnement virtuel activé, la commande suivante :
- python -m spacy download fr_core_web_sm
(et dans ce cas supprimer la dernière ligne du requirements : "https://github.com/explosion/spacy-models/releases/download/fr_core_news_sm-2.2.5/fr_core_news_sm-2.2.5.tar.gz" et relancer l'installation du requirements, car cela fera crasher l'installation de tous les autres packages)

Si cela ne fonctionne toujours pas, vous pouvez finalement tenter l'installation dans le Jupyter Notebook en créant une nouvelle cellule où vous écrirez puis activerez cela :
- pip install https://github.com/explosion/spacy-models/releases/download/fr_core_news_sm-2.2.5/fr_core_news_sm-2.2.5.tar.gz
Cependant, cette dernière méthode n'est pas une méthode correcte.




## Sens de lecture ##

Vous pouvez maintenant lancer votre jupyter notebook. Il faudra alors lancer **dans l'ordre** les fichiers en suivant l'ordre des "step" (step_1 puis step_2, etc...) indiqués dans le nom du fichier.



Enjoy :) 

