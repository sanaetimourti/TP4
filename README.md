# TP4 - Introduction à JavaScript

Ce dépôt contient les solutions du Travail Pratique 4 du module "Technologies du Web & Web Sémantique" du Master SDIA à l'École Normale Supérieure de l'Enseignement Technique de Mohammedia.

## Objectifs du TP
L'objectif principal de ce TD est d'expérimenter les constructions de base du langage JavaScript : types simples, déclarations de variables, instructions de contrôle, et itérations.

---

## Explications du Code par Exercice

### Exercice 1 : Conversion de températures
**But :** Convertir une température de Fahrenheit en Celsius.
**Explication du code :**
La fonction `degreC(tempF)` applique la formule mathématique `C = (5/9) * (tempF - 32)`. 
* On utilise `let` pour déclarer la variable `tempC`.
* La méthode `.toFixed(1)` est utilisée lors de l'affichage avec `console.log()` pour arrondir le résultat à un seul chiffre après la virgule, rendant l'affichage plus propre.

### Exercice 2 : Conversion de durées (Version simple)
**But :** Convertir un nombre total de secondes en jours, heures, minutes et secondes.
**Explication du code :**
* Nous utilisons `Math.floor()` pour obtenir la division entière (arrondie à l'inférieur). Par exemple, `Math.floor(s / 86400)` donne le nombre de jours complets (car il y a 86 400 secondes dans un jour).
* L'opérateur modulo `%` est crucial ici : il permet de récupérer le "reste" de la division. Ainsi, `s % 86400` nous donne les secondes restantes après avoir soustrait les jours entiers, que nous convertissons ensuite en heures, etc.

### Exercice 2-bis : Améliorer le programme de conversion
**But :** Ne pas afficher les valeurs nulles et gérer le pluriel/singulier (ex: "1 heure" vs "2 heures").
**Explication du code :**
* L'algorithme de calcul reste le même que l'exercice 2.
* La différence réside dans la construction de la chaîne de caractères `message`. 
* Nous utilisons des structures conditionnelles `if (valeur > 0)` pour s'assurer que les zéros ne sont pas affichés.
* Nous utilisons l'opérateur ternaire `(condition ? "vrai" : "faux")` pour ajouter un "s" uniquement si la valeur est strictement supérieure à 1.

### Exercice 3 : Classer 3 nombres
**But :** Afficher 3 nombres dans l'ordre croissant.
**Explication du code :**
* La fonction `classer(a, b, c)` n'utilise pas de fonction de tri préexistante.
* Elle utilise une structure conditionnelle multiple `if ... else if` pour tester exhaustivement toutes les permutations possibles (6 combinaisons au total) des trois variables afin de les afficher dans le bon ordre.

### Exercice 5 : Tester si un nombre est premier
**But :** Vérifier si un nombre n'est divisible que par 1 et par lui-même.
**Explication du code :**
* On initialise une variable booléenne `estPremier` à `true`.
* Une boucle `for` itère de `2` jusqu'à `n-1`. 
* À chaque itération, on vérifie si `n % i === 0` (si le reste de la division est 0, cela signifie que `i` est un diviseur).
* Si un diviseur est trouvé, on passe `estPremier` à `false` et on utilise l'instruction `break` pour stopper la boucle immédiatement, optimisant ainsi le code.

### Exercice 6 : Suite de Fibonacci
**But :** Calculer les termes de la suite de Fibonacci.
**Explication du code :**
* **Fibo1(n) :** Calcule le n-ième terme itérativement. On stocke les deux termes précédents dans `u0` et `u1`, et on calcule le `u_suivant`. À chaque tour de boucle, on décale les valeurs.
* **Fibo2(valeurMax) :** Utilise une boucle `while` pour générer la suite jusqu'à ce que la valeur `u1` dépasse la `valeurMax` donnée, tout en comptant le rang avec la variable `n`.

### Exercice 7 : Valeur approchée de la racine carrée
**But :** Approximer la racine carrée en utilisant une suite convergente.
**Explication du code :**
* La fonction `Raca1(A)` implémente la suite de Héron.
* La boucle `while` continue de tourner tant que la différence absolue entre le carré de notre approximation et `A` est supérieure ou égale à 10^-5 (`Math.abs(un * un - A) >= 1e-5`).
* L'expression `0.5 * (un + A / un)` correspond à la formule de récurrence mathématique.
