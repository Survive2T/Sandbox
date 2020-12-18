# NOTES

- Understand what Sass does for you
  Sass allows you to generate css files using variables, functions, and inheritence.

- Differentiate between CSS and Sass syntax
  Nesting
  .someClass p {
  background-color: black;
  }
  .someClass {
  p {
  background-color: black;
  }
  }

- Install Sass in a website project
  npm init -y
  npm i sass -D
  "name": something-other-than-sass
  "start": "sass index.scss styles.css --watch"
  npm start

- Modularize and re-use CSS
  %style-border{
  background-color: #FFCF00;
  border: 1px solid black;
  padding: 16px;
  }

- Use variables to reuse constants like colors and fonts
  $primary-color: #00916E;
  $secondary-color: #FFCF00;
  $tertiary-color: #FA003F;
  $primary-font-color: #353535;
  $padding-container: 16px;
  $primary-font: Arial, Helvetica, sans-serif;
  %style-border{
  border: 1px solid $primary-color;
  padding: $padding-container;
  }
  %style-text{
  font-family: $primary-font;
  color: $primary-font-color;
  }
  %style-container{
  @extend %style-border;
  @extend %style-text;
  }

- Use mixins to build groups of CSS declarations for reuse
  @mixin CreateContainer($prop-border, $prop-font){
  @extend %style-container;
  border-width: $prop-border;
  font-size: $prop-font;
  }
  @include CreateContainer(5px, large);
