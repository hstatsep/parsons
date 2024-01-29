---
layout: default
title: Sprites Construction
---

Construct a program that creates 2 sprites and sets their properties.

<div id="sortableTrash" class="sortable-code"></div>
<div id="sortable" class="sortable-code"></div>
<div style="clear:both;"></div>
<p>
    <input id="feedbackLink" value="Get Feedback" type="button" />
    <input id="newInstanceLink" value="Reset Problem" type="button" />
</p>
<script type="text/javascript">
(function(){
  var initial = "var palette = createSprite();\n" +
    "palette.setAnimation(&quot;paint palette&quot;);\n" +
    "var brush = createSprite();\n" +
    "brush.setAnimation(&quot;paint brush&quot;);\n" +
    "palette.x = 100;\n" +
    "palette.y = 300;\n" +
    "brush.x = 300;\n" +
    "brush.y = 100;\n" +
    "drawSprites();";
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LanguageTranslationGrader,
    "exec_limit": 2500,
    "can_indent": false,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true,
    "executable_code": "palette = Sprite();\npalette.setAnimation(\"paint palette\");\nbrush = Sprite();\nbrush.setAnimation(\"paint brush\");\npalette.x = 100;\npalette.y = 300;\nbrush.x = 300;\nbrush.y = 100;\ndrawSprites();",
    "programmingLang": "pseudo",
    "vartests": [
        {
            "message": "",
            "initcode": "class Sprite:\n  def __init__(self):\n    pass\n    \n  def setAnimation(self,anim):\n    self.anim = anim\n\ndef drawSprites():\n  palette.x\n  palette.y\n  palette.anim\n  brush.x\n  brush.y\n  brush.anim",
            "code": "",
            "variables": {}
        }
    ]
  });
  parsonsPuzzle.init(initial);
  parsonsPuzzle.shuffleLines();
  $("#newInstanceLink").click(function(event){
      event.preventDefault();
      parsonsPuzzle.shuffleLines();
  });
  $("#feedbackLink").click(function(event){
      event.preventDefault();
      parsonsPuzzle.getFeedback();
  });
})();
</script>