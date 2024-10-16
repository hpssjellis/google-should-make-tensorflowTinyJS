
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
TensorflowJS with TfMicro in the web browser using WebSerial<br>
Arduino Nano33BleSense Demo <a href="https://hpssjellis.github.io/tinyMLjs/public/acceleration/a00-best-acceleration.html"> here</a>

<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>


<ol>
  <li>TensorflowJS encredible web machine learning using vision and sound.</li>
  <li>TfLite / TfMicro / RTLite: ML training of low cost Edge Devices </li>
  <li>TinyMLjs proof of concept</li> 
  <li>Google can combine TensorflowJS with Tensorflow Micro</li>
</ol>

<br>

</td><td>
 Proof of concept Overview TinyMLjs<br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a01-tinyMLjs.mp4" type="video/mp4" >
 </video>
 </td></tr>
 </table>

 

<details class="myDetails" closed> <summary>Script</summary>


Let's explore the exciting potential of combining TensorFlowJS with TfMicro using WebSerial. 
We're familiar with TensorFlowJS for vision and sound models, but now let's push further. 
This proof of concept uses TinyMLjs to train sensor-based ML models for actuators on low-cost microcontrollers—all within the browser!

</details> 

<br><br><br><br><br><br>

<hr>


#### 2 
### Why TensorflowJS?

<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>
 <ol>
<li>Client-side</li>
<li>Secure and Private</li>
<li>Easier for Education and Makers</li>
<li>Community of Web Developers</li>
<li>Total Control</li>
<li>Version Control</li>
 </ol>
</td><td>
 Install Arduino IDE Library rocksettaTinyML a verison of TfMicro<br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a02-rocksettaTinyML.mp4" type="video/mp4" >
 </video>
 </td></tr>
 </table>


<details class="myDetails"  closed> <summary>Script</summary>
Why choose TensorflowJS for this approach? First, it's client-side, which means no data needs to leave your device—ensuring both privacy and security. 
 It’s also perfect for education and maker communities because it's simple to use. Plus, you have full control over the process, with robust version management and support from a massive community of web developers.
</details> 

<br><br><br><br><br><br>

<hr>


#### 3 
### Why TfMicro


<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>
<ol> 
<li>Millions of microcontrollers</li>
<li>ML at the Edge</li>
<li>Solves bandwidth</li>
<li>Low Energy</li>
<li>Low Power</li>
<li>Personal Solutions</li>
<li>Low Cost $</li>
<li>Right to Repair</li>
</ol>
</td><td>
 Connecting MCU to Browser with webSerial <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a03-compile-webserial.mp4" type="video/mp4">
 </video>
 </td></tr>
 </table>



<details  class="myDetails" closed> <summary>Script</summary>


And why TfMicro? The ability to run machine learning on millions of microcontrollers brings ML to the edge. 
It solves common bandwidth problems by processing data locally, with minimal energy consumption. 
These microcontrollers offer low-power, affordable solutions—making this approach accessible for personal projects as well as commercial applications. 
Our "Right to Repair" allows us easy ways to reuse, repair and restore these products.

</details> 

<br><br><br><br><br><br>

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

Let’s talk about how to use TinyMLjs with TfMicro. Step one: install the 'RocksettaTinyML' library, compile the sensor code, and upload it to your microcontroller using WebSerial. Once that’s done, generate your sensor data, train the model right in your browser, test it, and then export the final model. Simple and efficient!

</details> 

<br><br><br><br><br><br>

<hr>


#### 5 
###  TinyMLjs Steps (2 of 3)



<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>
<ol>
<li>Install or online load Python</li>
<li>TensorflowJS_converter from TFJS to Keras</li>
<li>From Keras to TFLITE</li>
<li>xxd from TfLite to a c-header file</li>
<li>I use an iPython notebook that bundles the outputs into a .zip folder</li>
</ol>


</td><td>
Connect the Microcontroller to the webpage using webSerial <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a05-connect-webserial.mp4" type="video/mp4">
 </video>
 </td></tr>
 </table>



<details  class="myDetails" closed> <summary>Script</summary>
In step two, you’ll need Python installed or loaded online. Then, use TensorflowJS_Converter to convert your trained TFJS model into Keras format, then to TFlite and finally using xxd convert 
 the tFlite file into a c-header file which is an array of the binary characters needed to be run in the microcontroller. I use an iPython notebook that bundles all of the output into a zipped folder
</details> 

<br><br><br><br><br><br>

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


