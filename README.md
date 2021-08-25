# CoGate
![image](https://user-images.githubusercontent.com/39031660/130774238-2281e4d5-3f10-4f57-a3bd-6c2e0af8778e.png)

> A smart AI-based gate which will open if the person will be wearing the mask with a sanitizing pathway based on liquid sanitizing for humans and UV sanitization for electronic gadgets.

Keywords: Corona; COVID19; Arduino; Mask; TensorflowJs; CoronaVirus; MaskDetection; 

#### Read the whole project published here: [IJSRET_V7_issue2_261.pdf](https://ijsret.com/wp-content/uploads/2021/03/IJSRET_V7_issue2_261.pdf)

## Introduction & the Problem.
There is widespread Corona Virus in the entire world and we have no solution rather have precautions and wearing masks is one of the essential. Since we found many people are entering without the mask to offices so I made this project.
As per the problem, we have come with an excellent solution which will solve this problem.

*Introducing CoGate, a smart AI-based gate that will only allow those who will be wearing masks and not allow who are not having masks.*

## CoGate : How it works?
> ![image](https://user-images.githubusercontent.com/39031660/130774617-2736f1a1-a153-4be7-8077-28d2bcad9aa5.png)
> The workflow

• The AI-based Gate: The gate is based on realtime Computer Vision and Machine Learning. It is built with a camera that is connected with Google's Teachable Machine Image processing platform. The camera will detect whether the person is wearing a mask or not. If the person will be wearing the mask then it will send the signal to open the gate, to the microcontroller (here, Arduino) via Serial Port Interface (we are using p5 Serial Port). If the person will not be wearing a mask then the gate will not open.

• The UV & Sanitizing Chambers:The pathway of CoGate will also have a sanitizing chamber, of liquid for humans and a UV sanitizing chamber for electronic gadgets, and at the last, there'll be another gate to let the person enter into the office/building.

• The crowd controller: The last gate can be used as a counter (in malls especially) to enter a particular number of people to avoid crowds over that place.


## Methods:
• The face mask recognition in this paper is developed with a machine learning algorithm through the image classification method using Google’s Teachable Machines; which is a GUI based online machine learning model trainer. 

• The teachable machine first takes nearly 200 images of persons with wearing variety of mask and 150 images of persons without masks. All the images are curated from Google Images. Also the images from the camera has been taken with the previous data for lightening conditions with total 224 image samples for “Mask” and 170 image samples for “Without Mask”. 

> ![image](https://user-images.githubusercontent.com/39031660/130774964-9877c0db-28b3-4025-be02-f23887bf8c21.png)

> Personal Dataset of Mask and No Mask

> ![image](https://user-images.githubusercontent.com/39031660/130775198-1a1696d0-4ac2-473e-aa9e-60b06d653abd.png)

> Dataset of Mask and No Mask

 • The data is trained with an Epochs of 60, Batch size of 32 and with a learning rate of 0.0011. The Teachable Machine uses a popular deep learning technique called transfer learning. It may take 2-3 minutes to 30 minutes depending upon the epochs, batch size and learning rate.

## Discussion
After the training, we got the accuracy per class is in ratio 34:26 (check the confusion matrix) with a test accuracy of 0.94999. The training data is exported in Tensorflow.js format. Using the exported result, we can use the link generated to add it to any website portal to run the model. 

![image](https://user-images.githubusercontent.com/39031660/130776641-ab1ef062-af19-4b37-82e2-7e66c47edc3d.png)

In this project, a sample webpage [visit here](https://test-cogate.netlify.app/) is created to test the trained data. The model implemented in the video. If a face is detected, it proceeds to the next process. From detected frames containing faces, reprocessing will be carried out including resizing the image size, converting to the array, pre-processing input using Tensorflow.js.

![image](https://user-images.githubusercontent.com/39031660/130776753-a43f7be3-85c1-4de7-8721-76fed97791d7.png)

Now, the algorithm sends signal to the Arduino through serial port (via P5.js webpage using Chrome WebUSB). If the person is wearing masks, the JavaScript script will send a signal to Arduino via P5.js to open the gate else it will give a warning to wear a mask.

![image](https://user-images.githubusercontent.com/39031660/130776900-b32d9f14-a072-4e52-8ce4-93d136325c8a.png)


## Conclusion and Future Scope:
In this work, a system for face mask detection has been introduced, and allowing the masked persons object to prevent COVID-19 spreads from human to human in various public places. For image detection, we have employed the model trained using Teachable Machines to produce high-performance outcomes using Tensorflow.js. Using P5.js, the algorithm sends signal to open the gate when the person is wearing mask. 

The system is quite slow since it is trained from a automatic trainer. In future, this model will be trained manually using OpenCV, Tensorflow & Deep Learning and will be deployed in a edged based device to optimize the algorithm. Further, there will be an implementation of temperature sensor to detect the temperature to make the screening more accurate.

Thus, in overall the system aims to stop the spread of the virus making the persons to wear mask and avoid crowd.


## References:
1.	WHO | About COVID-19 | COVID-19 | Health topics, [online] Available: http://www.emro.who.int/health-topics/corona-virus/about-covid-19.html
2.	Deploy Teachable Machine: Arduino, [online] Available:
https://medium.com/analytics-vidhya/deploy-teachable-machine-circuit-playground-express-arduino-p5-js-tinyusb-b30508d4024a
3.	Google’s Teachable Machine | Website, [online] Available:
https://teachablemachine.withgoogle.com/
4.	Deployment of Paper | Netlify, [online] Available:
https://test-cogate.netlify.app
5. Post in Ardiuno Forumn | [online] Available: https://create.arduino.cc/projecthub/samalsaswat0/cogate-1ce968?f=1#
6. Video | YouTube | [online] Available: https://youtu.be/kLkt-9Wvn44
