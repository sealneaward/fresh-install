# fresh-install
Step by step instructions to install all deep learning dependencies on machine on fresh install.

### Pre
- Verify GCC is working

```
gcc --version
```

- Update headers

```
sudo apt-get install linux-headers-$(uname -r)
```

### CUDA Install
- Download [CUDA 8.0](https://developer.nvidia.com/compute/cuda/8.0/prod/local_installers/cuda-repo-ubuntu1404-8-0-local_8.0.44-1_amd64-deb)

- Unpack and install package

```
sudo dpkg -i cuda-repo-ubuntu1404-8-0-local_8.0.44-1_amd64.deb
sudo apt-get update
sudo apt-get install cuda
```

### CUDA Setup

- Add this to  `~/.bashrc` profile

```bash
export PATH=/usr/local/cuda-8.0/bin${PATH:+:${PATH}}
export LD_LIBRARY_PATH=/usr/local/cuda-8.0/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
```

- Source the profile

```
source ~/.bashrc
```

- Restart your computer

- Compile the make file to test device

```
cd /usr/local/cuda/samples/
sudo make
cd bin/x86_64/linux/release
sudo ./deviceQuery
```

###  CUDNN Setup

- Download [CUDNN](https://developer.nvidia.com/cudnn)

- Extract the folder

- Copy contents into CUDA folderS

```
sudo cp lib64/* /usr/local/cuda-8.0/lib64
sudo cp include/* /usr/local/cuda-8.0/include
```