Using the RocksettaTinyML arduino Library and finding the ML model for your micrcontroller. The code has two files an .ino file and a c-header file. The c-header file needs to be replaced with the converted file you just made and then the entire sketch
needs to be compiled and uploaded to the micrcontroller and then tested in the serial monitor. Note: This testing can also be done in the browser.

</details> 

<br><br><br><br><br><br>

<hr>



#### 7 
### Why Do we need the Web Developers Community and Google? (1 of 4)
## General

<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>

 <ol>
  <li style="color:red">WebSerial barely works on Android</li>
  <li style="color:red">TensorflowJS_Converter is written in Python</li>
  <li style="color:red">Flashing code to MCU from the Browser only for the ESP boards</li>
  <li style="color:red">No community written code for the multitude of mcu's </li>
  <li style="color:red">Advanced: code can't yet be compiled in the browser client-side?</li>
</ol>
</td><td>
Train the model in the browser <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a07-train.mp4" type="video/mp4">
 </video>
 </td></tr>
 </table>


<details  class="myDetails" closed> <summary>Script</summary>

Now, why do we need support from the Web Developers, Maker Community and Google? First, WebSerial on Android needs some improvements, along with a Javascript lite version Python TensorflowJS_Converter. Flashing code directly from the browser will make it easier to support a wide range of microcontrollers. Imagine if we could even compile code right in the browser. These innovations are only possible with strong community and corporate support


</details> 

<br><br><br><br><br>

<hr>



#### 8 
### Why Do we need the community and Google? (2 of 4)
## WebSerial and TensorflowJS_Converter







<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>
 <ol>
  <li>WebSerial/WebUSB needs to be stable on Android so all of this can be done from your cell phone</li>
  <li>A lite version of TensorflowJS_Converter written in Javascript is needede to make the c-header file </li>
</ol>
</td><td>
After training the model test it in the browser <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a08-test-model.mp4" type="video/mp4" >
 </video>
 </td></tr>
 </table>



<details  class="myDetails" closed> <summary>Script</summary>
For WebSerial and TensorflowJS_Converter to reach their full potential, they need to be stable on Android. Additionally, a lightweight version of TensorflowJS_Converter written in Javascript would make generating C-header files much easier for developers.
</details> 

<br><br><br><br>

<hr>



#### 9 
### Why Do we need the community and Google? (3 of 4)
## Flashing from the browser and community code


<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>
 <ol>
  <li>The <a href="https://jason2866.github.io/WebSerial_ESPTool/">ESP online tool</a> can flash compiled code in the browser</li>
  <li>That ability needs to be able to be done on multiple mcu's</li>
  <li>The community can write the C++ code needed for the multitude of different mcu's sensors and actuators</li>
</ol>


</td><td>
View and export model from TensorflowJS <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a09-export-model.mp4" type="video/mp4">
 </video>
 </td></tr>
 </table>


 
<details  class="myDetails" closed> <summary>Script</summary>


The ESP tool already allows us to flash code directly from the browser for the ESP32 microcontroller board, but we need to expand that capability to other MCUs. The Community of Web Developers and Makers is essential for developing C++ code that will support a wide range of microcontrollers, sensors, and actuators and checking that these sketches work within the web browser environment.

</details> 

<br><br><br>

<hr>



#### 10 
### Why Do we need the community and Google? (4 of 4)
## Advanced: compiling microcontroller code from the browser! <br><br>



<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>
It’s good to remember Atwood’s Law: any application that can be written in JavaScript will eventually be written in JavaScript.<br><br>
Do we even need a microcontroller IDE? Can the code be written from the browser client-side or an image be saved and flashed directly to the microcontroller? These are questions that may become more importent and easier to achieve over the
next decade.


</td><td>
Load Python and use the TensorflowJS_Converter <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a10-python-convert-to-c-header.mp4" type="video/mp4" >
 </video>
 </td></tr>
 </table>


<details  class="myDetails" closed> <summary>Script</summary>
Finally, we reach the ultimate goal: compiling microcontroller code directly in the browser. Following Atwood’s Law, any application that can be written in Javascript eventually will be written in Javascript. 
 Do we even need a dedicated IDE anymore? Could all this be done from within the browser itself? Those are advanced questions that may take a while to answer.

</details> 

<br><br>

<hr>



#### 11
### Google Can Democritize ML on Microcontrollers in the Browser 




<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>

 
 <ol>
  <li style="color:green">Google can stabilize webSerial on Android</li>
  <li style="color:green">Google can make a lite TensorflowJS_converter in Javascript </li>
  <li style="color:green">Google can improve browser code flashing</li>
  <li style="color:green">Google can brainstorm clientside compiling</li>
