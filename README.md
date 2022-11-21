# Inference Server for truck detection 
Inference server for truck detection (waste reduction project) at Code for Israel

**Python Classes**
* Config - All configuration variables needed for the inference server (Cameras’ urls, AWS credentials, directories names, etc...).
* VideoCapture - 
Initiate access to camera - Start the connection to camera (GET 200 response code instead of 403) by using Selenium.
Read frames - Reading frames from camera, on a thread, by a given frame rate.
* Scraper - Saving a frame with image name format (camera’s ID, serial number, date and time) into a local input folder.
* Model - Using the model’s weights to infer images. Saving output images and labels (of exist) into a local output folder.
* Files
A logger instance for alerts logging and other metadata logging.
Creating input and output folders.
Deleting local folders and images.
Uploading and downloading files from a s3 bucket.

Inference time on local server:
Scraping and saving a frame: 1 - 14 ms
Inferring and saving outputs (images + labels): 180-190 ms
Total time: around 200 ms (0.2 seconds).