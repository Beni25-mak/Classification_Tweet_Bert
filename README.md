# Analyse des types de Tweet avec BERT

## Présentation du projet

Ce projet vise à analyser les types des tweets sur un ensemble de données. L'objectif principal est de classer les tweets en fonction des types suivants: sexual_violence, Physical_violence, emotional_violence, Harmful_Traditional_practice, economic_violence. Le projet utilise BERT (Bidirectional Encoder Representations from Transformers), un modèle de pointe pour les tâches de traitement du langage naturel, afin d'atteindre une grande précision. Il sied de signaler que notre entrainement du modèle va être fait avec BERT comme nous l'avons préciser précèdemment, après cette entrainement, nous avons créer une interface avec gradio pour la classification de tweets en fonction de type. gradio a été préfére par l'enseignement vu qu'il offre une interface web conviviale pour l'analyse des types des tweets en temps réel. 

## présentation du modèle BERT

BERT, pour Bidirectional Encoder Representations from Transformers, est un LLM (Large Language Model), entraîné sur un grand corpus de données textuelles et conçu pour générer du texte en langage naturel. Google AI a développé ce modèle en 2018, en utilisant des réseaux neuronaux. Cette technique de Machine Learning permet à l’algorithme de mieux comprendre le contexte d’une requête. 

Contrairement aux modèles antérieurs qui utilisaient une approche unidirectionnelle pour traiter le texte, BERT est capable de comprendre le contexte bidirectionnel du langage. Il prend donc en compte à la fois les mots précédents et les mots suivants dans une phrase. Cela lui permet de mieux comprendre le sens des mots et des phrases.

Diffusé en open source à la communauté scientifique en 2018, Google a annoncé en 2019 avoir appliqué la mise à jour sur son propre moteur de recherche et ses algorithmes.

a) Utilisation générale de BERT

Le modèle améliore la compréhension automatique du texte. Il permet d’extraire des informations, d’identifier des entités nommées et de faire de l’analyse textuelle en général. Il peut également générer des résumés automatiques de documents, même longs, en identifiant les parties les plus importantes du texte.. BERT est capable de répondre à des questions posées en langage naturel. Il comprend le contexte et génère des réponses pertinentes à partir de documents ou de corpus de texte.

Intégré dans des chatbots et des assistants virtuels, il améliore la compréhension des demandes des utilisateurs et génère des réponses plus naturelles. Le modèle capture les nuances et les contextes du langage source et cible. Il peut être utilisé pour améliorer la qualité des systèmes de traduction automatique. En analysant le contenu textuel, BERT peut déterminer le ton et l’émotion exprimés dans un texte.

BERT est utilisé dans les moteurs de recherche pour améliorer la pertinence des résultats en comprenant plus précisément la signification des requêtes et en identifiant des documents pertinents. Le modèle est également un composant des modèles de génération de texte. Il produit alors du contenu textuel, tant pour la rédaction automatique, que la génération de réponses de chatbot par exemple. Il peut aussi corriger grammaticalement un texte, en comprenant le contexte des phrases et en proposant des corrections adaptées.

b) Comment fonctionne le traitement de langage BERT ?

BERT repose sur une architecture de réseau de neurones profonds. Celle-ci permet à BERT de capturer des informations contextuelles bidirectionnelles et de s’adapter à différentes tâches de NLP.

## Le système de tokenisation
La tokenisation est un processus qui permet de découper une séquence de texte en unités plus petites, les tokens. Il peut s’agir d’un caractère, d’un mot ou d’une phrase, en fonction de la granularité. Cette étape est essentielle dans le traitement automatique du langage naturel, car il permet de préparer le texte brut pour des analyses plus approfondies.

## Le mécanisme Self-Attention
L’une de ses caractéristiques fondamentales est le mécanisme Self-Attention (auto attention). À chaque étape, chacun des mots de la séquence peut regarder les autres mots de manière à évaluer leur importance dans le contexte. Cela permet de comprendre les relations entre les mots à différentes distances dans une séquence.

## L’attention multitête
C’est le mécanisme clé d’une architecture Transformer. Le modèle va pouvoir tenir compte des relations entre les mots, tout en calculant des pondérations d’attention pour chaque paire de mots dans une séquence. Cela permet au modèle de déterminer l’importance des mots les uns par rapport aux autres.

## Empilement d’Encodeurs
Transformer utilise plusieurs couches d’encodeurs. Chacun se compose de deux sous-couches : une sous-couche d’auto attention multitêtes et une sous-couche de réseaux de neurones entièrement connectés (feedforward). Cela permet un apprentissage de représentations de plus en plus abstraites et contextuelles de la séquence.

## Positional Encoding ou encodage de position
Transformer n’a pas de notion intrinsèque d’ordre séquentiel. Les positional encoding s’ajoutent aux embeddings de mots pour donner à BERT une information sur la position des mots dans la séquence.

## Comprendre le fonctionnement de BERT
À ce jour, BERT existe sous différentes versions. Chacune ayant été entraînée sur divers types de corpus de données, aux volumes variables. On retrouve principalement deux versions, BERT-base et BERT-large.

