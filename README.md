# Guidance

> [This](./README.md) is the original README of the project.

## Preparation

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
cd openvla
pip install -r experiments/robot/libero/libero_requirements.txt
```

