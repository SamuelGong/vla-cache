# Guidance

> [This](./README.md) is the original README of the project.

## 1. Preparation

```bash
conda create -n vla python=3.10 -y
conda activate vla
```

First, install things related to OpenVLA:

```bash
# suppose that you are at $HOME

git clone https://github.com/openvla/openvla.git
cd openvla
pip install -e .
```

Next, install things related to LIBERO

```bash
# suppose that you are at $HOME

git clone https://github.com/SamuelGong/LIBERO# IMPORTANT: Not the original https://github.com/Lifelong-Robot-Learning/LIBERO.git
cd LIBERO
pip install .  # IMPORTANT: Not pip install -e .
```

Then, back to OpenVLA:
```bash
# suppose that you are at $HOME
cd openvla
pip install -r experiments/robot/libero/libero_requirements.txt
```

Next, install a customized version of transformers:

```bash
# suppose that you are at $HOME
git clone https://github.com/siyuhsu/transformers.git
cd transformers
git checkout vla-cache-openvla
pip install -e .
```

Finally, install vla-cache itself:
```bash
# suppose that you are at $HOME
git clone git@github.com:SamuelGong/vla-cache.git # IMPORTANT: not git@github.com:siyuhsu/vla-cache.git
cd vla-cache
cd src/openvla
pip install -e .
```

Also, download the necessary model for inference:
```bash
```bash
# suppose that you are at $HOME
cd vla-cache
cd src/openvla
python vla_cache_scripts/download_model_local.py \
  --model_id openvla/openvla-7b-finetuned-libero-spatial
```

## 2. Run

```bash
# with cache
python experiments/robot/libero/run_libero_eval.py \
  --pretrained_checkpoint checkpoints/openvla-7b-finetuned-libero-spatial \
  --task_suite_name libero_spatial \
  --use_vla_cache True
  
# or no cache
python experiments/robot/libero/run_libero_eval.py \
  --pretrained_checkpoint checkpoints/openvla-7b-finetuned-libero-spatial \
  --task_suite_name libero_spatial \
  --use_vla_cache False
  
# Both may take a bit long
```

