
**Projet 3 - 70 heures** 

# Créez et utilisez une base de données immobilière avec SQL

À partir des données de votre agence immobilière, concevez et créez une base de données, puis faites des requêtes SQL pour extraire certaines données. 

## Compétences cibles:

 -  Charger des données dans une base de données
 -  Créer des tables dans une base de données
 -  Créer le schéma d'une base de données
 -   Effectuer  des requêtes SQL pour répondre à une problématique métier  
 - Mettre à jour un catalogue de données

## Outils:

 - Excel Power Query 
 - SQLiteStudio 
 - SQL Power Architect
 

## Livrables:

Modèle relationnelle des données:

![1](https://github.com/piplagrivka/openclassrooms/blob/main/Projets/Projet03/images/1.jpg)

Les tableaux:

![2](https://github.com/piplagrivka/openclassrooms/blob/main/Projets/Projet03/images/2.jpg)

Les requêtes:

    *1 Nombre total d'appartements vendus au 1er semestre 2020* 
    select 
    count(*) as nombre_appartements 
    from Vente v, Bien b 
    where b.id_bien = v.id_bien 
    and v.date>='2020-01-01' and v.date<'2020-07-01' 
    and b.Type_local="Appartement"


    *2 Le nombre de ventes d'appartement par région pour le 1er semestre 2020* 
    select r.nom_region, 
    count(v.id_vente) as nombre_de_ventes 
    from 
    Region r, Departement d, Commune c, Bien b, Vente v 
    where 
    r.id_code_region = d.id_code_region
    and d.id_code_departement = c.id_code_departement
    and c.id_code_dep_commune = b.id_code_dep_commune
    and b.id_bien = v.id_bien 
    and v.date>='2020-01-01' and v.date<'2020-07-01' 
    and b.Type_local="Appartement" 
    group by r.nom_region 
    order by count(v.id_vente) desc

    
    *10 Différence en pourcentage du prix au mètre carré entre un appartement de 2 pièces et un appartement de 3 pièces 
    with tab1 as ( 
    select 
    b.Total_pieces, 
    avg(v.valeur)/avg(b.Surface_car) as prix1 
    from Region r, Departement d, Commune c, Bien b, Vente v 
    where r.id_code_region = d.id_code_region 
    and d.id_code_departement = c.id_code_departement 
    and c.id_code_dep_commune = b.id_code_dep_commune 
    and b.id_bien = v.id_bien 
    and b.Type_local='Appartement' 
    group by b.Total_pieces 
    having b.Total_pieces=2), 
    tab2 as (select 
    b.Total_pieces, 
    avg(v.valeur)/avg(b.Surface_car) as prix2 
    from Region r, Departement d, Commune c, Bien b, Vente v 
    where r.id_code_region = d.id_code_region 
    and d.id_code_departement = c.id_code_departement 
    and c.id_code_dep_commune = b.id_code_dep_commune 
    and b.id_bien = v.id_bien 
    and b.Type_local='Appartement' 
    group by b.Total_pieces 
    having b.Total_pieces=3) 
    select 
    round(tab1.prix1, 2) as prix_2_pieces, 
    round(tab2.prix2,2) as prix_3_pieces, 
    100-round(tab2.prix2*100/tab1.prix1, 2) as difference_pourcentage 
    from tab1,tab2;
