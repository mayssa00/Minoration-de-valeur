# Minoration-de-valeur
Ce projet vise à mettre à disposition un traitement qui permet la detection de fraude suite à la declaration des valeurs minorées par certains operateur dans le but de reduire les droits et les taxes de douane.
les résultats de ce traitement permet à aider les analystes lors de la phase de levée de doute.
## Comment l'utiliser
ce projet est de construction modulaire,


```
├───Minoration_valeur
          ├───conf
          ├───src
              ├───main.py
              ├───dataPrep.py
              ├───modelisation.py
              ├───statDesc.py
              ├───cartographie.py
              ├───prepFrontEnd.py
```
## à quoi sert chaque module ?
* conf==> ce repertoire contient les fichiers de configurations necessaires pour le projet
* src ==> regroupe les differents scripts du projet.
* src/main ==>Le lancement du programme se fait apartir de cette classe qui fait appel aux fonctions implémentées dans les autres classes 
* src/dataPrep: ce script permet de réaliser la preparation des données et effectuer les calculs necessaire pour la detection d'anomalie au sens statistique 
* src/modelisation ==> ce sript a pour but de mettre en place un modele predictif qui permet de calculer la valeur statistique réelle ( celle qui aurait du étre declaré par l'operateur)
* src/statDesc ==> ce script permet de realiser des statistiques descriptives
* src/cartographie ==> permer d'avoir une cartographie/listing de certaines informations
* src/prepFrontEnd ==> ce spript permet de preparer les données necessaires pour la partie front end
## description des fonctions qui se trouvent dans chaque modules ?
 
 
> dataPrep
* def_perimetre(table_name_intput)
Cette fonction a pour vocation de definir le perimetre des données sur les quelles on va travailler en applicant certaines régles définies par les metiers.
*extract_doublons(table_globale_genere)
Permet d'eleminer les doublons qui peuvent exister dans la table
*create_cd_pays(table_name, listpays)
Permet de rajouter l'information par rapport aux pays d'origine dans la table a partir d'un fichier csv stocké sur hdfs
*create_lb_marchandise(table_name,listmarchandise)
Permet de rajouter l'information par rapport au libellé  marchandise dans la table a partir d'un fichier csv stocké sur hdfs
*create_variables()

*calcul_ratio()
cette fonction permet de calculer les ratios pour en deduire le degré d'anomalie 
*join_siren()
permet de faire un rapprochement avec la table siren pour en récuprer certaines informations
*extract_whitelist()
*extract_error_MN()
*select_variables()





Afin de realiser la detection d'anomalie le projet  repose sur 2 aspects : statistique et predictif




 



