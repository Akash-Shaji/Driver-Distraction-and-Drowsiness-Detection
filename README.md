# Driver-Distraction-and-Drowsiness-Detection

Requirements

tensorflow version 2.10.1
cv2 version 4.7.0
numpy version 1.23.5
folium version 0.14.0
keras version 2.10.0
tensorflow_addons version 0.19.0
tf-models-official 2.11.5
pandas version 1.5.3
dash version 2.9.2 

Instructions to run Driver Distraction System


The driver distraction folder contains 1 ipnyb notebook and a driver_distraction_demo subfolder.
The 3mdad_training_proof notebook is only to view the notebook that achieved 80% test accuracy(finetuned using random erase based on our previous notebook which had only basic augmentations). The model had to re-implement a few packages (videoframe generators and its utils) as the source package was broken. In such cases the code was copied as such into the jupyter notebook and necessary changes were made.

For running the demo of the driver distraction model please keep in mind all the dependencies mentioned above especially the installation of tensorflow-addons and tf-models-official and opencv-python (might require uninstallation of opencv-headless if it shows function not built error on your system)
Also the driver_distraction demo must be run locally (no kaggle or colab).




driver_distraction_demo 

This method does not require you to download the full dataset. It includes a small subset we used for demo purposes.

Setting Up
In the setup function definition- you will have to change the path of the 'checkpoint.restore()' to your file path. Please do not include the '.index' suffix while loading the ckpt files.
While running the setup() check if the message "couldn't find/load checkpoint" appears. This means that there is some error in the path of the ckpt file. This causes the model to either crash or run using random weights leading to poor accuracy.
If the warning was "some weights are missing" or "expect partial"  ignore it.
In the play_demo function definition change the path to wherever you have loaded the demonew folder.
Even in the last cell of this notebook change the path to wherever you have loaded the demonew folder.
Ignore the dummy path given in the checkpoint_callback() in the setup function definition

Note: The watermark on the demo videos were generated while merging the clips using a third party application to create the demo. It has nothing to do with the model predictions. 

Common Error: “prediction_p referenced before assignment or prediction_p not defined” This error comes when the model is unable to load any videos. Kindly recheck the path given in the play_demo function definition as well as the path given in the last cell of the notebook.



Procedure

Open Driver_distraction notebook
Run the import cell as well as the function definitions
Then run the setup() function. This may take about 1-2 mins.
Then run the play_demo function.



Instructions for dashboard 

Setting Up and Running
Run the index.html file using the liveserver extension of vscode. The index.html file will open on your browser. The address bar will give you the local host port on your device. Copy that to the last line of the dash_board.py file (in the webbrowser.open_new_tab())
Then run the dash_board.py file. In the terminal it will display where the app is running. Then copy that path and paste in the iframe tag in the index.html file. Then relaunch the index.html file. You should be able to view the webpage and the dashboard (if the populated dashboard doesnt load immediately, click on the drop down on the top left of the dash-board and choose any option). 

In a real life scenario, cameras placed near the B pillar of the car will monitor the driver’s actions and an alarm would sound when the driver is distracted for longer durations. The outputs of the model are also sent to a dashboard for documentation and monitoring purposes. 

In this prototype, the deep learning model for detecting driver distraction was showcased. The dashboard is populated using a demo csv file.




Dataset References


Imen Jegham, Anouar Ben Khalifa, Ihsen Alouani, Mohamed Ali Mahjoub, A novel public dataset for multimodal multiview and multispectral driver distraction analysis: 3MDAD, Signal Processing: Image Communication, Volume 88, October 2020, 115966, DOI: https://doi.org/10.1016/j.image.2020.115960. 
 

Imen Jegham, Anouar Ben Khalifa, Ihsen ALOUANI, Mohamed Ali MAHJOUB, MDAD : A Multimodal and Multiview in-Vehicle Driver Action Dataset, In: Vento M., Percannella G. (eds) Computer Analysis of Images and Patterns. CAIP 2019. Lecture Notes in Computer Science, vol 11679. Springer, Cham, pp. 518-529.

In this project we have used a subset of the 3MDAD dataset.
