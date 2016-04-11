
# JavaScript

Cette documentation concerne le langage [JavaScript][] dans sa version standardisée nommée ECMAScript5 et se concentre sur le langage lui-même. Les aspects pour modifier le DOM HTML ou les évènements JavaScript ne sont pas couverts dans ces lignes. De plus, les bases de la programmation ne sont pas abordées, il est donc nécessaire d'avoir un minimum d'expérience dans le métier de développeur ou de connaître au moins un autre langage de programmation pour profiter pleinement de cette documentation.

## Historique

JavaScript a été créé en 1995 par [Brendan Eich][] pour le compte de la [Netscape Communications Corporation][]. De nombreux langages ont été source d'inspiration, notamment [Java][] (alors édité par la société [Sun Microsystems][]) mais ce sont bien deux langages totalement différents, JavaScript n'est pas Java, ni même une déclinaison ou une simplification. Lors de la conception du langage JavaScript, Brendan a voulu simplifier sa syntaxe pour les débutants, ce qui rend le langage accessible bien qu'il reste néanmoins relativement complexe sur certains aspects.

## Caractéristiques

Avant de rentrer plus en détail dans le vif du sujet, faisons un rapide tour de quelques caractéristiques importantes du langage :

- JavaScript est sensible à la casse des caractères
- il gère UTF-8 nativement
- c'est un langage de script
- mais aussi un langage objet par prototype
- il est exécuté dans une machine virtuelle, généralement côté client, dans un navigateur web
- mais aussi côté serveur, avec l'environnement [Node.js][] par exemple
- d'autres environnements existent (ePub version 3, applications avec [Node-Webkit][], etc.)
- son typage est faible et dynamique

## Syntaxe

Les instructions JavaScript sont séparées par des point-virgules `;`. Ils ne sont pas obligatoires mais il est fortement conseillé de les utiliser, notamment dans le cas où vous souhaitez minifier les fichiers de script. Des outils comme [JSHint][] indiquent cet oubli par une alerte. Il est toutefois nécessaire d'utiliser des sauts de ligne afin de séparer chaque instruction dans le cas où les point-virgules ne sont pas utilisés.

Une instruction peut-être composée de valeurs, d'opérateurs, d'expressions ou de mots-clés.

Il est à noter que les espaces multiples sont parfaitement acceptés en JavaScript. Vous pouvez les utilisez pour rendre votre code plus lisible.

Toujours dans un souci de lisibilité, il est possible d'utiliser le retour à la ligne. Généralement, il est conseillé d'avoir entre 80 et 120 caractères par ligne. Dans le cas de lignes de code trop longues (par exemple à cause de nombreuses tabulations), il est possible de revenir à la ligne afin d'alléger l'ensemble.

Attention, il faudra utiliser un anti-slash `\` lorsque vous souhaiterez réaliser un retour à la ligne au sein d'une chaîne de caractères, comme dans cet exemple :

```JavaScript
var s = 'Une chaîne de caractères sur \
         deux lignes.';
```

Sinon, une erreur sera levée et le code ne fonctionnera pas.

En plus de l'anti-slash `\` pour utiliser un retour à la ligne dans une chaîne de caractères, voici la liste des autres caractères spéciaux que l'on peut utiliser avec JavaScript :

| Caractère | Signification                                                                                     |
|:--------- |:------------------------------------------------------------------------------------------------- |
| `\b`      | Retour arrière                                                                                    |
| `\f`      | Saut de page                                                                                      |
| `\n`      | Saut de ligne                                                                                     |
| `\r`      | Retour chariot                                                                                    |
| `\t`      | Tabulation                                                                                        |
| `\v`      | Tabulation verticale                                                                              |
| `\'`      | Quote, guillemet simple ou apostrophe.                                                            |
| `\"`      | Guillemet double ou droit.                                                                        |
| `\\`      | Antislash ou barre oblique inverse.                                                               |
| `\XXX`    | Le caractère dont l'encodage Latin-1 est spécifié avec 3 chiffres octaux XXX entre 0 et 377.      |
| `\xXX`    | Le caractère dont l'encodage Latin-1 est spécifié par deux chiffres hexadécimaux entre 00 et FF.  |
| `\uXXXX`  | Le caractère Unicode spécifié par quatre chiffres hexadécimaux XXXX.                              |

### Valeurs

En JavaScript, les valeurs sont de deux types : valeur littérale ou variable. Les valeurs littérales sont définies de la façon suivante :

- Nombre : `1001` ou `10.50` (entier ou décimal)
- Chaîne de caractères : `"John Doe"` ou `'John Doe'`
- Une expression : `5 + 6` ou `5 * 10`

Les variables sont utilisées pour stocker des valeurs. Le mot-clé `var` permet de définir une variable et le signe égal `=` permet d'assigner une valeur à une variable :

```JavaScript
var x; // Définition de la variable x.
x = 6; // Assignation de la valeur littérale 6 à la variable x.
```

Comme dans les autres langages, il est possible de réunir ces deux actions en une seule instruction :

```JavaScript
var x = 6;
```

### Opérateurs

Il y a tout d'abord l'opérateur d'assignement vu précédemment :

```JavaScript
var x = 5;
var y = 6;
```

Et les opérateurs arithmétiques pour effectuer des calculs :

- L'opérateur mathématique d'addition `+`
- L'opérateur mathématique de soustraction `-`
- L'opérateur mathématique de multiplication `*`
- L'opérateur mathématique de division `/`
- L'opérateur mathématique du modulo `%` (calcul du reste d'une division)
- L'opérateur mathématique de l'incrémentation `++`
- L'opérateur mathématique de la décrémentation `--`

Exemple :

```JavaScript
var x = 5 + 6;
var y = x * 10;
```

### Commentaires

Pas de surprise concernant les commentaires, ils sont sur une ligne, précédés par deux slashs `//` :

```JavaScript
// Un commentaire sur une ligne
```

Ou sur plusieurs lignes, délimités par les symboles `/*` et `*/` :

```JavaScript
/*
    Commentaire sur
    plusieurs lignes.
*/
```

### Mots-clés

Voici la liste complète des mots-clés JavaScript :

