
 ``
 
   >> ``/*Ciconia/Modules/Administration .. / Gestion de référentiel*/``
  
| Fichier         | Explication (traitement)                                                                               |
| ----------------| ------------------------------                                                                         |
|`table.html.php`| Chargement des tables de la base de donénes                                                             |
|                | Pour chaque table, tester si ce profil a le droit d'afficher cette table ou nn, si oui, l'afficher      |
|                | === > si `[prf_id]` est inf ou = au niveau d'administration minimum                                     |
|                | Au clic sur une table ==> requete `html` renvoi vers le fichier `table.html` au `case 'afficherTable' :`|
|                | ##Ligne 43 ' a voir avec fabrice'                                                                   |
|                | Affichage de la liste des tables                                                                       |
|                | " + " Ajouter une ligne `(getModalCreate()) `                                                           |
|                |`(getModalCreat()) ` ==> Requete Ajax vers le fichier table.ajax  et `case 'ajouterLigne' :`            |
|`table.ajax.php`|`$sc=explode("_",$table); `                                                                             |
|                |`$schema=$this->schema; `                                                                               |
|                |`$schema=$this->_objCMFCAction->schema;`                                                                |
|                |`$desc=$this->_objCMFCAction->getDBObject($table,end($sc),'table',$schema);   `                         |
|                | Chargement de la table sys_database_object_sdo  = $desc                                                |
|                | Affichage de la modal avec le nom de la table selectionnée                                             |
|                | Chargement de la table sys_database_object_sdo = $Affichage                                            |
|                | Si le type de contrainte `sdo_constraint_type` = pk                                                    |
|                |`$table_ref=$affichage[0]['sdo_referenced_table']; $table_ref_exp=explode('_',$table_ref);$schema_ref=$affichage[0]['sdo_referenced_schema'];`                               |
|                | ` $affichage_ref=$this->_objCMFCAction->getDBObject($affichage[0]['sdo_referenced_field_name'],end($table_ref_exp),'field',$schema_ref);`                                                                                           |
|                |**La suite est compliquée, je repasserai!**    |
|                | A partir de ` if($affichage[0]['sdo_constraint_type']=='fk') `    |
|                | Si le type de contrainte `sdo_constraint_type` <> pk    |
|                |      |
|                |      |
|                |      |
|                |      |
|                |      |
|                |      |
|                |      |
|                |      |
|                |      |
