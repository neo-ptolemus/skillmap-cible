
# Jeu de cible

## Introduction @unplugged

Ça avance bien ! Il est temps d'ajouter le code pour pouvoir tirer sur la cible. 🎯

![Apercu](/apercu3.gif "Regarde ce qu'on va faire !")


## 1. Le principe

❓ Mais au fait, comment on va compter les points ?

---

🕹️ Le but du jeu est de faire le **maximum de points** en tirant le plus proche du **centre de la cible**.

✏️ On va donc devoir calculer la **distance entre le centre de la cible et la position du viseur** quand on appuie sur **(A)**.

🎯 En plus de ça, chaque couleur de la cible a un nombre de points différents : 

⚪ **50 pts**  
⚫ **250 pts**  
🔵 **500 pts**  
🔴 **750 pts**  
🟡 **1000 pts**  

Et en dehors de la cible ? *0pts...*

## 2. Créer une fonction calculDistance

1️⃣ Pour commencer, on va créer une **fonction** ! Ça rendra le code plus lisible.

- :mouse pointer: Crée une nouvelle **fonction** qui s'appelle **calculDistance** !

## 3. Calculer la distance 

_❓Est-ce que tu te rappelles de la formule du calcul de la distance ?_

![formule](/static/skillmap/racer/racer1.gif "La formule de la distance")

---

😅 Ça va pas être facile à écrire ! Mais allons-y pas à pas.
✨ Tout d'abord, il nous faut une **variable distance**, qui contiendra... la valeur de la distance, qu'on va calculer.

- :mouse pointer: Créer une variable **distance** et place le bloc qui permet de **définir sa valeur** dans le container `||functions: function [calculDistance] ||`

```blocks 
function calculDistance () {
    distance = 0

}
```

## 3. Les variables de la formule 

_🤔 Maintenant, de quoi on a besoin ?_

![formule](/static/skillmap/racer/racer1.gif "La formule de la distance")

---

**Dans la formule, on a deux points dont les coordonnées sont (x1, y1) et (x2,y2) ?**  
_❓ Mais pour nous, à quoi ça correspond ?_  
💭 Réfléchis, puis vérifie ta réponse en cliquant sur le bouton 💡  

```
Les coordonnées des sprites de la cible et du viseur !
```

## 4. Récupérer les éléments

**Ok, super ! Commençons par là**

- :mouse pointer: Récupère les blocs qui permettent d'avoir **la valeur des coordonnées des sprites**.

---

💡_**Indice 1 :** Chaque sprite aura deux blocs : un bloc pour son **x** et un bloc pour son **y**, donc 4 en tout !_  
💡_**Indice 2 :** Tu ne pourras pas les ajouter tout de suite dans le code, ils vont dans des **trous ronds**_

```
[ Ajouter une image des blocs ]
```

## 5. Construire la formule 

**Passons aux choses sérieuses !**
🚀 Il est temps de construire la formule.

--- 
✏️ Dans le trou rond de ``||Variables: définir [distance ▾] à (0)||``, on va ajouter au fur à mesure des blocs de la catégorie ``||Math:Maths||``.

- :mouse pointer: Essaie de construire la formule de la distance qui utilise les coordonnées du sprite **Cible** pour le point **(x1,y1)** et celles du sprite du **viseur** pour le point **(x2,y2)**.

💡_Si tu as besoin d'aide, regarde les étapes dans l'indice !_

```
1. définir [distance ▾] à (racine carrée ( ))
2. définir [distance ▾] à (racine carrée ( (1) + (2) ))
3. dans les trous (1) et (2) de l'addition, mettre un bloc () ** () (L'opérateur de puissance)
=> définir [distance ▾] à (racine carrée ( ((3) ** (4)) + ((5) ** (6)) ))
4. dans les trous (3) et (5) des puissance, mettre un bloc () - ()
=> définir [distance ▾] à (racine carrée ( (((7)-(8)) ** (4)) + (((9)-(10)) ** (6)) ))
5. écrire "2" dans les trous (4) et (6)
4. Compléter les trous comme ceci : 
    (7) = mySprite x
    (8) = Cible x
    (9) = mySprite y
    (10) = Cible y
=> définir [distance ▾] à (racine carrée ( (( mySprite x - Cible x) ** 2 ) + (( mySprite y - Cible y) ** 2 ) ))
```

## 6.  Un peu d'aide ? 

Tu n'est pas sûr·e de ton code ? 👀

