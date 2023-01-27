# La Guerre des Étoiles


## Introduction @unplugged

** Partons explorer les profondeurs de l'espace ! **

Dans ce tutoriel, tu va pouvoir créer ton propre vaisseau pour commencer ton voyage.

![Flying through space](/static/skillmap/space/space1.gif "Un voyage intergalactique" )

## Planter le décor
**Montre-leur quelque chose qui vaille la peine d'être regardé** 🔭

- :mouse pointer: Dans la catégorie ``||scene:Scene||``, prend le bloc  ``||scene: démarrer effet [confetti] sur l'écran``
et place-le à l'interieur du container ``||loops:au démarrage||`` qui est déjà sur l'espace de travail.

- :star: Ensuite, sélectionne ``||scene:champ étoilé||`` (au lieu de ``||scene:confetti||``) dans le menu déroulant. Regarde les étoiles défiler ! 🚀 


```blocks
// @highlight
effects.starField.startScreenEffect()
```



## Dessine ton vaisseau
**🧑🏿‍🚀 C'est le moment de choisir ton vaisseau ! 👩🏾‍🚀**

- :mouse pointer:Dans la catégorie ``||sprites:Sprites||``, prend le bloc ``||variables (sprites):définir [mySprite] à sprite [ ] de type [Player]||`` 
et connecte-le à la fin du containe ``||loops:au démarrage||``.

- :square:Clique sur le carré gris au milieu du bloc
``||variables (sprites):définir [mySprite] à sprite [ ] de type [Player]||``
pour dessiner ton propre vaisseau ! Tu es plutôt du genre vieux tas de féraille ou fusée blanche et épurée ?

--- 

**Astuce :** Tu n'as pas envie de tout dessiner toi-même ?   
Dans l'éditeur de sprite, clique sur l'onglet "Galerie" et choisis une des images déjà prête.

```blocks
effects.starField.startScreenEffect()
// @highlight
let mySprite = sprites.create(img`
    . . . . . . . 9 9 . . . . . . .
    . . . . . . 9 . . 9 . . . . . .
    . . . . . . 9 . . 9 . . . . . .
    . . . . . 9 . 9 9 . 9 . . . . .
    . . . . . 9 . 9 9 . 9 . . . . .
    . . . . 9 . 9 9 9 9 . 9 . . . .
    . . . . 9 . 9 9 9 9 . 9 . . . .
    . . . 9 . 9 9 9 9 9 9 . 9 . . .
    . . . 9 . 9 . . . . 9 . 9 . . .
    . . 9 . 9 9 . 9 9 . 9 9 . 9 . .
    . . 9 . 9 9 . . . . 9 9 . 9 . .
    . 9 . 9 9 9 . 9 9 9 9 9 9 . 9 .
    . 9 . 9 9 9 . 9 9 9 9 9 9 . 9 .
    9 . 9 9 9 9 9 9 9 9 9 9 9 9 . 9
    9 . . . . . . . . . . . . . . 9
    9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9
`, SpriteKind.Player)
```

## Contrôle ton vaisseau

🌟 Faison bouger ton vaisseau 🌟

---

- :mouse pointer: Trouve le bloc ``||controller: déplacer [mySprite] avec les boutons ⊕||`` 
et place-le à la fin du container ``||loops:au démarrage||``. 

** Maintenant, essaie de bouger ton vaisseau dans le simulateur !**  
Ton vaisseau peut bouger avec le joystick ou les flèches du clavier.  



```blocks
effects.starField.startScreenEffect()
let mySprite = sprites.create(img`
    . . . . . . . 9 9 . . . . . . .
    . . . . . . 9 . . 9 . . . . . .
    . . . . . . 9 . . 9 . . . . . .
    . . . . . 9 . 9 9 . 9 . . . . .
    . . . . . 9 . 9 9 . 9 . . . . .
    . . . . 9 . 9 9 9 9 . 9 . . . .
    . . . . 9 . 9 9 9 9 . 9 . . . .
    . . . 9 . 9 9 9 9 9 9 . 9 . . .
    . . . 9 . 9 . . . . 9 . 9 . . .
    . . 9 . 9 9 . 9 9 . 9 9 . 9 . .
    . . 9 . 9 9 . . . . 9 9 . 9 . .
    . 9 . 9 9 9 . 9 9 9 9 9 9 . 9 .
    . 9 . 9 9 9 . 9 9 9 9 9 9 . 9 .
    9 . 9 9 9 9 9 9 9 9 9 9 9 9 . 9
    9 . . . . . . . . . . . . . . 9
    9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9
`, SpriteKind.Player)
// @highlight
controller.moveSprite(mySprite)
```

## Rester sur l'écran

**Oh-oh... Si tu vas jusqu'aux bords de l'écran, ton vaisseau disparaît !**

- :mouse pointer: Pour faire en sorte que ton vaisseau reste dans la limite de l'écran, trouve le bloc  ``||sprites:définir [mySprite] rester à l'écran <on>||`` et connecte le à la din programme.


```blocks
effects.starField.startScreenEffect()
let mySprite = sprites.create(img`
    . . . . . . . 9 9 . . . . . . .
    . . . . . . 9 . . 9 . . . . . .
    . . . . . . 9 . . 9 . . . . . .
    . . . . . 9 . 9 9 . 9 . . . . .
    . . . . . 9 . 9 9 . 9 . . . . .
    . . . . 9 . 9 9 9 9 . 9 . . . .
    . . . . 9 . 9 9 9 9 . 9 . . . .
    . . . 9 . 9 9 9 9 9 9 . 9 . . .
    . . . 9 . 9 . . . . 9 . 9 . . .
    . . 9 . 9 9 . 9 9 . 9 9 . 9 . .
    . . 9 . 9 9 . . . . 9 9 . 9 . .
    . 9 . 9 9 9 . 9 9 9 9 9 9 . 9 .
    . 9 . 9 9 9 . 9 9 9 9 9 9 . 9 .
    9 . 9 9 9 9 9 9 9 9 9 9 9 9 . 9
    9 . . . . . . . . . . . . . . 9
    9 9 9 9 9 9 9 9 9 9 9 9 9 9 9 9
`, SpriteKind.Player)
controller.moveSprite(mySprite)
// @highlight
mySprite.setStayInScreen(true)

```


## Final @unplugged

**Joli travail !**

---

N'oublie pas de jouer un peu dans le simulateur avant de finir ce tutoriel.

![You in space](/static/skillmap/space/space1end.gif "Voyage dans ton propre jeu" )

Tout est bien comme tu veux ? Tu peux toujours retourner en arrière et éditer les étapes, si tu veux faire des modifications.


## Byeeee

** 🚀 C'est tout ! 🚀**

Tu es fin prêt·e à voyager dans l'univers !

Clique sur  **"Terminé"** pour passer à la suite.
