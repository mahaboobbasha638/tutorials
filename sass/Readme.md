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

# Extend

    .btn{}
    .btn-reverse{ 
        @extend .btn; 
        background: red;
    }