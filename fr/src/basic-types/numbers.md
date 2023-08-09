# Numbers

### Integer

1. 🌟

> Conseils: Si nous n'attribuons pas explicitement un type à une variable, le compilateur en déduira un pour nous.

```rust,editable

// Supprimer quelque chose pour le faire fonctionner
fn main() {
    let x: i32 = 5;
    let mut y: u32 = 5;

    y = x;

    let z = 10; // Type of z ?

    println!("Success!");
}
```

2. 🌟
```rust,editable

// Remplissez le blanc
fn main() {
    let v: u16 = 38_u8 as __;

    println!("Success!");
}
```

3. 🌟🌟🌟

> Conseils : Si nous n'attribuons pas explicitement un type à une variable, le compilateur en déduira un pour nous.

```rust,editable

// Modifie `assert_eq!` pour que çela fonctionne
fn main() {
    let x = 5;
    assert_eq!("u32".to_string(), type_of(&x));

    println!("Success!");
}

// Obtiens le type d'une variable donnée, renvoie une représentation sous forme de chaîne de caractères du type, par exemple "i8", "u8", "i32", "u32".
fn type_of<T>(_: &T) -> String {
    format!("{}", std::any::type_name::<T>())
}
```

4. 🌟🌟
```rust,editable

// Remplir les blancs pour que cela fonctionne
fn main() {
    assert_eq!(i8::MAX, __);
    assert_eq!(u8::MAX, __);

    println!("Success!");
}
```

5. 🌟🌟
```rust,editable

// Corriger les erreurs et les paniques pour que cela fonctionne
fn main() {
   let v1 = 251_u8 + 8;
   let v2 = i8::checked_add(251, 8).unwrap();
   println!("{},{}",v1,v2);
}
```

 [checked_add](https://docs.rs/num/latest/num/trait.CheckedAdd.html#tymethod.checked_add/)
: Effectue une addition qui renvoie None au lieu d'être contournée en cas de dépassement de capacité.

[unwrap](https://doc.rust-lang.org/stable/std/result/enum.Result.html#method.unwrap)
: Renvoie la valeur contenue dans Ok, en consommant la valeur propre.



6. 🌟🌟
```rust,editable

// Modifier `assert!` pour que cela fonctionne
fn main() {
    let v = 1_024 + 0xff + 0o77 + 0b1111_1111;
    assert!(v == 1579);

    println!("Success!");
}
```


### Virgule flottante
7. 🌟

```rust,editable

// Remplir le vide pour que cela fonctionne
fn main() {
    let x = 1_000.000_1; // ?
    let y: f32 = 0.12; // f32
    let z = 0.01_f64; // f64

    assert_eq!(type_of(&x), "__".to_string());
    println!("Success!");
}

fn type_of<T>(_: &T) -> String {
    format!("{}", std::any::type_name::<T>())
}
```

8. 🌟🌟 Le faire fonctionner de deux manières distinctes

```rust,editable

fn main() {
    assert!(0.1+0.2==0.3);

    println!("Success!");
}
```

### Rayon d'action (range)
9. 🌟🌟 Deux objectifs :
    1. Modifier `assert!` pour qu'il fonctionne
    2. Faire en sorte que `println!` affiche : 97 - 122

```rust,editable
fn main() {
    let mut sum = 0;
    for i in -3..2 {
        sum += i
    }

    assert!(sum == -3);

    for c in 'a'..='z' {
        println!("{}",c);
    }
}
```

10. 🌟🌟
```rust,editable

// Remplissez les blancs
use std::ops::{Range, RangeInclusive};
fn main() {
    assert_eq!((1..__), Range{ start: 1, end: 5 });
    assert_eq!((1..__), RangeInclusive::new(1, 5));

    println!("Success!");
}
```

### Calculs

11. 🌟
```rust,editable

// Remplir les blancs et corriger les erreurs
fn main() {
    // Integer addition
    assert!(1u32 + 2 == __);

    // Integer subtraction
    assert!(1i32 - 2 == __);
    assert!(1u8 - 2 == -1);

    assert!(3 * 50 == __);

    assert!(9.6 / 3.2 == 3.0); // error ! make it work

    assert!(24 % 5 == __);
    // Short-circuiting boolean logic
    assert!(true && false == __);
    assert!(true || false == __);
    assert!(!true == __);

    // Bitwise operations
    println!("0011 AND 0101 is {:04b}", 0b0011u32 & 0b0101);
    println!("0011 OR 0101 is {:04b}", 0b0011u32 | 0b0101);
    println!("0011 XOR 0101 is {:04b}", 0b0011u32 ^ 0b0101);
    println!("1 << 5 is {}", 1u32 << 5);
    println!("0x80 >> 2 is 0x{:x}", 0x80u32 >> 2);
}
```

> Vous pouvez trouver les solutions [ici](https://github.com/sunface/rust-by-practice/blob/master/solutions/basic-types/numbers.md)(sous le chemin des solutions), mais ne l'utilisez que lorsque vous en avez besoin.


