
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
### Should Google Develop TensorFlowTinyJS for Microcontrollers?

## TensorFlowTinyJS has the potential to revolutionize the way microcontrollers interact with web pages via WebSerial, allowing for seamless training and deployment directly within the browser. 

This innovative approach builds on the success of TensorFlow.js, which democratized machine learning (ML) by bringing it to the web. With the expected exponential growth in inexpensive ML-capable microcontrollers, developing TensorFlowTinyJS could be both timely and transformative, enabling a new era of accessible and efficient ML applications.

<img src="https://github.com/user-attachments/assets/a641b911-2c7b-49c3-933a-07583006d1c9" width=700 />


My Github Profile [https://github.com/hpssjellis](https://github.com/hpssjellis)
<details closed> <summary>Script</summary>
In 2017 Google presented TensorflowJS making machine learning easier in web pages and I did a few year deep dive into learning everything I could about it and presenting it as easily as I could. After I was happy with that I emersed myself into microcontrollers like Arduinos and also made learning the more powerful ones that could do machine learning like the Arduino PortentaH7 and Nano33BleSense.<br>

The problem is that microcontrollers are not as well organized as Tensorflow and TensorflowJS, everything is a bit more chaotic based entirely on how active the producing company is about the product you are working with and the supporting cloud providers they support. Microcontrollers don't have the strict version control that TensorflowJS can provide. Using raw GNU C++ is not very user friendly and microPython also has issues. 
</details>
<hr>



#### 2 
### Who is Jeremy Ellis

I have been making neural networks since the 1990's most of them did not work, I was really excited when Tensorflow was made public in 2015, I also followed the creation of deeplearn.js by Nikhil Thorat and Daniel Smilkov which became tensorflowJS in 2017. For vairous reasons I have always made single page web applications, with LLM's these pages are becoming very useful. About 6 years ago I spent a while making TensorflowJS examples in that style of minimum files.

See this website at:
[https://hpssjellis.github.io/beginner-tensorflowjs-examples-in-javascript/#tfjs-models](https://hpssjellis.github.io/beginner-tensorflowjs-examples-in-javascript/#tfjs-models)


My Github Profile [https://github.com/hpssjellis](https://github.com/hpssjellis)

<img src="https://github.com/user-attachments/assets/a641b911-2c7b-49c3-933a-07583006d1c9" width=700 />

<hr>


#### 2 
### Why Microcontrollers

After learning TensorflowJS I started teaching Robotics wishing to bring the simplicity of Javascript to Arduinos.

<hr>



#### 2


### Pros of TensorFlowTinyJS for Local Use (1/2)

## Accessibility:
No Installation Requirements: Unlike C++ or Python, TensorFlowTinyJS could run directly in the browser without additional installations.
Ease of Use: Simplifies the development process, making it accessible to a broader audience, including those with limited technical expertise.


## Data Security:
Local Execution: Training models locally ensures complete data security, as no data needs to be transmitted over the internet.
Privacy: Sensitive data remains on the local computer, reducing the risk of data breaches. The trained ML model is flashed to the microcontroller but typically  does not contain the personal
information of the training data.


## Offline Capability:
Field Work: Enables ML tasks to be performed in the field without requiring an internet connection, which is crucial for remote or mobile applications.

## Reliability: 
Ensures that ML applications and training can function even in areas with poor or no connectivity.

<hr>


#### 3
### Pros of TensorFlowTinyJS for Local Use (2/2)

## Resource Efficiency:
Optimized for Constraints: Only a fraction of TensorFlow’s capabilities are needed, focusing on lightweight models suitable for microcontrollers.

## Sensor Fusion: 
Many microcontroller applications use modern or just developed new sensors, much sensor fusion ML does not require complex deep learning models. 
Many microcontroller applications could be made using fairly simple dense layer deep learning models. Vision and sound typically need more complex models.


## Cost-Effective:
Low-Cost Hardware: Utilizes inexpensive microcontrollers, making it a cost-effective solution for various applications.


## Open Source: 
Leveraging open-source technologies can reduce costs and encourage community contributions.

## Low Energy: 
Many microcontroller machine learning models are trained to do simple functions that do not need energy expensive WiFi etc. 
With lower energy battery consumption is reduced and the hardware can potentially work longer with minimal servicing.


<hr>

#### 4

### Cons of TensorFlowTinyJS for Local Use (1/2)

### Performance Limitations:
## Processing Power: 
Microcontrollers have limited processing power, which can restrict the complexity of models that can be run locally.

## Memory and Storage: 
Limited memory and storage capacity can constrain the size and number of models.

## Complexity in Implementation:
## Integration Challenges: 
Ensuring seamless integration between WebSerial and various microcontrollers can be complex.

## Browser Compatibility: 
Ensuring consistent performance across different browsers can be challenging.



<hr>

#### 5

### Cons of TensorFlowTinyJS for Local Use (2/2)


### Security Concerns:

## Local Vulnerabilities: 
While data security is enhanced by local training execution, the microcontroller should be secured against physical tampering and local attacks. 
Note: The ML model on a microcontroller typically does not contain the original training data

### Resource Constraints:

## Power Consumption: 
Running large ML models continuously can be power-intensive, which is a concern for battery-operated devices. 
Note: many microcontrollers run very low power and with smaller models can be made to run continuously with minimal power consupmtion

## Model Optimization: 
Requires significant effort to optimize models for the limited resources of microcontrollers.

<hr>



#### 6

### Difficult Steps in Developing TensorFlowTinyJS (1/2)

## Framework Development:

## Creating a Lightweight ML Library: 
Developing a version of TensorFlow that is optimized for microcontrollers.
WebSerial Integration: Ensuring reliable communication between the browser and microcontrollers via WebSerial.

### Model Optimization:

## Quantization and Pruning: 
Techniques to reduce model size and improve performance on microcontrollers.

## Efficient Algorithms: 
Developing algorithms that can run efficiently on limited hardware.

<hr>

#### 7

### Difficult Steps in Developing TensorFlowTinyJS (2/2)

### Security Measures:

## Data Encryption: 
Implementing robust encryption methods to protect data.

## Secure Communication Protocols: 
Ensuring secure data transmission between the browser and microcontrollers.

### Testing and Debugging:

## Cross-Platform Testing: 
Ensuring the framework works seamlessly across different browsers and operating systems.

## Hardware Compatibility: 
Testing with a wide range of microcontrollers to ensure compatibility and performance.


<hr>

#### 8

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<hr>

#### 9

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<hr>

#### 10

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<hr>

#### 11

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<hr>

#### 12

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<hr>

#### 13

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<hr>

#### 14

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

