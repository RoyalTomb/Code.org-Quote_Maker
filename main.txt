var font;
var color;
var quote;
var size;

//Color Drop 
onEvent("colorInput", "click", function( ) {
  color = getText("colorInput");
  setProperty("colorOutput", "background-color", color);
  setProperty("quoteOutput", "background-color", color);
  checkFunction();
});
//Font Family Drop
onEvent("fontFamilyInput", "change", function( ) {
  font = getText("fontFamilyInput");
  setProperty("quoteOutput", "font-family", font);
  checkFunction();
});
onEvent("quoteInput", "keyup", function( ) {
  quote = getText("quoteInput");
  setText("quoteOutput", quote);
});

onEvent("fontSizeInput", "change", function( ) {
  size = getNumber("fontSizeInput");
  setProperty("quoteOutput", "font-size", size);
  checkFunction();
});

function checkFunction() {
  if (color == "lavender" && font == "Lucida Sans") {
    setText("feedbackOutput", "Great combo!");
  } else if (color == "lightgreen" && size == 25) {
    setText("feedbackOutput", "Looking fresh!");
  } else {
    setText("feedbackOutput", "Nice design!");
  }
}
