# Minoration-de-valeur
Ce projet vise à mettre à disposition un traitement qui permet la détection de fraude suite à la declaration des valeurs minorées par certains opérateurs dans le but de reduire les droits et les taxes de douane.
les résultats de ce traitement permettent à aider les analystes lors de la phase de levée de doute.
## Comment l'utiliser
ce projet est de construction modulaire,l'arboresence se présente comme ceci :

```
├───Minoration_valeur
          ├───conf
          ├───src
              ├───main
                  ├───utils
                      ├───dataPrep.py
                  ├───main.py ( donner à la classe main le nom du projets)
                  ├───modelisation.py
                  ├───statDesc.py
                  ├───cartographie.py
                  ├───prepFrontEnd.py
              ├───test
           
```
## à quoi sert chaque module ?
* conf==> ce repertoire contient les fichiers de configurations necessaires pour le projet
* src ==> regroupe les differents scripts du projet.
* src/main ==>Le lancement du programme se fait apartir de cette classe qui fait appel aux fonctions implémentées dans les autres classes 
* utils/dataPrep: ce script permet de réaliser la preparation des données et effectuer les calculs necessaire pour la detection d'anomalie au sens statistique 
* src/modelisation ==> ce sript a pour but de mettre en place un modele predictif qui permet de calculer la valeur statistique réelle ( celle qui aurait du étre declaré par l'operateur)
* src/statDesc ==> ce script permet de realiser des statistiques descriptives
* src/cartographie ==> permer d'avoir une cartographie/listing de certaines informations
* src/prepFrontEnd ==> ce script permet de préparer les données nécessaires pour la partie front end
* src/test ==> ce module contients les fonctions de tests unitaires 
## description des fonctions qui se trouvent dans chaque modules ?
 
> dataPrep
* def_perimetre(table_name_intput) :Cette fonction a pour vocation de definir le perimetre des données sur les quelles on va travailler en applicant certaines régles définies par les metiers.
* extract_doublons(table_globale_genere) :Permet d'eleminer les doublons qui peuvent exister dans la table
* create_cd_pays(table_name, listpays):Permet de rajouter l'information par rapport aux pays d'origine dans la table a partir d'un fichier csv stocké sur hdfs
* create_lb_marchandise(table_name,listmarchandise):Permet de rajouter l'information par rapport au libellé  marchandise dans la table a partir d'un fichier csv stocké sur hdfs.
* create_variables()

* calcul_ratio(): Cette fonction permet de calculer les ratios pour en deduire le degré d'anomalie 
* join_siren() :Permet de faire un rapprochement avec la table siren pour en récuprer certaines informations
* extract_whitelist()

* extract_error_MN()

* select_variables(): Permet de récuperer les données utiles pour la partie front end.

> Modélisation
* Extract_feature(table_name)
cette fonction a pour but de définier les 3 niveaux de complexites des features (simple, intermediaire, complet)
* train_model() :cette fonction permet l'execution itérative des niveaux de complexités sur chaque modéle.
* extract_performance_model() :  choisir le modele le plus pertinent parmis les 3 modéles générés 

* predict_model() :cette fonction permet de réaliser la prédiction apartir d'un modéle

* calcul_enjeu() :cette fonction consiste à calculer les enjeu (montants de droits de douane et les taxes) suite au modéle prédictif
* prep_restitution() :permet la préparation des variables de restitution.
* extact_blacklist_Op(): cette focntion permet l'extraction des opéateurs blacklistés.

> statDescriptive









 



