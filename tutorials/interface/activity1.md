# Apprendre à connaître MakeCode Arcade


```ghost
let mySprite: Sprite = null;
mySprite.startEffect(effects.spray)
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    game.showLongText("The little unicorn walked into the meadow.", DialogLayout.Top)
    scene.cameraShake(4, 500)
})
scene.setBackgroundColor(9)
scene.setBackgroundImage()
mySprite.x += 0
effects.confetti.startScreenEffect()
effects.confetti.endScreenEffect()
mySprite.setPosition(70, 80)
for (let index = 0; index < 4; index++) {
    controller.moveSprite(mySprite)
    music.setVolume(20)
    music.playMelody("- - - - - - - - ", 120)
}
game.onUpdateInterval(5000, function () {
    if (game.askForString("Continue?") == "Y" || game.askForString("Continue?") == "y") {
        mySprite.say(":)")
    }
    game.splash("")
})

```

### @explicitHints true

## Introduction @unplugged

![Psyched Monkey](/static/skillmap/interface/monkey.png "Psyched Monkey is Ready!" )

**Prêt·e à coder tes propres jeux ?**

À la fin de ce tutoriel, tu auras appris à :
- suivre les instructions du tutorials
- trouver les blocs dans la boite à outils
- assembler du code dans la zone de travail
- exécuter ton jeu dans le simulateur

Tu vas te retrouver avec ton propre jeu d'arcade avant d'avoir dit ouf !

## étape 1

**⭐Bienvenue⭐**

Tu viens de faire la chose la plus importante dans un tutoriel : lire les instructions !

Si tu n'arrives pas à lire toutes les instructions, appuie sur **[v Plus...]** pour agrandir la boite de texte.

---

Quand tu es prêt·e à passer à la prochaine étape, clique sur **[ > Suivant ]** pour continuer.


## étape 2

C'est dans cette boite que tu trouveras les informations pour chaque étape.

Si tu ne trouves pas toutes les informations dont tu as besoin, 
clique sur l'ampoule pour voir un indice supplémentaire.


#### ~ tutorialhint 
```
**Tu as trouvé les indices !**
```


## Utiliser l'espace de travail

