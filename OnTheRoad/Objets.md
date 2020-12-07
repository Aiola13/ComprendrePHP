# La programmation Orientée Objet

Mais qu'est ce que sont les objets ? 🙄

Vous connaissez les types int, string ect ...
Vous pouvez tout simplement définir vos propres types.

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

    public function SetCouleur($couleur)
    {
      $this->couleur = $couleur;
    }

    public function GetCouleur()
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
echo 'couleur de la voiture '.$maVoiture->GetCouleur().'<br />';

$maVoiture->SetCouleur("blanche"); // appel d'une méthode
echo 'couleur de la voiture '.$maVoiture->GetCouleur().'<br />';
?>
```

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