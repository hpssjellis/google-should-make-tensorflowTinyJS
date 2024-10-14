
### TensorflowJsMicro


Fork this repo, fill in your markdown and <html> for the 15 slides (max 20 slides), record your presentation and save it as ```recorded-talk.m4a``` (or change the code to reflect the new name.) A blank version of this github is [here](https://github.com/hpssjellis/pecha-kucha-lightning-talks-template)
 


<table border=1> <col style="width:30%"><col style="width:70%"><tr><td>
 This demo is viewed at <br><a href="https://hpssjellis.github.io/google-should-make-tensorflowTinyJS/">google-should-make-tensorflowTinyJS</a><br>
<img src="https://github.com/user-attachments/assets/ee407d91-f0cf-48f0-9abc-d9af472372f8" width=200 />
</td><td>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/tf-js-micro.mp4" type="video/mp4" >
 </video>
 </td></tr>
 </table>



Number of Slides: <input type="text" id="myCountLinks" size="6" value="15" >, Seconds per Slide: <input type="text" id="myCountMax" size="6" value="20" >

<div id="myNumSlides" style=" position:sticky; top:0px; left:20px; height:25px; "> ...</div> 

  









<div id="myStick"  style=" position:sticky; top:30px; display:inline; ">
 
 <input type=button value="Start-No-Sound" onclick="{
   document.getElementById('myStick').style.display = 'none';                                                 
   xSlide  = document.getElementById('myCountLinks').value; 
   myMainNum = document.getElementById('myCountMax').value;    
   myAudio01.pause();
   myAudio01.currentTime = 0;  
   myIndex = 0;  
   clearInterval(myLooper);  
   myCountUp = -1;
   carousel();  
}">
 
<input type=button value="Start-Pre-Recorded" style="background-color:green; color:yellow;" onclick="{                                                        
   document.getElementById('myStick').style.display = 'none';   
   xSlide  = document.getElementById('myCountLinks').value; 
   myMainNum = document.getElementById('myCountMax').value;  
   myAudio01.pause();
   myAudio01.currentTime = 0;                                                
   myAudio01 = new Audio('recorded-talk.m4a');
   myAudio01.play(); 
   myIndex = 0;  
   clearInterval(myLooper);  
   carousel();                                                
}">  
 
  <input type=button value="Rewind" onclick="{
   myIndex = 0;  
   clearInterval(myLooper);
   clearInterval(myCounting);
   if (myAudio01.paused && myAudio01.currentTime > 0 && !myAudio01.ended) {
      } else {
         myAudio01.pause();
     }
}">   

 <input type=button value="-" onclick="{
   clearInterval(myLooper);
   clearInterval(myCounting);
   myIndex -= 1;    
   window.location.href='#'+myIndex;
}">   
  
<input type=button value="+" onclick="{
  clearInterval(myLooper);
  clearInterval(myCounting);
  myIndex += 1;  
  window.location.href='#'+myIndex;
}"> 
  
<input type=button value="Back" onclick="{
   myIndex = myIndex - 2;    
   if (myIndex <= 0){myIndex=0};                                      
   myNext();
}">   
  
<input type=button value="Next" onclick="{
   myNext();
}"> 
 
    
  
 <input id="myPause" type=button value="Pause" onclick="{ 
   clearInterval(myLooper);
   clearInterval(myCounting);
   if (this.value == 'Pause'){                                                     
       this.value = 'Play / Pause'; 
       if (myAudio01.paused && myAudio01.currentTime > 0 && !myAudio01.ended) {
      } else {
         myAudio01.pause();
     }
   } else {    
     myIndex -= 1; 
     myCountUp += 1;
     carousel();                                                 
     this.value = 'Pause';  
     if (myAudio01.paused && myAudio01.currentTime > 0 && !myAudio01.ended) {
         myAudio01.play();
      }                                                    
   }
}"> 

 <input id="myPause" type=button value="Scripts Open" onclick="{ 
   let myScripts = document.getElementsByClassName('myDetails')
   if (this.value == 'Scripts Open'){                                                     
       this.value = 'Scripts Close'; 
       for (let i=0; i < myScripts.length; i++){
           myScripts[i].open = true
       }
   } else {                                           
     this.value = 'Scripts Open';  
       for (let i=0; i < myScripts.length; i++){
           myScripts[i].open = false
       }     
   }
}"> 

 
<input type=button value="Hide" onclick="{
   document.getElementById('myStick').style.display = 'none';
}"> 
  <input type=button value="TOP" onclick="{ 
   window.location.href='#top'; 
}">  
  
 </div>

