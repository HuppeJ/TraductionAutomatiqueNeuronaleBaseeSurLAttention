# Effective Approaches to Attention-based Neural Machine Tranlation

L'objectif de ce travail consiste à explorer les résultats obtenus dans l'article [Effective Approaches to Attention-based Neural Machine Translation](https://arxiv.org/abs/1508.04025) et de reproduire certain des ces résultats. 

Certaines parties de ce notebook sont basées sur le tutoriel [Neural machine translation with attention](https://www.tensorflow.org/tutorials/text/nmt_with_attention).


Ce notebook détail les implémentations des modèles utilisés pour la traduction de phrase d'anglais à français. Le dataset utilisé pour l'entraînement et l'évaluation de nos modèles provient du site http://www.manythings.org/anki/.


Travail présenté par : 

- Fabrice Charbonneau
- Antoine Daigneault-Demers
- Jérémie Huppé

## Structure du repo
- Notre notebook principal est disponible directement (Luong_Attention_Code_Source.ipynb)
- Le dossier Trace_de_exécutions contient les notebooks avec les sorties de l'exécution des 3 modèles
- Le dossier Données_tableaux contient les fichiers csv et le script utilisés pour générer nos graphiques. 

## Détails d'implémentation

### Encodeur 
- Un stack de 2 couches LSTM de 1000 units avec dropout de 0.2 optionnel

### Attention 

Deux implémentations de méchanismes d'attention sont présentées dans ce notebook :

- Attention globale avec score dot
- Attention local-p avec score general et une taille de fenêtre D = 10

### Décodeur 
- Un stack de 2 couches LSTM de 1000 units avec dropout de 0.2 optionnel
- Avec ou sans un méchanisme d'attention pour la prédiction
- Utilisation du principe de teacher forcing lors de l'entraînement

### Paramètres d'entraînement

Voici les paramètres utilisés lors de l'entraînement des différents modèles :

- BATCH_SIZE = 128
- embedding_dim = 1000
