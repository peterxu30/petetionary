## Welcome to Petetionary
Hit New Word below to generate a new word to draw! Don't refresh the page because while I'm crazy, I'm not crazy enough to add cookies.

## Your Word:
<div id="word"></div>
<button onclick="newWord()">New Word</button>

## Used Words
<div id="usedwords"></div>


<script>
var words = ["One Piece", "jigsaw puzzle", "doge", "agile", "Jira", "bending", "Appa", "Aang", "Katara", "Zuko", "Sokka", "my cabbages", "San Francisco", "tech bro", "disrupt", "startup", "gentrification", "burrito", "boba", "Missouri", "St. Louis", "California", "wall", "Chyna", "foodie", "influencer", "Uber", "Square", "Salesforce Tower", "Transamerica Tower", "Coit Tower", "Sutro Tower", "hipster", "Donald Trump", "BART", "Napa", "Carole Baskin", "Joe Exotic", "the Zucc", "Patagucci", "shelter-in-place", "Zoom", "Naruto", "toilet paper", "hand sanitizer"];
var usedWords = [];
function newWord() {
    usedWords.push(document.getElementById("word").innerHTML);
    document.getElementById("usedwords").innerHTML = usedWords.join("<br />");
    var newIndex = Math.floor(Math.random()*words.length);
    var newWord = words[newIndex];
    words.splice(newIndex, 1);
    document.getElementById("word").innerHTML = newWord;
}
</script>
