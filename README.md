# Analyse des types de Tweet avec BERT

## Présentation du projet

Ce projet vise à analyser les types des tweets sur un ensemble de données. L'objectif principal est de classer les tweets en fonction des types suivants: sexual_violence, Physical_violence, emotional_violence, Harmful_Traditional_practice, economic_violence. Le projet utilise BERT (Bidirectional Encoder Representations from Transformers), un modèle de pointe pour les tâches de traitement du langage naturel, afin d'atteindre une grande précision. Il sied de signaler que notre entrainement du modèle va être fait avec BERT comme nous l'avons préciser précèdemment, après cette entrainement, nous avons créer une interface avec gradio pour la classification de tweets en fonction de type. gradio a été préfére par l'enseignement vu qu'il offre une interface web conviviale pour l'analyse des types des tweets en temps réel. 

### 1. Préparation de l'environnement

par rapport à ce point nous voyons l'installations des toutes bibliothèques nécessaires pour la mise en oeuvre de cet entrainement avec BERT, nous avions vérifier faits quelques statistiques sur la variable type juste pour avoir une vision de l'ensemble.

### a) Chargement de jeu des données

La taille de notre dataset est de **39650** et **3 variables (ou colonnes)** :

 - *1ere colonne* : **Tweet_ID**
 - *2eme colonne* : **tweet**, ici nous avons les textes ou les tweets
 - *3eme colonne* : **type** ou la catégorisation des textes.

<!-- **N.B :** nous avons utilisé un echantillon de 1000 textes, pour palier au problème de memoire, vous pouvez consulter cet article à la page 7 [BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding](https://arxiv.org/pdf/1810.04805) et [transformer préprocessing sur le site huggingface](https://huggingface.co/docs/transformers/main/en/preprocessing) -->