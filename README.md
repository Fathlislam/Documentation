# Documentation

```JavaScript ```
```PHP ```
## Notations conformes aux demandes du responsable développement :

* Préfixes : 
  * Chaines de caractère  : <code> $strVariable = "mavariable"; </code>
  * Entiers               : <code> $intVariable = 13;</code>
  * Booléens              : <code> $Blnresultat = true;  </code>
  * Fonctions             : <code> function vodMaFonction ();</code>
  * Objets                : <code> $objMonObjet = new MonObjet();</code>
  * Tableaux              : <code> $arrTableaux = array()</code>
  * Ressources            : <code> $resFic = fopen("fichier.txt", 'a')</code>
  * Formulaire            : <code> form name="formTest"  action="" method="post"  </code>
  

## Récapitulatif 

>  Validation formulaire ( javaScript ) : 

>  >  Email 

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

>  >  Nom / Prenom

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

>  >  Etc etc .. a suivre 


>  Creation d'un fichier pour enregistrer les informations du formulaire

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
   
if($resFic = fopen("fichier.txt", 'a')) { 
   fputs($resFic, $strChaine); 
   fclose($resFic);
}
```

>  >  Affichage du fichier dans un tableau 

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

vodAfficher("fichier.txt", ";");
```

>  Affichage du tableau sur la page formulaire, sans redirection ( Ajax ) :


```javascript
    function getInfo(){
        var xmlhttp;
        if (window.XMLHttpRequest){
            xmlhttp = new XMLHttpRequest();
        }
        else{
            xmlhttp = new ActiveXObject("Microsoft.XMLHTTP");
        };

        var strFirstName = encodeURIComponent(document.getElementById("strFirstName").value);
        var strLastName = encodeURIComponent(document.getElementById("strLastName").value);
        var strEmail = encodeURIComponent(document.getElementById("strEmail").value);
        var strPassword = encodeURIComponent(document.getElementById("strPassword").value);
        var driver = encodeURIComponent(document.getElementById("driver").value);
        var strMessage = encodeURIComponent(document.getElementById("strMessage").value);
 
        xmlhttp.onreadystatechange = function(){
            if (xmlhttp.readyState == 4 & xmlhttp.status == 200) {
                document.getElementById("Jax").innerHTML = xmlhttp.responseText;
            };
        }

        xmlhttp.open("POST","action_corrige.php",true);
        xmlhttp.setRequestHeader("Content-type","application/x-www-form-urlencoded");
        xmlhttp.send("strFirstName=" + strFirstName + "&strLastName=" + strLastName + "&strEmail=" + strEmail + "&strPassword=" + strPassword + "&driver=" + driver + "&strMessage=" + strMessage);
    }

```

```PHP 

$bdd->exec(
    'INSERT INTO Informations(strFirstName, strLastName, strEmail, strPassword, sexe, driver, strMessage) 
    VALUES('. $bdd->quote($_POST['strFirstName']) .', '. $bdd->quote($_POST['strLastName']) .', '.                        $bdd->quote($_POST['strEmail']) .', '. $bdd->quote($_POST['strPassword']) .', '. $bdd->quote($_POST['sexe']) .',      '. $bdd->quote($_POST['strMessage']) .', NOW())'
    );

$reponse = $bdd->query('SELECT * FROM Informations'); 

$maintenant = mktime(date("H"),date("i"),0,date("m") ,date("d"),date("Y"));
$now = date('H:i  d/m/y', $maintenant); // date now

echo "<table border=\"1\">";
while ($donnees = $reponse->fetch()) {
    echo "<tr>";
    echo '<td>'. $donnees['strFirstName'] .' '. $donnees['strLastName'].'</td>';
    echo '<td>'. $donnees['strEmail'] . ' </td>';
    echo '<td>'. $donnees['strPassword'] . ' </td>';
    echo '<td>'. $donnees['sexe'].'</td>';
    echo '<td>'. $donnees['driver'].'</td>';
    echo '<td>'. $donnees['strMessage'].' </td>';
    echo '<td>'. $donnees[$now].'</td>';
    echo "</tr>";
}
echo "</table>";

```


