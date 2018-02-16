# Simple Image Blurring Algorithm

A very simple and probably not efficient parallel algorithm for blurring an image.

For the **blurring effect**, to find the value of a new pixel, we calculate the **average score** of the RGB values of the four neighbors and that of the old pixel. The effect may not be visible enough in large images. For it to be visible, more neighbors should be taken into account.

**Parallelization** is implemented by using a pool of processes and mapping to them areas of the image (specifically rows of pixels) to be calculated seperately.
