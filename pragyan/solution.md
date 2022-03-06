### Challenge name: Homework

<img src="https://raw.githubusercontent.com/kabilan1290/WebCTF/master/pragyan/Screenshot_2022-03-06_19-33-51.png">

<p>- This is the only misc challenge in pragyan CTF !  I managed to solve this with the help of my teammates from TamilCTF! cheers to everyone.</p>

<p>- The challenge gave us an link and the description says something about a traitor submitted home work and we have to find him maybe?lets try!</p>

<p>- Visting the link we are presented with the webpage ! hmm nothing interesting.</p>
  <br>
<img src="https://github.com/kabilan1290/WebCTF/blob/master/pragyan/Screenshot_2022-03-06_19-34-19.png">
  
<p>- The webpage has the response as `Sorry the portal is not accepting new assignments at this time`</p>
  
<p>- Source code does not have anything interesting too! so going on with directory brutefoce we found an interesting directory named `response` .</p>
  
  </p>- Upon visiting the endpoint,we get the below response.</p>
  
 <br>
 <img src="https://github.com/kabilan1290/WebCTF/blob/master/pragyan/Screenshot_2022-03-06_19-34-40.png">
 
 <p>- Voilà ! it seems we found the culprit who submitted the assignment! Its dipensu and we have an option to download his assignment.</p>
  
  <p>- Downloading the assignment gave us an zip file named pieces and inside the zip we can see lot of image files.</p>