---

- :lightbulb: Regarde dans l'ampoule pour comparer !

```blocks 

function calculDistance () {
    distance = Math.sqrt((mySprite.x - Cible.x) ** 2 + (mySprite.y - Cible.y) ** 2)
    
}
```

## 7. Calculer le score (1/3)

Super ! 🎉 Une bonne chose de faite.  
Maintenant, on doit calculer le score en fonction de la distance au centre de la cible.   
  
Pas de panique ! On a déjà calculé les distances pour toi :   

⚪ **50 pts** - distance ≤ 4  
⚫ **250 pts** - 4 < distance ≤ 9.5  
🔵 **500 pts** - 9.5 < distance ≤ 14  
🔴 **750 pts** - 14 < distance ≤ 20  
🟡 **1000 pts** - 20 < distance ≤ 22.5  

---

Dans la fonction `||functions: function [calculDistance] ||`, on va donc tester la valeur de distance dans un grand ``||logic: si < > alors||``. 

- :pencil: Sur ta fiche, écris en pseudo code ton ``||logic: si/sinon alors||``, qui permet de tester les valeurs de ``||Variables: distance||`` pour calculer le score.

## 8. Calculer le score (2/3)

Pour modifier le **score**, on va utiliser le bloc `||info:modifier le score de (1) ||`.

- :mouse pointer: Ajoute 5 blocs `||info:modifier le score de (1) ||` avec les différentes valeurs de score.

--- 

⚪ **50 pts** - distance ≤ 4   
⚫ **250 pts** - 4 < distance ≤ 9.5   
🔵 **500 pts** - 9.5 < distance ≤ 14   
🔴 **750 pts** - 14 < distance ≤ 20   
🟡 **1000 pts** - 20 < distance ≤ 22.5   

## 9. Calculer le score (3/3)

Tu veux vérifier ton code ? 👀
---

- :lightbulb: Regarde dans l'ampoule pour voir une solution!

```blocks 
function calculDistance () {
    distance = Math.sqrt((mySprite.x - Cible.x) ** 2 + (mySprite.y - Cible.y) ** 2)
    console.logValue("x", 0)
    if (distance < 4) {
        info.changeScoreBy(1000)
    } else {
        if (distance < 9.5) {
            info.changeScoreBy(750)
        } else {
            if (distance < 14) {
                info.changeScoreBy(500)
            } else {
                if (distance < 20) {
                    info.changeScoreBy(250)
                } else {
                    if (distance < 22.5) {
                        info.changeScoreBy(50)
                    }
                }
            }
        }
    }
}
```

## 9. On y est presque !

On a oublié quelque chose, non ? 🤔
Mais oui ! Il faut **appeler** `||functions: function [calculDistance] ||` !

- :mouse pointer: Ajoute le bloc pour appeler `||functions: function [calculDistance] ||` quand on appuie sur le **bouton (A)** !

```blocks

controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    mySprite.setImage(img`
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        2 2 2 2 2 2 2 . . 2 2 2 2 2 2 2 
        2 2 2 2 2 2 2 . . 2 2 2 2 2 2 2 
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        `)
    calculDistance()
})
function calculDistance () {}
let mySprite: Sprite = null
```

## Le final

✨ Bien joué !  

🕹️ Jette un oeil à ce que tu as créé jusqu'ici ! Maintenant, ton score augmente quand tu tires sur la cible !

🚀 Dès que tu es prêt·e, clique sur "Terminé" pour retourner à la carte des tutoriels et poursuivre la création de ce jeu. 

🎯 Dans la prochaine partie, on va ajouter un compte à rebours et rendre le jeu plus difficile !



