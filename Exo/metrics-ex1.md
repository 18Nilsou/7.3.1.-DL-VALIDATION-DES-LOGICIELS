
# Exercise 1 (Repo 1): Discover the Code & Rough Size

## Tableau récapitulatif

| Classe                | LOC (approx.) | NOM | Courte description de la responsabilité |
|-----------------------|:-------------:|:---:|----------------------------------------|
| `Bank`                | 412           | 14  | Gère la liste des comptes bancaires, permet d’ajouter, supprimer, rechercher des comptes, effectuer des transferts et calculer des statistiques|
| `BankAccount`         | 469           | 20  |  Représente un compte bancaire individuel, gère les opérations sur le compte (dépôt, retrait, limites, solde, titulaire, ...)|
| `Person`              | 324           | 23  | Représente une personne titulaire d’un compte, stocke et gère ses informations personnelles (nom, âge, genre, email, ...)|
| `BankAccountApp`      | 482           | 2   | Point d’entrée principal de l’application, orchestre l’exécution globale (main)|

## Analyse

**Est-ce que la taille de chaque classe correspond à sa responsabilité ?**

> Oui, mais cela n'est pas forcément vrai pour tous les cas.
Généralement les classes qui gèrent plus de logique métier ou de données ont plus de lignes et de methodes.\
Cela dépend aussi de la façon dont on mesure la taille (uniquement le nombre de ligne, le nombre de methode ou les deux). Par exemple, `BankAccountApp` a beaucoup de responsabilités mais seulement deux méthodes mais la fontion contient un grand nombre de ligne. Cela peut vouloir dire que la logique est concentrer en une seule methodes principale