</ol>

</td><td>
Python generates the tflite file then a c-header file all zipped <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a11-c-header.mp4" type="video/mp4" >
 </video>
 </td></tr>
 </table>


<details  class="myDetails" closed> <summary>Script</summary>


Google has the power to truly democratize machine learning at the edge. Google can stabilize webSerial on Android. Google can make a lite TensorflowJS_converter in Javascript. Google can improve browser code flashing.  Google can brainstorm clientside compiling.
Imagine millions of web developers having the ability to adapt machine learning models for physical world applications!
</details> 

<br><br><br><br><br><br>

<hr>



#### 12 
### Who is Jeremy Ellis



<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>

 <ol>
  <li>Technology teacher for ~35 years</li>
  <li>In the 1990's was making 3 layer 8 node neural networks</li>
  <li>Manually adjusted the weights. Nothing really worked</li>
  <li>2015 Tensorflow made everything easier</li>
  <li>By 2019 he was an expert in <a href="https://hpssjellis.github.io/beginner-tensorflowjs-examples-in-javascript/">browser based TensorflowJS</a></li>
  <li>Then he switched to ML on physical microcontrollers</li>
  <li>By 2024 he had become an expert at <a href="https://github.com/hpssjellis/maker100">Arduino Pro</a> and the <a href="https://github.com/hpssjellis/maker100-eco">Seeedstudio esp32</a>. </li>

</ol>
</td><td>
 RocksettaTinyML machine learning code to be compiled <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a12-rocksettaTinyML-ml-file.mp4" type="video/mp4" >
 </video>
 </td></tr>
 </table>



<details  class="myDetails" closed> <summary>Script</summary>

Jeremy Ellis has been a technology teacher for over 30 years. In the 1990's he was making 3 layer, 8 node, neural networks and manually adjusting the weights. Nothing really worked. 
In 2015 Tensorflow made everything easier. By 2019 he was an expert at TensorflowJS. Then he switched to physical mcu's. By 2024 he had become an expert at ML models on microcontrollers. 

</details> 

<br><br><br><br><br><br>

<hr>





#### 13 
### TinyMLjs Proof of Concept



<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>
TinyMLjs with RocksettaTinyML proves that the browser can train machine learning models and those models can be converted and installed on microcontrollers.
There are issues that could streamline this process, but solving thosee issues will take a wider community involvement beyond what I can do.

</td><td>
Replace the c-header file compile and test in the serial monitor <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a13-compile-and-text.mp4" type="video/mp4" >
 </video>
 </td></tr>
 </table>



<details  class="myDetails" closed> <summary>Script</summary>

TinyMLjs has shown that browser-based machine learning works, and it’s capable of training models that can then be converted and deployed onto microcontrollers. 

TensorFlowJS can be used to train a multitude of low-power, low-cost microcontrollers, giving power, privacy, freedom, and stability to everyone in this fast-changing world of microcontroller cloud costs and unstable software. 
Let’s be a part of using the greatest combination of Google frameworks: TensorFlowJS with TensorFlowMicro. 

</details> 

<br><br><br><br><br><br>

<hr>





#### 14
### TFJS with rtLite the new tfLite/Micro



<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>
Let's start making rtLite the new tf-micro and TensorflowJS work together in the browser. 
 It can be done, it just needs a community and some interest from Google.

</td><td>
The ML serial output can be tested in the browser <br>
 <video controls autoplay muted loop style="width:512px; height:288px;">
     <source src="media/vid/a14-webserial-test.mp4" type="video/mp4" >
 </video>
 </td></tr>
 </table>



<details  class="myDetails" closed> <summary>Script</summary>


In conclusion, let’s work together to make Tf-Micro and TensorflowJS function seamlessly in the browser. 
With the strength of the community, interest by Google, the future of machine learning at the edge is bright and full of possibilities making it accessible and practical for a wide range of people and applications. 
While there are challenges, the benefits of local execution, data security, Javascript simpicity and offline capability make it a compelling endeavor. 

</details> 

<br><br><br><br><br><br>

<hr>


#### 15 
### Credits





<table border=1> <col style="width:50%"><col style="width:50%"><tr><td>


 
It is exciting to be part of the TensorflowJS community that has so much potential for the future of ML on Edge Devices.

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
 Thank you all for being here today. It’s an exciting time to be part of the TensorflowJS community, and I’m thrilled to be on this journey with you. Let’s keep pushing the limits of what’s possible!



</details> 

<br><br><br><br><br><br>

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

