# HAML

==============================================================================

## So... what is it?

* HAML - HTML abstraction markup language
* haml.info (has tutorial & download link)

* __purpose__: make markup beautiful with DRY, aesthetically pleasing, well-indented, and clear code

* 3 __major focuses__: 
    * cleanliness
    * readability
    * speed

## Using HAML

* __first__ things first! 
    * ` gem install haml `

* can be used __3 different ways__:
    * within the command line
        i.e. ` haml input.haml output.html `
    * as a plugin for Rails
        i.e. ` gem "haml" `
    * as a Ruby module

* HAML can be used to _replace any ERB file_; __any__ file in the app/views folder can be switched, simply by changing the extension of the file.
    e.g. app/views/account/login.html.erb 
         app/views/account/login.html.haml
* note that both ERB and HAML can be mixed throughout the website; it's not an "either/or" type of situation

## Converting into HAML ...

* erb: ` <strong><%= movie.title %></strong> `
* HAML: ` %strong= movie.title `

* __NOTE__: 
    * tags are written by the '%' sign, followed by the tag name, followed by the '=' sign 
        * the '=' sign evaluates whatever follows into Ruby code
    * unlike ERB, HAML automatically detects newlines within the return value and formats the tag accordingly!

## Adding Attributes

* HTML: ` <strong class="heading" id="greeting-message">Welcome to our website!</strong> ` 
* HAML: ` %strong{:class => "heading", :id => "greeting-message"} Welcome to our website! ` 
    * note the absence of the '=' sign; we want the text to be evaluated as a string, not as Ruby code
* __CAN MAKE _EVEN_ SIMPLER__ by choosing to use the shorthand for ids and classes! 
    * ` %strong.heading#greeting-message Hello, World! ` 

* when you use the ` <div> ` tag, you can choose to omit it entirely
    * HTML: ` <div class='greeting'>Hello, World!</div> ` 
    * HAML: ` .greeting Hello, World! `

### References:
* http://haml.info/
* http://haml.info/docs/yardoc/file.REFERENCE.html