- `abstract`
- `arguments`
- `boolean`
- `break`
- `byte`
- `case`
- `catch`
- `char`
- `class` *
- `const`
- `continue`
- `debugger`
- `default`
- `delete`
- `do`
- `double`
- `else`
- `enum` *
- `eval`
- `export` *
- `extends` *
- `false`
- `final`
- `finally`
- `float`
- `for`
- `function`
- `goto`
- `if`
- `implements`
- `import` *
- `in`
- `instanceof`
- `int`
- `interface`
- `let`
- `long`
- `native`
- `new`
- `null`
- `package`
- `private`
- `protected`
- `public`
- `return`
- `short`
- `static`
- `super` *
- `switch`
- `synchronized`
- `this`
- `throw`
- `throws`
- `transient`
- `true`
- `try`
- `typeof`
- `var`
- `void`
- `volatile`
- `while`
- `with`
- `yield`

\* : Nouveaux mots-clés depuis ECMAScript5.

### Déclaration de variable

Toute variable en JavaScript doit être identifiée par un nom unique qui est appelé identifiant. Un identifiant peut être très court (comme `x`, `y` ou `z`) ou plus long et descriptif (comme `age`, `sum`, `totalVolume`). Il est préférable d'utiliser des identifiants longs qui permettent de comprendre rapidement l'utilisation de la variable concernée. Les règles de nommage sont les suivantes :

- L'identifiant peut contenir des lettres `a-z`, des nombres `0-9`, des underscores (ou caractère de soulignement) `_` ou des symboles dollar `$`
- L'identifiant doit commencer par une lettre `a-z`, un underscore (ou caractère de soulignement) `_` ou un symbole dollar `$`
- Les identifiants sont *case sensitive*, la variable `a` est donc différente de `A`
- Attention, il n'est pas possible d'utiliser de mot-clé JavaScript pour déclarer un identifiant

Il n'est pas conseillé, mais cela reste possible, d'utiliser des lettres Unicode ou ISO 8859-1 (comme å et ü) au sein des identifiants. Il est également possible d'utiliser les `\uXXXX` séquences d'échappement Unicode comme caractères dans les identifiants.

Un identifiant composé de plusieurs mots est généralement déclaré avec la technique dite *camelCase*, par exemple : `totalVolume`. Une variable commence toujours par une minuscule et chacun des mots suivants commence par une majuscule afin qu'ils soient tous bien délimités.

Une variable se déclare de la façon suivante :

```JavaScript
var maVar = 1;
```

Le mot-clé `var` est facultatif mais il est fortement conseillé de l'utiliser pour les raisons suivantes :

- Sans ce mot-clé, la variable sera globale, y compris si elle est déclarée dans une fonction
- L'utilisation du `use strict` oblige l'utilisation de ce mot-clé (configuration possible)
- Il vaut mieux utiliser les bonnes pratiques et éviter les variables globales

Il est à noter qu'après la déclaration précédente, si vous écrivez ceci :

```JavaScript
var maVar;
```

La variable `maVar` contiendra toujours la valeur `1`, cette déclaration ne remplace pas la précédente. Cette pratique est à proscrire mais il est intéressant de connaître son comportement. Il est à noter qu'une variable qui ne reçoit pas d'initialisation explicite sera initialisée par défaut à `undefined`.

Une constante se déclare de la manière suivante :

```JavaScript
const MAX = 10;
```

Attention : les constantes sont très peu utilisées en JavaScript car elles ne sont pas reconnues par tous les navigateurs. Certains moteurs JavaScript traitent le mot-clé `const` comme synonyme du mot-clé `var`. D'autres moteurs considèrent une variable définie avec le mot-clé `const` comme une variable en lecture seule. Le mot-clé `const` est une extension de JavaScript qui est supportée par les navigateurs Internet Firefox et Chrome. Mais ceci n'en fait pas un standard d'ECMASCRIPT 3 ou 5.

Il est à noter qu'une constante, comme une variable, doit-être initialisée à sa déclaration. Dans le cas contraire la constante aura pour valeur `undefined`. Par la suite, si une constante reçoit une nouvelle valeur, aucune erreur ne sera levée mais elle contiendra toujours la valeur initialement attribuée. Pour différencier une constante d'une variable, leurs identifiants sont écrit entièrement en majuscule. Si plusieurs mots composent le nom d'une constante, alors la séparation sera faite par des underscores `_` (exemples : `MAX_VALUE`, `POSITIVE_INFINITY`, etc.). Mis à part ces spécifications, les règles de nommage des variables s'appliquent aux constantes.

Afin d'éviter tout problème lié aux constantes, il est possible d'utiliser le mot-clé `var` et un identifiant écrit en majuscule. Ceci ne remplace en rien une constante mais permet toutefois d'indiquer que cette variable n'a pas pour vocation d'être modifiée dans la suite du code. La version ECMAScript 6 devrait régler ce problème ambigu.

### Scope

Une variable déclarée au sein d'une fonction, avec le mot clé `var`, est une variable locale. Une telle variable prend vie au début de la fonction et est détruite à la sortie de celle-ci ; on dit alors que le scope (*portée* en français) de la variable est limité à la fonction. En JavaScript, seules les fonctions permettent de créer un nouveau scope.

Dans tous les autres cas (variable déclarée en dehors de toute fonction ou sans le mot clé `var`), la variable sera globale et donc accessible à tout moment dans le script. Il est à noter que l'utilisation de variables globales est une mauvaise pratique et que l'emploi du `use strict` posera problème lors de la validation du code.

Il n'est pas possible, comme dans d'autres langages, d'insérer un nouveau bloc avec des accolades `{}` afin de créer un nouveau scope. Cette pratique n'a aucun effet en JavaScript (ceci change quelque peu avec ECMAScript 6).

Voici un exemple pour illustrer ce propos (environnement Node.js) :

```JavaScript
uneVar = 1;
var uneAutreVar = 2;
```

Ces deux variables sont globales (la première n'utilise pas le mot-clé `var`, la deuxième n'est pas dans une fonction), elles sont donc accessibles via l'objet `global` :

```JavaScript
global.uneVar;
global.uneAutreVar;
```

En créant de nouvelles variables globales, vous ajoutez des propriétés à l'objet `global`.

D'autres exemples (environnement web) :

```JavaScript
var i = 5;

(function afficherNombre() {
    var i = 'texte';
    alert(i);
}());

alert(i);
```

Le `alert` à l'intérieur de la fonction affichera `texte`. JavaScript remonte la portée des variables et récupère la première rencontrée.

Le second `alert`, à l'extérieur de la fonction, affichera la valeur `5` parce que le `i` de la fonction `afficherNombre` n'existe plus, c'est donc le premier qui sera appelé.

```JavaScript
var i = 5;

(function afficherNombre() {
    i = 'texte';
    alert(i);
}());

alert(i);
```

