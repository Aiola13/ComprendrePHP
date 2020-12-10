# La programmation Orientée Objet (POO)

Mais qu'est ce que sont les objets ? 🙄

Mais si, vous savez ce que c'est .... Si si réféchissez ... vous en avez tout autour de vous... un canapé, une table, une chaise ... Bous avez compris ...
En programmation c'est la même chose. 

L'exemple que je peux vous donner c'est une voiture, imaginons dans notre code un Objet VOITURE.

Cette voiture à une couleur, une marque, un type ... Ses caractérisques correspondent a des valeurs, des variables.
Mais elle a aussi des capacités, des actions qu'elle peut effectuer, comme être repeinte, être réparé, avancer, tourner ... des fonctions.

Toutes ces informations sont contenues dans une classe.

qu'est-ce-qu'une classe alors ? 

Comme je viens de le dire, les classes contiennent la définition des objets que l'on va créer par la suite. Prenons l'exemple le plus simple du monde : les gâteaux et et leur moule. Le moule est unique. Il peut produire une quantité infinie de gâteaux. Dans ce cas-là, les gâteaux sont les objets et le moule est la classe : le moule va définir la forme du gâteau. La classe contient donc le plan de fabrication d'un objet et on peut s'en servir autant qu'on veut afin d'obtenir une infinité d'objets.

Mais concrètement, une classe, c'est quoi ?

Une classe est une entité regroupant des variables et des fonctions. Chacune de ces fonctions aura accès aux variables de cette entité. Dans le cas de la voiture, nous aurons une fonction peindre(). Cette fonction devra simplement modifier la variable $couleur.

Maintenant que vous savez ce qu'est un objet et une classe, parlons de l'instanciation ...

L'instanciation est le fait de créer un objet via une classe, ce qui créé une instance de la classe dont elle dépend. 

Nous pouvons aussi parler de l'encapsulation, qui permet de rendre le code visible où non ... en mettant en place une visibilité d'un attribut ou une méthode.

Un exemple : 

Une voiture, comment pourrait-on définir une voiture ?

## Déclaration et définition

```php
<?php
  class Voiture // Déclaration de la classe
  {
    // Déclaration des données membres (Private, Public & Protected)
    private $couleur; // Déclaaration d'un attribut
    private $type = "sport"; // initialisation de la donnée membre
    private $marque; // initialisation de la donnée membre

    // Déclaration des fonctions membres (Méthodes)
    public function __construct($marque) // Constructeur
    {
      $this->couleur = "noire";
      $this->marque = $marque;
      // Le mot-clé "$this" faisant référence à l'objet est obligatoire
    }

    public function setCouleur($couleur)
    {
      $this->couleur = $couleur;
    }

    public function getCouleur()
    {
      return $this->couleur;
    }
  }
?>
```

## Instanciation

```php
<?php
$maVoiture = new Voiture("Infinity");
echo 'couleur de la voiture '.$maVoiture->getCouleur().'<br />';

// -> opérateur Objet
$maVoiture->setCouleur("blanche"); // appel d'une méthode
echo 'couleur de la voiture '.$maVoiture->getCouleur().'<br />';
?>
```
---


## Héritage

```php
<?php
  class VoitureLuxe extends Voiture // Déclaration de la sous-classe qui hérite de Voiture
  {
    
    private $belle; 

    public function __construc()
    {
      parent::__construct();
      $this->belle=TRUE();
    }
   
  }
?>
```

L'opérateur de résolution de portée 
parent `::` membre de la classe parent

self `::` membre de la même classe

## Polymorphisme (Redéfinition)

## Surcharge

## composition

---
# Prêt pour la prochaine partie ? 😉 [C'est par ici](./)