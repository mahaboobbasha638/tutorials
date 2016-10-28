# Sass Essentials
## Variables
- $main_color: #9E2932;<br />
  .navbar { <br />
     background: $main_color; <br />
  } <br />
  h2,h3{<br />
      background: darken($main_color, 20);<br />
  }<br />

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
        @extend .btn; <br />
        background: red;
    }