Maintenant, parlons un peu de ton [__*espace de travail*__](#workIt "C'est à dire, la zone où tu construis ton code").

Ton espace de travail est la zone à côté des instructions où tu vas connecter les blocs entre eux pour créer un programme.  
Tous les blocs ne se connectent pas, mais on en parlera un peu plus tard.

---

🔲 Clique à l'intérieur de la zone de texte du bloc  ``||game:splash "___"||`` 
etchange la phrase qui y est écrite en quelque chose d'un plus intéressant.

---

**Astuce :** Tu as remarqué que le premier "__espace de travail__" au début de cette étape a un style différent ? 
De temps en temps, on va marquer les mots importants de cette façon. Passe ta souris dessus pour voir une définition.

#### ~ tutorialhint 
```blocks
game.splash("J'aime les bananes !")
```

```template
game.splash("Ces blocs sont dans ton espace de travail !")

```

## À la rencontre des blocs @unplugged

Les blocs peuvent être tirés de la [__*boite à outils*__](#tools "La colonne entre le tutoriel et la zone de tavail qui contient une liste de catégories."), 

connecté, dupliqué, et supprimé.

Continue pour en apprendre plus sur les blocs.

![Block Animation](/static/skillmap/interface/use_blocks.gif "Ajout d'un bloc, connexion et suppression." )



## Ta boite à outils

**Les blocs dont tu as besoin ne seront pas toujours dans l'espace de travail dès le début.**

Dans les instructions, la description du bloc dont tu as besoin sera souvent 
de la même couleur que la catégorie dans laquelle il se trouve.

**Par exemple :** On peut écrire ``||game:splash "___"||`` si on veut que 
tu trouves ça :

```block
game.splash(" ")
```

Ce bloc ajout un "[__*splash screen*__](#splasht "Un message qui s'affiche en plein écran pendant que le programme se charge.")" à ton projet.

## Ta boite à outils 2

**Regardons comment ça marche**

🔲 Trouve le bloc
``||scene:set background color to [ ]||`` et connecte le tout en haut 
dans le bloc **au démarrage** qui est déjà dans la zone de travail.

#### ~ tutorialhint 
```blocks
scene.setBackgroundColor(0)
game.splash("Mon âne est plus fort que le tiens")
```



## L'exception

Toute règle a une exception, alors jetons un coup d'oeil à un des blocs qui
n'est pas de la même couleur que sa catégorie.
Le bloc ``||variables: définir [mySprite] à sprite [ ] de type [Player]||`` est rouge,
mais il fait partie de la catégorie ``||sprites:Sprites||``.

---

<!-- **Astuce :** Si tu n'arrives pas à trouver le bloc dont tu as besoin, essaie -->


🔲 Connecte ``||variables: définir [my sprite] à sprite [ ] de type [Player]||`` à la fin
du bloc **au démarrage** et
bidouille-le jusqu'à ce que le [__*sprite*__](#sprote "Une image 2D qui bouge sur l'écran") s'affiche sur l'écran du simulateur.

*(Passe ta souris sur le mot __sprite__ ci-dessus pour voir une défintion)*

---

**Astuce :** Attrape le bloc ``||game:splash "___"||`` qui se trouve dans le bloc ``||loops: au démarrage||``
et fais-le glisser sur la boite à outils pour le supprimer. Ton sprite va s'afficher !
#### ~ tutorialhint

![Open image editor](/static/skillmap/misc/open-image-editor-small.gif "Comment ouvrir l'éditeur d'image." )

---



```blocks
scene.setBackgroundColor(5)
let mySprite = sprites.create(img`
    e e e . . . . e e e . . . . 
    c d d c . . c d d c . . . . 
    c b d d f f d d b c . . . . 
    c 3 b d d b d b 3 c . . . . 
    f b 3 d d d d 3 b f . . . . 
    e d d d d d d d d e . . . . 
    e d f d d d d f d e . b f b 
    f d d f d d f d d f . f d f 
    f b d d b b d d 2 f . f d f 
    . f 2 2 2 2 2 2 b b f f d f 
    . f b d d d d d d b b d b f 
    . f d d d d d b d d f f f . 
    . f d f f f d f f d f . . . 
    . f f . . f f . . f f . . . 
    `, SpriteKind.Player)
```


## Blocs "Container"

**Maintenant, regardons les différents types de blocs et comment les utiliser.** 

Tout d'abord, il y a les blocs [__*container*__](#blockIt "Les blocs qui contiennent d'autres blocs"). 
Les containers ont un bord supérieur et inférieur, entourant un espace ouvert au milieu
qui permet de connecter des blocs à l'intérieur. Les containers gèrent *quand* le code à l'intérieur est exécuté. Voici un exemple : 

```blocks
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
	
})
```
---

🔲  Trouve le container ``||controller:quand bouton [A] est [appuyé] ||`` et place-le 
dans l'espace de travail. On le complétera à l'étape suivante.

#### ~ tutorialhint

```blocks
controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    let mySprite: Sprite = null
})
```

## Blocs "ordinaires"

Ensuite, il y a les blocs [__*ordinaires*__](#sBlockIt "Les blocs d'une seule ligne qui constituent la plus grande partie des programmes"). 
Les blocs ordinaires sont des blocs d'une seule ligne avec une encoche en haut et en
bas qui leur permet de se connecter avec d'autres blocs. Les blocs sont exécutés de haut en bas dans le container dans lequel ils sont placés.

Voici un exemple de bloc ordinaire :

```block
let mySprite: Sprite = null;
mySprite.startEffect(effects.spray)
```

---

🔲  Trouve le bloc ``||sprites:[mySprite] commencer effet [spray] ||``  
et connecte-le dans le container  **quand bouton A est appuyé**... ensuite choisis
ton effet préféré !

#### ~ tutorialhint
```blocks
let mySprite: Sprite = null;

controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    mySprite.startEffect(effects.confetti)
})
```



## Blocs valeurs
Enfin, il existe les blocs [__*valeur*__](#aBlockIt "une pièce spéciale qui fournit des valeurs pour d'autres blocs"). 
Les blocs valeurs sont des pièces spéciales qui joute des informations 
aux autres blocs.
Parfois ils sont pointus, parfois ils sont arrondis, mais ils ont toujours besoin d'être connectés dans un autre bloc.
Les blocs valeurs ressemblent à ça :

![Value Blocks](/static/skillmap/interface/parameter-blocks.png "This is what the shape of an value block looks like" )

---

🔲  Connecte le bloc ``||sprites:[mySprite] dit [":)"] ||`` à la fin du container
**quand bouton A appuyé**.

🔲  Trouve le bloc valeur ``||game: demande un nombre [" "] ||`` et connecte-le à la 
place de **":)"**
---

**Astuce :** Les blocs valeurs ont des formes différentes suivant 
le type d'information qu'ils contiennent.
Chaque valeur ne peut rentrer que dans certains types de trous.
#### ~ tutorialhint
```blocks
let mySprite: Sprite = null;

controller.A.onEvent(ControllerButtonEvent.Pressed, function () {
    mySprite.say(game.askForNumber(""))
})
```

## L'assemblage final

🎨 C'est le moment d'être créatif·ve ! 🎨

N'hésite pas à jeter un coup d'oeil aux blocs que l'on a ajoutés dans la boite à outils.

Ce n'est pas grave si tu ne sais pas ce qu'ils font.
Bidouille-les un peu et regarde ce que ça fait au jeu !

---

**Astuce :** Tu peux tester ton jeu à n'importe quel moment grâce au simulateur à droite !
Utilise le bouton rafraîchir (🔄) pour relancer le chargement, et joue avec ton jeu 
en utilisant les boutons que tu as programmés !



## Conclusion 

🎈 Félicitations 🎈 

Tu as appris tout ce que tu devais savoir pour passer à un nouveau tutoriel.
Maintenant, tu vas pouvoir continuer à apprendre de nouvelles astuces pour 
créer des jeux avec MakeCode Arcade !
