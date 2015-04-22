# Documentation

```JavaScript
```
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

```PHP
$strSeparateur  = ";";
 
$strChaine      = $_POST['strFirstName'];
$strChaine     .= $strSeparateur . $_POST['strLastName'];
$strChaine     .= $strSeparateur . $_POST['strEmail'];
$strChaine     .= $strSeparateur . $_POST['strPassword'];
  
if($_POST['sexe'] == "male") {
    $strChaine .= $strSeparateur . "Homme";
}
else {
   $strChaine .= $strSeparateur . "Femme";
}
   
if ($_POST['driver'] == 1 ) {
   $strChaine .= $strSeparateur . "Permis";
}
else { 
   $strChaine .= $strSeparateur . "Pas de Permis";
}
$strChaine .= $strSeparateur . $_POST['strMessage'] . "\n"; 
   
if($resFic = fopen("forms_corrige.txt", 'a')) { 
   fputs($resFic, $strChaine); 
   fclose($resFic);
}
```
> > Affichage du fichier dans un tableau 

```PHP
/*
*
* function vodAfficher      affiche un tableau html à partir d'un fichier texte
* strFile                   nom du fichier
* strSeparateur             séparateur des champs
* 
*/
function vodAfficher($strFile, $strSeparateur) {
    if($arrTab = file($strFile)) {
        echo "<table border=\"1\">";
            foreach ($arrTab as $strVal) {
                echo "<tr>";
                    $arrSsTab = explode($strSeparateur, $strVal);
                    foreach($arrSsTab as $strSsVal) {
                        echo  "<td>" . $strSsVal . "</td>";
                    }
                echo "</tr>";
            }
        echo "</table>";
    }
    else {
        echo "erreur lors de l'ouverture du fichier text";
    }
}

vodAfficher("forms_corrige.txt", ";");
```


