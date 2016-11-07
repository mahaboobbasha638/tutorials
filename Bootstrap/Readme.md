# Bootstrap Essentials
## Bootstrap Grid
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


# Bootstrap CSS classes

## Heading and body style
- It will look ofr Helvetica, Arial after that sans-serif
- You can use classes h1, h2 etc.. instead of tags
    
        <div class="h1"></div>

- You can use small tag as well as class to differentiate secondary text
- Lead class will make text different compared to existing.

## Inline text styles
- "Mark" tag will give background color yellow
- "S", "del" tag for strike through text
- "ins", "u" to show insert text 
- "strong", "b" for bold
- "em", "i" for emphosis tag shows with italic

## Alignment, transformation and abbreviations
### Alignment
- We can use alignment classes like "text-left" for floating text to left
    - text-left -> for float left
    - text-rigt -> for float right
    - text-center -> for center
    - text-justify -> for justify
    - text-nowrap -> for whitespace nowrap (in single line)

### transformation
- We can use transformation classeds to text transformation
    - text-lowercase -> lowercase letters
    - text-uppercase -> for capitalize
    - text-capitalize -> for firstletter capitalize
### Abbreviations    
- abbr tag uses for abbrivation, on hover it will show complete abbrivation.

        <abbr title="Captain" class="initialism">Capt.</abbr>
  
## Blockquotes
- "blockquote" tag gives the proper indentation 
- by footer tag we can add author as will in proper alignment
- blockquote-reverse class will float right and add indentation in the right

        <blockquote class="blockquote-reverse"></div>

## List style
- "list-unstyled" class will disable the list format, but only that particular level. if you want in sublevels as will we need to add for each level.

        <ol class="list-unstyled">
            <li>list1</li>
            <li>list2</li>
            <ul>
                <li>list3</li>
                <li>list4</li>
            </ul>
        </ol>

- "list-inline" class will keep the all list items in one like and removes the bullets.

        <ol class="list-inline">
            <li>list1</li>
            <li>list2</li>
        </ol>

- by adding "dl-horizontal" class to defination element at certain break point it will breaks into two columns.

        <dl class="dl-horizontal">
            <dt>Lorem</dt>
            <dd>Ipsum dolor sit amet, consectetur adipisicing elit. Esse quo ducimus dolorum dolore ipsam unde, facere explicabo quae natus alias deserunt quibusdam voluptatem, officiis itaque rerum magni eius odio mollitia!</dd>
        </dl>

## styling code 
- we can use kbd tag to create keyboard button look, using var tag italisize the text( for equations).
- Pre tag will keep the text as it is and keep into a block with proper border (to display java script code etc).
- by adding pre-scrollable class it will prove scrollable box.

# Other CSS Styles
## buttons
- btn class allows the add the buttons style
- Default btn style calsses 
    - btn, btn-default
- Button content classes 
    - btn-primary
    - btn-success 
    - btn-info
    - btn-warning
    - btn-danger
- Bbutton size classes
    - btn-xs
    - btn-sm
    - btn-md
    - btn-lg
    - btn-block
- Button state class
    - active
- Button disabled class
    - disabled

## Tables
- "table" class will give proper style to table.
- Class List
    - table-striped
    - table-border
    - table-hover
    - table-condensed
- By adding the contextual classes you can give colors
    - active
    - success
    - info
    - warning
    - danger

- By keeping the table inside container class "table-contanier" will make the table responsive.

## Images
- By adding the "img-responsive" class image gets the resonsive style.
- By adding "center-block" will make the image in the center of the column.
- By adding "img-rounded" it added rounded edges.
- By adding "img-circle" it will give circle images.
- By adding "img-thumbnail" it will give circle images.

## Helper classes
- text-muted for light color
- Can add contextual colors
    - text-primary
    - text-success ..etc
- Can add background colors using contentual colors
    - bg-primary
    - bg-success ..etc
- Layout class (ex on image can add)
    - pull-left
    - pull-right
    - center-block
- Can add show/hidden class to show and hide elements
- Class "Invisible" will hide the image but it will take the corresponding space.

## Responsive Utilities
- We can controls the visibility of certain elements using utility classes at that break point
    - VISIBILITY-SIZE(-DISPLAY)
        - Visibility: visible or hidden
        - Size: xs, sm, md, lg, print
        - Display: block, inline, inline-block, print
    - example
        - visible-xs-block shows up element in xs breakpoint as block element
        - hidden-xs hide the element in xs breakpoint
        - Print element will appear when printing the element
            - visible-print-block
# Styling Forms
## Basic Forms
- "form-control" class will style the inputbox to width and proper padding
- "form-group" class will create little bit of seperation between element 

## Radio and Check boxes
- Classes "radio", "checkbox" will give the proper alignemnts
- Classes "radio-inline", "checkbox-inline" will display all the radio and checkbox elements in a line
- disabled propery will disable the selection of the elements
## Inline Forms
- "form-inline" class dispaly form inline style but only in min width of 768px.
## Horizontal Forms
- Good for mobile user 
- On desktop we can align in the center label and textbox next to eachother
- On mobile label and textbox one after the Other
- "form-horzontal" will solve that purpose
## Validation Styles
- We can show the validation state to the user
    - has-warning

            <div class="form-group has-warning">
                <label for="inputName">Name</label>
                <input class="form-control" type="text"
                    id="inputName" placeholder="Your Name">
            </div>

    - has-error

            <div class="form-group has-error">
                <label for="inputName">Name</label>
                <input class="form-control" type="text"
                    id="inputName" placeholder="Your Name">
            </div>

    - has-success

            <div class="form-group has-success">
                <label for="inputName">Name</label>
                <input class="form-control" type="text"
                    id="inputName" placeholder="Your Name">
            </div>

- By adding the control-lable class will affect the same color style to corresponding label.

            <div class="form-group has-success">
                <label class="control-label" for="inputName">Name</label>
                <input class="form-control" type="text"
                    id="inputName" placeholder="Your Name">
            </div>

- We can show the icons as well along with this validation 
- Bootstrap uses the glyphicons

            <div class="form-group has-success has-feedback">
                <label class="control-label" for="inputName">Name</label>
                <input class="form-control" type="text"
                    id="inputName" placeholder="Your Name">
                <span class="glyphicon glyphicon-ok form-control-feedback"></span>
            </div>

## Input groups
- Allow to combine input field together with other elements
- Like label and input filed combine to disaple each other combinedly
    - Example 
           
            <div class="form-group">
                <label for="inputName">Name</label>
                <input class="form-control" type="text"
                    id="inputName" placeholder="Your Name">
            </div>

    - Combining with addon

            <div class="form-group">
                <div class="input-group">
                    <span class="input-group-addon">$</span>
                    <input class="form-control" type="text"
                    id="inputName" placeholder="Your Name">
                </div>
            </div>

    - Combining with button

            <div class="form-group">
                <div class="input-group">
                    <input class="form-control" type="text"
                    id="inputName" placeholder="Enter search term">
                    <span class="input-group-btn">
                        <button class="btn btn-primary" type="button">Search</button>
                    </span>
                </div>
            </div>

## Fieldset
- Fieldset forms the groups
- Can do group operations like complete fieldset elements can disable by addidng disable attribute.

            <fieldset disable>
                <input type="text">
                <input type="button">
                <input type="password">
            </fieldset>

- No need to add for each input box we can add only to fieldset

## Icons
- we can add icons from glyphicons
    
        <span class="glyphicon glyphicon-phone"></span>
        <button type="button"><span class="glyphicon glyphicon-print"></span> Print</button>

# Navigation Components
