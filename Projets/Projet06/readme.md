**Projet 6 - 100 heures** 

# Analysez les ventes d'une librairie avec R ou Python

 
Vous avez accès à toutes les données de vente de votre client, une librairie. Répondez à leurs demandes en analysant les comportements d'achats. 

## Compétences cibles:

 - Réaliser un test statistique 
 - Réaliser une analyse bivariée pour   interpréter des données 
  - Analyser des séries temporelles

## Outils:

 - Google Colab Notebooks 
 - Python, librairies: scipy.stats, pandas, numpy,  matplotlib, seaborn, os, datetime
 
## Livrables:
Google Colab Notebook: [analyse des ventes de la librairie](https://github.com/piplagrivka/openclassrooms/blob/main/Projets/Projet06/Projet6_Gerasimova_Anna_02_19032023.ipynb)

**Sujets travaillés:**

 1. présenter les différents indicateurs et graphiques autour du chiffre d'affaires, voir l’évolution dans le temps et mettre en place une décomposition en moyenne mobile pour évaluer la tendance globale
    
 2. faire un zoom sur les références, pour voir un peu les tops et les
    flops, la répartition par catégorie, etc. 
    
 3. quelques informations sur les profils de nos clients, et également la répartition du chiffre  d'affaires entre eux, via par exemple une courbe de Lorenz 
 4. le lien entre le genre d’un client et les catégories des livres achetés 
 5. le lien entre l’âge des clients et le montant total des achats, la fréquence d’achat, la taille du panier moyen et les catégories des livres achetés 
 6.  le lien entre le genre et le chiffre d'affaires

**Exemples de la réalisation:**

Chiffre d'affaire par jour avec SMA (moyenne mobile simple), CMA (moyenne mobile cumulée), EWM (moyenne mobile exponentielle):

![1](https://github.com/piplagrivka/openclassrooms/blob/main/Projets/Projet06/images/1.jpg)

Répartition de la clientèle par âge:

![2](https://github.com/piplagrivka/openclassrooms/blob/main/Projets/Projet06/images/2.jpg)

Chiffre d'affaire par client. Courbe de Lorentz:

![3](https://github.com/piplagrivka/openclassrooms/blob/main/Projets/Projet06/images/3.jpg)

Le lien entre le genre d’un client et les catégories des livres achetés:

![4](https://github.com/piplagrivka/openclassrooms/blob/main/Projets/Projet06/images/4.jpg)
