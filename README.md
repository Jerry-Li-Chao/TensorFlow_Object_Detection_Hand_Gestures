# Tensorflow Object Detection on Hand Gestures (Periodically Updating)
## Steps
<br />
<b>Step 1.</b> Clone this repository: https://github.com/Jerry-Li-Chao/TensorFlow_Object_Detection_Hand_Gestures
<br/><br/>
<b>Step 2.</b> Create a new virtual environment 
<pre>
python -m venv tfod
</pre> 
<br/>
<b>Step 3.</b> Activate your virtual environment
<pre>
source tfod/bin/activate # Linux
.\tfod\Scripts\activate # Windows 
</pre>
<br/>
<b>Step 4.</b> Install dependencies and add virtual environment to the Python Kernel
<pre>
python -m pip install --upgrade pip
pip install ipykernel
python -m ipykernel install --user --name=tfod
</pre>
<br/>
<b>Step 5.</b> Collect images using the Notebook 1. Image Collection.ipynb - ensure you change the kernel to the virtual environment as shown below
<br/>
<br/>
<b>Step 5.1</b> Labeling pictures, create bounding boxes for features that needs to be identified.  
<img src="img/ThumbsUp_cropped.png" width="400px"> 
<img src="img/LiveLong_my_cropped.png" width="400px"> 
<img src="img/LiveLong_cropped.png" width="400px"> 
<br/>
<b>Step 6.</b> Manually divide collected images into two folders train and test. So now all folders and annotations should be split between the following two folders. <br/>
\Tensorflow\workspace\images\train<br />
\Tensorflow\workspace\images\test
<br/><br/>
<b>Step 7.</b> Begin training process by opening 2. Training and Detection.ipynb, this notebook will walk you through installing Tensorflow Object Detection, making detections, saving and exporting your model. 
<br /><br/>
<b>Step 8.</b> After installing Tensorflow Object Detection, I began my initial learning with 2000 steps. Here are the results:  <br/><br/>
Loss Matrices:  
<img src="img/loss_matrices.png" width="500px">  
Learning Rate:  
<img src="img/learning_rate.png" width="300px">  
Precision: 77.52%  
<img src="img/precision.png" width="400px">  
Recall: 80%  
<img src="img/recall.png" width="400px">  
<br/><br/>

<b>Good results:</b>  
The recognition performance for "LiveLong", "ThumbsUp", and "ThumbsDown" behave quite consistently well for a training of merely 2000 steps.  
<img src="img/LiveLong_result.png" width="400px">  
<img src="img/ThumbsUp_result.png" width="400px">  

<b>Problematic results:</b>   
The recognition performance for "ThankYou" in sign language is more prone to errors. My explanation for this is that "ThankYou" gesture is special in a way that it requires two hands, the bounding box is much bigger and thus more susceptible to the noise and variation of the input images. I will increase the training steps to 10,000 for the next training, and double the testing input image for better recognition.  
<img src="img/ThankYou_result.png" width="400px">  
<br /> <br/>
