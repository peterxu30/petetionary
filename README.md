## Welcome to Petetionary
Hit New Word below to generate a new word to draw! Don't refresh the page because while I'm crazy, I'm not crazy enough to add cookies.

## Timer
<h3 id="timer">0m 0s</h3>

## Your Word:
<div id="word"></div>
<button onclick="newWord()">New Word</button>

## Used Words
<div id="usedwords"></div>


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
    }
    
    var d = new Date();
    var countDownDate = d.getTime() + (2 * 60 * 1000); // 2  minute timer
    // Update the count down every 1 second
    x = setInterval(function() {
        // Get today's date and time
        var now = new Date().getTime();
            
        // Find the distance between now and the count down date
        var distance = countDownDate - now;
            
        // Time calculations for days, hours, minutes and seconds
        var minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
        var seconds = Math.floor((distance % (1000 * 60)) / 1000);
            
        // Output the result in an element with id="demo"
        document.getElementById("timer").innerHTML = minutes + "m " + seconds + "s ";
            
        // If the count down is over, write some text 
        if (distance < 0) {
            clearInterval(x);
            document.getElementById("timer").innerHTML = "TIME'S UP";
        }
    }, 1000);
}


</script>