#### 1 
### Exciting times for WebAI!
TensorflowJS with TfMicro in the web browswer using WebSerial

<table border=1> <col style="width:30%"><col style="width:70%"><tr><td>

We all know that TensorflowJS makes amazing Machine Learning models
in the browswer using vision or sound but now we can start thinging about
other sensors and real actuators using microcontrollers trained in the browser
 

<br>

</td><td>
 Proof of concept Overview TinyMLjs<br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a01-tinyMLjs.mp4" type="video/mp4" >
 </video>
 </td></tr>
 </table>

 

<details class="myDetails" closed> <summary>Script</summary>



</details>
<hr>


#### 2 
### Why TensorflowJS?

<table border=1> <col style="width:30%"><col style="width:70%"><tr><td>
<li>client-side</li>
<li>Secure and Private</li>
<li>Easier</li>
<li>Community</li>
<li>Total Control</li>
<li></li>

</td><td>
 Install Arduino IDE Library rocksettaTinyML a verison of TfMicro<br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a02-rocksettaTinyML.mp4" type="video/mp4" >
 </video>
 </td></tr>
 </table>


<details class="myDetails"  closed> <summary>Script</summary>

</details>
<hr>


#### 3 
### Why TfMicro


<table border=1><tr><td>
 
<li>Millions of microcontrollers</li>
<li>ML at the Edge</li>
<li>Solves bandwidth</li>
<li>Low Energy</li>
<li>Low Power</li>
<li>Personal Solutions</li>
<li>Low Cost $$</li>

</td><td>
 Connecting MCU to Browser with webSerial <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a03-compile-webserial.mp4" type="video/mp4">
 </video>
 </td></tr>
 </table>



<details  class="myDetails" closed> <summary>Script</summary>




</details>
<hr>


#### 4 
### TinyMLjs Steps (1 of 3)

Explaining the videos on the right side of the page.

<table border=1><tr><td>
<ol>
<li>Install tf-Micro Arduino Library  "RocksettaTinyML"</li>
<li>Compile and upload to mcu webSerial sensor code</li>
<li>Generate Data</li>
<li>Train ML Model in Browser</li>
<li>Test ML model</li>
<li>Export ML model</li>
</ol>
</td><td>
 Compile-upload to micrcontroller, check serial LED on/off <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a04-close-arduino.mp4" type="video/mp4" >
 </video>
 </td></tr>
 </table>


<details  class="myDetails" closed> <summary>Script</summary>



</details>
<hr>


#### 5 
###  TinyMLjs Steps (2 of 3)



<table border=1><tr><td>
<ol>
<li>Install or online load Python</li>
<li>TensorflowJS_converter from TFJS to c-header file</li>
</ol>


</td><td>
Connect the Microcontroller to the webpage using webSerial <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a05-connect-webserial.mp4" type="video/mp4">
 </video>
 </td></tr>
 </table>



<details  class="myDetails" closed> <summary>Script</summary>

</details>
<hr>



#### 6
###  TinyMLjs Steps (3 of 3)


<table border=1><tr><td>
<ol>
<li>RocksettaTinyML library examples Arduino Code</li>
<li>Replace c-header file library</li>
<li>Compile, upload and test in the serial monitor</li>
<li>Can also test back in the browser</li>
</ol>
</td><td>
 Create motion x, y, z data <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a06-data.mp4" type="video/mp4" >
 </video>
 </td></tr>
 </table>



 
<details  class="myDetails" closed> <summary>Script</summary>




</details>
<hr>



#### 7 
### Why TensoflowJS



<table border=1><tr><td>


</td><td>
 Title <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a07-train.mp4" type="video/mp4">
 </video>
 </td></tr>
 </table>


<details  class="myDetails" closed> <summary>Script</summary>

TensorFlowJS, on the other hand, offers ease of use, client-side security, privacy, simplicity, power, and a very solid NPM based version control. My ML webpages made six years ago still typically work as intended. The many positives for TFJS have given it a very strong user base, but most web ML solutions stay on the web and have little impact on the real world.


</details>
<hr>



