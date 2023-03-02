# Cuda-10.2-Cudnn-8.2.1-TensorRT-8.0.1.6-Install-Ubuntu-18.04
Ubuntu 18.04 Operating system, TensorRt installation on a computer with Nvidia Gtx 1080Ti graphics card


### 1 - Cuda 10.02 Instalition
	wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/cuda-ubuntu1804.pin	
	sudo mv cuda-ubuntu1804.pin /etc/apt/preferences.d/cuda-repository-pin-600	
	wget https://developer.download.nvidia.com/compute/cuda/10.2/Prod/local_installers/cuda-repo-ubuntu1804-10-2-local-10.2.89-440.33.01_1.0-1_amd64.deb
	sudo dpkg -i cuda-repo-ubuntu1804-10-2-local-10.2.89-440.33.01_1.0-1_amd64.deb	
	sudo apt-key add /var/cuda-repo-10-2-local-10.2.89-440.33.01/7fa2af80.pub	
	sudo apt-get update	
	sudo apt-get -y install cuda

	# set PATH for cuda 10.2 installation in bashrc
	if [ -d "/usr/local/cuda-10.2/bin/" ]; then
		export PATH=/usr/local/cuda-10.2/bin${PATH:+:${PATH}}
		export LD_LIBRARY_PATH=/usr/local/cuda-10.2/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
	fi
	
### 1 - Cudnn 8.2.1 Instalition
	sudo dpkg -i libcudnn8_8.2.1.32-1+cuda10.2_amd64.deb
	sudo dpkg -i libcudnn8-dev_8.2.1.32-1+cuda10.2_amd64.deb

### 1 - TensorRT 8.0.1.6 Instalition

	sudo dpkg -i nv-tensorrt-repo-ubuntu1804-cuda10.2-trt8.0.1.6-ga-20210626_1-1_amd64.deb
	sudo apt update
	sudo apt install tensorrt 

	python3 -m pip install numpy
	sudo apt-get install python3-libnvinfer-dev python3-libnvinfer
	
	python3 -m pip install protobuf
	sudo apt-get install uff-converter-tf

	python3 -m pip install numpy onnx==1.4.1
	sudo apt-get install onnx-graphsurgeon
