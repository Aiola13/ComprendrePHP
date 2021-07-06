# Exercices

## Exercices 1

- Écrire un programme qui permet de calculer et d’afficher la réduction effective au produit par rapport à un pourcentage de réduction, le prix initial HT et une TVA de 19,6%.


Prix Hors Taxe : 100
Applique à ce prix hors taxe la TVA : 19,6

119,6

Applique la réduction sur prix TTC



```
    <?php
        function prixReduit($rReduc, $iPrixHT)
        {
          define("TVA", 1.196);

          return $iPrixHT * TVA * $rReduc / 100;
        }

        echo 'La réduction que j\'aurais sur mon prix final sera de : '.prixReduit(50, 50);



    ?>
```
---
## Exercices 2

- Écrire un programme qui informe si un nombre est posifif, négatif ou nul


```
//Version Denis
function positifOrNotPositif($iNbr)
{
  switch ($iNbr<=>0){
    case -1:
        return "Négatif";
    case 0:
        return "Nul";
    case 1:
        return "Positif";
  }
}

echo positifOrNotPositif(rand(-10, 10));
```


```
function positifOrNotPositif($iNbr)
{
  if($iNbr > 0)
  {
    return "Positif";
  }
  elseif($iNbr < 0)
  {
    return "Négatif";
  }
  else
  {
    return "Aucun des deux";
  }
}

echo positifOrNotPositif(rand(-10, 10));
```
```
fonction pour stan:
$iNombre = rand(-100,100);

switch (true) {
    case ($iNombre>0):
        echo "le nombre est positif";
        break;
    
    case ($iNombre<0):
        echo "le nombre est négatif";
        break;
    
    default:
        echo "aucun des deux";
        break;
}

```

```
function jojo()
{
  $a = 5;

  if ($a > 0){
      echo "a est positif";
  } elseif($a == 0){
      echo "a n'est ni positif ni négatif";
  } else{
      echo "a est négatif";
  }
  
}
```
---

- Écrire un programme et déclarer une variable qui contient la valeur 42. Grâce à var_dump() pour vérifier, faire en sorte que ce ne soit pas la valeur 42 mais bien un string.


```
function phrase($iNbrs = "42") {
    var_dump($iNbrs);
}

phrase();

```
---

- Créer une variable de type int, qui stock une valeur (celle de votre choix de 0 à 24) qui permet de dire si nous sommes le matin, l'après-midi ou le soir.
(Vous pouvez même utiliser la fonction `date()`)


```
<?php


$rHeure = date('H');

if($rHeure < 12)
{
    echo "on est le matin";
}
elseif($rHeure < 20 )
{
    echo "on est l'apres midi";
}
else
{
    echo "on est le soir";
}
 
?>
```
---

- Via une boucle `for`, écrire un script qui produit le résultat ci-dessous.

```
1
22
333
4444
55555

```<?php

      for($a = 1; $a <= 5; $a++) 
      {
        for($b = 1; $b <= $a; $b++) 
        {
          echo $a;
        }

        echo '<br>';
      }

    ?>
```

---

- Créer un tableau qui stock 5 pays d'europe avec leur capitale, afficher ce tableau via une boucle


```
<?php
  $array = array(
      "France"=> "Paris",
      "Allemagne"=> "Berlin",
      "Portugal"=> "Lisbone",
      "Angleterre"=> "Londres",
      "Italie"=> "Rome",
      "Espagne"=> "Madrid"
  );
  
  var_dump($array);
  foreach($array as $indice => $valeur);
  {
      echo "$indice sa capitale est $valeur <br/>";
  }
?>
```
---

- Grâce à la fonction rand(), remplir un tableau et vérifier si le chiffre 13 est présent et afficher un message en conséquence.


```
(Pikachu)

$iTableSize=25;
$aTableSize = [];

for ($i=0; $i<$iTableSize ; $i++) {
    $aTableSize[]= rand(0,20) ;
}


if (in_array(13, $aTableSize)) {
    echo "13 est présent";
}
else{
    echo "13 est absent";
}


```
---

- Créer une fonction qui prendra obligatoirement un argument de type string et testera si un password est bon. Elle devra retourner un boolean qui vaut true si le password fait au moins 8 caractères et false si moins.


```
function check_mdp_format($mdp)
{
  //Regex ou Expression régulière
  
	$majuscule = preg_match('@[A-Z]@', $mdp);
	$minuscule = preg_match('@[a-z]@', $mdp);
	$chiffre = preg_match('@[0-9]@', $mdp);
	
	if(!$majuscule || !$minuscule || !$chiffre || strlen($mdp) < 8)
	{
		return false;
	}
		return true;
}

