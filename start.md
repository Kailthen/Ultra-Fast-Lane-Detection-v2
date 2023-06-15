
PY3=python3
PY3D="python3 -m debugpy --wait-for-client --listen 0.0.0.0:5678"

export CUDA_HOME=/usr/local/cuda-11.8
export PATH=${CUDA_HOME}/bin:${PATH}
export LD_LIBRARY_PATH=${CUDA_HOME}/lib64:${CUDA_HOME}/lib64/stubs:${LD_LIBRARY_PATH}
pip install --extra-index-url https://developer.download.nvidia.com/compute/redist --upgrade nvidia-dali-cuda110


${PY3D} perception/lane/Ultra-Fast-Lane-Detection-v2/demo.py perception/lane/Ultra-Fast-Lane-Detection-v2/configs/curvelanes_res34.py \
  --test_model http://172.22.102.122:3923/qianmo/cfzd/Ultra-Fast-Lane-Detection-v2/curvelanes_res34.pth