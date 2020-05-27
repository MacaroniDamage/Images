# About
This is a demonstration of useful functionalities that are offered by HTML and CSS to show pictures 
on a web-page.

# Implementing pictures
## As CSS Background
Create a container inside your HTML file where the picture will be placed

~~~html
<section id="headerBackground">
</section>
~~~
Then you can add css code that addresses the id `headerbackground`
This css instructions will add a picture as a background of a dog to the tag with the id `headerBackground`
You can try to write something into the section. That text that was written into this section
will be shown at the front of the picture
~~~
#headerBackground{
    background-image: url("img/dog1.jpg");
}
~~~
You won't see the picture, if you do not add content between the section tags. You can add
an height attribute to your CSS instructions to solve this problem. For example `height: 100vh;`
This will make the picture as high as your monitor is.
~~~css
#headerBackground{
    background-image: url("img/dog1.jpg");
    height: 100vh;
}
~~~

That will look like this. Oh the picture looks a bit big scaled...
To solve that you can use `background-size:cover;`
~~~css
#headerBackground{
     background-image: url("img/dog.jpg");
        height: 100vh;
        background-size: cover;
        background-repeat: no-repeat;
} 
~~~


If you have smaller pictures you should use the attribute `background-repeat: no-repeat;`, so the picture won't be
displayed multiple times.  
```css
#headerBackground{
    background-image: url("img/dog.jpg");
    height: 100vh;
    background-size: cover;
    background-repeat: no-repeat;
}
```


## With HTML tags
A picture should be always implemented inside an container and the image tags should be always the child of this 
container.

```html
<div class="imgContainer">
        <img src="img/dog2.jpg">
</div>
```

If you do not have implemented a css framework that makes everything beautiful, you will have to add some fancy CSS
to make the pictures to behave, because pictures in HTML can be nasty bitches.

```css
img{
    width: 100%;
    height: 100%;
    display: block;
}
```
`width: 100%;` as well as `height: 100%;` makes the picture just as wide as the surrounding container is. 
To specify the width or height of the picture you will have to talk to the container.
`display: block;` says to the img tag that it should behave as block so height and width can be applied.

To define 

### Example: Image gallery
To implement a image gallery into you HTML document you will need css3 grids and three pictures.
The basic structure will look like this. 
```html
<section id="imageGallery">
    <div class="imgContainer thirdWidth">
        <img src="img/cat1.jpg">
    </div>
    <div class="imgContainer thirdWidth">
        <img src="img/dog2.jpg">
    </div>
    <div class="imgContainer thirdWidth">
        <img src="img/cat2.jpg">
    </div>
</section>
``` 
At first comes a container that contains the picture containers.
Then there will be the image containers that contain the images.

The next step is to tell the imageGallery that it should display the image containers as a flexbox well known as grid or flex grids.
 ```css
#imageGallery{
    display: flex;
    flex-wrap: wrap;
    flex-direction: row;
}
```
`display: flex;` Tells the imageGallery to display the pictures as a grid. 

`flex-direction: row;` Tells to display the elements inside imageGallery as a row. Between each other.

`flex-wrap: wrap;`  Tells to begin a new line of elements, if the elements have reached the maximal possible space.

The last step is to tell the images the maximum height as well as their maximum width.
```css
#imageGallery .imgContainer{
    max-height: 50vh;
    max-width: 33.33%;
}
```
`max-height: 50vh;` Tells the imageContainer to be just half as high as the screen

`max-width: 33.33%;` Tells the imageContainer to be just a third as wide as the screen. So three image will be displayed in a row.
# Resources
If you want more profound knowledge about this topic, you should check these links out.

[Complete Flexbox Guide ](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

[Ressource To Display Attributes](https://www.w3schools.com/CSSref/pr_class_display.asp)

[Tutorial For Background Attributes](https://www.w3schools.com/css/css_background.asp)

[CSS Selectors](https://www.w3schools.com/cssref/css_selectors.asp)

[CSS Height And Width Attributes](https://www.w3schools.com/css/css_dimension.asp)

[CSS Lengths](https://www.w3schools.com/css/css_units.asp)
 