#### 8 
### The Steps (TinyMLjs)








<table border=1><tr><td>
<ol>
  <li> Load serial monitor input-output C++ code using your favorite microcontroller IDE. </li>
  <li> Connect the microcontroller to the browser using webSerial. </li>
  <li> Send sensor data to the browser. </li>
  <li> Train an ML model. </li>
  <li> Using TensorflowJS_converter installed using Python convert the model from TFJS to TFlite, then to a C-header file using xxd. </li>
  <li> Put that C-header file into working C++ code using your IDE, compile and flash it to the microcontroller. </li>
</ol>

</td><td>
 Title <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a08-test-model.mp4" type="video/mp4" >
 </video>
 </td></tr>
 </table>



<details  class="myDetails" closed> <summary>Script</summary>
<ol>
  <li> Load serial monitor input-output C++ code using your favorite microcontroller IDE. </li>
  <li> Connect the microcontroller to the browser using webSerial. </li>
  <li> Send sensor data to the browser. </li>
  <li> Train an ML model. </li>
  <li> Using TensorflowJS_converter installed using Python convert the model from TFJS to TFlite, then to a C-header file using xxd. </li>
  <li> Put that C-header file into working C++ code using your IDE, compile and flash it to the microcontroller. </li>
</ol>
</details>
<hr>



#### 9 
###  The small print (Issues)



<table border=1><tr><td>
TensorflowJS_converter only works using python on from a cloud site.

WebUSB/WebSerial not stable on Android


</td><td>
 Title <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a09-export-model.mp4" type="video/mp4">
 </video>
 </td></tr>
 </table>


 
<details  class="myDetails" closed> <summary>Script</summary>


So, if I’ve solved the issue, why involve Google? Here are a few reasons:

The TensorFlowJS converter is written in Python, which means people have to install Python. If you must and are able to install Python, why not just stay with Python? We need a simplified TensorflowJS-converter written in Javascript. I can’t do that.

Web serial is not as stable on Android. Google could probably solve that.



</details>
<hr>



#### 10 
### The advanced Issues




<table border=1><tr><td>
Flashing compiled code using webSerial over the browser.
<a href="https://jason2866.github.io/WebSerial_ESPTool/">ESP Online Flash Tool </a> <br>
<img src="https://github.com/user-attachments/assets/5620a834-a696-49b0-aec8-848ecb1cc28c" width=300 />

Compiling MCU code in the browser.

</td><td>
 Title <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a10-python-convert-to-c-header.mp4" type="video/mp4" >
 </video>
 </td></tr>
 </table>


<details  class="myDetails" closed> <summary>Script</summary>

Flashing code from the browser is possible as proven by esp online but not yet developed for all microcontrollers.

Do we even need a microcontroller IDE? Can the code be written client-side or an image be saved and flashed directly to the microcontroller?

</details>
<hr>



#### 11
### Google has the Power





<table border=1><tr><td>
Google can do it!

</td><td>
 Title <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a11-c-header.mp4" type="video/mp4" >
 </video>
 </td></tr>
 </table>


<details  class="myDetails" closed> <summary>Script</summary>

Google has the power to maintain and make this available to everyone. 

It’s good to remember Atwood’s Law: any application that can be written in JavaScript will eventually be written in JavaScript.

Reminder tensorflowJS combined with TensorflowMicro does not have to work for all ML models and all microcontrollers. It needs to be able to simplify
using microcontrollers for the general public. Anyone is welcome to try to use the most optimized Python or C++ methods to work on more advanced microcontroller machine learning 

</details>
<hr>



#### 12 
###  Extras


<table border=1><tr><td>


</td><td>
 Title <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a12-rocksettaTinyML-ml-file.mp4" type="video/mp4" >
 </video>
 </td></tr>
 </table>



<details  class="myDetails" closed> <summary>Script</summary>



</details>
<hr>





#### 13 
### Nearly Finished



<table border=1><tr><td>
TinyMLjs proves that the browser can train macine learning models and those models can be converted and installed on microcontrollers.


</td><td>
 Title <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a13-compile-and-text.mp4" type="video/mp4" >
 </video>
 </td></tr>
 </table>



<details  class="myDetails" closed> <summary>Script</summary>

