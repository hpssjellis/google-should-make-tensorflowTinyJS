 

 

 

Hello, my name is Jeremy Ellis, and I have the unique talent of making every possible technological mistake a grade 10 student could make. This has made me a very understanding teacher, and I’ve been teaching technology for over 35 years. 

Back in the 1990s, I was experimenting with neural networks while most people were using if statements for AI. My models never worked. When TensorFlow launched in 2015, I saw a glimmer of hope. By 2018, I had become an expert in TensorFlowJS, and since then, I’ve been striving to master machine learning coding using TFmicro on the Arduino MBED Pro line and more recently, the SeeedStudio XIAO’s line of microcontrollers. 

Today, I propose combining these two passions: TensorFlowJS and TFmicro. Web serial allows us to connect microcontrollers in the browser, merging these two Google-created technologies to create something incredibly powerful for the public, makers, education, and especially for economically disadvantaged students with poor internet and minimal ability to install software. 

Let me explain. 

Microcontrollers 

While the world is buzzing about both cloud and client-side LLMs, one of the next phases is low-power, low-cost, specifically trained ML-capable microcontrollers that interact with the real world. The Seeedstudio thumb sized XIAO-esp32s3-sense, for example, has an onboard camera that can perform vision machine learning at about 7 FPS for just $14 USD. This kind of capability was unheard of even a few years ago at that price. However, the reality isn’t so rosy—most training happens in the cloud, for which the costs can change, companies have limited time to solve issues, and new software versions often deprecate previous solutions. 

TensorFlowJS 

TensorFlowJS, on the other hand, offers ease of use, client-side security, privacy, simplicity, power, and a very solid NPM based version control. My ML webpages made six years ago still typically work as intended. The many positives for TFJS have given it a very strong user base, but most web ML solutions stay on the web and have little impact on the real world.  

The Challenge 

Microcontroller machine learning is hard to do, cloud based and constantly changing. TFJS is easier and stable but lacks real-world power. 

The Solution 

Combine TensorFlowJS with TensorFlowMicro. That’s what I’ve done with TinyMLJS using the Arduino Nano33Ble-Sense. I have a Github example I call TinyMLjs   

 https://hpssjellis.github.io/tinyMLjs/public/acceleration/a00-best-acceleration.html 

 

Steps: 

Load serial monitor input-output C++ code using your favorite microcontroller IDE. 

Connect the microcontroller to the browser using webSerial. 

Send sensor data to the browser. 

Train an ML model. 

Convert the model from TFJS to TFlite, then to a C-header file. 

Put that C-header file into working C++ code and flash it to the microcontroller. 

Sounds great, but things aren’t perfect, and that’s why we need Google. 

What Needs Improvement: 

So, if I’ve solved the issue, why involve Google? Here are a few reasons: 

The TensorFlowJS converter is written in Python, which means people have to install Python. If you must and are able to install Python, why not just stay with Python? We need a simplified TensorflowJS-converter written in Javascript. I can’t do that. 

Web serial is not as stable on Android. Google could probably solve that. 

Flashing code from the browser is possible as proven by esp online but not yet developed for all microcontrollers. 

Do we even need a microcontroller IDE? Can the code be written client-side or an image be saved and flashed directly to the microcontroller? 

Google has the power to maintain and make this available to everyone. 

It’s good to remember Atwood’s Law: any application that can be written in JavaScript will eventually be written in JavaScript. 

Conclusion 

I have a proof of concept that TensorFlowJS can be used to train the multitude of low-power, low-cost microcontrollers, giving power, privacy, freedom, and stability to everyone in this fast-changing world of microcontroller cloud costs and unstable software. Let’s be a part of using the greatest combination of Google frameworks: TensorFlowJS with TensorFlowMicro. I hope they call it something creative like TensorFlowTinyJS or TensorFlowJSMicro or... 

 

 

Thank you, by Jeremy Ellis 2024  

LinkedIn: https://www.linkedin.com/in/jeremy-ellis-4237a9bb/ 

Github: https://github.com/hpssjellis 

 
