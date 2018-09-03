# K-Means-Clustering-using-Octave-Ex-7
My solutions to Stanford Machine Learning Course

<h2>Implementation of the K-means Clustering and Principal Component Analysis</h2>

The K-means algorithm is a method to automatically cluster similar data examples together. 

Given a training set 
{ x(1), x(2) .... x(i) } (where x(i) ∈ R), and want to group the data into a few cohesive clusters.

The intuition behind K-means is an iterative procedure that starts by guessing the initial centroids, and then refines this guess by repeatedly assigning
examples to their closest centroids and then recomputing the centroids based on the assignments.

The initial assignments of centroids for the example dataset in ex7.m 

```
  %Initialize the centroids to be random examples

  %Randomly re-order the indices of examples
  randidx = randperm(size(X, 1));

  %Take the first K examples as centroids
  centroids = X(randidx(1:K), :);
```

The code above randomly permutes the indices of the examples (using randperm). Then, it selects the first K examples based on the random
permutation of the indices. This allows the examples to be selected at random without the risk of selecting the same example twice.

<h3>Image compression with K-means</h3>

In a straightforward 24-bit color representation of an image, 2 each pixel is represented as three 8-bit unsigned integers (ranging from 0 to 255) that specify the red, green and blue intensity values. This encoding is often refered to as the RGB encoding.

![](https://raw.githubusercontent.com/Radiowala/K-Means-Clustering-using-Octave-Ex-7/master/ex7/bird_small.png)

It is possible to represent (compress) the photo in an efficient way. Specifically, you only need to store the RGB values of the 16 selected colors, and for each pixel in the image you now need to only store the index of the color at that location (where only 4 bits are necessary to represent 16 possibilities).
![](https://raw.githubusercontent.com/Radiowala/K-Means-Clustering-using-Octave-Ex-7/master/ex7/ex7.jpg)

If your image is very large, then K-means can take a long time to run. 
