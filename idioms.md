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
    url: "https://martinbarge.github.io/sml5202-sts/datasets/idioms.json",
    dataType: "json"
  }).done(function(result) {
    let id = Math.floor(Math.random() * 5);
    let idiom = result['idioms'][id]['idiom'];
    let meaning = result['idioms'][id]['meaning'];
    let example = result['idioms'][id]['example'];

    let dstring = "Idiom: " + idiom + " Meaning: " + meaning + " Example: " + example;
    //dataContainer.text(dstring);
    
    document.querySelector("#quote").innerHTML = "<dt>" + idiom + "</dt>" + "<dd><strong>Example:</strong> " + example + "</dd><dd><strong>Meaning:</strong> " + meaning + "</dd>" ;
  });

});
</script>
