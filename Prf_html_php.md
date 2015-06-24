
 ``
   >> ``/*Ciconia/Modules/Administration .. / Gestion de profils*/``
  
| Fichier         | Explication (traitement)                                                                               |
| ----------------| ------------------------------                                                                         |
|`prf.html.php`| Chargement des tables de la base de donénes                                                             |
|                | Pour chaque table, tester si ce profil a le droit d'afficher cette table ou nn, si oui, l'afficher      |
|                | === > si `[prf_id]` est inf ou = au niveau d'administration minimum                                     |
|                | Au clic sur une table ==> requete `html` renvoi vers le fichier `table.html` au `case 'afficherTable' :`|
|                | **Ligne 43 ' a voir avec fabrice'**                                                                   |
|                | Affichage de la liste des tables                                                                       |
|                | " + " Ajouter une ligne `(getModalCreate()) `                                                           |
|                |`(getModalCreat()) ` ==> Requete Ajax vers le fichier table.ajax  et `case 'ajouterLigne' :`            |
|                |`$sc=explode("_",$table); `                                                                             |
|                |`$schema=$this->schema; `                                                                               |
|                |`$schema=$this->_objCMFCAction->schema;`                                                                |
|                |`$desc=$this->_objCMFCAction->getDBObject($table,end($sc),'table',$schema);   `                         |
|                | Chargement de la table sys_database_object_sdo  = $desc                                                |
|                | Affichage de la modal avec le nom de la table selectionnée                                             |
|                | Chargement de la table sys_database_object_sdo = $Affichage                                            |
|                | Si le type de contrainte `sdo_constraint_type` = pk                                                    |
