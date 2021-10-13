### 1. jQuery code for the CPA continuing eduction

When I take the CPA Continuing Education, I realize the audience has to move/click the mouse every 10 minutes. If you do not move/click your mouse, the time will not be counted. In order to solve this issue, I prepare a jQuery snippet below.

setInterval() is a jQuery function to run a function for every a certain time.
setTimeout() is to let the function run after a certain time. 

The below code snippet is to click the pause button and then the resume button 2 seconds later. This step is looped for every 5 minutes.

However, the system will give you some exercises when you watch the video. If it prompts exercise, this code snippet will not help.


```js

setInterval(function(){
   $( ".pv-playpause" ).click();
setTimeout(
  function() 
  {
    $( ".pv-playpause" ).click();
  }, 2000);

},300000);

```



if ($("#examcontent > label").length){
    $('#examcontent > input').each(function () { 
    this.click(); // select item
    
    if(value === "foo") {
        return false; // breaks
    }
    
    })
    };

