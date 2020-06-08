## Welcome to Petetionary
Welcome to Petetionary: Pictionary with my special touch. Hit **New Word** below to generate a new word to draw! You've one minute to craft your materpiece. Make sure your audio's on, an alarm will sound when time's up. I ain't a baker so there are no cookies. Don't refresh the page or you'll lose *everything*.

Pete's Protip: You can also play charades.

<h2 id="timer">Time: 0:0 </h2>

## Your Word:
<div><b id="word"></b></div>
<button onclick="newWord()">New Word</button>

## Used Words
<div id="usedwords"></div>

<audio id="timersound">
  <source src="/petetionary/assets/audio/synthwave-loop_by_furbyguy.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>

<script>
// Don't be trying to spy on the inner workings!!!
// But if you're reading this, mash that button till the end.
var words = ["T25lIFBpZWNl", "amlnc2F3IHB1enpsZQ==", "SmlyYQ==", "YmVuZGluZw==", "QWFuZw==", "S2F0YXJh", "WnVrbw==", "bXkgY2FiYmFnZXM=", "U2FuIEZyYW5jaXNjbw==", "dGVjaCBicm8=", "ZGlzcnVwdA==", "c3RhcnR1cA==", "Z2VudHJpZmljYXRpb24=", "Ym9iYQ==", "TWlzc291cmk=", "U3QuIExvdWlz", "Q2FsaWZvcm5pYQ==", "Q2h5bmE=", "Zm9vZGll", "aW5mbHVlbmNlcg==", "VWJlcg==", "U3F1YXJl", "U2FsZXNmb3JjZSBUb3dlcg==", "aGlwc3Rlcg==", "RG9uYWxkIFRydW1w", "QkFSVA==", "TmFwYQ==", "Q2Fyb2xlIEJhc2tpbg==", "Sm9lIEV4b3RpYw==", "dGhlIFp1Y2M=", "UGF0YWd1Y2Np", "c2hlbHRlci1pbi1wbGFjZQ==", "Wm9vbQ==", "TmFydXRv", "dG9pbGV0IHBhcGVy", "aGFuZCBzYW5pdGl6ZXI=", "U29iZXk=", "Y2hpbGRyZW4ncyBjYXJkIGdhbWU=", "cXVhcnRlci1saWZlIGNyaXNpcw==", "Y29udmVydGVkIGxpdmluZyByb29t"];

var msg = ["VGltZQ==", "ZmxpZXM=", "d2hlbg==", "SQ==", "c3BlbmQ=", "aXQ=", "d2l0aA==", "eW91Lg=="];

var usedWords = [];
var i = 0;
function newWord() {
    setTimer()
    if (i == msg.length) {
        storePreviousWord();
        i++;
    }

    if (i < msg.length) {
        storePreviousWord();
        if (!setNewWord()) {
            setMsg()
        }
    }
}

function setNewWord() {
    if (words.length == 0) {
        return false;
    }

    var newIndex = Math.floor(Math.random()*words.length);
    var newWord = atob(words[newIndex]);
    words.splice(newIndex, 1);
    document.getElementById("word").innerHTML = newWord;
    return true;
}

function storePreviousWord() {
    var previousWord = document.getElementById("word").innerHTML;
    if (previousWord !== "") {
        usedWords.push(previousWord);
        document.getElementById("usedwords").innerHTML = usedWords.join("<br />");
    }
}

function setMsg() {
    if (i < msg.length) {
        document.getElementById("word").innerHTML = atob(msg[i++]);
    }
}

var x;
function setTimer() {
    if (x !== undefined) {
        clearInterval(x);
        pauseAudio();
        loadAudio();
    }
    
    var duration = 60000; // 1.5  minute timer
    // Update the count down every 1 second
    x = setInterval(function() {
        // // Get today's date and time
        // var now = new Date().getTime();
            
        // // Find the distance between now and the count down date
        // var distance = countDownDate - now;
        duration = duration - 1000;
            
        // Time calculations for days, hours, minutes and seconds
        var minutes = Math.floor((duration % (1000 * 60 * 60)) / (1000 * 60));
        var seconds = Math.floor((duration % (1000 * 60)) / 1000);
            
        // Output the result in an element with id="demo"
        document.getElementById("timer").innerHTML = "Time: " +  minutes + ":" + seconds;
            
        // If the count down is over, write some text 
        if (duration < 0) {
            clearInterval(x);
            document.getElementById("timer").innerHTML = "TIME'S UP";
            playAudio();
        }
    }, 1000);
}

var timersound = document.getElementById("timersound"); 

function playAudio() { 
  timersound.play(); 
} 

function pauseAudio() { 
  timersound.pause(); 
} 

function loadAudio() {
    timersound.load();
}

</script>
