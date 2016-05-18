# style-transfer

## Requirements

 - Python >= 2.7
 - CUDA >= 6.5 (highly recommended)
 - Caffe

CUDA will enable GPU-based computation in Caffe.

## Download

To run the code, you must have Caffe installed and the appropriate Python bindings in your `PYTHONPATH` environment variable. Detailed installation instructions for Caffe can be found [here](http://caffe.berkeleyvision.org/installation.html).

All of the necessary code is contained in the file `style.py`. You can try it on your own style and content image by running the following command:

```
python style.py -s <style_image> -c <content_image> -m <model_name> -g 0 -n 1000 -o <output_path>
```

The protobufs which come with the vanilla Caffe install aren't quite compatible with this code - working ones have already been added to this repository as a result of this. To get the pretrained models, simply run:

```
bash scripts/download_models.sh
```

This will grab the convnet models from the links provided in the [Caffe Model Zoo](https://github.com/BVLC/caffe/wiki/Model-Zoo). You may also specify the exact model you'd like to download by running:

```
bash scripts/download_models.sh <model_name>
```

Here, `<model_name>` must be one of `vgg16`, `vgg19`, `googlenet`, or `caffenet`.
