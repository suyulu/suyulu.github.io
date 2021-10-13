### 1. jQuery code for a continuing eduction

When I take a continuing education, I realize the audience has to move/click the mouse every 10 minutes. If you do not move/click your mouse, the time will not be counted. In order to solve this issue, I prepare a jQuery snippet below.

setInterval() is a jQuery function to run a function for every a certain time.
setTimeout() is to let the function run after a certain time. 

The below code snippet is to click the pause button and then the resume button 2 seconds later. This step is looped for every 5 minutes.

However, the system will give you some exercises when you watch the video. If it prompts exercise, this code snippet will not help.


```js

function detect_clean_exam(){
   if ($("#examcontent > label").length) // have an exam
   {     
      var ans = $('#examcontent > p >  input[type=button]').parent().html();
      const myArr = ans.split("'");
      var myans = myArr[1];
      var myint = myans.charCodeAt(0) - 65;
      $('#examcontent > label')[myint].click();
      $('#examcontent > p >  input[type=button]').click(); //submit the answer
      
      // $('#examcontent > label').each(function () { 
      //    this.click(); // select an answer
      //    $('#examcontent > p >  input[type=button]').click() //submit the answer
      //    if($('#examcontent > input').length) { // when the answer is wrong
      //        $('#examcontent > input').click() // remove prompt
      //    }
      //    else{
      //        return false; // when answer is corrce, breaks the for-each loop
      //    }
      // })
    };
}

setInterval(function(){
   detect_clean_exam();
   $( ".pv-playpause" ).click();
   setTimeout(
      function() 
      {
         $( ".pv-playpause" ).click();
      }, 2000);
},300000);

```
