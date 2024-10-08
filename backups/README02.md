
### TensorflowTinyJS


Fork this repo, fill in your markdown and <html> for the 15 slides (max 20 slides), record your presentation and save it as ```recorded-talk.m4a``` (or change the code to reflect the new name.)
 
 Setup gitPages --> settings-->pages-->none to master-->save--> copy the link and replace below.

Demo of this Github Markdown can be viewed at this GitPages site  [https://hpssjellis.github.io/javascript-on-markdown/](https://hpssjellis.github.io/google-should-make-tensorflowTinyJS//)


This Github Repository [https://github.com/hpssjellis/google-should-make-tensorflowTinyJS](https://github.com/hpssjellis/google-should-make-tensorflowTinyJS)


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
 
<input type=button value="Start-Pre-Recorded" onclick="{                                                        
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
 
<input type=button value="Hide" onclick="{
   document.getElementById('myStick').style.display = 'none';
}"> 
  <input type=button value="TOP" onclick="{ 
   window.location.href='#top'; 
}">  
  
 </div>

#### 1 
### Why Google Should Develop TensorFlowTinyJS for Microcontrollers

## TensorFlowTinyJS has the potential to revolutionize the way microcontrollers interact with web pages via WebSerial, allowing for seamless training and deployment directly within the browser. 

This innovative approach builds on the success of TensorFlow.js, which democratized machine learning (ML) by bringing it to the web. With the expected exponential growth in ML-capable microcontrollers, developing TensorFlowTinyJS could be both timely and transformative, enabling a new era of accessible and efficient ML applications.

<img src="https://user-images.githubusercontent.com/5605614/175780835-2b0d64a4-0ba8-4c90-9f05-fb4e89cd6980.png" width=700 />

[https://github.com/hpssjellis](https://github.com/hpssjellis)

<hr>


#### 2


### Pros of TensorFlowTinyJS for Local Use (1/2)

## Accessibility:
No Installation Requirements: Unlike C++ or Python, TensorFlowTinyJS can run directly in the browser without additional installations.
Ease of Use: Simplifies the development process, making it accessible to a broader audience, including those with limited technical expertise.


## Data Security:
Local Execution: Running models locally ensures complete data security, as no data needs to be transmitted over the internet.
Privacy: Sensitive data remains on the device, reducing the risk of data breaches.


## Offline Capability:
Field Work: Enables ML tasks to be performed in the field without requiring an internet connection, which is crucial for remote or mobile applications.
Reliability: Ensures that ML applications can function even in areas with poor or no connectivity.

<hr>


#### 3
### Pros of TensorFlowTinyJS for Local Use (2/2)

## Resource Efficiency:
Optimized for Constraints: Only a fraction of TensorFlow’s capabilities are needed, focusing on lightweight models suitable for microcontrollers.
Sensor Fusion: Many microcontroller applications, such as sensor fusion, do not require complex deep learning models, which can be handled server-side if necessary.


## Cost-Effective:
Low-Cost Hardware: Utilizes inexpensive microcontrollers, making it a cost-effective solution for various applications.
Open Source: Leveraging open-source technologies can reduce costs and encourage community contributions.


<hr>

#### 4

### Cons of TensorFlowTinyJS for Local Use (1/2)

## Performance Limitations:
Processing Power: Microcontrollers have limited processing power, which can restrict the complexity of models that can be run locally.
Memory and Storage: Limited memory and storage capacity can constrain the size and number of models.

## Complexity in Implementation:
Integration Challenges: Ensuring seamless integration between WebSerial and various microcontrollers can be complex.
Browser Compatibility: Ensuring consistent performance across different browsers can be challenging.



<hr>

#### 5

### Cons of TensorFlowTinyJS for Local Use (2/2)


## Security Concerns:
Local Vulnerabilities: While data security is enhanced by local execution, the device itself must be secured against physical tampering and local attacks.

## Resource Constraints:
Power Consumption: Running ML models can be power-intensive, which is a concern for battery-operated devices.
Model Optimization: Requires significant effort to optimize models for the limited resources of microcontrollers.

<hr>



#### 6

### Difficult Steps in Developing TensorFlowTinyJS (1/2)

## Framework Development:
Creating a Lightweight ML Library: Developing a version of TensorFlow that is optimized for microcontrollers.
WebSerial Integration: Ensuring reliable communication between the browser and microcontrollers via WebSerial.

## Model Optimization:
Quantization and Pruning: Techniques to reduce model size and improve performance on microcontrollers.
Efficient Algorithms: Developing algorithms that can run efficiently on limited hardware.

<hr>

#### 7

### Difficult Steps in Developing TensorFlowTinyJS (2/2)

## Security Measures:
Data Encryption: Implementing robust encryption methods to protect data.
Secure Communication Protocols: Ensuring secure data transmission between the browser and microcontrollers.

## Testing and Debugging:
Cross-Platform Testing: Ensuring the framework works seamlessly across different browsers and operating systems.
Hardware Compatibility: Testing with a wide range of microcontrollers to ensure compatibility and performance.


<hr>

#### 8

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<hr>

#### 9

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<hr>

#### 10

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<hr>

#### 11

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<hr>

#### 12

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<hr>

#### 13

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<hr>

#### 14

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<hr>

#### 15


Developing TensorFlowTinyJS for local use on microcontrollers could democratize ML, making it accessible and practical for a wide range of applications. While there are challenges, the benefits of local execution, data security, and offline capability make it a compelling endeavor. The anticipated growth in ML-capable microcontrollers underscores the importance of such a development.

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
