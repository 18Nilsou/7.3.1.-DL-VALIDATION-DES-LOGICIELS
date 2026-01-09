# SonarQube: Static Analysis & Quick Fixes

## BankAccount line 179 col 2
**Try-with-resources should be used (java:S2093)**

Si on n'utilise pas la méthode `close()` ou un `try-with-resources`, les ressources utilisées par Java ne sont pas automatiquement libérées par le garbage collector. Il faut donc appeler `close()` ou utiliser un `try-with-resources` pour les libérer. Ne pas les libérer peut amener à des fuites mémoire (leaks).

## Bank line 191 col 80
**Unused method parameters should be removed (java:S1172)**

Il ne faut pas déclarer de paramètres dans une fonction si on ne les utilise pas dans le corps de la fonction. Cela peut introduire des erreurs et prêter à confusion.

## Bank line 31 col 2
**Static fields should not be updated in constructors (java:S3010)**

Une variable static appartient à la classe et non à une instance. Donc si la valeur est modifiée sur une instance, elle l'est pour toutes les instances de la classe. Il faut donc soit enlever le static soit déclarer la variable en dehors du constructeur.

## Do SonarLint issues appear more often in the classes with higher WMC / CBO you saw earlier, or not really?
>Oui, en général, les classes avec un WMC ou un CBO élevé ont tendance à présenter plus de problèmes détectés par SonarLint. Mais ce n’est pas une règle absolue : il peut y avoir des classes simples avec des problèmes, et des classes complexes bien écrites sans “issues”.