Le premier `alert`, à l'intérieur de la fonction, affichera `texte` et le second `alert`, à l'extérieur de la fonction, affichera lui aussi `texte` parce que la fonction `afficherNombre` ne déclare pas de variable mais affecte une nouvelle valeur à une variable déjà existante.

```JavaScript
var i = 5;

(function afficherNombre() {
    var i = 'texte';
    alert(window.i);
}());

alert(i);
```

Le premier `alert`, à l'intérieur de la fonction, affichera `5`, car on appelle la variable `i` qui est dans la portée de `window` (dans un navigateur, l'environnement peut changer en fonction du contexte d'exécution)

Le second `alert`, à l'extérieur de la fonction, affichera lui aussi la valeur `5`.

Une bonne pratique, afin d'éviter les variables globales, est de déclarer dans chaque fichier de script une fonction anonyme appelée immédiatement, *anonymous self-invoking function* en anglais, où sera placé le code comme ici :

```JavaScript
(function () {
    var x = "Hello!";

    // Code...
}());
```

La variable `x` n'aura d'existence que dans ce fichier. Lorsque les fichiers de scripts seront concaténés, il n'y aura aucun risque de collision entre des variables globales.

Toutefois, si l'usage de variables globales est nécessaire, voici une méthode qui est fonctionnelle quel que soit l'environnement (navigateur, Node.js, etc.) :

```JavaScript
(function(globals) {
    'use strict';
    globals.GLOB = {};
}(this));
```

Lors de l'appel de cette fonction, le paramètre `this` représente l'environnement global qui est passé en argument. C'est-à-dire que le paramètre `this` représente l'objet global `document` dans un environnement web mais est l'objet `global` sous un environnement Node.js.

### Structures conditionnelles

Nous allons parcourir rapidement les structures conditionnelles qui sont identiques à ce que l'on peut trouver dans d'autres langages.

#### if

Pour exécuter une portion de code uniquement quand une condition est remplie, utilisez la structure `if` :

```JavaScript
if (condition) {
    // code conditionnel
}
```

#### if/else

Rien de nouveau non plus pour le combo `if`/`else` :

```JavaScript
if (condition) {
    // faire ceci
} else {
    // ou cela
}
```

#### if/else if/else

Bien que le mot-clé `else if` n'existe pas en JavaScript, il est possible d'enchaîner plusieurs blocs de conditions en associant le mot-clé `else` et le mot-clé `if`, comme ceci :

```JavaScript
if (condition) {
    // code exécuté dans le cas de la première condition remplie
} else if (condition2) {
    // code exécuté dans le cas de la deuxième condition remplie
} else if (condition3) {
    // code exécuté dans le cas de la troisième condition remplie
} else {
    // si aucune des conditions précédentes n'est remplie, alors ce code est exécuté
}
```

#### switch

Le switch en javascript est classique :

```JavaScript
switch (expression) {
    case n:
        // bloc de code
        break;
    case n:
        // bloc de code
        break;
    default:
        // bloc de code par défaut
}
```

Les mot-clés `break` ne sont pas obligatoires mais s'ils ne sont pas présents, les `case` s'enchaîneront. C'est à dire que si on entre dans le premier `case` et que le `break` n'est pas présent, JavaScript exécutera aussi le code du deuxième `case` et ainsi de suite.

Le mot-clé `default` n'est pas non plus obligatoire mais il permet d'exécuter le code présent dans ce bloc quand aucun `case` précédent n'a été sélectionné.

Il est à noter que le `case` réalise une comparaison stricte (équivalent à `===`), c'est à dire `expression === n`.

#### ternaire

On retrouve ce genre de condition dans des langages comme le PHP :

```JavaScript
var i = 10;
var result = (i === 10) ? 'ok' : 'ko';
```

La variable `result` prendra la valeur : `'ok'`.

### Les boucles

#### for

Les boucles `for` sont utilisées pour réaliser un certain nombre de fois un bout de code, ce nombre est généralement connu à l'écriture :

```JavaScript
for (var i = 0 ; i < 10 ; i++) {
    console.log("i vaut : " + i);
}
```

Il est à noter qu'une boucle déclarée en dehors de toute fonction fixera la variable `i` comme variable globale.

La variable `i` reste toujours accessible dans le *scope* où elle à été déclarée une fois la boucle terminée.

Si la variable `i` est déclarée sans le mot-clé `var`, alors elle est globale, y compris si la boucle `for` est déclarée au sein d'une fonction.

Enfin, tous les paramètres de la boucle `for` sont optionnels. La variable `i` peut-être déclaré avant la boucle et incrémentée (ou décrémentée) au sein de la boucle. La condition peut être à l'intérieur de la boucle mais il faudra penser au mot-clé `break` pour éviter de créer une boucle infinie. À trop supprimer ces paramètres, il sera peut-être plus judicieux d'utiliser une boucle `while` ou `do while` (voir après). De plus, attention à la lisibilité du code qui risque de se complexifier.

Il est à noter que les conditions peuvent s'accumuler :

```JavaScript
for (var i = 0 ; i < 10 && exemple === true ; i++) {
    console.log("i vaut : " + i);
}
```

La boucle `for` peut être utilisée pour parcourir des tableaux :

```JavaScript
for (var i = tab.length - 1 ; i >= 0 ; i--) {
    tab[i];
}
```

Voir aussi le chapitre sur les *objets* concernant les boucles `for in`.

#### while

Cette boucle est très utile quand on doit effectuer un certain nombre d'actions mais qu'on ne connaît pas ce nombre à l'écriture du code :

```JavaScript
var i = 5;

while (i--) {
    console.log(i);
}
```

La boucle tourne tant que la condition est égale à `true`. Dans l'exemple, elle se termine quand `i` atteint la valeur de `-1`.

#### do/while

Quand il est nécessaire d'exécuter le code d'une boucle au moins une fois, on préfèrera cette structure :

```JavaScript
do {
    // code à répétition
} while (condition);
```

### Les types

Les différents types en JavaScript sont les suivants :

- `string`
- `number`
- `NaN`
- `boolean`
- `null`
- `undefined`
- `object`
- `function`

#### string

Les guillemets simples `'` ou doubles `"` sont identiques en JavaScript, ils représentent les chaînes de caractères. Par convention, on utilise les guillemets simples `'` pour les chaînes de caractères en JavaScript, les guillemets doubles `"` étant destinés à être utilisé dans les fichiers HTML et CSS.

