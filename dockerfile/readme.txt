#tensorflow
pip install tensorflow

#horovod
ldconfig /usr/local/cuda-10.0/targets/x86_64-linux/lib/stubs && \
HOROVOD_GPU_ALLREDUCE=NCCL HOROVOD_WITH_TENSORFLOW=1 HOROVOD_WITH_PYTORCH=1 pip install --no-cache-dir horovod && \
ldconfig

#build docker image
docker build -t yazhou/devel:cuda10.0-ubuntu18.04-horovod -f  myDockerfile .

#build docker container 
nvidia-docker run -it --privileged --name feedads_ocpc -p 8008:8008 -p 6666:6666  -v /home:/home -v /data:/data  liuyazhou/devel:ubuntu18.04-cuda10.0-openmpi4.0