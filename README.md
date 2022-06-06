LES AVIS CLIENTS AU SERVICE DE L'EXPERIENCE DES UTILISATRICES.

SUJET : 
Une société d'e-commerce spécialisée dans les protections menstruelles à fait appel à moi pour aider le service marketing à mettre en place une stratégie de fidélisation cliente.
Concidérent les avis utilisatrices comme une source d'information précieuse dans l'expérience cliente, nous avons décider d'analyser ces avis afin de mettre en évidence les relations entre sujets d'avis (topics) et les notes.

Ce projet à été réalisé en 5 étapes :

ETAPE 1 :

Télécharger la donnée (10 000 avis de clientes avec 85% d'avis positifs, note entre 4 et 5)
Vérfier les incohérences et nettoyer le fichier
Utiliser la librairie Spacy (Tokenization : Lemmatisation, filtre pour garder les verbes , noms, adjectifs et adverbes )



![image](https://user-images.githubusercontent.com/98116639/172199698-bb7b9e14-3179-46e9-8727-aa4325f1ed92.png)


ETAPE 2 :

La pipeline de traitement. 
En général, dans les projets de Machine Learning, les données doivent subir des transformations.
Pour ma part, j’ai utilisé tf-idf (de l'anglais term frequency-inverse document frequency).
Cette mesure statistique permet d'évaluer l'importance d'un terme contenu dans un ou des document(s).
Cette technique produit des matrices de même dimension permettant d’enlever :
les mots rares (min-df), 
trop fréquents (max-df) et 
de trouver les bigrammes  (ngram-range). « Ensemble de mot ayant une relation ».

![image](https://user-images.githubusercontent.com/98116639/172200817-0cae3d37-4081-4900-9cd4-b78d396d7690.png)


ETAPE 3 : 

Utilisation du modèle LDA (modèle qui m’a donné le meilleur résultat) 
L’algorithme génère un modèle de probabilité, qui va parcourir l’ensemble des avis clients, afin d’identifier des groupes de « sujet ».
Ces groupes de sujet sont mis en évidence en fonction de la probabilité de cooccurrence des mots.

![image](https://user-images.githubusercontent.com/98116639/172200933-ddf11c80-9586-4023-83be-5b57df6e3b7a.png)

ETAPE 4 :

Les metrics afin de pouvoir vérifier que le modèle correspond aux objectifs fixés soit les relations entres les mots des avis clients et les notes.

![image](https://user-images.githubusercontent.com/98116639/172201672-219abd51-d5a5-4348-b7bf-3283ee0dfb42.png)


Distribution de  la probabilité d’appartenir à un topic pour les avis avec les notes 1/5 

![image](https://user-images.githubusercontent.com/98116639/172201522-56535576-d5b8-4692-ade4-d0ec816c6d30.png)

ETAPE 5 :

Déploiement de l’application :

L’application est prête à être mise en production !
J’ai mis en place un Docker. L’application a été déployée sur Flask et hébergée sur Heroku

![image](https://user-images.githubusercontent.com/98116639/172202079-942ece57-aa05-49ae-9dea-5ff6db7d29a5.png)

LE RESULTAT : 

![image](https://user-images.githubusercontent.com/98116639/172202983-a8873a8d-9ceb-44f2-838e-5383a064be3e.png)



RETROUVEZ MA PRESENTATION EN VIDEO : https://vimeo.com/716861875/a13132a889



