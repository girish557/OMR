What is Optical Mark Recognition (OMR)?

Optical Mark Recognition, or OMR for short, is the process of automatically analyzing human-marked documents and interpreting their results.
The most famous, easily recognizable form of OMR are bubble sheet multiple choice tests

#### Example Input: Filled in bubble sheet exam paper
![alt text](https://github.com/yasersakkaf/OMR/blob/master/optical-mark-recognition/images/test_01.png)

 #### Output: “Green” circle indicates “correct” and “red” circle indicates “incorrect” choice with the score displayed in the top left corner of the image.
 ![alt text](https://github.com/yasersakkaf/OMR/blob/master/optical-mark-recognition/images/exam.jpg)

#### Usage:

Works with `Python3+`
Install the required libraries using the following command:
`pip install -r requirements.txt`

Execute the script using the following command:
`python optical-mark-recognition/test_grader.py -i optical-mark-recognition/images/test_01.png`