Si d'autres guillemets simples doivent être utilisés dans une chaîne de caractères, deux solutions sont possibles :

1. Échapper les guillemets simples `'` par des antislashs `\` :
    `'Une solution d\'échappement.'`
2. Utiliser des guillemets doubles `"` pour délimiter la chaîne de caractères :
    `"Une autre solution pour s'échapper."`

JavaScript intègre UTF-8, il n'y a donc aucun problème concernant les caractères accentués. Attention toutefois, le fichier qui contient le script doit être encodé en UTF-8.

La déclaration littérale d'une chaîne de caractères se présente ainsi :

```JavaScript
var stringA = 'Une chaîne de caractères';
var stringB = "Une chaîne de caractères avec des guillemets doubles";
```

La déclaration par constructeur d'une chaîne de caractères s'écrit de la manière suivante :

```JavaScript
var stringC = new String('Une autre chaîne de caractères');
```

Pour les exemples qui vont suivre, nous utiliserons la chaîne de caractères stringA : `'Une chaîne de caractères'`.

Il est possible d'accéder aux caractères d'une chaîne :

```JavaScript
stringA[4];
```

Retournera `'c'`, le premier caractère étant à l'emplacement 0, le deuxième caractère à 1, etc. Attention néanmoins, cette méthode est dangereuse et imprévisible :

- Elle ne fonctionne pas dans tous les navigateurs (IE5, IE6, IE7)
- Ceci fait penser qu'une chaîne de caractères se comporte comme un tableau, ce qui est faux
- Ce genre de code : `str[0] = 'H'` ne retournera pas d'erreur mais ne fonctionnera pas non plus pour autant

Si vous souhaitez lire une chaîne de caractères comme un tableau, il faut d'abord la convertir :

```JavaScript
stringA.split('');
```

##### Propriétés

###### length

Retourne un `number` qui représente le nombre de caractères contenus dans une chaîne de caractères.

```JavaScript
stringA.length;
```

Retournera la valeur : `24`.

##### Méthodes

###### charAt()

Retourne le caractère à la position spécifiée en paramètre.

```JavaScript
stringA.charAt(4);
```

Retournera `'c'`, qui correspond au quatrième caractère de la chaîne de caractères `stringA`. Ici encore, le premier caractère est à l'emplacement 0.

Il est à noter qu'un dépassement de limite est géré automatiquement. C'est à dire qu'un paramètre trop important passé à cette méthode la fera renvoyer une chaîne de caractères vide, exemple :

```JavaScript
stringA.charAt(40);
```

Retournera `''`. 

Le paramètre de cette méthode est requis et doit être un chiffre entier qui représente l'emplacement du caractère recherché.

###### charCodeAt()

Retourne la valeur Unicode du caractère à la position donnée en paramètre.

```JavaScript
stringA.charCodeAt(4);
```

Retournera pour la chaîne de caractères `stringA` le `number` 99. Il est à noter qu'un dépassement de limite renvoie la valeur `NaN` (*Not a Number*). 

Le paramètre de cette méthode est requis et doit être un chiffre entier qui représente l'emplacement du caractère recherché.

###### indexOf()

Retourne la position de la première instance du caractère passée en paramètre.

```JavaScript
stringA.indexOf('c');
```

Retournera pour la chaîne de caractères `stringA` le `number` 4. Le premier caractère `c` rencontré dans la chaîne de caractères `stringA` se situe donc au niveau du cinquième emplacement. Pour rappel, un tableau commence à l'indice 0, voir la section qui détaille les objets Array.

Attention, `indexOf()` est sensible à la casse :

```JavaScript
stringA.indexOf('C');
```

Retournera le `number` -1, ce caractère (*C* en majuscule) n’étant pas dans la chaîne de caractères `stringA`.

Cette méthode peut prendre un deuxième paramètre qui indique à partir de quelle position on commence la recherche :

```JavaScript
stringA.indexOf('c', 11);
```

Retournera pour la chaîne de caractères `stringA` le `number` 14. 

###### lastIndexOf()

Retourne la position du dernier caractère passé en paramètre, la recherche commençant par la fin :

```JavaScript
stringA.lastIndexOf('c');
```

Retournera pour la chaîne de caractères `stringA` le `number` 18, ce qui indique donc que la dernière instance du caractère 'c' dans la chaîne de caractères `stringA` se situe à la dix-neuvième position. Pour rappel, un tableau commence à l'indice 0, voir la section qui détaille les objets Array.

###### fromCharCode()

Converti une ou des valeurs Unicode en caractères.

```JavaScript
String.fromCharCode(66, 111, 110, 106, 111, 117, 114);
```

Retournera la chaîne de caractères `'Bonjour'`.

Il est à noter qu'il s'agit d'une méthode statique de la classe `String`, la syntaxe est donc toujours :

```JavaScript
String.fromCharCode(n1, n2, ..., nX);
```

Cette méthode prend un ou plusieurs paramètre(s), dont la valeur varie de 1 à *n* pour une valeur Unicode.

###### concat()

Concatène deux ou plusieurs chaînes de caractères.

```JavaScript
var a = 'Hello';
var b = ' World';
var c = '!';
var d = a.concat(b, c);
```

La variable `d` contient désormais la `string` suivante : `'Hello World!'`. Les paramètres de cette méthode sont requis, ils sont au nombre minimum de deux jusqu'à *n*.

La valeur ainsi retournée est donc une nouvelle chaîne de caractères.

On utilise généralement l'opérateur mathématique plus `+`, qui, dans le cadre d'opérations avec des chaînes de caractères, produit le même résultat que cette méthode.

```JavaScript
var d = a + b + c;
```

###### toUpperCase()

Met en majuscule tous les caractères d’une chaîne de caractères.

```JavaScript
stringA.toUpperCase();
```

Retournera la `string` suivante : `'UNE CHAÎNE DE CARACTÈRES'`.

Il est à noter qu'il existe la variante `toLocaleUpperCase()`. Les paramètres linguistiques sont ici récupérés du navigateur internet de l'utilisateur. Généralement, cette méthode retourne la même chose que la méthode `toUpperCase()` mais parfois il existe des conflits avec les références Unicode (par exemple avec le Turc). De ce fait, les résultats peuvent varier.

La valeur de retour est une nouvelle chaîne de caractères, la chaîne originale n'est pas modifiée.

Cette méthode ne prend aucun paramètre.

###### toLowerCase()

Met en minuscule tous les caractères d’une chaîne de caractères.

```JavaScript
stringA.toLowerCase();
```

