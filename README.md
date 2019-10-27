# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) SOFTWARE ENGINEERING IMMERSIVE

# Flexbox Basics and Css Pseudo Classes Practice

### Objectives

Students will be able to:

- Build Professional Layouts Using Flexbox
- Implement layouts based on design specs
- Make webpages responsive
- Use css pseudo classes to target specific elements

## Getting Started

1. Fork
2. Clone

### Combining Design With Flexbox

It's time to flex our new Flexbox layout skills! Haha get it? Now that you've been given an introduction into the world of flexbox, it's time to actually put that knowledge to use.

<img src='https://media.giphy.com/media/sSsKWDd1hcOc0/giphy.gif' height='300px'/>

<br>
<br>

You have been provided with starter html code containing predefined classes. Images have been provided for you, but feel free to use any images you would like. The `styles.css` contains some boiler plate for you. **Do not** modify what has been provided.

## Classnames

Open the provided `index.html` file and take note of the classnames used.

You'll notice that there are several classnames already added to the html code:

| Classes   | Description                                                                                                                                             |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| container | Main container styling, handles our overall page width and background color.                                                                            |
| hero      | Handles our hero section, commonly used in modern layouts to attract initial attention and to display a company's catch phrase or brand statement.      |
| content   | Keeps our informative content in it's own box to have better control of positioning.                                                                    |
| top       | Divides content based on position on the page, in this case all content in the upper section of our page is kept here.                                  |
| columns   | As the name suggest, creates a wrapping container for any items we want to display in the column position. Typically you will see either column or row. |
| col       | Allows us to style every item with .col the same, useful for things such as color, shadows or sizing.                                                   |
| col-sm    | Let's us specify which columns should be small and apply styles to size appropriately.                                                                  |
| col-lg    | Works the same way as .col-sm, but in this case we are specifying which columns should be a larger size.                                                |
| top       | Keeps our content separated in the top section of the `.content` `<div>` and allows us to apply unique layouts to this content.                         |
| bottom    | Keeps our content separated in the bottom section of the `.content` `<div>` and allows us to apply unique layouts to this content.                      |

The above classes are not set in stone, they can be named to suit your needs, but this is common practice in the world of front end development!

## Pseudo Classes

Smashing Magazine:

> Without getting overcomplicated with the W3C’s technical definition, a pseudo-class is basically a phantom state or specific characteristic of an element that can be targeted with CSS. A few common pseudo-classes are :link, :visited, :hover, :active, :first-child and :nth-child.

Pseudo classes can be our best friends as developers. They allow us to specifically target elements without having to clutter our code with more `classes` and `ids`. It makes our css much more readable by our fellow peers and if used correctly can help us create some amazing layouts with eye catching effects!

We'll use `:hover` as an example for the time being:

`:hover` is a very common pseudo class that gives us the ability to add some visual flair to our elements.

<img src='https://sei-nyc-owls.s3.amazonaws.com/flex-box-basics-practice/hover.gif' height='400px'/>

<br>
<br>

Remember it's all about the small details!

There are many pseudo classes avaible to us. During this lab we'll be using `:nth-child`, `:first-of-type`, and `:last-of-type`.
These pseudo classes will allow us to recreate our designs exactly!

## Design Specs

As a developer, often times you will be given design specs to follow. We've provided a design that needs to be implemented. A color pallete has also been provided.

