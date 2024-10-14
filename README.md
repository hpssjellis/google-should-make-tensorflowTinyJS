
Fork this repo, fill in your markdown and <html> for the 15 slides (max 20 slides), record your presentation and save it as ```recorded-talk.m4a``` (or change the code to reflect the new name.) A blank version of this github is [here](https://github.com/hpssjellis/pecha-kucha-lightning-talks-template)
 
<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>
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
TensorflowJS with TfMicro in the web browser using WebSerial

<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>

We all know that TensorflowJS makes amazing Machine Learning models
in the browser using vision or sound but now with my Proof of concept
we can start thinking about training other sensors and real life actuators 
using low cost microcontrollers doing ML at the edge all trained in the browser.
 

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

<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>
<li>client-side</li>
<li>Secure and Private</li>
<li>Easier for Education and Makers</li>
<li>Community of Web Developers</li>
<li>Total Control</li>
<li>Version Control</li>

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


<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>
 
<li>Millions of microcontrollers</li>
<li>ML at the Edge</li>
<li>Solves bandwidth</li>
<li>Low Energy</li>
<li>Low Power</li>
<li>Personal Solutions</li>
<li>Low Cost $</li>

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

<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>
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



<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>
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


<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>
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
### Why Do we need the community and Google? (1 of 4)
## General

<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>

 <ol>
  <li>WebSerial on Android</li>
  <li>TensorflowJS_Converter in Python</li>
  <li>Flashing code to MCU from the Browser</li>
  <li>Community written code for multitude of  mcu's </li>
  <li>Advanced: code compiled in the browser?</li>
</ol>
</td><td>
 Title <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a07-train.mp4" type="video/mp4">
 </video>
 </td></tr>
 </table>


<details  class="myDetails" closed> <summary>Script</summary>




</details>
<hr>



#### 8 
### Why Do we need the community and Google? (2 of 4)
WebSerial and TensorflowJS_Converter







<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>
 <ol>
  <li>WebSerial/WebUSB needs to be stable on Android so all of this can be done from your cell phone</li>
  <li>A lite version of TensorflowJS_Converter written in Javascript is needede to make the c-header file </li>
</ol>
</td><td>
 Title <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a08-test-model.mp4" type="video/mp4" >
 </video>
 </td></tr>
 </table>



<details  class="myDetails" closed> <summary>Script</summary>

</details>
<hr>



#### 9 
### Why Do we need the community and Google? (3 of 4)
Flashing from the browser and community code


<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>
 <ol>
  <li>The <a href="https://jason2866.github.io/WebSerial_ESPTool/">ESP online tool</a> can flash compiled code in the browser</li>
  <li>That ability needs to be able to be done on multiple mcu's</li>
  <li>The community can write the C++ code needed for the multitude of different mcu's sensors and actuators</li>
</ol>


</td><td>
 Title <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a09-export-model.mp4" type="video/mp4">
 </video>
 </td></tr>
 </table>


 
<details  class="myDetails" closed> <summary>Script</summary>




</details>
<hr>



#### 10 
### Why Do we need the community and Google? (4 of 4)
Advanced: compiling micr0controller code from the browser! <br><br>

It’s good to remember Atwood’s Law: any application that can be written in JavaScript will eventually be written in JavaScript.

<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>

Do we even need a microcontroller IDE? Can the code be written client-side or an image be saved and flashed directly to the microcontroller?


</td><td>
 Title <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a10-python-convert-to-c-header.mp4" type="video/mp4" >
 </video>
 </td></tr>
 </table>


<details  class="myDetails" closed> <summary>Script</summary>


</details>
<hr>



#### 11
### Google Can democritize ML on Microcontrollers (1 of 2)




<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>
Google can help make micr0controller machine learning training possible in the 
browser on desktop, laptop and Android phone. Google can democritize ML at the edge
 with some minor changes to the TensorflowJS_Converter, which would allow millions 
 of web Developers the Power to adapt ML models for the physical world. 


</td><td>
 Title <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a11-c-header.mp4" type="video/mp4" >
 </video>
 </td></tr>
 </table>


<details  class="myDetails" closed> <summary>Script</summary>



</details>
<hr>



#### 12 
### Google Can democritize ML on Microcontrollers (1 of 2)

Not yet mentioned.

<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>


 <ol>
  <li></li>
  <li></li>
  <li></li>
  <li></li>
</ol>
</td><td>
 RocksettaTinyML machine learning code to be compiled <br>
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



<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>
TinyMLjs proves that the browser can train machine learning models and those models can be converted and installed on microcontrollers.


</td><td>
Replace the c-header file compile and test in the serial monitor <br>
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



<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>
Let's start making rtLite and TensorflowJS work together in the browser. It can be done, just needs a community.

</td><td>
Also serial output can be tested in th browswer <br>
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





<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>
Exciting to be part of the TensorflowJS community that has so much potential for the future of ML.

Thank you, by Jeremy Ellis<br><br>

LinkedIn: <a href="https://www.linkedin.com/in/jeremy-ellis-4237a9bb/">jeremy-ellis-4237a9bb</a><br>

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

