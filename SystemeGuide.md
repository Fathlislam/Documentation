###Sommaire

Module Guide  : Module de gestion du personnel extérieur.


* [Gestion de Profil](#"profil")
* [Gestion de visiteur](#visiteur)
* [Gestion de référentiel](#référentiel)
* [Ajout d'un avis de visite](#Ajoutavis)
* [Voir l'avis de visite](#Voirl'avis)
* [Suppression de l'avis de visite](#Suppressionavis)
* [Ajout d'un visiteur](#Ajoutvisiteur)
* [Faire entrer/sortir le visiteur](#entrer/sortir)
* [Voir les informations du visiteur](#informationsvisiteur)
* [Enregistrer les modifications](#Enregistrer)
* [Rafraichir la liste](#Rafraichir)



	

##Gestion de Profil                          <a id="Profil"></a>

#### Droit sur les tables   ``/*(Modules/Administration*/fonctionnalités/Gestion des profiles/détail du profil)*/``
	
	A la création du profil, nous arrivons sur la page de droit, on fait un select par rapport au profil (prf_id),
	en fonction de cela on va afficher l'interface, 
	et automatiquement cocher les enregistrements qui doivent être cocher. 
	Il y a 3 colonnes en fonction de l'ajout, l’édition et suppression. 
	donc lorsqu'on va cocher une case, on va déclencher un traitement Ajax qui va, 
	dans un premier temps vérifier l'état 	des 3 cases (s'il y a entrée ou non). 
	Pour résumer, au clic sur l'une des croix, cela appellera une fonction Ajax qui a pour paramètre 
	le nom de la table et le profile, si on a un enregistrement on fait un ``update`` de cet enregistrement, 
	sinon on fait un ``insert``.

	Le droit de lecture est le résultat des 3 colonnes (Ajout/Edition/suppression).
	Pour ce droit on va faire un select, s'il y a une entrée, alors le droit de lecture est coché, 
	mais s'il y a au moins l'une des 3 cases qui est cochée, alors la case (lecture) est cochée et grisée. 
	Par contre, s'il n’y a pas d'entrée, on fait un ``insert`` et toutes ces valeurs seront à 0.

	
	
	
	
	
	
	
	
##Gestion de visiteur                       <a id="visiteur"></a>
##Gestion de référentiel                  <a id="référentiel"></a> 		
##Ajout d'un avis de visite               <a id="Ajoutavis"></a> 		
##Voir l'avis de visite                       <a id="Voirl'avis"></a>	
##Suppression de l'avis de visite 	<a id="Suppressionavis"></a>		
##Ajout d'un visiteur 			<a id="Ajoutvisiteur"></a> 			
##Faire entrer/sortir le visiteur 	<a id="entrer/sortir"></a> 			
##Voir les informations du visiteur   <a id="informationsvisiteur"></a> 	
##Enregistrer les modifications 	<a id="Enregistrer"></a> 			
##Rafraichir la liste 				<a id="Rafraichir"></a> 
