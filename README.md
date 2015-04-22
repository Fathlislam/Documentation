# Documentation

## Notations conformes aux demandes du responsable développement :

* Préfixes : 
  * Chaines de caractère  : <code> $strVariable = "mavariable";</code>
  * Entiers               : <code> $intVariable = 13;</code>
  * Booléens              : <code> $Blnresultat = true;  </code>
  * Fonctions             : <code> function vodMaFonction ();</code>
  * Objets                : <code> $objMonObjet = new MonObjet();</code>
  * Tableaux              : <code> $arrTableaux = array()</code>
  * Ressources            : <code> $resFic = fopen("fichier.txt", 'a')</code>
  * Formulaire            : <code> form name="formTest"  action="" method="post"  </code>
  

## Memento 

> Validation formulaire ( javaScript ) : 
> > Email 

```JavaScript
 function blnValidateEmail() {     
     var strEmail = document.forms["formTest"]["strEmail"].value;
     intAtPos = strEmail.indexOf("@");
     intDotPos = strEmail.lastIndexOf(".");
     if(intAtPos < 1 || ( intDotPos - intAtPos < 2 )) {
         alert("Please enter correct email ")
         document.forms["formTest"]["strEmail"].focus() ;
         return false;
     }
     else {
         return true;
     }
 }
```
> > Nom / Prenom

```JavaScript
 function blnValidateForm() {

   // Nom
   var strName = document.forms["formTest"]["strFirstName"].value;
   if(strName == null || strName == "") {
       alert("First name is required");
       return false;
   }

   // Prenom
   var strName = document.forms["formTest"]["strLastName"].value;
   if(strName == null || strName == "") {
       alert(" Last name is required");
       return false;
   }
```

> > Etc etc .. a suivre 

> Creation d'un fichier pour enregistrer les informations du formulaire




