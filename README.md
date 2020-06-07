## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/peterxu30/petetionary/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/peterxu30/petetionary/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

<div> Your Word: </div>
<div id="word"></div>
<button onclick="newWord()">New Word</button>

<div> Used Words </div>
<div id="usedwords"></div>


<script>
var words = ["One Piece", "jigsaw puzzle", "doge", "agile", "Jira", "bending", "Appa", "Aang", "Katara", "Zuko", "Sokka", "my cabbages", "San Francisco", "tech bro", "disrupt", "startup", "gentrification", "burrito", "boba", "Missouri", "St. Louis", "California", "wall", "Chyna", "foodie", "influencer", "Uber", "Square", "Salesforce Tower", "Transamerica Tower", "Coit Tower", "Sutro Tower", "hipster", "Donald Trump", "BART", "Napa", "Carole Baskin", "Joe Exotic", "the Zucc", "Patagucci", "shelter-in-place", "Zoom", "Naruto", "toilet paper", "hand sanitizer"];
var usedWords = [];
function newWord() {
    usedWords.push(document.getElementById("word").textContext);
    document.getElementById("usedwords").innerHTML = usedWords.join("<br>");
    var newIndex = Math.floor(Math.random()*words.length);
    var newWord = words[newIndex];
    words.splice(newIndex, 1);
    document.getElementById("word").innerHTML = newWord;
}
</script>
