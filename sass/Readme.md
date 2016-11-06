# Sass Essentials
## Variables
-       $main_color: #9E2932;
        .navbar { 
            background: $main_color; 
        } 
        h2,h3{
            background: darken($main_color, 20);
        }
-
        $main_color: #9E2932;
        
        $main-background-color: $main_color;
        .navbar { 
            background: $main-background-color; 
        } 
        h2,h3{
            background: darken($main-background-color, 20);
        }

-       adding font-family
        
        @import url('https://fonts.googleapis.com/css?family=Roboto+Slab');
        $main-font-family: 'Roboto Slab', serif;
        $main_color: #9E2932;
        
        $main-background-color: $main_color;
        .navbar { 
            background: $main-background-color; 
            color: $main-font-family;
        } 
        

## Nesting

    .pixgrid{ 
      ul{ 
        margin: 0; 
        li {
            float: left;
        }
      }
  }

## Partials
    @import "variables" 
    @import "mixins" 

    @import "modules/intro" 

## mixins
    @mixin backImage($image, $height: 100vh, $bgPos: center center ) {
        background: linear-gradient( to bottom, rgba(0,0,0,0), rgba(0,0,0,.6)), url($image);
        background-repeat: no-repeat;
        background-position: $bgPos;
        background-size: cover;
        height: $height;
    }

    .jumbotron {
        @include backImage(
            '../images/water.jpg', 600px);
    }

## Extend

-       .btn{}
        .btn-reverse{ 
            @extend .btn; 
            background: red;
        }

-       %btn {
            display: inline-block;
            padding: 6px 12px;
            text-align: center;
            white-space: nowrap;
            vertical-align: middle;
            cursor: pointer;
            border: none;
            border-radius: 4px;
            font-family: $font-highlight;
            user-select: none;
            color: $color-btn-text;
        }

        .btn-default {
            @extend %btn;
            background: $color-btn-default;
        }

        % exclude creating btn class

## Parent selector

-       .item {
                padding-bottom: 10px;
                padding-top: 10px;
                padding-left: 10px;
                border-top: 1px dotted $color-item-border;
                &:hover {
                    background: $yellow;
                }
                &:last-of-type {
                    border-bottom: 1px dotted $color-item-border;
                }
            }

-       .item {
                padding-bottom: 10px;
                padding-top: 10px;
                padding-left: 10px;
                border-top: 1px dotted $color-item-border;
                &:hover {
                    background: $yellow;
                }
                &:last-of-type {
                    border-bottom: 1px dotted $color-item-border;
                }
                #typography & {
                    color: $red;
                }
            }
        Whenever the item class found in typography then it will change the color.

-      Instead of adding clear to html whereever we want, we can simplay add to sass class wherever that class comes it will add the clear style. 
        @mixin clearfix {
            &:before,
            &:after {
                content: '';
                display: table;
            }
            &:after {
                clear: both;
            }
        }
        .item {
            padding-bottom: 10px;
            padding-top: 10px;
            padding-left: 10px;
            border-top: 1px dotted $color-item-border;
            &:hover {
                background: $yellow;
            }
            &:last-of-type {
                border-bottom: 1px dotted $color-item-border;
            }
            @include clearfix;
        }

## Math opertions

-     @mixin imagegrid($qty, $margin) {
            width: ((100% - (($qty - 1) * $margin))/$qty);
            &:nth-child(n) {
                margin-right: $margin;
                margin-bottom: $margin;
            }
            &:nth-child(#{$qty}n) {
                margin-right: 0;
                margin-bottom: 0;
            }
        }

        .grid {
            @include clearfix;
            .item {
                float: left;
                @include imagegrid(3, 2%);
            }
        }

        so it become the grid of 3 columns 

## Content

        @mixin break($length){
            @media (min-width: $length){
                @content;
            }
        } 

        .branding{
            float:left;
            display: none;
            @include break(1000px){
                display: block;
            }
        }

        So branding show up in case of min-width 1000px

## If conditions

-     @mixin break($length...){
            @if length($arg) == 1 {
                @media (min-width: nth($length, 1)) {
                    @content;
                }
            }
            
            @if length($arg) == 2 {
                @media (min-width: nth($length, 1)) 
                    and (max-width: nth($length, 2)) {
                    @content;
                }
            }

        } 
 
 -       @mixin break($length...){
            @if length($arg) == 1 {
                @media (min-width: nth($length, 1)) {
                    @content;
                }
            } @else {
                @media (min-width: nth($length, 1)) 
                    and (max-width: nth($length, 2)) {
                    @content;
                }
            }
        }

        footer {
            @include break(0, 500px){
                display: none;
            }
        }

## Loops

        $color-headline: $blue, $purple, $green, $red, $orange, $yellow;

        @for $item from 1 through length($color-headline){
            h#{$item}{
                color: nth($color-headline, $item);
            }   
        }

        We can use loop to give diffent color for different headline tag.
        it will create css as h1{color: $blue;}, h2{color: $purple} etc..

        [ReadMore]('http://sass-lang.com/documentation/file.SASS_REFERENCE.html#each-directive')

## Each

        $color-btn-name: 'default', 'hot', 'cool';
        $color-btn-values: $color-main, $red, $blue;

        @each $name in $color-btn-name{
            $i: index($color-btn-name, $name);
            .btn-#{$name}{
                background-color: nth($color-btn-values, $i);
            }
        }

        It will generate like: 

        .btn-default{},
        .btn-hot{}.
        .btn-cool{}

## Associate array

        $color-btns: (
            default: $color-main,
            hot: $red,
            cool: $blue
        );

        @each $key, $value in $color-btns{
            .btn-#{$key}{
                background-color: $value;
            }
        }


## Sass functions links 
- [Documentation](http://sass-lang.com/documentation/Sass.html)
- [functions](http://sass-lang.com/documentation/Sass/Script/Functions.html)