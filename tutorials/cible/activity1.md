# Jeu de cible

## Introduction @unplugged

🎯 **Codons un jeu de tir à la cible !** 🎯

Dans ce tutoriel, on va réviser la formule de la distance euclidienne en créeant un jeu de tir.

![Apercu](/apercu1.gif "Regarde ce qu'on va faire !")

## 1. Planter le décor
**Montre-leur quelque chose qui vaille la peine d'être regardé** 🔭

- :mouse pointer: Dans la catégorie ``||scene:Scene||``, prends le bloc  ``||scene: définir image d'arrière-plan à []||``
et place-le à l'interieur du container ``||loops:au démarrage||`` qui est déjà sur l'espace de travail.

- :image: Ensuite, clique sur le carré ◻️ pour choisir un arrière-plan dans la galerie, ou dessine le tien ! 🖍️

```blocks
// @highlight
scene.setBackgroundImage(sprites.builtin.aquaticBackground)
```

## 2.1 Dessine ton viseur


- :mouse pointer: Dans la catégorie ``||sprites:Sprites||``, prends le bloc ``||variables (sprites):définir [mySprite] à sprite [ ] de type [Player]||`` 
et connecte-le à la fin du container ``||loops:au démarrage||``.

- :square: Clique sur le carré gris au milieu du bloc
``||variables (sprites):définir [mySprite] à sprite [ ] de type [Player]||``. Tu trouveras déjà un viseur au début de la galerie, mais tu peux dessiner le tien ! ➕

```blocks
scene.setBackgroundImage(sprites.builtin.aquaticBackground)
// @highlight
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
```

## 2.2 Contrôle ton viseur

🌟 Faison bouger ton viseur  🌟

---

- :mouse pointer: Trouve le bloc ``||controller: déplacer [mySprite] avec les boutons ⊕||`` 
et place-le à la fin du container ``||loops:au démarrage||``. 

** Maintenant, essaie de bouger ton viseur dans le simulateur !**  
Ton vaisseau peut bouger avec le joystick ou les flèches du clavier.

```blocks
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
// @highlight
controller.moveSprite(mySprite)
```

## 2.3 Rester sur l'écran

**Oh-oh... Si tu vas jusqu'aux bords de l'écran, ton viseur disparaît !**

- :mouse pointer: Pour faire en sorte que ton viseur reste dans la limite de l'écran, trouve le bloc  ``||sprites:définir [mySprite] rester à l'écran <on>||`` et connecte le à la fin du programme.

- :sliders: Tu peux aussi en profiter pour modifier la vitesse de ton viseur ! Appuie sur le bouton **⊕** du bloc ``||controller: déplacer [mySprite] avec les boutons ⊕||`` et met  les les valeurs de **vx** et **vy** à **120**. Quel boost ! 🚀

```blocks
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
// @highlight
controller.moveSprite(mySprite, 120, 120)
// @highlight
mySprite.setStayInScreen(true)
```

```package
cible_assetpack=github:neo-ptolemus/cible_assetpack
```