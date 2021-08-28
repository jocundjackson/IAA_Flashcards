# IAA_Flashcards

## How to use:
* Go to student profiles: https://analytics.ncsu.edu/?page_id=243
* Open your browser's console in developer tools (F12)
* Paste in minified code below and quiz yourself!

```function flashcard_game(){jQuery("#flashcards").remove();var e=[];jQuery.each(jQuery("div.entry-content table tbody tr td:odd"),function(j,k){e.push(jQuery(k).text().split("\n")[0])});var h=[];jQuery.each(jQuery("div.entry-content table tbody tr td:even span img"),function(j,k){h.push(jQuery(k))});var g=[];var b=5;while(g.length<b){var f=Math.floor(Math.random()*e.length);if(!g.includes(f)){g.push(f)}}var a=Math.floor(Math.random()*b);var d="";for(var c=0;c<b;c+=1){d+='<input type="radio" class="answer" id="student'+c+'" name="studentselection" value="';if(c!=a){d+="in"}d+='correct" onclick="check_answer()" /> <label for="student'+c+'">'+e[g[c]]+"</label><br/>"}jQuery('<div id="flashcards" style="background:#ccc; min-width:80%; min-height:30em; padding-left:5em; padding-top: .5em; height:80%; color:black; z-index:9999; position: absolute; left: 10%; top: 50px;"><img src='+h[g[a]][0].currentSrc+' height="250em" width="250em"><form>'+d+'<input type="button" onclick="flashcard_game()" value="Play Again!"></form></div>').appendTo("body")}function check_answer(){jQuery(".answer[value=correct]").next().css({backgroundColor:"#00ff00"})}flashcard_game();```
