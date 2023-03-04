# Pedestrian Detection and Tracking

* Image Name: newimage

* Image ID: b7a4e48c4385c94341355a29c9726e029546604cd1e7135c512c14d3b155023a


* Steps for the Containerization:

  * First open the docker desktop in the background.
  * Next create a working folder which contains all the necessary files for the containerization.
  * The structure of the working folder is:
     * Folder Name(e.g. Demo) with the docker file
     * Inside Demo folder:
       * Fine_tune_model (containing the checkpoint and pipeline.config files)
       * Images (Image Test Dataset)
       * Tfrecords (Containing the train and test record files and label_map files)
       * Inference.py file
  * Create the docker file using the type nul > Dockerfile
  * Copy the dependencies for the dockerfile from [here](https://gitlab.iotiot.in/interns-projects/pedestrian-detection-and-tracking/-/blob/Containerization_of_Inference_Model/Dockerfile)
  * Setup this docker file in the working folder along with the demo folder.

  * Create the image which copies all the content from the demo folder to the model folder in the image using the following command.
     *  **docker build -t imagename .**

  * After creating the docker image, we start the docker container using the following command:
     *  **docker run -ti imagename /bin/bash**

  * After this create one output directory using the (mkdir output) command which will be used for the output image storage.
 
  * Navigate to the inference.py file and execute it using the following command:
     *  **python3 inference.py**

  * After running the inference.py output images are generated and they are stored in the output directory which was created earlier.
 
  * After that copy the output images from the container to the host machine, open the new terminal and use the following command:
     *  **docker cp {container_id}:output {path_in_host}**
 

  * The images can be seen in the output folder in the ({path_in_host}) directory in the host machine.

