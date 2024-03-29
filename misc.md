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


### 2. Replace Chinese characters

Chinese characters can be found in the Unicode ranged from 4e00 to 9fff.

```py

import re

def CNCharactersReplace(s):
   r = re.compile(r'[\u4e00-\u9fff]+')
   r.sub(s, " ") # replace Chinese Characters with space
   return s

```

Ref: Mastering Large Datasets With Python, Manning, Page 52.


### 3. Conda registration and virtual environment in batch command file

There is a fast manner to register conda's path to Windows system. Conda includes a well-prepared python code to register Conda.
The file is `C:\Users\\[username]\anaconda3\Tools\scripts\win_add2path.py`



When we activate python virtual environment in Windows Batch file, it is quite easy to make mistakes. If you invoke 
`conda activate [virtual environment]`,
the batch file will terminate immediately. To continue the batch file, we can use instead
`call activate [virtualenv name]`.



The activate function of conda is stored in the file `C:\Users\\[username]\anaconda3\condabin\conda.bat`. 
When you input 
`conda activate [virtualenv name]`,
the code will be interpreted to 
`C:\Users\\[username]\anaconda3\condabin\conda.bat activate [virtualenv name]`.