if (check_mdp_format("1Formatik") != true)
{
    echo "<br/>";
    echo "<br/>";
	echo "Format non correct";	
}
else {
    echo "<br/>";
    echo "<br/>";
    echo "Format correct";
    echo "<br/>";
    echo "<br/>";
}
    
```
```
<?php
function passWord($sMDP){

    if(strlen($sMDP) >=8 ){
        echo "le mot de passe est bon";
    }else {
        echo "le mot de passe est faux";
    }
}

$sMDP = "monmotdepass1";
passWord($sMDP);

?>
```



---


-  Créer une fonction qui  :
  - afficher une variable
  - l'incrémenter sa valeur de 2
  - Si sa valeur est égale à 10, la mettre en valeur avec la balise HTML appropriée.
  - arréter arrivé à 30


```
   function incrementation($iIncre = 0){;
    while ($iIncre <= 30) {
        if ($iIncre === 10) {
          echo '<strong>'.$iIncre.'</strong>';	  
        } else {
          echo $iIncre;
        }
        echo '<br />';
        $iIncre = $iIncre + 2;
      }
    }
incrementation();
```

```
function f($iNbre1){
    for ($iNbre = $iNbre1; $iNbre <= 30; $iNbre +=2){
        if ($iNbre === 10){
            echo "<b>". $iNbre ."</b>";
        }else{
            echo $iNbre;
        }
        echo "<br/>";
    }
}
f(0);

```
---
 
- Créer une fonction où vous déclarez un tableau contenant plusieurs pays, puis :
  - Pour chaque pays entrer lui les informations suivantes :
    - Le nombre d'habitants
    - La capital
      - Pour chaque capital :
        - le nombre d'habitant
    - la monnaie
    - la langue
  - Afficher en suite le pays qui à le plus d'habitant
  - Afficher le pays qui à la capital avec le plus d'habitant
  - Afficher tous les pays qui ont la même monnaie ou la même langue
  - Afficher le nombre de pays présent dans le tableau
  - Vérifier si le pays "Canada" existe


```

$pays = [
    'France' => [ 'Habitant Pays' => 66000000,
                  'Capital' => array('paris',2100000),
                  'Monnaie' => '€', 
                  'Langue' => 'Francais']
];


var_dump($pays);
// $sous_pays = $pays['France'];
// echo $sous_pays['Monnaie'];
//$pays[]

echo $pays['France']['capital'][0];

foreach ($pays as $clef => $pays){
    echo 'Pays : ' .$clef. '<br>';

    foreach ($clef as $capital => $valeur) {
        echo $capital. ' : ' .$valeur. '<br>';
    } 
    echo '<br>';
    echo '<br>';
}
```
---


- Créer une fonction qui prendra un argument de type string et qui devra retourner cette même string mais en remplacant les e par des 3, les i par des 1 et les o par des 0 Exemple :

"Hello à tous, il fait bien froid aujourd'hui !" => "H3ll0 à t0us, 1l fa1t fr01d auj0urd'hu1 !"


```
function transform(string $texte){
    for($i=0; $i<strlen($texte);$i++){
        if($texte[$i]=="e"){$texte[$i]=3;}
        if($texte[$i]=="i"){$texte[$i]=1;}
        if($texte[$i]=="o"){$texte[$i]=0;}
    }
    
    echo $texte;
}
transform("Hello à tous, il fait bien froid aujourd'hui !");
```

```
$texte = "Hello à tous, il fait bien froid aujourd'hui !";
$texte = str_replace('i', '1', $texte);
$texte = str_replace('o', '0', $texte);
$texte = str_replace('e', '3', $texte);
echo $texte;
```

```
$sPhrase = "Hello à tous, il fait bien froid aujourd'hui !";

$sPhrase = str_replace(array ("e", "o", "i"), array("3", "0", "1"), $sPhrase);


echo $sPhrase;
```

```
function leetSpeak(string $texte):string{
    $search= array("e","o","i");
    $replace=array("3","0","1");
    return str_replace($search,$replace,$texte);
}
echo leetSpeak("Hello à tous, il fait bien froid aujourd'hui !");
```
---