## Welcome to Petetionary
Hit New Word below to generate a new word to draw! Don't refresh the page because while I'm crazy, I'm not crazy enough to add cookies.

## Your Word:
<div id="word"></div>
<button onclick="newWord()">New Word</button>

## Used Words
<div id="usedwords"></div>


<script>
// Don't be trying to spy on the inner workings!!!
// But if you're reading this, mash that button till the end.
var words = ["T25lIFBpZWNl", "amlnc2F3IHB1enpsZQ==", "YWdpbGU=", "SmlyYQ==", "YmVuZGluZw==", "QWFuZw==", "S2F0YXJh", "WnVrbw==", "bXkgY2FiYmFnZXM=", "U2FuIEZyYW5jaXNjbw==", "dGVjaCBicm8=", "ZGlzcnVwdA==", "c3RhcnR1cA==", "Z2VudHJpZmljYXRpb24=", "Ym9iYQ==", "TWlzc291cmk=", "U3QuIExvdWlz", "Q2FsaWZvcm5pYQ==", "d2FsbA==", "Q2h5bmE=", "Zm9vZGll", "aW5mbHVlbmNlcg==", "VWJlcg==", "U3F1YXJl", "U2FsZXNmb3JjZSBUb3dlcg==", "aGlwc3Rlcg==", "RG9uYWxkIFRydW1w", "QkFSVA==", "TmFwYQ==", "Q2Fyb2xlIEJhc2tpbg==", "Sm9lIEV4b3RpYw==", "dGhlIFp1Y2M=", "UGF0YWd1Y2Np", "c2hlbHRlci1pbi1wbGFjZQ==", "Wm9vbQ==", "TmFydXRv", "dG9pbGV0IHBhcGVy", "aGFuZCBzYW5pdGl6ZXI=", "U29iZXk=", "Y2hpbGRyZW4ncyBjYXJkIGdhbWU=", "cXVhcnRlci1saWZlIGNyaXNpcw==", "Y29udmVydGVkIGxpdmluZyByb29t"];

var msg = ["VGltZQ==", "ZmxpZXM=", "d2hlbg==", "SQ==", "c3BlbmQ=", "aXQ=", "d2l0aA==", "eW91Lg=="];

var usedWords = [];
var i = 0;
var done = false;
function newWord() {
    var previousWord = document.getElementById("word").innerHTML;
    if (previousWord !== "") {
        if (i == msg.length) {
            return
        }
        usedWords.push(previousWord);
        document.getElementById("usedwords").innerHTML = usedWords.join("<br />");
    }

    if (done) {
        document.getElementById("word").innerHTML = atob(msg[i++]);
        return
    }
    
    var newIndex = Math.floor(Math.random()*words.length);
    var newWord = atob(words[newIndex]);
    words.splice(newIndex, 1);
    if (words.length === 0) {
        done = true;
    }
    document.getElementById("word").innerHTML = newWord;
}
</script>
