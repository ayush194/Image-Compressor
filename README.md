# Image-Compressor

A simple python command line app to compress images. It can be used to seamlessly compress and decompress images in .png, .bmp, .tiff, .git, .exif and other image formats. Does not have .jpg support as they are already highly compressed. It uses the K-Means Algorithm to form clusters which is representative of its mean color. It then uses these mean colors to decompress the image back.
A sample outcome for this program with number of clusters set to 16
![Original Image](https://raw.githubusercontent.com/ayush194/Image-Compressor/master/flower1.png)

![Decompressed Image](https://raw.githubusercontent.com/ayush194/Image-Compressor/master/flower1_decompressed.png)

## Dependencies
For OSX :
You should have Python 3.0 or greater to run this program. Check this
```bash
python3 --version
```
Python libraries [numpy](http://www.numpy.org) and [scikit-image](https://scikit-image.org/) should installed. If not, depending on which ones are not present, run
```bash
brew install python3, numpy, skimage
```

## Instructions
cd into the directory where you cloned the repository.
```bash
cd ./path-to-repository/
tar -xf Image-Compressor-master.zip
cd Image-Compressor-master
```

### Compress
run the program img_compress.py
```bash
python3 img_compress.py
```
To compress an image, simply enter the image name and the number of clusters. The more clusters, the lesser the compression will be and the better the reconstructed image will be at the cost of a greater running time. Remember that compressing may take a while although decompression will be quick.
```bash
image-to-compress.png 16
```
end the program
```bash
exit()
```
You will see two new files 'image-to-compress_clusters.png' and 'image-to-compress_means.npy'.
These contain the data to reconstruct the original image.

### Decompress
To reconstruct the original image, you need to have the 'image-to-compress_clusters.png' and 'image-to-compress_means.npy' compressed data files in the same folder.
Now run img_decompress.py
```bash
image-to-compress.png
```
end the program
```bash
exit()
```
The final decompressed image will be created.

