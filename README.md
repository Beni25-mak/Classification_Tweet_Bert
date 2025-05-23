# Analyse des types de Tweet avec BERT

## Présentation du projet

Ce projet vise à analyser les types des tweets sur un ensemble de données. L'objectif principal est de classer les tweets en fonction des types suivants: sexual_violence, Physical_violence, emotional_violence, Harmful_Traditional_practice, economic_violence. Le projet utilise BERT (Bidirectional Encoder Representations from Transformers), un modèle de pointe pour les tâches de traitement du langage naturel, afin d'atteindre une grande précision.

Le projet comprend également le prétraitement des données textuelles brutes, comme la suppression des caractères spéciaux, la tokenisation, la lemmatisation, la suppression des mots vides et la conversion du texte en minuscules. Le modèle est déployé avec gradio, offrant une interface web conviviale pour l'analyse des types des tweets en temps réel. Caractéristiques du projet

### 1. Préparation de l'environnement

par rapport à ce point nous voyons l'installations des toutes bibliothèques nécessaires 
pour la mise en oeuvre de cette modélisation avec BERT.

### 2. Chargement de jeu des données

La taille de notre dataset est de 39650 et 3 variables (ou colonnes) :
 - *1ere colonne* : Tweet_ID
 - *2eme colonne* : tweet, ici nous avons les textes ou les tweets
 - *3eme colonne* : type ou la catégorisation des textes.
