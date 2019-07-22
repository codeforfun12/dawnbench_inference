# dawnbench_inference
## Prepare Environment
1. Pull Docker Image nvcr.io/nvidia/tensorrt:19.05-py3 from NGC
2. Clone this repo
## Run inference
Start container of nvcr.io/nvidia/tensorrt:19.05-py3 and run:
```
taskset -c 0,2,4,6,8,10,12,14,16,18 python3 resnet50_inference.py \
                                            --model resnet50_int8.pb \
                                            --data_dir /data/dataset/imagenet_tfrecord/validation/ \
                                            --batch_size 1 \
                                            --intra 1 \
                                            --inter 10
```
