---
layout: default
title: Sprites Construction
---

Drag the items to the right in the correct hierarchy of boroughs, neighborhoods, and schools. HINT: start with <code>nyc</code>.

<div id="sortableTrash" class="sortable-code"></div>
<div id="sortable" class="sortable-code"></div>
<div style="clear:both;"></div>
<p>
    <input id="feedbackLink" value="Get Feedback" type="button" />
    <input id="newInstanceLink" value="Reset Problem" type="button" />
</p>
<script type="text/javascript">
(function(){
  var initial = 'nyc\n' +
    '  brooklyn\n' +
    '    bay-ridge\n' +
    '      fort-hamilton\n' +
    '      hstat\n' +
    '    sunset-park\n' +
    '  manhattan\n' +
    '  queens\n' +
    '  staten-island\n' +
    '  the-bronx\n'
  var parsonsPuzzle = new ParsonsWidget({
    "sortableId": "sortable",
    "max_wrong_lines": 10,
    "grader": ParsonsWidget._graders.LineBasedGrader,
    "exec_limit": 2500,
    "can_indent": true,
    "x_indent": 50,
    "lang": "en",
    "show_feedback": true,
    "trashId": "sortableTrash"
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