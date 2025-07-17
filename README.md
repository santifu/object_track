
# Real-time Object Tracking Documentation

This repository houses a project for the Digital Tectonics class, focused on exploring and developing new design workflows based on algorithmic thinking and the integration of cutting-edge technologies.

![alt text](/files/image.png)


Our inspiration for this research comes from the compelling project "Form Follows Life" on Hackster.io:

[Form Follows Life - Hackster.io](https://www.hackster.io/group-2/form-follows-life-b5a7a0)

Our goal is to push this concept further: we aim to extract movement patterns from detected objects in video streams and use this data as a dynamic input to influence a generative 3D algorithm.

Imagine capturing the motion of a person or an object, and that movement not only becomes visible but also serves as the "seed" or "energy" that sculpts and transforms a three-dimensional geometry.

## Workflow and Key Steps

This project integrates real-time object detection and 3D manipulation with Blender to achieve its goals.

Here's how to follow our workflow:

### 1\. Blender Preparation

-   Download Blender: If you don't have it yet, download the latest version of Blender from their official website: [blender.org/download](https://www.google.com/search?q=https://www.blender.org/download/)
    

### 2\. Generating Movement Patterns (Live Camera or Video Upload)

This application allows you to generate movement patterns using either your webcam in real-time or by uploading a video file.

-   Access the Tracking Tool: Open your browser and go to our object tracking web application: [santifu.github.io/object\_track/](https://www.google.com/search?q=https://santifu.github.io/object_track/)
    
-   Choose Your Input (Camera or Video):
    
    -   Using a Webcam (Live): If you wish to use your webcam, ensure you grant camera permissions when prompted by your browser. The live video feed will appear automatically.
        
    -   Uploading a Video: Click the "Upload Video File" button and select a video from your computer or mobile device. Make sure the video starts playing and the status message indicates "Video reproduciéndose. Iniciando detección..." (Video playing. Starting detection...).
        
-   Select Objects to Track: Once the application detects objects, a list of checkboxes will appear with the labels of the detected objects (e.g., "person", "car", "chair"). Select the object(s) you wish to track by checking their respective box.
    
-   Generate Pattern: As the video (or live feed) plays, you'll see white trajectory points drawing on the canvas, representing the movement pattern of your selected objects. Adjust the "Trajectory Point Size" slider to change the size of these points.
    
-   Save the Pattern (PNG): When you're satisfied with the generated pattern, click the "Save Trajectory (PNG)" button. This will save the image containing the generated trajectory.
    

### 3\. Integration into Blender (Geometry Nodes)

-   Open Blender: Launch Blender.
    
-   Go to the UV Editing Tab: At the top of the Blender window, click on the "UV Editing" tab. We don't need a complex UV map, just an image viewer.
    
-   Open the Pattern Image: In the UV editor (usually on the left), go to `Image > Open` (or use the folder icon) and load the `.png` image you saved in the previous step.
    
-   Go to the Geometry Nodes Tab: At the top, click on the "Geometry Nodes" tab.
    
-   Load the Image into a Node:
    
    -   Ensure you have a node tree (if not, select your object and click "New").
        
    -   Press `Shift + A` to add a new node. Search for "Image Texture" and add it to your node tree.
        
    -   In the "Image Texture" node, click the folder icon to load the same `.png` image you used previously.
        
-   Connect and Experiment:
    
    -   Connect the output of the "Image Texture" node (typically the color or alpha) to a parameter within your generative algorithm in Geometry Nodes. This could influence extrusion, deformation, point density, or other properties.
        
    -   Play with Parameters: Experiment with the parameters of your Geometry Nodes tree. The trajectory image will now be influencing the 3D form.
        
    -   Switch between Algorithms: We've designed different generative algorithms (e.g., "lines", "pattern", "cubes") within our Geometry Nodes setup. Modify the connections or values to switch between these algorithms and observe how the same movement pattern translates into diverse 3D expressions.
        

We hope you enjoy exploring this fascinating intersection of real-world movement and algorithmic 3D design!