Retournera la `string` suivante : `'une chaîne de caractères'`.

De même que pour la méthode `toUpperCase()`, il existe la variante `toLocaleLowerCase()`. Les paramètres linguistiques sont alors récupérés du navigateur internet de l'utilisateur. Cette méthode retourne généralement la même chose que la méthode `toLowerCase()` mais parfois il existe des conflits avec les références Unicode (par exemple avec le Turc). Les résultats peuvent ainsi varier.

La valeur de retour est une nouvelle chaîne de caractères, la chaîne originale n'est pas modifiée.

Cette méthode ne prend aucun paramètre.

###### slice()

Renvoie une extraction de caractères.

```JavaScript
stringA.slice(4, 10);
```

Retournera la chaîne de caractères `'chaîne'`.

Au moins un paramètre est requis, il représente la position de début où sera appliqué le découpage de la chaîne de caractères. Le deuxième paramètre, facultatif, représente la position de la fin de ce découpage. Il est à noter qu'un paramètre négatif fera s’appliquer le découpage à partir de la fin de la chaîne de caractères.

Un exemple avec un seul paramètre :

```JavaScript
stringA.slice(4);
```

Retournera la chaîne de caractères `'chaîne de caractères'`.

La valeur de retour est une nouvelle chaîne de caractères, la chaîne originale n'est pas modifiée.

###### substring()

Cette méthode est similaire à `slice()`, la différence étant qu'elle ne peut pas accepter d'index négatif.

###### substr()

Cette méthode est similaire à `slice()`, la différence étant que le second paramètre représente la longueur de la chaîne à extraire.

Si le premier paramètre est négatif, la position de départ se fera à partir de la fin de la chaîne de caractères.

Le second paramètre ne peut pas être négatif parce qu'il représente la longueur de la chaîne à découper.

Enfin, si le second paramètre est omis, le restant de la chaîne sera découpé.

###### trim()

Permet d'effacer les espaces en trop au début et à la fin d'une chaîne de caractères.

#### number

Les nombres en JavaScript sont toujours des doubles flottants codés en 64 bits. Il n'existe pas, comme dans la plupart des autres langages, de types `short int`, `int` ou `float`.

La déclaration littérale d'un nombre s'écrit de la manière suivante :

```JavaScript
var num = 5;
```

La déclaration par constructeur d'un nombre s'écrit de la manière suivante :

```JavaScript
var num = new Number(5);
```

JavaScript ne fonctionnant qu'avec des flottants, la précisions des entiers n'est pas son point fort :

```JavaScript
var x = 999999999999999;    // x prendra la valeur 999999999999999
var y = 9999999999999999;   // y prendra la valeur 10000000000000000
```

De plus, une division par 0 retournera `Infinity` :

```JavaScript
var x = 2 / 0;              // x prendra la valeur Infinity
var y = -2 / 0;             // y prendra la valeur -Infinity
```

Il faut garder néanmoins à l'esprit qu'il s'agit d'un abus du JavaScript, la division par le 0 absolu étant mathématiquement impossible, une telle division ne devrait pas retourner une valeur infinie.

##### Propriétés

###### MAX_VALUE

Retourne la valeur maximale possible en JavaScript.

```JavaScript
Number.MAX_VALUE;           // 1.7976931348623157e+308
```

###### MIN_VALUE

Retourne la valeur minimale possible en JavaScript.

```JavaScript
Number.MIN_VALUE;           // 5e-324
```

###### NEGATIVE_INFINITY

Représente l’infini négatif.

```JavaScript
Number.NEGATIVE_INFINITY;   // -Infinity
```

###### NaN

Représente une valeur qui n'est pas un nombre (*Not a Number*).

```JavaScript
Number.NaN;                 // NaN
```

Il est possible d'utiliser la fonction globale `isNaN()` pour vérifier si la valeur passé en argument est un `NaN` :

```JavaScript
var i = 'string';
isNaN(i);
```

Retournera `true`.

###### POSITIVE_INFINITY

Représente l’infini positif.

```JavaScript
Number.POSITIVE_INFINITY;   // Infinity
```

##### Méthodes

###### toExponential()

Convertit un nombre en exposant :

```JavaScript
var i = 5;
i.toExponential();
```

Retournera `5e+0`. Le paramètre (optionnel) doit être un nombre entier, compris entre 0 et 20, qui représente le nombre de chiffres après la virgule :

```JavaScript
i.toExponential(5);
```

Retournera `5.00000e+0`.

###### toFixed()

Arrondi une valeur en conservant après la virgule le nombre de chiffres passé en paramètre (0 sans paramètre) :

```JavaScript
var j = 342.5476876124537;
j.toFixed();
```

Retournera `343` 

```JavaScript
j.toFixed(4);
```

Retournera `342.5477`.

###### toPrecision()

Formate le nombre à la longueur demandée :

```JavaScript
var k = 13.30938540223;
k.toPrecision();
```

Retournera `'13.30938540223'`.

Cette commande convertit un nombre en chaîne de caractères tout en gardant le nombre spécifié de chiffres après la virgule. Un arrondi supérieur est calculé. Le paramètre (optionnel) indique le nombre de chiffres, partie entière incluse, souhaités :

```JavaScript
k.toPrecision(5);
```

Retournera `'13.309'`.

###### toString()

Convertit un nombre en chaîne de caractères :

```JavaScript
var l = 342.5476876124537;
l.toString();
```

Retournera `'342.5476876124537'`.

Le paramètre, facultatif, indique la base à utiliser pour la conversion (entre 2 et 36). S’il est omis, la valeur est retournée telle quelle.

```JavaScript
l.toString(2);
```

Retournera `'101010110.10001100001101010100000101011111111010011011'`.

```JavaScript
l.toString(8);
```

Retournera `'526.430325012776466'`.

```JavaScript
l.toString(16);
```

Retournera `'156.8c35415fe9b'`.

Il est à noter qu'il existe `toLocaleString()` qui utilise les paramètres linguistique du navigateur pour localiser la chaîne de caractères.

```JavaScript
l.toLocaleString();
```

###### valueof()

Retourne la primitive d'un nombre déclaré avec un constructeur.

Lorsque l'on utilise un constructeur pour définir un nombre, il est nécessaire de passer par cette méthode pour récupérer la valeur ainsi créée :

```JavaScript
var unNombre = new Number(4);
```

Pour récupérer la valeur `4` :

```JavaScript
unNombre.valueOf();
```

#### NaN

