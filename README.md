# formdown.js
A mark-down inspired language for developing web forms

Example:

```
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
