
   >> ``/*Ciconia/Modules/Systeme Guide*/``
  
| Fichier         | Explication (traitement)                                                                               |
| ----------------| ------------------------------                                                                         |
|`cic.html.php`   | Séléction de l'accueil                                                             |
|                | Requete`Ajax` renvoi vers le fichier `cic.ajax` au `case 'chooseRpt2' :`      |
| `cic.ajax.php` | Récuperation de l'id `[rpt_id]` de l'accueil s'lectionné                                       |
|                | Mise en session de `[rpt_id]`         |
|                | Execution de la requete`html` renvoi vers le fichier `cic.html` au `case 'none' :`       |
| `cic.html.php` | Mise a disposition des 4 etats (fonctionalitées) attendu/present/sorti/entré             |
|                | Tableau de la liste des visiteur selon etat ( par défaut : la liste des visiteurs attendus)    |
|                |Affichage des icones " imprimer/ enregistrer/rafraichir/ajouter un avis de visite "  avec requete       (ajax/html) selon icone          |
|                |si clic  `Ajout d'un avis de visite `                                                               |
|                |Requete`html` renvoi vers le fichier `meetingnotice.html` au `case 'ajoutAvis' :`       |
|`meetingnotice.html.php`|`$sc=explode("_",$table); `                                                                 |
|                |`$schema=$this->schema; `                                                                               |
|                |`$schema=$this->_objCMFCAction->schema;`                                                                |
|                |`$desc=$this->_objCMFCAction->getDBObject($table,end($sc),'table',$schema);   `                         |
|                |                                |
|                |                                |
|                |                                |
|                |                                |
|                |                                |
|                |                                                                                           |
|                |**La suite est compliquée, je repasserai!**    |
|                | A partir de ` if($affichage[0]['sdo_constraint_type']=='fk') `    |
|                | Si le type de contrainte `sdo_constraint_type` <> pk    |
|                |      |
