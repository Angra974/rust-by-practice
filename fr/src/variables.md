# Variables

### Liaison et mutabilité (Binding and mutability)
1. 🌟 Une variable ne peut être utilisée que si elle a été initialisée.
```rust,editable

// Corrige de l'erreur ci-dessous avec le moins de modifications au code
fn main() {
    let x: i32; // Non initialisé mais utilisé, ERREUR !
    let y: i32; // Uninitialized but also unused, only a Warning !

    assert_eq!(x, 5);
    println!("Success!");
}
```

2. 🌟 Utilisez `mut` pour marquer une variable comme mutable.
```Rust,editable

// Remplir les blancs dans le code pour le faire compiler
fn main() {
    let __ __ = 1 ;
    __ += 2 ;

    assert_eq !(x, 3) ;
    println !("Success !") ;
}
```

### Portée
Le champ d'application est la plage du programme pour laquelle l'élément est valable.

3. 🌟
```Rust,editable

// Corrigez l'erreur ci-dessous avec un minimum de modifications
fn main() {
    let x : i32 = 10 ;
    {
        let y : i32 = 5 ;
        println !("La valeur de x est {} et la valeur de y est {}", x, y) ;
    }
    println !("La valeur de x est {} et la valeur de y est {}", x, y) ;
}
```


4. 🌟🌟
```rust,editable

// Corriger l'erreur avec l'utilisation de define_x
fn main() {
    println!("{}, world", x);
}

fn define_x() {
    let x = "hello";
}
```

### Shadowing
Vous pouvez déclarer une nouvelle variable avec le même nom qu'une variable précédente,
ici nous pouvons dire **la première est cachée par la seconde**.

5. 🌟🌟
```rust,editable

// Ne modifiez que `assert_eq!` pour que `println!` fonctionne(affiche `42` dans le terminal)
fn main() {
    let x: i32 = 5;
    {
        let x = 12;
        assert_eq!(x, 5);
    }

    assert_eq!(x, 12);

    let x = 42;
    println!("{}", x); // Prints "42".
}
```

6. 🌟🌟
```rust,editable

// Supprimer une ligne dans le code pour le rendre compilable
fn main() {
    let mut x: i32 = 1;
    x = 7;
    // Shadowing and re-binding
    let x = x;
    x += 3;


    let y = 4;
    // Shadowing
    let y = "I can also be bound to text!";

    println!("Success!");
}
```

### Variables non utilisées (Unused variables)
7. Corrigez l'avertissement ci-dessous avec :

- 🌟  Une seule solution
- 🌟🌟  Deux solutions distinctes

> Note : aucune des solutions proposées ne consiste à supprimer la ligne `let x = 1`

```rust,editable

fn main() {
    let x = 1;
}

// Warning: unused variable: `x`
```

### Déstructuration (Destructuring)
8. 🌟🌟 Nous pouvons utiliser un modèle avec `let` pour déstructurer un tuple en séparant les variables.

> Tips: vous pouvez utiliser l'ombrage (shadowing) ou la mutabilité (mutability).

```rust,editable

// Corrigez l'erreur ci-dessous en la modifiant le moins possible
fn main() {
    let (x, y) = (1, 2);
    x += 2;

    assert_eq!(x, 3);
    assert_eq!(y, 2);

    println!("Success!");
}
```

### Affecter par décomposition (Destructuring assignments)
Introduit dans Rust 1.59 : Vous pouvez maintenant utiliser les modèles tuple,
slice et struct comme partie gauche d'une affectation.

9. 🌟🌟

> Note: la fonctionnalité `Destructuring assignments` nécessite la version 1.59 ou supérieure de Rust

```rust,editable

fn main() {
    let (x, y);
    (x,..) = (3, 4);
    [.., y] = [1, 2];
    // Remplir le vide pour que le code fonctionne
    assert_eq!([x,y], __);

    println!("Success!");
}
```


> Vous pouvez trouver les solutions [ici](https://github.com/sunface/rust-by-practice)(sous le chemin des solutions), mais ne l'utilisez que lorsque vous en avez besoin.
