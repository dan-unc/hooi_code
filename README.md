# hooi_code

## About
This repository is adapted from  [Hiroshi Watanabe's implementation](https://github.com/kaityo256/hooi_sample) of HOOI, for the purpose of deliverying a presentation and demonstrating Higher Order Orthogonal Interation of Tensors (Multi-linear Subspace Learning) in the National Student TechTalk Series (Session - 11) organized by the Computer Society of India (Trivandrum Chapter).


## Summary
HOOI is a data-decomposition technique used for Multi-linear Subsapce Learning. It can be used as a pre-processing technique to reduce the dimensionality of data in higher order spaces. Further details can be found in the presentation attached. For the goal of a simple demonstration, the code performs a low rank approximation of a given image.


## Usage

```
$ python hooi_sample.py <your-imagefilename.extension> <ratio>
```

The 1st argument is input file. The 2nd argument determines how many ranks will be used for approximation. Let us consider a image with the size of (w,h). Then the width will be truncated to be `int(w*ratio)` and the height to be `int(h*ratio)`.

When the value of ratio is not specified, then 0.2 will be used as the default value.

## Demo

```
Ratio = 0.01
Performing HOOI
0.17573546857671554
0.13808886214733368
0.13564254487225905
0.13520919673683202
0.13506667982075782
0.13500505493072593
0.13497461610984957
0.13495809353214824
0.13494837866795126
0.1349422721238217
Saved as Lenna_hooi.png

```

The numbers denotes the residual. Suppose X is the original tensor and XP is the approximated tensor. Then residula r is defined by r = |X - XP|/|X|, where |X| denotes the Frobenius norm of X. 

## Insights from varying the compression ratio
HOOI has been implemented with minor changes in the syntax of the code. As one can observe, the changes in the compression ratio which given as the second argument makes a lot of difference in the output image. The difference in the output images can be observed at r = 0.6, 0.2, as well as 0.01.
