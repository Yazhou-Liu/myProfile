#tensorflow
pip install tensorflow

#horovod
ldconfig /usr/local/cuda-10.0/targets/x86_64-linux/lib/stubs && \
HOROVOD_GPU_ALLREDUCE=NCCL HOROVOD_WITH_TENSORFLOW=1 HOROVOD_WITH_PYTORCH=1 pip install --no-cache-dir horovod && \
ldconfig