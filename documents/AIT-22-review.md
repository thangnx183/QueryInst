1. Clone repo
```
git clone https://github.com/thangnx183/QueryInst.git
```
2.  Setup docker 
```
cd QueryInst
docker build -t query_mmd docker/
nvidia-docker run --name query --gpus all --shm-size=32g -p 7000:7000 -p 7001:7001 -it -v /data/thang/QueryInst/:/mmdetection -v /data/thang/mmdetection/data/:/mmdetection/data  query_mmd
```
3.  Install apex
```
git clone https://github.com/NVIDIA/apex
cd apex
git checkout f3a960f80244cf9e80558ab30f7f7e8cbf03c0a0
python setup.py install --cuda_ext --cpp_ext
```