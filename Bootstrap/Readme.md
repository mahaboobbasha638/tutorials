# Bootstrap Essentials
## Important modules
- Container
    - Controls the layout
    - adds 15px padding, no never reaches edges.
    - So full width modules don't put in container
    - Two typs of Containers
        - Fluid container
            - Always adjusts with size of the device
        - Fixed-Width container
            - Specific width size depending on the size of view port
            - 15px padding on each side
            - adjusts to media query breakpoints 
                - width: auto; < 768px width
                - width: 750px; >= 768px width
                - width: 970px; >= 992px width
                - width: 1170px; >= 1200px width

- Rows
    - Allow you to create Horizontal groups 
    - Place within container
    - Should Always include Columns
    - Get rid of container padding
- Columns
    - Allow you to create vertical groups
    - it creates 30px gutters
        - 15px on each side
    - (>12) columns wrap
    - Uses col-SIZE-SPAN
        - SIZE Metrics
            - SIZE represents at which break points it has to devide into the columns
            - Extra Small .col-xs- width: auto; < 768px width
            - Small .col-sm- width: ~62px; >= 768px width
            - medium .col-md- width: ~81px; >= 992px width
            - Large .col-lg- width: ~97px; >= 1200px width
            - you can add as many break points as you want.
        - SPAN Metrics
            - Defines how many columns should display.


## Adding diffente break points
- You can add as many break point as you want like
        
        <div class="col-sm-2 col-md-4 col-lg-6"></div>

## Fixing random alignment issues
- By using clearfix and Resoponse utility class like visible-sm-block, hidden-sm we can Fixed
    random alignment issues when heights are not equal.

## Offsetting columns
- On small screen we can add offset to adjust in the middile by adding column offset
        
        <div class="col-xs-offset-3 col-xs-6 col-md col-md-4 col-lg-6"></div>
- We need to clear by adding offset zero in the next break point without affeting further

        <div class="col-xs-offset-3 col-xs-6 col-sm-offset-0 col-md-4 col-lg-6"></div>

## Nesting columns
- We can add rows inside another row and can play with the columns.

## Customizing column order with push and pull
- You can rearrange the section by using push and pull classes
            
        <div class="col-xs-4 col-sm-push-8"></div>
        <div class="col-xs-4 col-sm-pull-8"></div>

