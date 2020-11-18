# Notions de bases

## Intégration d'un script dans une page

Les pages contenant du php doivent porter l'extension **.php**. Voici comment insérer du code PHP dans du HTML : `<?php ... ?>`

```php
<?php
  $sTexteHtml = '<p>Bonjour, voici ma première page</p>';
?>
<!doctype html>
<html lang="fr">
  <head>
    <meta charset="utf-8">
    <title>Titre de la page</title>
    <link rel="stylesheet" href="style.css">
    <script src="script.js"></script>
  </head>
  <body>
    <?php
      echo $sTexteHtml;
    ?>
  </body>
</html>
```

## Les commentaires

Un script PHP se commente comme dans beaucoup de langage, tels que C ou javascript :

```php
<?php
  // commentaire sur une ligne
  /* commentaire
    sur plusieurs
    lignes */
  #commentaires comme en shell
?>
```

/!\ Comme pour tous les langages, il est vivement conseillé de commenter ses scripts.

---

# Prêt pour la prochaine partie ? 😉 [C'est par ici](./Data.md)
