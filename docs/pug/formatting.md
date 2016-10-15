#Formatting

Pug is a very strict enforcer of properly formatted syntax. There is however one forgiving aspect that will be addressed to help ensure consistency during production.

##Multiple Attributes

If your element has one attribute, make sure it's on the same line as the element that is being declared. Notice that attributes are declared with double quotes, much like how standard html is declared.

```pug
button.harmonica-header(role="tab")
```

If your element has multiple attributes, make sure they are entered on a new line, declared with double quotes, and separated without commas.

```pug
img.lantern-light.full-width(
  src="http://i.imgur.com/SOABm96.jpg"
  title="Petrified Forest National Park, Arizona"
)
```