```template
controller.A.onEvent(ControllerButtonEvent.Released, function () {
    mySprite.setImage(img`
        . . . . . . . 1 1 . . . . . . . 
        . . . . . . . 1 1 . . . . . . . 
        . . . . . . . 1 1 . . . . . . . 
        . . . . . . . 1 1 . . . . . . . 
        . . . . . . . 1 1 . . . . . . . 
        . . . . . . . 1 1 . . . . . . . 
        . . . . . . . 1 1 . . . . . . . 
        1 1 1 1 1 1 d . . d 1 1 1 1 1 d 
        1 1 1 1 1 1 d . . d 1 1 1 1 1 d 
        . . . . . . . d d . . . . . . . 
        . . . . . . . 1 1 . . . . . . . 
        . . . . . . . 1 1 . . . . . . . 
        . . . . . . . 1 1 . . . . . . . 
        . . . . . . . 1 1 . . . . . . . 
        . . . . . . . 1 1 . . . . . . . 
        . . . . . . . d d . . . . . . . 
        `)
})
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    mySprite.setImage(img`
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        2 2 2 2 2 2 2 . . 2 2 2 2 2 2 2 
        2 2 2 2 2 2 2 . . 2 2 2 2 2 2 2 
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        . . . . . . . 2 2 . . . . . . . 
        `)
})
scene.setBackgroundImage(sprites.builtin.aquaticBackground)
let mySprite = sprites.create(img`
    . . . . . . . 1 1 . . . . . . . 
    . . . . . . . 1 1 . . . . . . . 
    . . . . . . . 1 1 . . . . . . . 
    . . . . . . . 1 1 . . . . . . . 
    . . . . . . . 1 1 . . . . . . . 
    . . . . . . . 1 1 . . . . . . . 
    . . . . . . . 1 1 . . . . . . . 
    1 1 1 1 1 1 d . . d 1 1 1 1 1 d 
    1 1 1 1 1 1 d . . d 1 1 1 1 1 d 
    . . . . . . . d d . . . . . . . 
    . . . . . . . 1 1 . . . . . . . 
    . . . . . . . 1 1 . . . . . . . 
    . . . . . . . 1 1 . . . . . . . 
    . . . . . . . 1 1 . . . . . . . 
    . . . . . . . 1 1 . . . . . . . 
    . . . . . . . d d . . . . . . . 
    `, SpriteKind.Player)
mySprite.setStayInScreen(true)
controller.moveSprite(mySprite, 120, 120)
let Cible: Sprite = null
Cible = sprites.create(img`
    .................1111111111111.................
    ..............1111111111111111111..............
    ............11111111111111111111111............
    ..........111111111111111111111111111..........
    .........11111111fffffffffffff11111111.........
    ........1111111fffffffffffffffff1111111........
    .......111111fffffffffffffffffffff111111.......
    ......11111fffffffffffffffffffffffff11111......
    .....11111fffffffffffffffffffffffffff11111.....
    ....11111fffffffff99999999999fffffffff11111....
    ...11111ffffffff999999999999999ffffffff11111...
    ...1111fffffff9999999999999999999fffffff1111...
    ..11111ffffff999999999999999999999ffffff11111..
    ..1111ffffff99999999999999999999999ffffff1111..
    .11111fffff9999999222222222999999999fffff11111.
    .1111ffffff9999922222222222229999999ffffff1111.
    .1111fffff999992222222222222229999999fffff1111.
    1111ffffff999922222222222222222999999ffffff1111
    1111fffff99999222222222222222229999999fffff1111
    1111fffff99992222225555555222222999999fffff1111
    1111fffff99992222255555555522222999999fffff1111
    1111fffff99992222255555555522222999999fffff1111
    1111fffff99992222255555555522222999999fffff1111
    1111fffff99992222255555555522222999999fffff1111
    1111fffff99992222255555555522222999999fffff1111
    1111fffff99992222255555555522222999999fffff1111
    1111fffff99992222255555555522222999999fffff1111
    1111fffff99992222225555555222222999999fffff1111
    1111fffff99999222222222222222229999999fffff1111
    1111ffffff999922222222222222222999999ffffff1111
    .1111fffff999992222222222222229999999fffff1111.
    .1111ffffff9999922222222222229999999ffffff1111.
    .11111fffff9999999222222222999999999fffff11111.
    ..1111ffffff99999999999999999999999ffffff1111..
    ..11111ffffff999999999999999999999ffffff11111..
    ...1111fffffff9999999999999999999fffffff1111...
    ...11111ffffffff999999999999999ffffffff11111...
    ....11111fffffffff99999999999fffffffff11111....
    .....11111fffffffffffffffffffffffffff11111.....
    ......11111fffffffffffffffffffffffff11111......
    .......111111fffffffffffffffffffff111111.......
    ........1111111fffffffffffffffff1111111........
    .........11111111fffffffffffff11111111.........
    ..........111111111111111111111111111..........
    ............11111111111111111111111............
    ..............1111111111111111111..............
    .................1111111111111.................
    `, SpriteKind.Enemy)
    Cible.setPosition(80, 35)
    Cible.vx = 35
```


```package
cible_assetpack=github:neo-ptolemus/cible_assetpack
```
