# Simple Image Blurring Algorithm

A very simple and probably not efficient parallel algorithm for blurring an image, using the library **multiprocessing** of Python 3.6.

To run the algorithm, call the function **blur_image_from_disk**, set as parameters the input name and the output name of the image, as also the number of processes to use.

For the **blurring effect**, to find the value of a new pixel, we calculate the **average score** of the RGB values of the four neighbors and that of the old pixel. The effect may not be visible enough in large images. For it to be visible, more neighbors should be taken into account.

**Parallelization** is implemented by using a pool of processes and mapping to them areas of the image (specifically rows of pixels) to be calculated seperately.

The algorithm was tested on a processor with 4 cores for different numbers of processes and 5 images with different sizes. The results are shown below at the image.

![results](https://user-images.githubusercontent.com/22857719/36328453-d61d7688-136a-11e8-9066-5d1a68589625.png)

Using parallelization, the algorithm sped up about 2 times with 4 processes. The factor would be even greater, but the construction of the final image is made on the main process and demands important time.
