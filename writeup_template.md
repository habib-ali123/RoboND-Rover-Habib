## Project: Search and Sample Return
### Writeup Template: You can use this file as a template for your writeup if you want to submit it as a markdown file, but feel free to use some other method and submit a pdf if you prefer.

---


**The goals / steps of this project are the following:**  

**Training / Calibration**  

* Download the simulator and take data in "Training Mode"
* Test out the functions in the Jupyter Notebook provided
* Add functions to detect obstacles and samples of interest (golden rocks)
* Fill in the `process_image()` function with the appropriate image processing steps (perspective transform, color threshold etc.) to get from raw images to a map.  The `output_image` you create in this step should demonstrate that your mapping pipeline works.
* Use `moviepy` to process the images in your saved dataset with the `process_image()` function.  Include the video you produce as part of your submission.

**Autonomous Navigation / Mapping**

* Fill in the `perception_step()` function within the `perception.py` script with the appropriate image processing functions to create a map and update `Rover()` data (similar to what you did with `process_image()` in the notebook). 
* Fill in the `decision_step()` function within the `decision.py` script with conditional statements that take into consideration the outputs of the `perception_step()` in deciding how to issue throttle, brake and steering commands. 
* Iterate on your perception and decision function until your rover does a reasonable (need to define metric) job of navigating and mapping.  

[//]: # (Image References)

[image1]: ./misc/rover_image.jpg
[image2]: ./calibration_images/example_grid1.jpg
[image3]: ./calibration_images/example_rock1.jpg 

## [Rubric](https://review.udacity.com/#!/rubrics/916/view) Points
### Here I will consider the rubric points individually and describe how I addressed each point in my implementation.  

---
### Writeup / README

#### 1. Provide a Writeup / README that includes all the rubric points and how you addressed each one.  You can submit your writeup as markdown or pdf.  

The simulator was downloaded for Windows from the link given in the course. Then the course on Anaconda and Jupyter Notebook was taken and completed.
With the end of the Anaconda and Jupyter Notebook course, the environment was set up.
The codes in the Jupyter Notebook were experimented with. 
process_image() was tried again and again, but was not successful. Help from Udacity live help, made me understand what mistakes I am committing.
Then relevant changes were made and with a few iterations the process_image() worked, and the video was saved.
Similar to the process_image() was the implementation of the perception_step().
decision_step() didn't need much modification. I did a trial and error with different settings, but just a minor change worked fine.



### Notebook Analysis
#### 1. Run the functions provided in the notebook on test images (first with the test data provided, next on data you have recorded). Add/modify functions to allow for color selection of obstacles and rock samples.


![alt text][C:\Users\Habib Ali\Pictures\RoboND Screenshots\Project 1 Images\Coordinate Transform]

#### 1. Populate the `process_image()` function with the appropriate analysis steps to map pixels identifying navigable terrain, obstacles and rock samples into a worldmap.  Run `process_image()` on your test data using the `moviepy` functions provided to create video output of your result. 


![alt text][C:\Users\Habib Ali\Pictures\RoboND Screenshots\Project 1 Images\Video Output]
### Autonomous Navigation and Mapping

#### 1. Fill in the `perception_step()` (at the bottom of the `perception.py` script) and `decision_step()` (in `decision.py`) functions in the autonomous mapping scripts and an explanation is provided in the writeup of how and why these functions were modified as they were.
Initially the function rotate_pix(), translate_pix() were modified to include the formula of translation and rotation.
Then a variable image was assigned to Rover.img
The destination and source were set based on the calibration image.
Perspective transform was then applied.
Then color threshold to identify navigable terrain/obstacles/rock samples was made
Then Rover.vision_image was updated
Then map image pixel values were converted to rover-centric coords
Then rover-centric pixel values were converted to world coordinates. The world_size was taken as 200. 
Rover worldmap was updated. 
Rover-centric cordinates were converted to polar cordinates inorder to give directions to navigate the rover.

#### 2. Launching in autonomous mode your rover can navigate and map autonomously.  Explain your results and how you might improve them in your writeup.  
The rover was launched in autonomous mode. It did map a fair amount with good fidelity.
The test data provided is used. I implemented the thresholding based on values used in the notebook. They seemed to work good enough. 
The rover was able to detect all sample rocks.
Adding the pick up manuever would be an improvement.
Experimenting more with the thresholding values would certainly improve the fidelity.

**Note: running the simulator with different choices of resolution and graphics quality may produce different results, particularly on different machines!  Make a note of your simulator settings (resolution and graphics quality set on launch) and frames per second (FPS output to terminal by `drive_rover.py`) in your writeup when you submit the project so your reviewer can reproduce your results.**

Here I'll talk about the approach I took, what techniques I used, what worked and why, where the pipeline might fail and how I might improve it if I were going to pursue this project further.  



![alt text][C:\Users\Habib Ali\Pictures\RoboND Screenshots\Project 1 Images\Project1]


