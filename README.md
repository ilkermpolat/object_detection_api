# object_detection_api
# ANACONDA
```bash
# create new environment
conda create --name py36-tf2 python=3.6

# activate your environment before installation or running your scripts 
conda activate py36-tf2
```
# Steps
https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/tf2.md

1.Download https://github.com/tensorflow/models

2.Unzip models

3.Download Protoc https://github.com/protocolbuffers/protobuf/releases on Windows

4.run this on terminal but in this way models/research

```bash
cd models/research
#you need to write your protoc file path
protoc object_detection/protos/*.proto --python_out=.
```
now we will use tensor model:
```bash
cd models/research
python setup.py build
python setup.py install
```
object detection api:
```bash
pip install tensorflow-gpu==2.2.0
```
```bash
# CPU only support (slow)
pip install tensorflow==2.2.0
```

also these are needed library:
```bash
pip install pillow
pip install lxml
pip install jupyter
pip install matplotlib
```
download:
```bash
#this repo
http://download.tensorflow.org/models/object_detection/tf2/20200711/efficientdet_d0_coco17_tpu-32.tar.gz
# unzip it
```

also run these command:
```bash
python detect_objects.py
python detect_objects.py --model_path models/efficientdet_d0_coco17_tpu-32/saved_model --path_to_labelmap models/mscoco_label_map.pbtxt --images_dir data/samples/images/
python detect_objects.py --video_input --class_ids "1" --threshold 0.3  --video_path data/samples/pedestrian_test.mp4 --model_path models/efficientdet_d0_coco17_tpu-32/saved_model --path_to_labelmap models/mscoco_label_map.pbtxt
```
