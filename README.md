# Sliding Window Algorithm

[![Documentation](https://docs.rs/opencv/badge.svg)](https://docs.opencv.org/4.x/index.html)

The sliding window method is a popular road line detection method.
You can use it to detect road lines in your self-driving car projects.

## Opencv installation

Make sure the  OpenCV version (3.x or 4.x) is installed on your system

You should write the following line of code in the terminal
```toml
pip install opencv
```

import opencv

```rust
import cv2
```
You should write "cv2" not "opencv"


## What is the Sliding Window Algorithm ? 

The sliding window technique is the selection of a fixed-size subset from a larger data set. 
It can be thought of as looking at a small window from inside a large window. 
Operations are usually performed by sliding this window over the data.
![sliding method](https://logicmojo.com/assets/dist/new_pages/images/slidingwindow1.png)
Here you may notice that the window scrolls over the array. 
One index at a time shifts to the right. If we want to find the sum of the 3 indexes in each section;

1st sub-array = 20 + 10 + 30 = 60

2nd sub-array = 10 + 30 + 40 = 80

3nd sub-array = 30 + 40 + 20 = 90

4nd sub-array = 40 + 20 + 10 =70

To get the current sum of a block of k elements just subtract the first element from the previous block and add the last element of the current block.
This is the sliding window technique. Following this technique, we gonna able to find the sum of maximum sub-array in a single iteration.
```jsunicoderegexp
# setup library
import sys

# O(n * k) solution for finding
# maximum sum of a subarray of size k

INT_MIN = -sys.maxsize - 1


def maxSum(a, n, k):

  
    max_sum = INT_MIN

    # starting with i.
    for i in range(n - k + 1):
        current_sum = 0
        for j in range(k):
            current_sum = current_sum + a[i + j]

        # Update result 
        max_sum = max(current_sum, max_sum)

    return max_sum


# Driver code
a = [20, 10, 30, 40, 20, 10]
k = 2
n = len(a)
print(maxSum(a, n, k))

# This code is contributed by mits
```


## Sliding Window Method with Opencv-Lane Detection
![sliding method](https://pub.mdpi-res.com/sensors/sensors-19-03166/article_deploy/html/images/sensors-19-03166-g013.png?1564757431)
## Project Steps
+ Use the "region of interest" method to get the positions of lines on the road
+ For a clearer view, use the "bird's eye view" method
+ Create a trackbar to apply a mask to the image
+ apply sliding window method



The project steps are explained briefly. Since this project is about how a method is used in image processing, the basic operations of OpenCV are not included.



### OpenCV version support

The following OpenCV versions are supported at the moment:

* 3.4
* 4.x

