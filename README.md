## Welcome to Petetionary
Hit New Word below to generate a new word to draw! Don't refresh the page because while I'm crazy, I'm not crazy enough to add cookies.

## Your Word:
<div id="word"></div>
<button onclick="newWord()">New Word</button>

## Used Words
<div id="usedwords"></div>


<script>
// Don't be trying to spy on the inner workings!!!
var words = ["T25lIFBpZWNl", "amlnc2F3IHB1enpsZQ==", "ZG9nZQ==", "YWdpbGU=", "SmlyYQ==", "YmVuZGluZw==", "QXBwYQ==", "QWFuZw==", "S2F0YXJh", "WnVrbw==", "U29ra2E=", "bXkgY2FiYmFnZXM=", "U2FuIEZyYW5jaXNjbw==", "dGVjaCBicm8=", "ZGlzcnVwdA==", "c3RhcnR1cA==", "Z2VudHJpZmljYXRpb24=", "YnVycml0bw==", "Ym9iYQ==", "TWlzc291cmk=", "U3QuIExvdWlz", "Q2FsaWZvcm5pYQ==", "d2FsbA==", "Q2h5bmE=", "Zm9vZGll", "aW5mbHVlbmNlcg==", "VWJlcg==", "U3F1YXJl", "U2FsZXNmb3JjZSBUb3dlcg==", "VHJhbnNhbWVyaWNhIFRvd2Vy", "Q29pdCBUb3dlcg==", "U3V0cm8gVG93ZXI=", "aGlwc3Rlcg==", "RG9uYWxkIFRydW1w", "QkFSVA==", "TmFwYQ==", "Q2Fyb2xlIEJhc2tpbg==", "Sm9lIEV4b3RpYw==", "dGhlIFp1Y2M=", "UGF0YWd1Y2Np", "c2hlbHRlci1pbi1wbGFjZQ==", "Wm9vbQ==", "TmFydXRv", "dG9pbGV0IHBhcGVy","aGFuZCBzYW5pdGl6ZXI="];

var usedWords = [];
function newWord() {
    var previousWord = document.getElementById("word").innerHTML;
    if previousWord !== "" {
        usedWords.push(previousWord);
        document.getElementById("usedwords").innerHTML = usedWords.join("<br />");
    }
    
    var newIndex = Math.floor(Math.random()*words.length);
    var newWord = atob(words[newIndex]);
    words.splice(newIndex, 1);
    document.getElementById("word").innerHTML = newWord;
}

function bin2String(array) {
  return String.fromCharCode.apply(String, array);
}
</script>