`NaN` est de type `number` et signifie : « Not a Number » ; que l'on pourrait traduire en français par : « pas un nombre ».

Autrement dit, il s’agît d’une représentation en nombre (de type `number`) d'une valeur qui n'est pas un nombre.

On peut demander son type :

```JavaScript
typeof NaN;
```

Retourne bien `number`.

#### boolean

Rien de spécial en JavaScript avec ce type, on retrouve les valeurs : `true` et `false`.

La déclaration littérale d'un `boolean` est la suivante :

```JavaScript
var boolean = true;
```

La déclaration par constructeur d'un `boolean` est la suivante :

```JavaScript
var boolean = new Boolean();
```

La méthode par constructeur peut prendre un paramètre pour initialiser la valeur. S’il est omis, `false` est la valeur par défaut.

Les paramètres attendus ne sont pas uniquement `true` ou `false`, il est également possible d'utiliser des tests :

```JavaScript
var boolean = 3 < 4;
var boolean2 = new Boolean(5 > 6);
```

##### Astuce

Pour obtenir un équivalent booléen d'une variable, on peut utiliser le transtypage avec le double point d'exclamation `!!` :

```JavaScript
var i = 5;
!!i;
```

Retournera `true`

```JavaScript
i = 0;
!!i;
```

Retournera `false`.

0 est en fait l’équivalent de `false`, tous les autres nombres sont transtypés en `true`, y compris les valeurs négatives.

##### Méthodes

###### toString()

Ne prend pas de paramètre. Retourne la valeur en tant que chaîne de caractères. Si la variable `boolean` contient la valeur `true`, alors :

```JavaScript
boolean.toString();
```

Retournera la chaîne de caractères `'true'`.

Il est à noter que JavaScript appelle automatiquement cette méthode lorsqu’un Boolean est utilisé dans des opérations avec des chaînes de caractères.

###### valueOf()

Ne prend pas de paramètre. Retourne la valeur primitive du Boolean. Avec la variable `boolean` qui contient `true` :

```JavaScript
boolean.valueOf();
```

Retournera : `true`. Cette méthode doit être utilisée quand une variable a été initialisée avec un constructeur pour récupérer sa valeur. C'est un bon exemple qui montre que l'initialisation par constructeur induit des manipulations qui ne sont pas nécessaires avec des déclarations littérales. Effectivement, ceci :

```JavaScript
var bool = true;
```

Permet de récupérer simplement la valeur en utilisant l'identifiant `bool`. La méthode `valueOf()` devient, de fait, inutile.

#### null

La valeur `null` est un objet vide qui ne possède ni propriété, ni méthode :

```JavaScript
var personne = null;
typeof personne;
```

Retourne `object`.

Pour information, il est également possible d'initialiser un objet à `undefined` :

```JavaScript
var personne = undefined;
typeof personne;
```

