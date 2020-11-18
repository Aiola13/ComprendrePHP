# Les instructions

Pour plus d'informations, Merci de vous rendre dans le _ComprendreAlgorithmique_.
Ici ce ne sera que simple rappel avec les spécificités du PHP.

## Les opérateurs :

### Les opérateurs arithmétiques

| Signe |               Opération               |
| :---: | :-----------------------------------: |
|  `–`  |     (unaire) Changement de signe      |
|  `+`  |               Addition                |
|  `-`  |             Soustraction              |
|  `*`  |            Multiplication             |
|  `/`  |               Division                |
|  `%`  | Modulo (reste de la division entière) |

### La concaténation de chaînes

Le « . » (le point)

### Les opérateurs logiques (et binaires)

|   Signe    |      Opération      |
| :--------: | :-----------------: |
|    `!`     |     NON logique     |
| `&&` `AND` |     ET logique      |
| `||` `OR`  |     OU logique      |
|   `XOR`    | OU exclusif logique |


### Les opérateurs relationnels (de comparaison)

| Signe |       Opération       |
| :---: | :-------------------: |
| `==`  |        Egalité        |
| `===` |       Identité        |
| `!=`  |       Différent       |
|  `<`  | Strictement Inférieur |
| `<=`  |   Inférieur ou égal   |
|  `>`  | Strictement Supérieur |
| `>=`  |   Supérieur ou égal   |

### Cas particulier de l'affectation

|   Signe    |         Opération         |   Equivalent    |
| :--------: | :-----------------------: | :-------------: |
|  `$a = 1`  |   Afffection par copie    |        \        |
| `$b = &$a` | Affectation par référence |        \        |
| `$a += $b` |          Egalité          | `$a = $a + $b`  |
| `$a -= $b` |         Identité          | `$a = $a -* $b` |
| `$a *= $b` |         Différent         | `$a = $a * $b`  |
|   `$a++`   |      Incrémentation       |  `$a = $a + 1`  |

/!\ Une référence est une copie de l'adresse mémoire de la variable.

### Règles des priorités des expressions


![mon image](<../resources/regles-priorite-operateurs_(Small).png>)


# Boucles et Conditions

[comment]: #'CONDITIONS'

## Structure Alternative et de choix

### Structure Alternative

```php
if($a == $b)
{
  echo "A est égal à B";
}
elseif($a > $b)
{
  echo "A est supérieur à B";
}
else
{
  echo "A est inférieur à B";
}
```
### Structure de Choix Multiple

```php
switch($a)
{
  case $b : echo "A est égal à B";
            break

  case >$b: echo "A est supérieur à B";
            break;

  default : echo "A est inférieur à B";
            break
}
```

### Opérateur ternaire

```php
// syntaxe
// (condition) ? valeur vrai : valeur faux;
$var = 2;
echo ($var > 3) ? 'plus grand<br />' : 'plus petit<br />';
```

[comment]: #'BOUCLES'

## Structures de répétition

### While

```php
$i = 0;
while($i <= 10)
{
  echo "-$i-";
  $i++;
}
```

### Do - While

```php
$i = 0;
do
{
  echo "-$i-";
  $i++;
} while($i <= 10)
```

### For

```php
for($i = 0; $i <= 10; $i++)
{
  echo "-$i-";
}
```

## Mots-clés

### CONTINUE
`continue` permet de sortir de l'itération en cour et de passer à la suivante.

```php
for (var i = 0; i < 10; i++) {
	if (i <= 5) {
		continue;
	}
	echo "- ";
}
```

### BREAK
`break` permet de sortir de la boucle en cours.

```php
for (var i = 0; i < 10; i++) {
	if (i <= 5) 
  {
		echo $i;
	}
  else
  {
    break;
  }
	echo "- ";
}
```


---

# Prêt pour la prochaine partie ? 😉 [C'est par ici](./Tableaux.md)
