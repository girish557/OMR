### Implementation by Dr Adrian Rosebrock: Bubble sheet multiple choice scanner and test grader using OMR, Python and OpenCV
  
Find details in the link below

https://www.pyimagesearch.com/2016/10/03/bubble-sheet-multiple-choice-scanner-and-test-grader-using-omr-python-and-opencv/


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

#### Extending the OMR and test scanner
In the current implementation, we (naively) assume that a reader has filled in one and only one bubble per question row.

What happens if a user does not bubble in an answer for a particular question?
What if the user is nefarious and marks multiple bubbles as “correct” in the same row?
Luckily, detecting and handling of these issues isn’t terribly challenging, we just need to insert a bit of logic.

For issue #1, if a reader chooses not to bubble in an answer for a particular row, then we can place a minimum threshold.

If this value is sufficiently large, then we can mark the bubble as “filled in”. Conversely, if total  is too small, then we can skip that particular bubble. If at the end of the row there are no bubbles with sufficiently large threshold counts, we can mark the question as “skipped” by the test taker.

A similar set of steps can be applied to issue #2, where a user marks multiple bubbles as correct for a single question:

Again, all we need to do is apply our thresholding and count step, this time keeping track if there are multiple bubbles that have a total  that exceeds some pre-defined value. If so, we can invalidate the question and mark the question as incorrect.