Mais dans ce cas, le type de la variable (de l'*objet*) retournée sera `undefined`.

Différences entre `undefined` et `null` :

```JavaScript
typeof undefined;             // undefined
typeof null;                  // object
null === undefined;           // false
null == undefined;            // true
```

#### undefined

Indique qu'une variable n'a pas de valeur. Le type `undefined` est à la fois un type et une valeur, c'est à dire qu'une variable déclarée et non initialisée contiendra cette valeur :

```JavaScript
var maVariable;
console.log(maVariable);
```

Affichera `undefined`, tout en étant de ce type :

```JavaScript
typeof maVariable;
```

Retournera `undefined`.

Il est à noter qu'il est possible d'initialiser une variable à `undefined`, le résultat obtenu sera le même :

```JavaScript
var maVariable = undefined;
```

#### object

Il n'y a pas de concepts objets en JavaScript comme on peut en trouver, par exemple, dans le langage Java. Les notions d'héritage (au sens Java), de polymorphisme ou d'interface n'existent pas.

Pour résumer, il existe 5 types primitifs différents qui peuvent contenir des valeurs :

1. `string`
2. `number`
3. `boolean`
4. `object`
5. `function`

Il existe 3 types d'objets :

1. `Object`
2. `Date`
3. `Array`

Et deux types qui ne peuvent contenir aucune valeur :

1. `null`
2. `undefined`

Pour affecter une valeur à une variable il est possible d’utiliser une déclaration littérale :

```JavaScript
var number = 5;
var string = 'Une chaîne de caractères';
var bool = true;
var function = function(){};
var array = [1, 'chaîne', function(){}];
var object = {propriete1: 5, propriete2: {}, propriete3: 'chaîne'};
var regex = /REGEX/;
```

C'est la méthode la plus utilisée en JavaScript. Une autre approche, l'approche *objet*, consiste à passer par un constructeur :

```JavaScript
var number = new Number(5);
var string = new String('Une chaîne de caractères');
var bool = new Boolean(true);
var function = new Function();
var array = new Array();
var object = new Object();
var regex = new RegExp();
```

L'un des problèmes de cette approche est que lorsque vous testez l'une des variables précédentes avec un `typeof`, le retour sera systématiquement : `object`. Il est donc plus difficile de faire la différence entre le type des objets comme, là encore, on pourrait le faire avec un langage comme Java.

Par exemple, dans le cas d'un Array, le retour d'un `typeof` sera *object*. Comment alors faire la différence entre un objet (générique) et un tableau ? Dans le cas d'un tableau il est possible d'utiliser le code suivant :

```JavaScript
var tab = [];
Array.isArray(tab);
```

Retournera `true` pour indiquer que l’objet est bien un tableau, une autre solution est de faire ceci :

```JavaScript
var tab = [];
tab.hasOwnProperty('length');
```

Retournera `true`.

Il faut ajouter que la notation littérale est plus lisible mais aussi plus rapide. Elle nécessite moins de traitement au niveau de la machine virtuelle JavaScript. De ce fait, seule la notation littérale est utilisée en JavaScript dans la plupart des cas.

Pour ajouter des fonctionnalités à une classe, on peut passer par son prototype. Attention toutefois, cela est déconseillé car il est impossible de savoir comment évoluera le langage. A titre d'exemple :

```JavaScript
Array.prototype.shiftpop = function() {
    this.shift(); // Supprime le premier élément du tableau.
    this.pop(); // Supprime le dernier élément du tableau.
    
    return this;
}
var tab = [0, 1, 2, 3, 4];
tab.shiftpop();
```

Retournera : `1, 2, 3`.

##### Parcourir un objet

Pour parcourir les propriétés d'un objet, il est possible d'utiliser une boucle `for in`, comme ceci :

```JavaScript
for (var prop in obj) {
    console.log(prop + ' : ' + obj[prop]);
}
```

##### Afficher un objet dans la console

Généralement, pour afficher des informations dans la console, la concaténation est très largement utilisée :

```JavaScript
console.log('Un objet : ' + obj);
```

Dans le cas d'affichage d'objet, le problème de la concaténation, c'est que vous « perdez » les informations qui constituent l'objet. Si vous affichez de cette façon un objet, le retour dans la console ressemblera à : `[object Object]`. Pour éviter cela, il faut savoir que la méthode `log` de l'objet `console` prend plusieurs arguments, ainsi :

```JavaScript
console.log('Un objet : ', obj);
```

Passé comme deuxième argument, l'objet sera entièrement accessible dans la console JavaScript du navigateur.

##### Test de propriété

Afin de tester si une propriété est disponible dans un objet :

```JavaScript
var obj = {
 nom1: 5,
 nom2: 'Test'
}
'nom2' in obj;
```

Retournera la valeur `true`.

##### instanceof

Quand des objets sont instanciés par un constructeur, il est possible de tester ces instanciations (type de l'objet) :

```JavaScript
var myNumber = new Number(3);
myNumber instanceof Number;
```

Retournera `true` alors que :

```JavaScript
myNumber instanceof String;
```

Retournera `false`. Ceci ne fonctionne pas avec les déclarations littérales.

#### Array

Il n'existe qu'un seul type de tableau en JavaScript : les tableaux indicés. Il est à noter qu'ils ne sont pas typés. C'est à dire que l'on peut trouver, par exemple, au sein d'un même tableau : des chaînes de caractères, des objets et/ou des nombres. De plus, il n'est pas nécessaire de prédéfinir une taille à la création d'un tableau, elle peut changer dynamiquement.

Les dictionnaires, que l'on peut trouver dans les autres langages de programmation, n'existent pas. Par contre, ce sont des objets que l'on utilise avec le JavaScript, c'est ce qu’on appelle le format [JSON][].

```JavaScript
var tab1 = new Array();                // Méthode par constructeur
var tab2 = [0, false, function(){}];   // Méthode Littérale
```

Lors d'une déclaration littérale d'un tableau, il n'est pas nécessaire de définir tous ses éléments. Si vous utilisez deux virgules, l'une à la suite de l'autre, la valeur du tableau sera initialisée à `undefined` :

```JavaScript
var poisson = ['Voiture', , 'Maison'];
```

Une virgule ajoutée à la fin sera tout simplement ignorée. Il est à noter toutefois que les anciennes versions de navigateurs peuvent lever des erreurs dans ce genre de cas. De ce fait, il est intéressant de connaître ce comportement mais cette pratique est quoi qu’il en soit à proscrire. Si vous souhaitez ne pas renseigner de valeur, utilisez directement la valeur `undefined`.

```JavaScript
var tab1 = new Array(5);           // Taille du tableau : 5
var tab1 = new Array('5');         // Taille du tableau : 1 qui contient la chaîne de caractères '5'
```

##### Méthodes

Voici la liste des différentes méthodes que l'on peut utiliser avec des Array.

###### concat()

Concatène deux tableaux ou plus et retourne un nouveau tableau, résultat de cette opération.

###### indexOf()

Recherche dans le tableau un élément (passé en paramètre) et retourne l'index de sa position. Si aucun élément ne correspond à l'objet demandé, la valeur `-1` est retournée.

###### join()

Joint tous les éléments d'un tableau et retourne une chaîne de caractères permettant de les visualiser. Cette méthode est équivalente à `toString()` mais vous pouvez spécifier un séparateur d’éléments en argument :

```JavaScript
unArray.join(' ; ');
```

###### lastIndexOf()

Recherche un élément dans un tableau en commençant par la fin et retourne l'index de sa position. Si aucun élément ne correspond à l'objet demandé, la valeur `-1` est retournée.

###### pop()

Supprime le dernier élément d'un tableau et le retourne.

###### push()

Ajoute un ou plusieurs élément(s) à la fin d'un tableau et retourne la nouvelle longueur de ce tableau.

###### reverse()

Inverse l'ordre des éléments d'un tableau.

###### shift()

Supprime le premier élément d'un tableau et le retourne.

###### slice()

Sélectionne une partie d'un tableau et retourne le résultat du nouveau tableau. Deux paramètres doivent être passés en argument, le premier indique l'indice de départ et le deuxième l'indice du dernier élément à sélectionner dans le tableau. Si le deuxième argument n'est pas indiqué alors la sélection prendra le reste complet du tableau.

```JavaScript
unArray.slice(2, 6);
```

###### sort()

Effectue un tri sur les éléments d'un tableau.

###### splice()

Ajoute ou supprime les éléments d'un tableau. Pour ajouter des éléments :

```JavaScript
var fruits = ['Banana', 'Orange', 'Apple', 'Mango'];
fruits.splice(2, 0, 'Lemon', 'Kiwi');
```

Le premier paramètre, `2`, définit la position où les nouveaux éléments doivent être ajoutés. Le second paramètre, `0`, définit combien d'éléments doivent être supprimés. Enfin, le reste des paramètres, `'Lemon', 'Kiwi'`, indique les nouveaux éléments à ajouter.

Pour en supprimer :

```JavaScript
var fruits = ['Banana', 'Orange', 'Apple', 'Mango'];
fruits.splice(0, 1);
```

Le premier paramètre, `0`, définit la position à partir de laquelle les éléments doivent être supprimés. Le second paramètre, `1`, définit combien d'éléments doivent être supprimés.

###### toString()

Convertit un tableau en chaîne de caractères et retourne le résultat.

###### unshift()

Ajoute le(s) élément(s) passé(s) en paramètre(s) au début d'un tableau et retourne la nouvelle longueur de ce tableau.

###### valueOf()

Retourne la valeur primitive d'un tableau, cette méthode est équivalente à `toString()`.

#### Appels de méthode

On pourrait penser que les méthodes vues précédemment ne sont applicables qu'à des objets déclarés avec des constructeurs. Il n’en est rien, une méthode peut être appelée sur une valeur déclarée de manière littérale. Le moteur JavaScript convertit automatiquement le littéral en un objet typé temporaire. L'appel de la méthode se réalise et l'objet temporaire est, à la suite de ces opérations, détruit.

#### function

Une fonction suit les même règles de déclaration des variables quand il s'agit de leur attribuer un nom. Une déclaration de fonction est composée de la manière suivante :

```JavaScript
function nomDeFonction (un, ou, des paramètres, facultatif) {
    // Le corps de la fonction
}
```

Une fonction déclaré de cette façon sera simplement appelé par son nom : `nomDeFonction();`.

Il est possible d'attribuer une fonction à une variable :

```JavaScript
var maFonction = function (un, ou, des paramètres, facultatif) {
    // Le corps de la fonction
}
```

C'est en fait une fonction anonyme que l'on attribue à une variable. Pour exécuter cette fonction, on utilisera le nom de la variable qui l'a contient, sans oublier les parenthèses : `maFonction();`.

Comme on vient de le voir, une fonction peut être anonyme, c'est-à-dire qu'elle ne possède pas de nom. Généralement, elles sont utilisées en tant que `callback`, c'est à dire qu'elles sont appelées lorsqu'une action se termine. Des bibliothèques comme [jQuery][] ou des framework comme [Angular][] en usent et en abusent.

Une fonction peut renvoyer un résultat, il suffit d'utiliser le mot-clé `return`. Attention, à la rencontre de ce mot-clé, la fonction renvoie le résultat et se termine.

De plus, il est possible d'utiliser des fonctions anonymes appelées immédiatement, *anonymous self-invoking function* en anglais, comme ceci :

```JavaScript
(function () {
    var x = "Hello!!";
}());
```

Les parenthèses de fin permettent d'exécuter automatiquement ces fonctions. Il est possible d'y placer des arguments que l'on peut récupérer dans les parenthèses de la fonction. Ce système est utilisé pour isoler le code des fichiers de script.

##### Closure

Comme nous l'avons vu précédemment, seules les fonctions génèrent un nouvel espace mémoire (ce qui a comme conséquence de générer un nouveau scope pour les variables qui y sont contenues). Il est possible d'imbriquer une fonction dans une autre. Une fonction fille (une fonction située dans une autre) ne partage pas son espace mémoire avec la fonction parente mais peut cependant accéder à sa plage mémoire, c'est-à-dire accéder à ses variables. Ce mécanisme est communément appelé en JavaScript une *closure*, ou *fermeture* en français.

Une fonction imbriquée, une *closure*, hérite donc des arguments et des variables de la fonction parente.

##### Arguments

Tous les arguments d'une fonction sont maintenus dans un tableau et sont accessibles avec le mot-clé `arguments` au sein de cette fonction.

On peut accéder aux arguments passés à cette fonction très simplement : `arguments[i]` où *i* représente l'index de l'argument recherché. Le nombre total d'arguments contenu dans le tableau peut être connu grâce à la propriété `length` : `arguments.length`.

En utilisant le tableau `arguments`, il est possible de recenser les arguments supplémentaires fournis à la fonction si jamais il y en a plus que nécessaire. La propriété `arguments.length` permet de déterminer le nombre d'arguments qui sont réellement passés à la fonction rendant ainsi possible l'accès à ces derniers en parcourant le tableau.

Note : le mot-clé `arguments` est une variable « semblable » à un tableau. Mais ce n'est pas un tableau au sens strict. En effet, bien qu’il possède un index numéroté ainsi qu'une propriété `length`, il ne possède pas les méthodes classiques de manipulation des tableaux (`Array`).

#### RegExp et Date

Les objets `RegExp` et `Date` ne seront pas traités dans cette documentation. Il s'agit d'objets spécifiques et relativement complexes qui nécessiteraient à eux seuls une documentation importante.

### Debug

Les blocs `try`/`catch` sont utiles pendant la conception mais sont à éviter en production. Voici la syntaxe :

```JavaScript
try {
    // code à tester
} catch (e) {   // Il est possible de sélectionner le type d'erreur : if(e instanceof ReferenceError)
    console.log(e);
} catch (e) {   // On peut en avoir plusieurs
    
} finally {
    // Dans tous les cas on entre ici (facultatif).
}
```

Pour lancer une erreur :

```JavaScript
if (isNaN(nb) || nb < 0 || Math.round(nb) != nb) {
    throw('Erreur de valeur : ' + nb + 'n\'est pas un nombre entier positif.');
}
```

### Méthodes obsolètes

Toutes les méthodes qui permettent d'entourer du code avec des balises HTML sont obsolètes. Elles ne sont pas un standard et peuvent fonctionner de manière très différente entre les différents navigateurs (voir ne pas fonctionner du tout). Dans un environnement Node.js, ces méthodes ne sont pas disponibles :

- `anchor()`
- `big()`
- `blink()`
- `bold()`
- `fixed()`
- `fontcolor()`
- `fontsize()`
- `italics()`
- `link()`
- `small()`
- `strike()`
- `sub()`
- `sup()`

De plus, la méthode JavaScript `eval()` ne doit plus être utilisée. Elle permet d'évaluer du code sous forme d'une chaîne de caractères. Le paramètre passé en argument possède les privilèges de l'environnement appelant. Pour des raisons de sécurité, il est donc fortement conseillé de ne pas l'utiliser.

### Conclusion

Pour terminer cette documentation sur les éléments du langage qui peuvent paraître étranges :

```JavaScript
var text = '';
var arr = [];
```

Un test booléen donnera ces résultats :

- `!!text` : retourne `false`.
- `!!arr` : retourne `true`.

Sur certaines comparaisons :

- `[] === []` : retourne `false`.
- `[] == []` : idem.
- `'' === ''` : retourne `true`.
- `'' == ''` : idem.

[JavaScript]: https://fr.wikipedia.org/wiki/JavaScript "JavaScript - Wikipedia"
[Brendan Eich]: https://fr.wikipedia.org/wiki/Brendan_Eich "Brendan Eich - Wikipedia"
[Netscape Communications Corporation]: https://fr.wikipedia.org/wiki/Netscape_Communications "Netscape Communications Corporation - Wikipedia"
[Java]: http://fr.wikipedia.org/wiki/Java_(langage) "Java - Wikipedia"
[Sun Microsystems]: https://fr.wikipedia.org/wiki/Sun_Microsystems "Sun Microsystems - Wikipedia"
[Node.js]: http://nodejs.org "Node.js - Site officiel"
[Node-Webkit]: http://nwjs.io "Node-Webkit - Site officiel"
[JSHint]: http://jshint.com "JSHint - Site officiel"
[JSON]: http://www.json.org/json-fr.html "Présentation de JSON"
[jQuery]: http://jquery.com "jQuery - Site officiel"
[Angular]: https://angularjs.org "Angular - Site officiel"
