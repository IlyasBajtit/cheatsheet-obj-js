# Cheatsheet-obj-js

## Difference entre un objet et une variable 

**- Une variable est comme une étiquette que vous collez sur une boîte pour y mettre une chose, et un objet est comme une boîte spéciale qui peut avoir plusieurs étiquettes (propriétés) pour différentes choses à l'intérieur.**



## Comment crée un objet:

``` javascript
let user = new Object(); // "object constructor" syntax
let user = {};  // "object literal" syntax
 exemple : 

 let user = {     // an object
  name: "John",  // by key "name" store value "John"
  age: 30        // by key "age" store value 30
}; 
```


### Pour supprimer une propriété, on peut utiliser delete l'opérateur :

``` javascript
 delete user.age;
```

- Pour les propriétés multimots, l'accès aux points ne fonctionne pas :

``` javascript 
// this would give a syntax error
user.likes birds = true
```

**- JavaScript ne comprend pas cela. Il pense que nous traitons user.likes, puis donne une erreur de syntaxe en cas d'erreur inattendue birds.**

**- Il faut utiliser ca :** 
``` javascript
let user = {};

// set
user["likes birds"] = true;

// get
alert(user["likes birds"]); // true

// delete
delete user["likes birds"];
```

 ## Savoir itérer dans un objet

 - https://javascript.info/object 

 ``` javascript
 for (key in object) {
  // executes the body for each key among object properties
}
```

**- PAR EXEMPLE :** 

``` javascript
 let user = {
  name: "John",
  age: 30,
  isAdmin: true
};

for (let key in user) {
  // keys
  alert( key );  // name, age, isAdmin
  // values for the keys
  alert( user[key] ); // John, 30, true
}
```

 ## Savoir copier un objet (cloner)

 - https://fr.javascript.info/object-copy

**- Lorsqu’une variable d’objet est copiée – la référence est copiée, l’objet lui-même n’est pas dupliqué.**

Par exemple:

``` javascript 
let user = { name: "John" };

let admin = user; // copie la référence 
```

**- On peut utiliser n’importe quelle variable pour accéder à l’objet et modifier son contenu :**

``` javascript 
let user = { name: 'John' };

let admin = user;

admin.name = 'Pete'; // changé par la référence "admin"

alert(user.name); // 'Pete', les changements sont visibles sur la référence "user"
```


 ## Garbage Collection

 - https://fr.javascript.info/garbage-collection

 
**- La Garbage Collection en JavaScript est comme un nettoyeur automatique qui supprime automatiquement les choses inutiles (comme les variables qui ne sont plus nécessaires) pour libérer de l'espace mémoire et maintenir le programme efficace.**

## Méthodes d'objet, "this"

- https://fr.javascript.info/object-methods

**- Pour accéder à l’objet, une méthode peut utiliser le mot-clé this.**

**- La valeur de this est l’objet “avant le point”, celui utilisé pour appeler la méthode.**

**- Par exemple :**

```javascript
let user = {
name: "John",
age: 30,

sayHi() {
// "this" is the "current object"
alert(this.name);
}

};

user.sayHi(); // John
```


 - ` “this” ` n’est pas lié 

**- En JavaScript, le mot clé this se comporte différemment de la plupart des autres langages de programmation. Il peut être utilisé dans n’importe quelle fonction, même si ce n’est pas une méthode d’un objet.**

- Il n’y a pas d’erreur de syntaxe dans le code suivant :

``` javascript
function sayHi() {
  alert( this.name );
}
```

**- La valeur de this est définie au moment de l’exécution.**

**- Lorsqu’une fonction est déclarée, elle peut utiliser this, mais ce this n’a aucune valeur jusqu’à ce que la fonction soit appelée.
Une fonction peut être copiée entre des objets.
Lorsqu’une fonction est appelée dans la syntaxe “méthode” : object.method(), la valeur de this lors de l’appel est objet.**



## Convertion des objets en js 

https://fr.javascript.info/object-toprimitive#hints

### Il existe trois variantes de conversion de type, appelées “hints”, décrites dans la specification :

**1- string**

Pour une conversion d’un objet vers une chaîne de caractères, lorsque nous effectuons une opération sur un objet qui attend une chaîne, comme alert :

``` javascript
// output
alert(obj);

// utiliser un objet comme clé de propriété
anotherObj[obj] = 123;
```

**2- "number"**

Pour une conversion d’objet en nombre, comme lorsque nous faisons des calculs :

``` javascript
// conversion explicite
let num = Number(obj);

// maths (except binary plus)
let n = +obj; // unary plus
let delta = date1 - date2;

// comparaison supérieur/inférieur
let greater = user1 > user2;
```

Résumé : https://fr.javascript.info/object-toprimitive#resume





