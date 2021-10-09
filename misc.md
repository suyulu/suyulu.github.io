When I take the CPA Continuing Education, I realize the audience has to move/click the mouse every 10 minutes. If you do not move/click your mouse, the time will not be counted. In order to solve this issue, I prepare a jquery snippet below.

setInterval() is JQuery function to run a function for every certain time.
setTimeout() is to let the function run after a certain time. 

The below code snippet is to click the pause button and the resume button 2 seconds later. This step is looped for every 5 minutes.

'''

// Javascript code with syntax highlighting.

setInterval(function(){
   $( ".pv-playpause" ).click();
setTimeout(
  function() 
  {
    $( ".pv-playpause" ).click();
  }, 2000);

},300000);

'''
