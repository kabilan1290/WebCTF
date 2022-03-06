### Challenge name: Homework

<img src="https://raw.githubusercontent.com/kabilan1290/WebCTF/master/pragyan/Screenshot_2022-03-06_19-33-51.png">

<p>- This is the only misc challenge in pragyan CTF !  I managed to solve this with the help of my teammates from TamilCTF! cheers to everyone.</p>

<p>- The challenge gave us an link and the description says something about a traitor submitted home work and we have to find him maybe?lets try!</p>

<p>- Visting the link we are presented with the webpage ! hmm nothing interesting.</p>
  <br>
<img src="https://github.com/kabilan1290/WebCTF/blob/master/pragyan/Screenshot_2022-03-06_19-34-19.png">
  
<p>- The webpage has the response as `Sorry the portal is not accepting new assignments at this time`</p>
  
<p>- Source code does not have anything interesting too! so going on with directory brutefoce we found an interesting directory named `response`.</p>
  
</p>- Upon visiting the endpoint,we get the below response.</p>
  
<br>
<img src="https://github.com/kabilan1290/WebCTF/blob/master/pragyan/Screenshot_2022-03-06_19-34-40.png">
 
<p>- Voilà ! it seems we found the culprit who submitted the assignment! Its dipensu and we have an option to download his assignment.</p>
  
<p>- Downloading the assignment gave us an zip file named pieces and inside the zip we can see lot of image files.</p>
  
<img src="https://github.com/kabilan1290/WebCTF/blob/master/pragyan/Screenshot_2022-03-06_19-37-39.png">
  
<p>- Seems a image was separated into multiple parts and i thought of merging them together btw is it sorted in a order? and there was 90 separate images.</p>
  
<p>- After a initial analysis on the image we were to find there are coordinates on each image metadata !</p>

<img src="https://github.com/kabilan1290/WebCTF/blob/master/pragyan/coordinate.png">

<p>- The total 90 images contains X coordinate ranges from 1 to 9 and y coordinates ranges from 1 to 10 but the images were not sorted!</p>
  
<p>- We can merge the images but first we need to sort them according to the coordinates and better i decided to change the images name according to the coordinates</p>

<p>- I wrote a script to name the images with coordinates and i attached the script below.[Added comments for explanation]</p>

```
import os
#Directory which has images
a = os.listdir()

# Command = exifool -G -Artist filename
# The above command is used for extracting only particular information from exiftool data and we only interested in coordinates.
command = "exiftool -G -Artist "
for i in a:
    x=os.popen('exiftool -G -Artist '+i).read()
    # we getting the cordinates in the variable x
    x =x.replace(' ', '')
    # removing whitespaces
    x =x[20:]
    
    os.system("cp "+i+" "+x)
    #renaming the images with coordinate names
    os.system("rm "+i)
    #removing the orginal file
  ```
  
  <p>- With the above script,we get the beautiful output as follows.
  
  <img src="https://github.com/kabilan1290/WebCTF/blob/master/pragyan/sorted.png">
  
  <p>- We got the result and to our plus,our images comes sorted and we can easily merge them with x and y coordinates.
