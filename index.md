<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>



<dl id="quote"></dl>

<div>
  <button id="btn1">Show idiom</button>
</div>



<script>
var btn = $("#btn1");
// handle click and add class
btn.on("click", function(e) {

  $.ajax({
    url: "items.json",
    dataType: "json"
  }).done(function(result) {
    let id = Math.floor(Math.random() * 3);
    let item = result['items'][id]['item'];
    let meaning = result['items'][id]['meaning'];
    let image = result['items'][id]['image'];
    let audio = result['items'][id]['audio'];
    

      let dstring = "Idiom: " + idiom + " Meaning: " + meaning + " Example: " + example;
    
       //dataContainer.text(dstring);
document.querySelector("#quote").innerHTML = "<dt>" + item + "</dt>" + "<dd><img src='" + image + "' /></dd><audio controls><source src='" + audio + "' type=\"audio/mpeg\"></audio></dd><dd><strong>Meaning:</strong> " + meaning + "</dd>" ;
  });

});
</script>