I have a proof of concept that TensorFlowJS can be used to train the multitude of low-power, low-cost microcontrollers, giving power, privacy, freedom, and stability to everyone in this fast-changing world of microcontroller cloud costs and unstable software. Let’s be a part of using the greatest combination of Google frameworks: TensorFlowJS with TensorFlowMicro. As MCU become more common our right to repair in a simplified way becomes more important.

</details>
<hr>





#### 14
### Conclusion



<table border=1><tr><td>
Let's start working on making rtLite and TensorflowJS working together in the browser. It can be done, just needs a community.

</td><td>
 Title <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a14-webserial-test.mp4" type="video/mp4" >
 </video>
 </td></tr>
 </table>



<details  class="myDetails" closed> <summary>Script</summary>

Developing TensorFlowTinyJS for local use on microcontrollers could democratize ML, making it accessible and practical for a wide range of people and applications. While there are challenges, the benefits of local execution, data security, Javascript simpicity and offline capability make it a compelling endeavor. The anticipated growth in ML-capable microcontrollers underscores the importance of such a development.

</details>


<hr>


#### 15 
### Exit





<table border=1><tr><td>
Exciting to be part of the TensorflowJS commkunity that has so much potential for the future

Thank you, by Jeremy Ellis

LinkedIn: <a href="https://www.linkedin.com/in/jeremy-ellis-4237a9bb/">jeremy-ellis-4237a9bb</a>

Github: <a href="https://github.com/hpssjellis">github.com/hpssjellis</a>

</td><td>
 Title <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/tf-js-micro.mp4" type="video/mp4" >
 </video>
 </td></tr>
 </table>



<details  class="myDetails" closed> <summary>Script</summary>

I hope they call it something creative like TensorFlowTinyJS or TensorFlowJSMicro or...

Thank you, by Jeremy Ellis 2024

LinkedIn: https://www.linkedin.com/in/jeremy-ellis-4237a9bb/

Github: https://github.com/hpssjellis

</details>
<hr>




<a href="#top">Top of page</a>









### By Jeremy Ellis LinkedIn <a href="https://ca.linkedin.com/in/jeremy-ellis-4237a9bb">jeremy-ellis-4237a9bb</a> Use at your own Risk!
### Note the github for this page, with markdown and javascript is at [https://github.com/hpssjellis/google-should-make-tensorflowTinyJS](https://github.com/hpssjellis/google-should-make-tensorflowTinyJS) 

A blank template repository for you to make your own presentations is at [https://github.com/hpssjellis/pecha-kucha-lightning-talks-template](https://github.com/hpssjellis/pecha-kucha-lightning-talks-template)



<script>
 let myIndex = 1;
 let myLooper = 0;
 let myCounting = 0;
 let myMainNum = 20;   
 let myCountUp = 0;
 let xSlide = 3;
 let myAudio01 = new Audio();
 
;
function carousel() {
  clearInterval(myCounting);
  myCountUp = -1;
  var i;
;
  myIndex++;
  if (myIndex > xSlide) {myIndex = xSlide};    
  window.location.href='#'+myIndex;
  myCountDown();
  myCounting = setInterval(myCountDown, 1000);
  myLooper = setTimeout(carousel, myMainNum*1000); 
}
  
function myCountDown(){
  myCountUp++;
  if (myCountUp >= myMainNum ) {
    myCountUp = myMainNum;                              
  }
  if (myIndex >= xSlide && myMainNum == myCountUp){ 
     document.getElementById("myNumSlides").innerHTML = `&nbsp;&nbsp;&nbsp; Slide ${myIndex} of ${xSlide} slides. ALL DONE <input type=button value="Show"  style="height:25px; " onclick="{document.getElementById('myStick').style.display = 'inline'; }"> `;
     clearInterval(myCounting);             
     clearInterval(myLooper);  
  }
  else {    
     document.getElementById("myNumSlides").innerHTML = `&nbsp;&nbsp;&nbsp; Slide ${myIndex} of ${xSlide} slides. ${myMainNum-myCountUp} seconds remaining <input type=button value="Show" style="height:25px; " onclick="{document.getElementById('myStick').style.display = 'inline'; }"> `;
  }
}
;
function myNext(){   
  xSlide  = document.getElementById('myCountLinks').value; 
  myMainNum = document.getElementById('myCountMax').value;                        
  clearInterval(myLooper) ; 
  carousel();  
}  
;
</script>  