**[Click Here to view Specs](https://xd.adobe.com/spec/ead7331e-f575-4881-6399-52d30ef999c1-9ce6/)**

You will be completing the **Desktop**, **Tablet** and **Mobile** design.

## Final Products

#### Desktop

<img src='https://sei-nyc-owls.s3.amazonaws.com/flex-box-basics-practice/desktop-solution.png'/>

#### Tablet

<img src='https://sei-nyc-owls.s3.amazonaws.com/flex-box-basics-practice/tablet-solution.png' height='800px' width='40%'/>

#### Mobile

<img src='https://sei-nyc-owls.s3.amazonaws.com/flex-box-basics-practice/mobile-solution.png' height='800px' width='20%'/>

## Instructions

**Reminder: Do Not modify any of the provided code!**

Let's start by opening our `index.html` file in our browser by running `open index.html` in your terminal.
Any time you make changes to your `styles.css` or `index.html`you have to refresh your browser page.
<kbd>⌘</kbd> + <kbd>R</kbd> is a useful shortcut for us to remember!

Once you have your web page running, we can start writing some css!!

### Part 1

Let's start working on our general layout. In your `styles.css`, find the `.columns` selector. You should only see:

```css
.columns {
	width: 100%;
}
```

Go ahead and give `.columns` a display property of `display:flex`. We want our content to have some space between each other. Now your first instinct might be to just add some `margin`, but flexbox has our backs! We can use a property called `justify-content:space-between`.

Our `.columns` selector should now look like this:

```css
.columns {
	width: 100%;
	display: flex;
	justify-content: space-between;
}
```

Now let's style the individual boxes.

Start by finding the css selector `.top .columns .col-sm`

Let's give it a style of `flex: 1`.

Your `.top .columns .col-sm` selector should now look like this:

```css
.top .columns .col-sm {
	flex: 1;
}
```

Find the css selector `.top .columns .col-lg`.
Give it a style of `flex:2`.

Your selector should now look like this:

```css
.top .columns .col-lg {
	flex: 2;
	background-color: #4f5c75;
}
```

Let's take a look at our page now and see the changes.

Wait, hold on what's going on here... Our content doesn't have any space between them...

We've run into one of those gotcha moments with flexbox.
Because `justify-content: space-between` requires available space around the `.col` in order to create space between them.
Our `.col-lg` and `.col-sm` were given flex properties that make them take up that available space. One way we can solve this problem is by setting `min-height` and `max-height` for our flex items.

Let's find our `.top .columns .col-sm` and give it a style of `max-width: 300px`. This will allow our `.col-sm` boxes to only ever have a maximum width of `300px`.

Let's do the same for our `.top .columns .col-lg` and give it a style of `max-width: 480px`.

Now your `.top .columns .col-sm` should look like this:

```css
.top .columns .col-sm {
	flex: 1;
	max-width: 300px;
}
```

And your `.top .columns .col-lg` should look like this:

```css
.top .columns .col-lg {
	flex: 2;
	background-color: #4f5c75;
	color: #f8f8f8;
	max-width: 480px;
}
```

Great, it looks like our flex items are behaving exactly as we wanted them to.

### Part 2

Let's actually make sure that these flex items won't cause issues on smaller screens.

To accomplish this we can use a built in tool from css called **Media Queries**.

From Techopedia:

> A media query is an HTML/CSS functionality that allows the content of a Web page to adapt to the type of media that the page is being rendered in, such as a computer screen or that of a phone or tablet.

For more information about media queries:

**[Media Queries](https://www.w3schools.com/cssref/css3_pr_mediaquery.asp)**

To prevent any future issues with devices smaller than standard computer screens, we are going to use a media query to handle every screen width until a width of `1024px`.

To use this let's write a media query rule like this:

```css
@media (min-width: 1024px) {
}
```

The above rule will handle all screen sizes until the breakpoint of `1024px` is reached.

Let's add in our styles:

```css
@media (min-width: 1024px) {
	.top .columns .col-sm {
		max-width: 200px;
		max-height: 300px;
		margin-bottom: 1em;
	}
	.top .columns .col-lg {
		max-width: 480px;
		max-height: 300px;
	}
}
```

Great now we have screens covered until our minimum width is reached!

### Part 3

Now we are going to start targeting specific elements for styling.
We can do this a number of ways. A common practice is to just give an element an id attribute like this:

```html
<div id="element"></div>
```

or by adding adding additional classnames like so:

```html
<div classname=".col .col-sm dark"></div>
```

The problem with these approaches are that they end up cluttering up our css file with selectors that we might end up only using once which makes readability a little more difficult for someone who didn't write the code.

Instead we can use Psuedoclasses.

Example:

```css
.columns .col:first-of-type {
}
```

Using the `:first-of-type` allows us to target the first element with that classname. It gives us much finer control without adding more classnames than we need!

Let's see that in action. Locate the `.top .columns .col-sm:first-of-type` selector and give it the following styles:

```css
.top .columns .col-sm:first-of-type {
	background-color: #4f5c75;
	color: #f8f8f8;
}
```

Take a look at your browser and now the first box should be a dark gray!

Another common Pseudo class is `:nth-child()`. We won't be using this one today, but it's handy to remember! Using `:nth-child` allows us to select elements based on if they are in an odd position or an even position. Think of it as selecting an element in an array based on whether the index of the element is even or odd.

Example:

```css
.top .columns .col-sm:nth-child(odd) {
}
```

The above let's us target each element in an odd position.

```css
.top .columns .col-sm:nth-child(even) {
}
```

The above allows us to target each element in an even position.

---

Pseudo Classes are pretty amazing, they even allow you to input formulas!

From **[Css Tricks](https://css-tricks.com/useful-nth-child-recipies/)**

Example :

```css
li:nth-child(5) {
	color: green;
}
```

Gives us the result:
![](https://css-tricks.com/wp-content/uploads/2011/06/5.png)

As you can see, the above selector allowed us to select the 5th element in the list!

Psuedo classes are powerful once you know how to use them properly!

## Independent Practice

We've styled the top portion of our page for desktop devices, now it's your turn to style the lower portion of the screen and to make the page responsive!

For tablet devices use the breakpoint `(max-width:1024px)` and for mobile devices use `(max-width:500px)`.

Now start flexin!

## Bonus

- Implement the Bonus mockup. **[Specs](https://xd.adobe.com/spec/ead7331e-f575-4881-6399-52d30ef999c1-9ce6/screen/ad7a185e-0837-4c04-aa37-bbea7386cff5/Bonus)**
- Add `:hover` effects to the buttons, they should behave like so:

  <img src='https://sei-nyc-owls.s3.amazonaws.com/flex-box-basics-practice/hover-effect.gif' width='400px'/>

- Add `:active` effects to button so that when clicked it gives the effect of being pushed in like so:

  <img src='https://sei-nyc-owls.s3.amazonaws.com/flex-box-basics-practice/click-effect.gif' width='400px'/>

### Resources

- [Lorem Ipsum Generator](https://loremipsum.io/generator)
- [Media Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries)
- [Css Pseudo Classes](https://www.w3schools.com/css/css_pseudo_classes.asp)
- [Css Tricks](https://css-tricks.com/)
