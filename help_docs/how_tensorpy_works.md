### How TensorPy Works (Detailed Explanation)

Once TensorPy is installed with **[install.sh](https://github.com/TensorPy/TensorPy/blob/master/install.sh)**, a command called ``classify`` is added to your command line, which takes a URL as input. When called, TensorPy determines if that URL links to an image or a web image. If it's an image, TensorPy downloads the image to a new folder called ``downloads_folder``. From there, the image is converted to a JPEG. Then, the image is fed to the local **[tensorpy/classify_image.py](https://github.com/TensorPy/TensorPy/blob/master/tensorpy/classify_image.py)** which tells TensorFlow to use the ImageNet Inception database to classify the image and print out the result.

If the ``classify`` command is called with a web page as input, then all images on that page (up to the limit defined in **[tensorpy/settings.py](https://github.com/TensorPy/TensorPy/blob/master/tensorpy/settings.py)**) will get downloaded to ``downloads_folder``, where TensorPy does the work listed above per image, with the exception of images smaller than the minimum size defined in tensorpy/settings.py (currently 50x50 pixels). Images that are too small will be skipped because results have shown that icons and other tiny images get extremely poor classification results.

You can also use TensorPy to classify images from within a Python program. (See the example to learn how: **[examples/test_python_classify.py](https://github.com/TensorPy/TensorPy/blob/master/examples/test_python_classify.py)**)

If you make any changes to **[tensorpy/settings.py](https://github.com/TensorPy/TensorPy/blob/master/tensorpy/settings.py)**, you will need to rerun ``python setup.py install`` for your changes to take effect.
