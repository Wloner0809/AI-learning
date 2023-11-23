### Q1:

**ImportError: cannot import name 'COMMON_SAFE_ASCII_CHARACTERS' from 'charset_normalizer.constant'  (/home/wloner0809/miniconda3/envs/Grounding4Rec/lib/python3.9/site-packages/charset_normalizer/constant.py)**

## S1:

> pip3 install chardet

### Q2:
**huggingface_hub.utils._validators.HFValidationError: Repo id must use alphanumeric chars or '-', '_', '.', '--' and '..' are forbidden, '-' and '.' cannot start or end the name, max length is 96: 'YOUR_LLAMA_PATH/'.**

### S2:

> 没有写模型的名字导致的

### Q3:

**ImportError: Using `load_in_8bit=True` requires Accelerate: `pip install accelerate` and the latest version of bitsandbytes `pip install -i https://test.pypi.org/simple/ bitsandbytes` or pip install bitsandbytes` **

### S3:

> 更新bitsandbytes包, 安装scipy包(没用)
> Linux上要有英伟达驱动: sudo apt install nvidia-utils-470; sudo apt install nvidia-cuda-toolkit; install nvidia drivers; 装完nvidia驱动之后注意要装一个插件支持触控板手势
>
> 在服务器上是因为tranformers库的版本太高，降级即可

### Q4:

**OSError: We couldn't connect to 'https://huggingface.co' to load this file, couldn't find it in the cached files and it looks like decapoda-research/llama-7b-hf is not the path to a directory containing a file named config.json.**

### S4:

> 在Linux实体机上配置代理:
>
> export https_proxy=http://127.0.0.1:7890
> export http_proxy=http://127.0.0.1:7890
> export all_proxy=socks5://127.0.0.1:7890
> 加入到~/.zshrc中(在使用zsh的情况下), 配置代理
>
> 如何配置服务器的现在还不会……

### Q5:

**ValueError: Some modules are dispatched on the CPU or the disk. Make sure you have enough GPU RAM to fit the quantized model. If you want to dispatch the model on the CPU or the disk while keeping these modules in 32-bit, you need to set `load_in_8bit_fp32_cpu_offload=True` and pass a custom `device_map` to `from_pretrained`. Check https://huggingface.co/docs/transformers/main/en/main_classes/quantization#offload-between-cpu-and-gpu for more details.**