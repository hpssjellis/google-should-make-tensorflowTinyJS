
### TensorflowJsMicro


Fork this repo, fill in your markdown and <html> for the 15 slides (max 20 slides), record your presentation and save it as ```recorded-talk.m4a``` (or change the code to reflect the new name.) A blank version of this github is [here](https://github.com/hpssjellis/pecha-kucha-lightning-talks-template)
 


<table border=1><tr><td>
 This demo is viewed at <br><a href="https://hpssjellis.github.io/google-should-make-tensorflowTinyJS/">google-should-make-tensorflowTinyJS</a><br>
<img src="https://github.com/user-attachments/assets/ee407d91-f0cf-48f0-9abc-d9af472372f8" width=250 />
</td><td>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/tf-js-micro.mp4" type="video/mp4" >
 </video>
 </td></tr>
 </table>



Number of Slides: <input type="text" id="myCountLinks" size="6" value="15" >, Seconds per Slide: <input type="text" id="myCountMax" size="6" value="20" >

<div id="myNumSlides" style=" position:sticky; top:0px; left:20px; height:25px; "> ...</div>  <br>

  









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
### Jeremy Ellis






<table border=1><tr><td>
 
## 35 years as a coding teacher, including working on neural networks, Javascript and almost a decade on robotics, 3D printing and blender 3D animation.
<br>
 Jeremy Ellis Github Profile at <br><a href="https://github.com/hpssjellis](https://github.com/hpssjellis">github.com/hpssjellis</a><br>
<img src="https://github.com/user-attachments/assets/36fad8cf-1329-4bc1-b374-586b98aa2528" width=350 />
</td><td>
 <video controls autoplay muted loop style="width:400px; height:300px;">
     <source src="media/vid/a01-tinyMLjs.mp4" type="video/mp4" width="400px" height="300px">
 </video>
 </td></tr>
 </table>

 

<details class="myDetails" closed> <summary>Script</summary>

Hello, my name is Jeremy Ellis, and I have the unique talent of making every possible technological mistake a grade 10 student could make. This has made me a very understanding teacher, and I’ve been teaching technology for over 35 years.

Back in the 1990s, I was experimenting with 3 layer, 8 node neural networks while most people were using "if" statements for AI. I manually changed the weights. My models never worked.

</details>
<hr>


#### 2 
### Tensorflow 

<table border=1><tr><td>


</td><td>
 Title <br>
 <video controls autoplay muted loop style="width:400px; height:300px;">
     <source src="media/vid/a02-rocksettaTinyML.mp4" type="video/mp4" width="400px" height="300px">
 </video>
 </td></tr>
 </table>


<details class="myDetails"  closed> <summary>Script</summary>

When TensorFlow launched in 2015, I saw a deep learning glimmer of hope. By 2018, I had become an expert in TensorFlowJS, and since then, I’ve been striving to master machine learning coding using TFmicro on the Arduino MBED Pro line and more recently, the SeeedStudio XIAO’s line of microcontrollers.

</details>
<hr>


#### 3 
### Proposal






<table border=1><tr><td>
 
<img src="https://github.com/user-attachments/assets/f5bda31b-6db5-47b2-a18a-ee7f41bec10f" width=300 />


</td><td>
 Title <br>
 <video controls autoplay muted loop style="width:400px; height:300px;">
     <source src="media/vid/a03-compile-webserial.mp4" type="video/mp4" width="400px" height="300px">
 </video>
 </td></tr>
 </table>



<details  class="myDetails" closed> <summary>Script</summary>

Today, I propose combining these two passions: TensorFlowJS and TFmicro. Web serial allows us to connect microcontrollers in the browser, merging these two Google-created technologies to create something encredibly powerful for the public, makers, education, and especially for economically disadvantaged students with poor internet and minimal ability to install software.


</details>
<hr>


#### 4 
### Microcontrollers



<table border=1><tr><td>


</td><td>
 Title <br>
 <video controls autoplay muted loop style="width:400px; height:300px;">
     <source src="media/vid/a04-close-arduino.mp4" type="video/mp4" width="400px" height="300px">
 </video>
 </td></tr>
 </table>


<details  class="myDetails" closed> <summary>Script</summary>

While the world is buzzing about both cloud and client-side LLMs, one of the next phases is low-power, low-cost, specifically trained ML-capable microcontrollers that interact with the real world. The Seeedstudio thumb sized XIAO-esp32s3-sense, for example, has an onboard camera that can perform vision machine learning at about 7 FPS for just $14 USD. This kind of capability was unheard of even a few years ago at that price.

</details>
<hr>


#### 5 
### Not All Rosy



<table border=1><tr><td>
Working with Microcontrollers has a lot of issues:


</td><td>
 Title <br>
 <video controls autoplay muted loop style="width:400px; height:300px;">
     <source src="media/vid/a05-connect-webserial.mp4" type="video/mp4" width="400px" height="300px">
 </video>
 </td></tr>
 </table>



<details  class="myDetails" closed> <summary>Script</summary>

However, the reality isn’t so rosy—most training happens in the cloud, for which the costs can change, companies have limited time to solve issues, and new software versions often deprecate previous solutions.

</details>
<hr>



#### 6
### TensorflowJS


<table border=1><tr><td>
TensorflowJS solves a lot of the issues microcontrollers have: 


</td><td>
 Title <br>
 <video controls autoplay muted loop style="width:400px; height:300px;">
     <source src="media/vid/a06-data.mp4" type="video/mp4" width="400px" height="300px">
 </video>
 </td></tr>
 </table>



 
<details  class="myDetails" closed> <summary>Script</summary>

TensorFlowJS, on the other hand, offers ease of use, client-side security, privacy, simplicity, power, and a very solid NPM based version control. My ML webpages made six years ago still typically work as intended. The many positives for TFJS have given it a very strong user base, but most web ML solutions stay on the web and have little impact on the real world.




</details>
<hr>



#### 7 
### The Solution



<table border=1><tr><td>
TinyMLjs

My Proof of concepts TinyMLjs 

[https://hpssjellis.github.io/tinyMLjs/public/acceleration/a00-best-acceleration.html](https://hpssjellis.github.io/tinyMLjs/public/acceleration/a00-best-acceleration.html)


Combine TensorFlowJS with TensorFlowMicro. That’s what I’ve done with TinyMLJS using the Arduino Nano33Ble-Sense. I have a Github example I call TinyMLjs.


</td><td>
 Title <br>
 <video controls autoplay muted loop style="width:400px; height:300px;">
     <source src="media/vid/a07-train.mp4" type="video/mp4" width="400px" height="300px">
 </video>
 </td></tr>
 </table>


<details  class="myDetails" closed> <summary>Script</summary>

Microcontroller machine learning is hard to do, cloud based and constantly changing. TFJS is easier and stable but lacks real-world power.



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
 <video controls autoplay muted loop style="width:400px; height:300px;">
     <source src="media/vid/a08-test-model.mp4" type="video/mp4" width="400px" height="300px">
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
 <video controls autoplay muted loop style="width:400px; height:300px;">
     <source src="media/vid/a09-export-model.mp4" type="video/mp4" width="400px" height="300px">
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
 <video controls autoplay muted loop style="width:400px; height:300px;">
     <source src="media/vid/a10-python-convert-to-c-header.mp4" type="video/mp4" width="400px" height="300px">
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
 <video controls autoplay muted loop style="width:400px; height:300px;">
     <source src="media/vid/a11-c-header.mp4" type="video/mp4" width="400px" height="300px">
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
 <video controls autoplay muted loop style="width:400px; height:300px;">
     <source src="media/vid/a12-rocksettaTinyML-ml-file.mp4" type="video/mp4" width="400px" height="300px">
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
 <video controls autoplay muted loop style="width:400px; height:300px;">
     <source src="media/vid/a13-compile-and-text.mp4" type="video/mp4" width="400px" height="300px">
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
 <video controls autoplay muted loop style="width:400px; height:300px;">
     <source src="media/vid/a14-webserial-test.mp4" type="video/mp4" width="400px" height="300px">
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
 <video controls autoplay muted loop style="width:400px; height:300px;">
     <source src="media/tf-js-micro.mp4" type="video/mp4" width="400px" height="300px">
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









### By Jeremy Ellis Twitter <a href="https://ca.linkedin.com/in/jeremy-ellis-4237a9bb">jeremy-ellis-4237a9bb</a> Use at your own Risk!
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

