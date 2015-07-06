
 ``
   >> ``/*Ciconia/Modules/Administration .. / Gestion de profils*/``
  
|Fichier         | Explication (traitement)                                                                               |
|----------------| ------------------------------                                                                         |
|`prf.html.php`  | Affichage du tableau de la liste des profiles  |
|                | Affichage des icones imprimer/rafraichir/ajouter profiel |
|                | Récuperation de la table `cli_profile_prf` correspondant au site séléctionné ( voir cic.html.php) |
|                | Affichage de la liste des profiles |
|                | Ajout de l'icone detail du profile pour chaque profile                                     |
|                | Vérification de réstriction de chaque profile                                              |
|                | S'il ya réstriction, Ajout de l'icone "supprimer profile"                                  |


|Requetes            |  (traitement)                                                                              |
|----------------    | ------------------------------                                                             |
|  Rafraichir        | Requete html renvoi au debut du fichier prf.html.php                                       |
|  Ajouter un profil | Requete html renvoi vers le fichier `prfedit.html` au `case 'createPrf' :`                 |
|                    | Affichage du formulaire "Informations générales"                                           |
|                    | Affichage de l'icone "Creer le profil"                                           |
| Details du profil  | Sinon, Ne pas donner l'acces à la suppression du profile                                   |
|                    |                                                                              |
|                    |                                                                              |
