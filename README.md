# HW-giphyAssignment
GisTastic assignment is to use the GIPHY API to make a dynamic web page that populates with gifs of our choice. I chose a superhero theme for this assignment and used AJAX calls to the Gify API website and adding those calls to buttons dynamically and also upon a search on the HTML page, we add that as a dynamic button to an existing array of buttons and also make an AJAX call for the newly added button to display results. In addition, we should also dynamically change the images from still to gif's upon click. 

## Table of contents
Technologies Used
Applications Used
Screenshots of homework progress
Code Snippets

## Technologies Used
HTML
Javascript/jQuery
AJAX
APIs
Markdown

## Applications Used
GitHub
ChromeDev tools
Visual Studio Code
Chrome browser

## Screenshots of homework progress

![Code progression Final](https://github.com/krishnaaddala/HW-giphyAssignment/blob/master/assets/images/StartGifTasticPage.png "Starting page of gifTastic")

![Code progression Final](https://github.com/krishnaaddala/HW-giphyAssignment/blob/master/assets/images/responsive-1.png "gifTastic reponsive layout 1")

![Code progression Final](https://github.com/krishnaaddala/HW-giphyAssignment/blob/master/assets/images/responsive-2.png "gifTastic reponsive layout 2")

## Gif walkthrough

#### gif did not work in this section as the file was too large regardles of how small i tried to edit the GIF.

## Code Snippets

```<body onload="addButtons()" background="assets/images/marvelvsDC.jpg">
    <div class="container">
        <h1> Giphy Images</h1>

        <div class="giphy-form">
            <label for="giphy-input"></label>
            <!-- added onFocus to remove the search field automatically
            upon adding the search as a button -->
            <input type="text" id="giphy-input" onfocus="this.value=''">
            <input id="add-giphy" type="submit" value="Add a Superhero">
            <div id="dynamic-btnview"></div>
        </div>
  ```

  ```function giphyDisplay() {
    $("#giphy-btndisplay").empty();
    var superhero = $(this).attr("data-giphy");
    var queryURL = "https://api.giphy.com/v1/gifs/search?api_key=tuHOptJN3WWLtwMil1BWJF8fU18JA1f5&q=" + superhero + "&limit=10&offset=0&rating=G&lang=en";
    //Making an AJAX call
    $.ajax({
        url: queryURL,
        method: "GET"
    }).then(function (response) {
  ```

  ```$("#add-giphy").on("click", function (event) {
    event.preventDefault();
    var superhero = $("#giphy-input").val().trim();
    superheroList.push(superhero);
    addDynamicBtn(superhero);
});
  ```
  ```$(document).on("click", ".super_hero_images", function () {
    img = this;
    var imgSrc = img.getAttribute("src");
    var imgAlt = img.getAttribute("data-alt");
    img.setAttribute("src", imgAlt);
    img.setAttribute("data-alt", imgSrc);
});
  ```
Git commands:

```git status
    git add .
    git commit -m "message"
    git push origin master
    ```