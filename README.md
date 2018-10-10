# Tensorflow-GPU-1.8.0-cp36-cp36m-macosx_10_13_x86_64_AVX_SSE4.1_SSE4.2

适用于老旧CPU的Tensorflow-GPU-1.8 python 3.6<br />

>环境要求<br />
macOS High Sierra	10.13.6<br />
TensorFlow 1.8<br />
python 3.6.5/6<br />
NVIDIA Web-Drivers 387.10.10.10.40.105<br />
CUDA-Drivers 387.178<br />
CUDA Toolkit 9.1.128<br />
cuDNN 7.0.5<br />
<br />
>~/.bash_profile<br />
export CUDA_HOME=/usr/local/cuda<br />
export DYLD_LIBRARY_PATH="$CUDA_HOME/lib:$CUDA_HOME/extras/CUPTI/lib"<br />
export LD_LIBRARY_PATH=$DYLD_LIBRARY_PATH<br />
export PATH=$DYLD_LIBRARY_PATH:$PATH<br />
export flags="--config=cuda --config=opt"<br />
<br />
>编译环境<br />
Homebrew<br />
bazel	0.10.0<br />
Xcode	8.2<br />
Anaconda3-5.2.0-Python-3.6.5<br />
nccl 2.1.15<br />
<br />
>编译指令<br />
bazel build --config=cuda --config=opt --cxxopt="-D_GLIBCXX_USE_CXX11_ABI=0" --action_env PATH --action_env LD_LIBRARY_PATH --action_env DYLD_LIBRARY_PATH --copt=-march=native --copt=-msse4.1 --copt=-msse4.2 --copt=-mavx //tensorflow/tools/pip_package:build_pip_package<br />
<br />
>如遇-ncclAllReduce<br />
下载_nccl_ops.so文件替换到你的Pyhon安装目录... /Lib/site-packages/tensorflow/contrib/nccl/ops<br />
