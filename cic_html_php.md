
   >> ``/*Ciconia/Modules/Systeme Guide*/``
  
| Fichier         | Explication (traitement)                                                                               |
| ----------------| ------------------------------                                                                         |
|`cic.html.php`   | Séléction de l'accueil                                                             |
|                | Requete`Ajax` renvoi vers le fichier `cic.ajax` au `case 'chooseRpt2' :`      |
|                | Récuperation de l'id `[rpt_id]` de l'accueil s'lectionné                                       |
|                | Mise en session de `[rpt_id]`         |
|                | Execution de la requete`html` renvoi vers le fichier `cic.html` au `case 'none' :`       |
| `cic.ajax.php` | Mise a disposition des 4 etats (fonctionalitées) attendu/present/sorti/entré             |
|                | Tableau de la liste des visiteur selon etat ( par défaut : la liste des visiteurs attendus)    |
|                |Affichage des icones " imprimer/ enregistrer/rafraichir/ajouter un avis de visite "  avec requete       (ajax/html) selon icone          |
|                |`$schema=$this->schema; `                                                                               |
|                |`$schema=$this->schema; `                                                                               |
|`cic.ajax.php`|`$sc=explode("_",$table); `                                                                             |
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
