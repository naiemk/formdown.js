# formdown.js
A mark-down inspired language for developing web forms

## Form Controls

### Text box

**Short text box**

```
_ One underline creates one text box
```

**Long text box**


```
__ Two underlines create one bigger text box
```

**Text area**

```
___ Three underlines create a text area
```

### Checkbox and Radio buttons

**Checkbox**

```
X Start a line with X or O for a checkbox
```

**Radio buttons**

```
O [
Radio button 1,
Radio button 2,
Radio button 3
] Start a line with X or O then follow up with a list
```


**Grouped checkbox**

```
O *[
Check box 1,
Check box 2,
Check box 3
] Start a line with X or O then follow up with a list. 
  Add an asteric to allow multiple section.
```

### Dropdown


```
[
Item 1,
Item 2,
Item 3
] Start a line a list. 
  A list represents a dropdown
```

### Multi-select list


```
*[
Item 1,
Item 2,
Item 3
] Start a line a list and asterics. 
  Similar to dropdown with an extra asterics
```

### Custom Controls

```
<Address> The custom control name
```

### Comments

**Comment on controls**

```
_ Email
To add comments to a control simply type text in the
lines below it. For example this is a comment for the 
textbox presented above.
```

**Comment on the form**

```
_ Email
O [Male, Female] Gender
X Agreed with the <a href='tnc.html'>term and conditions</a>
---
Every thing after the --- will be considered form comments.
You can not have any more form controls after three dashes.
```

# Summary

Example:

```javascript
let formdownText = `
This is an example <b>formdown</b> form. This line will end up in form.label

X You can use X or O to define a radio button / checkbox
_ A short text box
__ A longer text box
___ And a textarea
Any comment I add here would be in the comments field of the textarea object
[Apple, Orange, Banana] A dropdown for fruits
*[Apple, Orange, Banana] A multi-select for fruits if there is a * at the begining
O [Male, Fmale] A radio group
X *[Green, Orange, Blue] And a multi-checkbox for my colors. * means multi
  Add comments for any control after the line
<address> Define custom controls
mybox: _ A textbox named mybox (control.name)
  Note that above line defined a name for the control. Other lines don't.
---
You can write form comments here after three dashes. They will show in the
form.comments field.
`

let form = formdown().compile(formdownText);
formdownRender().render(form)
```
