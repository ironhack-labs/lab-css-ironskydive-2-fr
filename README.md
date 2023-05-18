![logo_ironhack_blue 7](https://user-images.githubusercontent.com/23629340/40541063-a07a0a8a-601a-11e8-91b5-2f13e4e6b441.png)

# Exercice guidé - IronSkydive 🎨 - stylisme (CSS)

<br>

## Introduction

À ce stade, vous vous êtes familiarisé avec les feuilles de style en cascade (CSS), et vous savez comment:

- cibler les éléments en utilisant les balises, les classes ou les identifiants,
- travailler avec les propriétés de police et de texte,
- ajouter des couleurs au texte et à l'arrière-plan.

N'oubliez pas d'ouvrir le **CodePen** que vous avez créé au début de l'exercice pour effectuer les différentes itérations de l'exercice.

C'est parti !

<br>

## IDs

Tout d'abord, vous allez ajouter quatre id, un par `<section>` que vous avez définie. Du haut vers le bas, les identifiants doivent être :

- `general-information`
- `structure`
- `team`
- `schedule`

Cela va nous aider à identifier les différentes sections. Cela crée également quelque chose appelé [liens internes](http://www.yourhtmlsource.com/text/internallinks.html). Que se passe-t-il maintenant si vous cliquez sur les liens `<nav>` en haut de la page ? Elle défile automatiquement jusqu'à la section! :white_check_mark:

<br>

## Paramètres généraux pour toute la page

OK, commençons à utiliser l'onglet CSS dans votre projet CodePen. Nous allons commencer par configurer toute la page pour utiliser la règle suivante (copiez le snippet au début de l'onglet CSS):

```css
html,
body {
  margin: 0;
  padding: 0;
}
```

Cela va supprimer toutes les `margin` et tous les `padding` des éléments, ou en français simple, les mettre à `0`. Pourquoi faisons-nous cela ? Nous le faisons pour réinitialiser certains styles que votre navigateur applique automatiquement aux éléments, connus sous le nom de _styles par défaut du navigateur_.

<br>

![](https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_603c70d5d3664d3cd0d7829c6b0367cb.png)

<br>

:thought_balloon: Ne vous inquiétez pas de ce que sont les propriétés de `margin` et `padding` pour l'instant, nous en parlerons dans un instant.

<br>

## Police et texte

### font-family

Pour l'ensemble du site Web IronSkydive, nous allons utiliser une police appelée `Roboto`. Vous pouvez la trouver dans `https://fonts.google.com/`, le référentiel de Google qui héberge un grand nombre de polices. En général, vous devez suivre un processus pour incorporer l'une de ces polices dans votre site, mais nous l'avons simplifié pour vous.

Au tout début de l'onglet CSS de votre CodePen, copiez la ligne suivante:

```css
@import url("https://fonts.googleapis.com/css?family=Roboto+Condensed:700|Roboto:100,300,700");
```

Rien ne se passe encore. Cela ajoute simplement une référence à deux polices différentes:

- `Roboto`, avec des poids de 100, 300 et 700.
- `Roboto Condensed`, avec un poids de 700.

Vous allez utiliser les deux sur votre site Web. Alors changeons la police pour l'ensemble du document. Le document entier doit avoir un texte formaté comme suit :

- font : `Roboto`.
- size : `10px`.
- line height : `3,5em`.
- weight : `300`.

Rappelez-vous: nous pouvons cibler des éléments sur lesquels nous voulons appliquer des styles en utilisant des classes ou des identifiants ou _le nom de la balise_.
Vous pouvez utiliser la balise `body` et ajouter ces propriétés CSS respectives à celle-ci. Une fois que vous avez défini la police pour le document, changeons le comportement des en-têtes.

Vous utilisez des en-têtes de 1 à 5, utilisez un sélecteur multiple qui les sélectionnera tous. À l'intérieur de ce sélecteur, vous définissez la police sur `Roboto Condensed`. Nous allons modifier la taille des en-têtes dans un sélecteur différent, car chacun d'entre eux aura une taille différente.

```css
/* CSS multiselector example */

h1,
h2,
h3,
h4,
h5,
h6 {
  /*  define font-family here  */
}
```

Le résultat devrait ressembler à ceci:

<br>

![](https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_8772412e132f34f5246213a371f16ea5.png)

<br>

### Propriétés du texte

Actuellement, toutes les polices ont la même taille, changeons cela. Tout d'abord, stylisons les en-têtes en incluant les propriétés suivantes:

| Heading | Properties                                                                                                                                                                                         |
| ------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `<h1>`  | Size: `9em` <br> Align: `center` <br> Transform: `uppercase`                                                                                                                                       |
| `<h2>`  | Size: `5em` <br> Align: `center` <br> Transform: `uppercase`                                                                                                                                       |
| `<h3>`  | Size: `4.2em` <br> Align: `center` <br> [Line height](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height): `1em`                                                                         |
| `<h4>`  | Size: `1.5em` <br> [Letter spacing](https://developer.mozilla.org/en/docs/Web/CSS/letter-spacing): `0.4px` <br> [Line height](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height): `1em` |
| `<h5>`  | Size: `1.2em` <br> [Line height](https://developer.mozilla.org/en-US/docs/Web/CSS/line-height): `1em`                                                                                              |

Une fois que vous avez appliqué ces styles aux différents en-têtes dont vous disposez, le `<h1>` et le `<h2>` ont besoin de plus d'espace entre eux. Ajoutons plus d'espace en définissant la propriété `line-height` (hauteur de ligne) de `<h2>` sur `4em`.

Vous avez déjà spécifié tous les styles de texte dont vous avez besoin sur votre site web.

<br>

![](https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_b0f5f1c39886cbe09c75630ca7706c2a.png)

<br>

Super, maintenant ajoutons des couleurs à notre site web.

## Couleurs

<br>

Précédemment, vous avez utilisé les propriétés CSS de texte pour modifier l'apparence du site web, en ajoutant une police personnalisée et des tailles en fonction de la balise. Maintenant, il est temps de lui donner de la couleur!

Lorsque vous développez un site web, il est bon de garder à l'esprit un tableau avec les différentes couleurs que vous allez utiliser. Dans ce cas, le tableau est le suivant:

| Couleur                | RGB            | Résultat                                                                                      |
| ---------------------- | -------------- | --------------------------------------------------------------------------------------------- |
| Bleu                   | `67, 163, 230` | <div style="background: rgb(67, 163, 230); height: 20px; margin: 0 auto; width: 20px;"></div> |
| Dark Blue (Bleu foncé) | `25, 33, 41`   | <div style="background: rgb(25, 33, 41); height: 20px; margin: 0 auto; width: 20px;"></div>   |
| Texte                  | `0, 0, 0`      | <div style="background: rgb(0, 0, 0); height: 20px; margin: 0 auto; width: 20px;"></div>      |

Ce tableau vous aidera à communiquer avec votre équipe de conception UX/UI. Lorsqu'ils vous demandent d'appliquer le `Dark Blue` (Bleu foncé) comme couleur de fond, vous saurez immédiatement de quelle couleur il s'agit.

Un par un, décrivons les modifications que vous devez apporter aux différentes sections que nous avons définies lors de la première itération de cet exercice. Rappelez-vous de la mise en page que nous avons créée:

<br>

![](https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_8f778c8cd703db596d5bb22dae089716.jpg)

<br>

Ouvrez CodePen dans votre navigateur et commençons!

<br>

### Nav

<br>

L'objectif final pour la barre de navigation (`nav`) est le suivant:

<br>

![](https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_065124c74d928a12e32e446b759968e3.png)

<br>

Commençons par ajouter de la couleur. Ajoutez `Dark Blue` comme couleur de fond.

Il est bon d'utiliser des sélecteurs de classe au lieu d'utiliser des sélecteurs de balises HTML pour définir les styles. Et si vous appliquez un style à la balise `nav` et qu'à l'avenir, vous la changez en `header`? Vous perdriez tous les styles et devriez les modifier un par un dans le CSS.

Créez un sélecteur dans votre onglet CSS appelé `.nav-bar` et attribuez-lui le style décrit ci-dessus. Ensuite, attribuez la classe à la balise `nav` dans votre HTML.

<br>

![](https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_320885335d288348997362c44aa6f6b0.png)

<br>

Ça marche... en quelque sorte. Nous devons définir la couleur des liens en blanc et si vous essayez de définir la propriété `color: white` à l'intérieur de la classe `.nav-bar`, cela ne fonctionnera pas car les mots/liens sont enveloppés dans des balises `a`.

Nous pouvons aller dans la direction de créer une nouvelle classe et y attacher la classe à chaque élément `li` à l'intérieur de `<nav>`, ou nous pouvons suivre le principe **DRY** (Don't Repeat Yourself) et éviter de créer une autre classe, mais plutôt référencer les éléments que nous voulons cibler à travers la classe existante `.nav-bar`.

```css
.nav-bar a {
  /*  styles to be added here    */
}
```

<!-- Créons une autre classe, appelée `nav-bar-item`, et -->

Changez la `color` en _blanc_, la `text-decoration` en _none_, et la `font-size` en `2em` afin d'obtenir le résultat souhaité.

<br>

![](https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_e03b2f8983da0df77b6e88f973cfc0c5.png)

<br>

Dans les prochaines itérations, vous allez compléter le menu. Vous êtes prêt à passer à la section suivante.

<br>

### Header (En-tête)

<br>

![](https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_e80b0ee85c8f2fb8126befe68b152ab2.png)

<br>

N'ayez pas peur! C'est plus facile que ça en a l'air. Tout d'abord, vous devez définir [background image (l'image de fond)](https://developer.mozilla.org/en/docs/Web/CSS/background-image?v=control). Les propriétés de l'image de fond sont:

- **url:** `https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/ironhack-skydive-background.jpg`.
- **position:** `0 0`.
- **repeat:** `no-repeat`
- **size:** `cover`.

N'oubliez pas de créer une classe, dans ce cas `header`, et de l'attribuer à la balise `header` de votre HTML pour utiliser ce style. Maintenant, il suffit de définir la `height` de `header` à `650px`.

La prochaine étape consiste à changer la couleur du `h2` en blanc, puis à ajouter un peu de [text-shadow](https://developer.mozilla.org/en/docs/Web/CSS/text-shadow). La propriété `text-shadow` doit avoir pour valeur `#020819 8px -20px 9px`.

Pour finir cette section, changez la font-size (taille) de la citation. Définissez-la à `2.5em`. Créez une classe `quote` pour cela et ajoutez la classe à la balise `aside` dans le HTML.

<br>

![](https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_c03f57b39ea0d76161156d6e58d91307.png)

<br>

### Section 1

Dans l'une des itérations précédentes, vous avez ajouté un _id_ `general-information` à cette section. Notre objectif final pour cette section est de:

<br>

![](https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_505f90aabf6c0d4e03b4216c07c615f8.png)

<br>

Créer un sélecteur de classe `dark-background` qui applique les propriétés suivantes:

- background color (couleur de fond): dark blue (bleu foncé) (consultez le tableau au début de cette itération).
- color: white.

Une fois que vous avez créé la classe dans votre CSS, ajoutez-la à la section. Après l'application de la classe, vous pouvez constater que le texte dans la balise `<p>` est petit et n'est pas centré. Résolvons ce problème.

Tout d'abord, ajoutez une classe `text` à chaque paragraphe à l'intérieur de la section `general-information`.

Ce sélecteur devrait avoir les propriétés CSS suivantes:

- Font size (Taille de police): `2em`.
- Font weight (Poids de la police): `100`.
- Text align (Alignement du texte): `center`.

Beaucoup mieux. Terminons cette section en ajoutant quelques styles aux liens. Les liens ressembleront à des boutons et tous les liens de cette section auront la même apparence. Cela signifie que vous devez créer une classe qui applique les propriétés CSS nécessaires à un lien pour qu'il ressemble à un bouton.

<br>

:::info
:bulb: **Pourquoi n'utiliserions-nous pas un bouton**? Consultez [cette réponse très concise de StackOverflow](https://stackoverflow.com/a/25350722/4624718) pour une bonne règle de base.
:::

<br>

Créez une classe `link-btn` avec les propriétés suivantes:

- background color: blue (check out the table at the beginning of this iteration).
- color: white.
- font-family: `Roboto Condensed`.
- font size: `2em`.
- [Letter Spacing](https://developer.mozilla.org/en/docs/Web/CSS/letter-spacing): `0.5px`.
- text-align: `center`.
- text-decoration: `none`.

Ajoutez la classe aux trois liens que vous avez dans la section.

<br>

![](https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_7847968ca22bceb75dac295214859d36.png)

<br>

Hmm... Il semble que nous avons besoin d'un moyen de réorganiser nos éléments et de les placer à des positions spécifiques. Cela sera l'objectif d'une des prochaines itérations.

Passons à la section suivante.

### Section 2

Dans la deuxième section, nous avons ajouté un id `structure`. Dans cette section, vous devez simplement configurer les propriétés de taille de police et d'alignement.

Créez une classe `service-box` dans le CSS, avec les propriétés suivantes:

- Font Size: `1.7em`.
- Text Align: `center`.

Attribuez cette classe à chaque `article` à l'intérieur de la section `structure`.

Maintenant, créez de nouveaux sélecteurs multiples pour toutes les classes `img` à l'intérieur de la classe `service-box`.

:+1: Spoiler: Similaire à ce que vous avez déjà fait avec les liens dans la barre de navigation, nous aurons ce qui suit:

```css
.service-box img {
  /*  styles to be added  */
}
```

Ajoutez une propriété à l'intérieur pour définir la largeur de ces images sur `125px`.

<br>

![](https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_85b85fdc98c951967b3554ee821cbfaa.png)

<br>

### Section 3

L'objectif le plus important pour écrire du CSS de qualité est de créer des classes réutilisables. Dans cette section, nous avons à nouveau un fond bleu foncé comme couleur de fond. Vous avez déjà créé une classe `dark-background` et vous devez maintenant ajouter cette classe à la section `team`.

Maintenant, vous devez créer deux classes différentes - une pour le texte de la section et une autre pour les noms des membres de l'équipe. La première classe, `section-text`, définira la taille de police à `1.9em` et le texte sera aligné au `center`.

D'autre part, la classe `member-name` définira la taille de police à `1.5em` avec un poids de police de `700`. Ajoutez la première classe au `p` dans le HTML et la deuxième classe à tous les tags `h4`.

Pour éviter que les propriétés écrasent d'autres classes, créez un sélecteur multiple pour définir ces classes spécifiquement à l'intérieur de l'élément d'ID team:

```css
#team .section-text {
}

#team .member-name {
}
```

En outre, occupons-nous des images de cette section. Comme nous pouvons le voir, elles sont très grandes. Utilisons des sélecteurs multiples pour cibler les balises `img` à l'intérieur de `#team` et définissons:

- width à 250px et
- height à 180px.

:+1: Spoiler:

```css
#team img {
  /* styles to be added here */
}
```

<br>

![](https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_dbe16d63517310a82a988f9f13df4867.png)

<br>

### Section 4

_Rien à faire ici... pour l'instant!_

### Footer (Pied de page)

Encore une fois, nous avons un fond sombre et un texte blanc. Ajoutez la classe `dark-background` à la balise `footer` dans le HTML. Créez une classe `footer` et ajoutez-la comme deuxième classe sur la balise `<footer>`. Utilisez cette classe pour centrer tout le texte à l'intérieur de cet élément et pour définir la taille de police à `1.9em`.

:+1: Astuce : Pour ajouter une deuxième classe, vous devez faire ce qui suit:

```html
<!-- ... -->

<footer class="dark-background footer">
  <!-- ... -->
</footer>
```

Maintenant, créez une nouvelle classe - `address`, et assignez-la à la balise HTML `address`. Dans cette classe, définissez:

- font style: `normal`.
- font size: `0.8em`.

Nous y sommes presque. De la même manière que nous avons ciblé tous les liens à l'intérieur de la barre de navigation (en utilisant une approche de sélecteur multiple), ciblons ici tous les liens à l'intérieur du pied de page et leurs styles:

- color: blue (vérifiez la table au début de cette itération.).
- text-decoration: none.

Attribuez cette classe à chaque élément de la liste que vous avez dans le pied de page.

:+1: Astuce : La façon de procéder est la suivante:

```css
.footer a {
  /* styles to be added here */
}
```

Et enfin, la dernière chose pour cette itération est de supprimer les points de la liste qui affiche les liens des médias sociaux. Vous pouvez cibler la balise `ul` à l'intérieur du pied de page et définir la propriété `list-style` sur _none_. Voilà!

<br>

![](https://s3-eu-west-1.amazonaws.com/ih-materials/uploads/upload_791457cbe452066c3123de22f4182eb8.png)

<br><br>

:heart: **Happy coding!**
