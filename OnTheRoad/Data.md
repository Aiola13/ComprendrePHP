# Les variables et les données

## Les Variables

Voici la particularité du PHP : **Pas de déclaration**

- elle est implicitement déclarée dès qu'elle est utilisée.
- Son type se détermine en fonction de son contenu.
- Le type de contenu peut évoluer avec le temps.

```php
<?php
  $sNom = "Durand";
  $sPrenom = "Loïc";
?>
```

### Règle de nommage des variables

/!\ Syntage :

- sensible à la casse
- commence toujours par **\$**
- continuent par une lettre ou par \_ mais pas de chiffre
- peuvent terminer par un nombre, une lettre ou \_

### Convention de nommage que vous utiliserez dans tous vos scripts php :

- Le nom de la variable doit être évocateur de son contenu
- la première lettre d'une variable est une minuscule
- Chaque variable commence par une lettre qui identifie le type de la donnée
  - s pour string
  - i pour integer
  - r pour réel
  - b pour booléen
  - t pour tableau
  - o pour objet
- Chaque changement de mot est précédé du caractère \_ ou commence par une majuscule

## La Portée

Comme en algorithmique, la portée d'une variable (ou identifiant) est la partie dans la quelle la variable est connu.

|                  Variables locales                   |       Variables globales       |
| :--------------------------------------------------: | :----------------------------: |
| Visibles que dans le "block" où elles ont été créées | Visible dans tout l'algorithme |

Pour qu'une variable soit utilisable dans un autre block, il faut qu'elle soit passée en paramètre. Toutes les variables sont locales en PHP.

### Les Globales

- Utilisation de la super-globale **\$GLOBALS[]**

```php
<?php
  $sNom = "Durand";
  $sPrenom = "Loïc";
  message("Mon nom est","Mon prénom est")

  function message($_msg1, $msg2)
  {
    echo $_msg1." ".$GLOBALS['sNom']." ".$_msg2." ".$GLOBALS['sPrenom'];
  }
?>
```

- utilisation de l'instruction _global_

```php
<?php
  $sNom = "Durand";
  $sPrenom = "Loïc";
  message("Mon nom est","Mon prénom est")

  function message($_msg1, $msg2)
  {
    global $sNom, $sPrenom;
    echo $_msg1." ".$sNom." ".$_msg2." ".$sPrenom;
  }
?>
```

### Les Variables dynamiques

- Référence (pointeur) &

```php
<?php
  $iNbr = 100; // la variable est initialié à la valeur 100
  $adr_iNbr = &$iNbr; /* La variable $adr_iNbr fait référence à $iNbr
                        et contient l'adresse de $iNbr */
  $iNbr++; // on chage la valeur de $iNbr
  echo $adr_iNbr;
?>
```

### Les Constantes

- Identifiant :

  - Mêmes règles de nommage que les variables
  - Par convention, les identifiants constantes sont en majuscules
  - Une constante ne commence jamais par \$

- Déclaration

```php
define("NOM_CONSTANTE", "Valeur");
```

- Exemple

```php
  define("TVA", 19.6);
  echo TVA;
```

## Traitement sur les variables

- Quelques fonctions :

|        Fonctions        |                                        Utilisation                                         |
| :---------------------: | :----------------------------------------------------------------------------------------: |
|      `empty($var)`      | renvoie vrai si la variable `$var` n'existe pas, si elle contient 0 ou une chaine vide('') |
|      `isset($var)`      |                          renvoi vrai si la variable `$var` existe                          |
|      `unset($var)`      |                                détruit une variable `$var`                                 |
|     `gettype($var)`     |                           retourne le type de la variable `$var`                           |
| `settype($var, "type")` |                            convertit la variable `$var` (cast)                             |

```php
$sNom = '';
if(empty($sNom))
  echo 'La variable <i>$sNom</i> est vide. Elle est de type : <i>'.gettype($sNom).'</i>';

```

- Le PHP permet aussi des trucs étranges ...

Comme le fait qu'une variable peut avoir pour identificateur la valeur d'une autre variable. `${$var} = valeur;`

```php
  $sToto = "foobar";
  ${$sToto} = 2020;
  echo $foobar // ceci affichera 2020
```

# Les types de données

Il existe **deux familles** :

- Les types scalaires (types simples

|  Type   |         Nom         |       Exemple       |
| :-----: | :-----------------: | :-----------------: |
| Entier  |    int, integer     |  `$iNombre = 12;`   |
|  Réel   | real, float, double |  `$rReel = 1.12;`   |
| Chaîne  |       string        | `$sNom ='Durand';`  |
| Booléen |    bool, boolean    | `$bDrapeau = true;` |

- Les types composés

|  Type   |  Nom   |
| :-----: | :----: |
| Tableau | array  |
|  Objet  | object |

# Cas des chaînes de caractères

On peut les définir :

|     Nom      | Signe  |                 Exemple                  |
| :----------: | :----: | :--------------------------------------: |
| double quote | `('')` | `echo '<p id="para">'.$sNom.'</p><br>';` |
| simple quote | `("")` |  `echo "<p id=\"para\">$sNom</p><br>";`  |

Voici quelques fonctions de traitement des chaînes :

|          Fonctions          |                         Utilisation                          |
| :-------------------------: | :----------------------------------------------------------: |
|       `strlen($var)`        |         retourne le nombre de caractère d'une chaîne         |
|      `strtlower($var)`      |                   conversion en minuscule                    |
|        `trim($var)`         |          suppression des espaces de début et de fin          |
|  `strnatcmp($var1, $var2)`  |                 comparaison de deux chaînes                  |
| `explode(separateur, $var)` | renvoie un tableau des valeurs comprises entre le séparateur |


---

# Prêt pour la prochaine partie ? 😉 [C'est par ici](./Instructions.md)
