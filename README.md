# Analyse des types de Tweet avec BERT

## Présentation du projet

Ce projet vise à analyser les types des tweets sur un ensemble de données en s'appuyant sur le modèle BERT perfectionné pour la classification des tweets, avec une attention particulière portée à la détection des types des tweets. Grâce aux capacités avancées de compréhension du langage naturel de BERT, le modèle peut identifier et catégoriser efficacement les contenus dans les tweets, contribuant ainsi à un environnement en ligne plus sûr. 

## Objectif du projet

L'objectif principal est de classer les tweets en fonction des types suivants: sexual_violence, Physical_violence, emotional_violence, Harmful_Traditional_practice, economic_violence. 

Comme nous l'avons dit précédement, le projet utilise **BERT** (Bidirectional Encoder Representations from Transformers), un modèle de pointe pour les tâches de traitement du langage naturel, afin d'atteindre une grande précision. Après l'entrainement du modèle par BERT. Nous avons créer une interface avec gradio pour la classification de tweets en fonction de type. gradio a été préfére par l'enseignement vu qu'il offre une interface web conviviale pour l'analyse des types des tweets en temps réel. 

## Caractéristiques du modèle BERT

## L'Architecture de BERT

![tiré dans le papier de BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding] (images/image_bert.png)

### 1. Classification des tweets basée sur BERT

Le projet utilise un modèle BERT optimisé pour classer les tweets et identifier ceux qui contiennent des types de tweets.
**Utilisation :** La capacité de BERT à comprendre le contexte et les nuances de langage le rend très efficace pour des tâches telles que la detection des types de tweets.
**Fonctionnement :** Le modèle traite les tweets d'entrée et les affecte à des catégories prédéfinies (par exemple, sexual_violence, Physical_violence, emotional_violence, Harmful_Traditional_practice, economic_violence) en fonction du contenu détecté.

### 2. Modèle BERT optimisé

Le modèle BERT utilisé dans ce projet a été optimisé spécifiquement pour la détection du type de tweet.

**fonctionnement :** Le modèle BERT pré-entraîné est ensuite entraîné sur un ensemble de données contenant des exemples de tweets de harcèlement et de non-harcèlement, ce qui affine sa capacité à distinguer les deux.

**A.Préparation de l'environnement**

Par rapport à ce point nous voyons l'installations des toutes bibliothèques nécessaires pour la mise en oeuvre de cet entrainement avec BERT, nous avions vérifier faits quelques statistiques sur la variable type juste pour avoir une vision de l'ensemble.

**a) Chargement de jeu des données**

La taille de notre dataset est de **39650** et **3 variables (ou colonnes)** :

 - *1ere colonne* : **Tweet_ID**
 - *2eme colonne* : **tweet**, ici nous avons les textes ou les tweets
 - *3eme colonne* : **type** ou la catégorisation des textes.

<!-- **N.B :** nous avons utilisé un echantillon de 1000 textes, pour palier au problème de memoire, vous pouvez consulter cet article à la page 7 [BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding](https://arxiv.org/pdf/1810.04805) et [transformer préprocessing sur le site huggingface](https://huggingface.co/docs/transformers/main/en/preprocessing) -->

Dans ce point, nous avions vérifier les données manquantes, un petit accent a été mis sur la description et visualisation de la variable **type**. 

Nous avions lu des articles suivants pour attester le choix de l'échantillonnage concernant le problème des mémoires ou ressources des machines [REVISITING FEW-SAMPLE BERT FINE-TUNING](https://arxiv.org/pdf/2006.05987), [Effectiveness of Pre-training for Few-shot Intent Classification](https://arxiv.org/pdf/2109.05782), [A Comparison of LSTM and BERTfor Small Corpus](https://arxiv.org/pdf/2009.05451)