BERT-base a été développé à partir d’un ensemble de données non labellisées composé de 800 millions de mots, extraits de BookCorpus. Celui-ci est constitué de textes provenant de 16 genres différents de livres libres de droits. De son côté, BERT-large a été entraîné sur un corpus bien plus volumineux contenant 2,5 milliards de mots, extraits des articles rédigés en anglais de Wikipédia.

## Pré entraînement
Durant cette phase, le modèle a été formé de manière non supervisée, sans données labellisées, sur deux tâches spécifiques.

Masked Language Modeling, c’est-à-dire la modélisation du langage masqué (MLM) consiste à demander au modèle de prédire des mots intentionnellement masqués dans une phrase. Le modèle devait deviner ces mots masqués en se basant sur le contexte fourni par les autres mots de la phrase.
Next Sentence Prediction, en français, prédiction de la phrase suivante (NSP). L’objectif est de faire prédire au modèle la séquence de mots suivante. Cette tâche vise à permettre au modèle de comprendre la continuité entre des phrases consécutives.

## Fine Tuning
Après la phase de pré-entraînement, BERT est fine-tuné sur des tâches spécifiques. Des couches supplémentaires s’ajoutent et sont entraînées sur des données annotées. Elles permettent à BERT de s’adapter aux exigences de tâches particulières.

## Modèles de langue dérivés
Référence dans le domaine des modèles de langue, BERT a également ses dérivés :

- RoBERTa, de Google AI Language, un modèle dont les paramètres de préentraînement permettent un traitement plus rapide ;
CamemBERT, développé par Facebook AI Research et l’Inria, est basé sur RoBERTa et entraîné sur un corpus de 138 Go en français, pour des tâches de remplissage et masquage ;
- FlauBERT, développé par le CNRS, aussi entraîné en français, mais sur 71 Go de data seulement ;
DistilBERT développé par Hugging Face, est une version plus petite et plus rapide de BERT, mais qui conserve toutefois le même niveau de performance.
## Impact de BERT sur le SEO
L’algorithme est venu modifier la façon dont les entreprises envisagent le référencement. Plutôt que de se focaliser sur des mots-clés particuliers, elles doivent désormais se concentrer sur la compréhension de l’intention de l’utilisateur.

Comme BERT donne la priorité aux requêtes en langage naturel, les contenus doivent s’aligner sur les modèles de langage du public cible. Une page web doit proposer du contenu de qualité en adéquation avec l’intention de recherche des utilisateurs. La réponse doit être aussi claire et précise que possible, pour pouvoir facilement être dictée par un assistant vocal.

## Quels sont les avantages de BERT ?

Le Large Language Model BERT apporte de nombreux avantages dans le domaine du traitement automatique du langage naturel (NLP) et de l’analyse textuelle. 

- Le modèle est adapté à une variété de tâches de traitement de texte, de la classification de texte à la traduction automatique, en passant par l’extraction d’entités nommées.
- Spécialement conçu pour saisir la signification des mots en fonction du contexte, il distingue les subtilités et les nuances du langage naturel.
- L’approche bidirectionnelle améliore considérablement sa capacité à comprendre le contexte global. 
- BERT réduit la nécessité de prétraiter manuellement le texte. Il a la capacité de gérer des données brutes avec moins de préparation.
- Il excelle dans la compréhension des questions posées en langage naturel. Il fournit des réponses plus pertinentes et précises aux questions des utilisateurs.
- La recherche vocale est améliorée grâce à sa capacité à comprendre les requêtes vocales formulées de manière naturelle.

Google BERT constitue une avancée significative dans le domaine du NLP. Grâce à sa capacité à saisir le contexte, il améliore la précision, la pertinence et l’adaptabilité du traitement linguistique. Sa polyvalence, notamment dans des langues multiples, en fait un outil puissant pour améliorer la compréhension des requêtes de recherche, l’expérience utilisateur et la qualité des résultats textuels.

### 1. Préparation de l'environnement

Par rapport à ce point nous voyons l'installations des toutes bibliothèques nécessaires pour la mise en oeuvre de cet entrainement avec BERT, nous avions vérifier faits quelques statistiques sur la variable type juste pour avoir une vision de l'ensemble.

### a) Chargement de jeu des données

La taille de notre dataset est de **39650** et **3 variables (ou colonnes)** :

 - *1ere colonne* : **Tweet_ID**
 - *2eme colonne* : **tweet**, ici nous avons les textes ou les tweets
 - *3eme colonne* : **type** ou la catégorisation des textes.

<!-- **N.B :** nous avons utilisé un echantillon de 1000 textes, pour palier au problème de memoire, vous pouvez consulter cet article à la page 7 [BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding](https://arxiv.org/pdf/1810.04805) et [transformer préprocessing sur le site huggingface](https://huggingface.co/docs/transformers/main/en/preprocessing) -->

Dans ce point, nous avions vérifier les données manquantes, un petit accent a été mis sur la description et visualisation de la variable **type**. 

