![build](https://github.com/jfcrenshaw/pzflow/workflows/build/badge.svg)
[![codecov](https://codecov.io/gh/jfcrenshaw/pzflow/branch/main/graph/badge.svg?token=qR5cey0swQ)](https://codecov.io/gh/jfcrenshaw/pzflow)

# pzflow
Modeling galaxy redshifts and magnitudes with a normalizing flow

## Development

To work on pzflow, after cloning this repo:
1. Create a virtual environment with Python  
E.g., with conda `conda create -n pzflow`
2. Activate the environment.  
E.g., `conda activate pzflow`  
3. Install pzflow in edit mode with the `dev` flag  
I.e., in the root directory, `pip install -e .[dev]`

If you want to run pzflow on a GPU with CUDA, then you need to follow the GPU-enabled installation instructions for jaxlib [here](https://github.com/google/jax).
You make also need to add the following to your `.bashrc`:
```
# cuda setup
export LD_LIBRARY_PATH=/usr/local/cuda/lib64:$LD_LIBRARY_PATH
export PATH=$PATH:/usr/local/cuda/bin
```

### Sources

The idea to use normalizing flows for photometric redshifts orginated with [Bryce Kalmbach](https://github.com/jbkalmbach).

The jax structure of `pzflow` is largely based on [`jax-flows`](https://github.com/ChrisWaites/jax-flows) by [Chris Waites](https://github.com/ChrisWaites). The implementation of the Neural Spline Coupling is largely based on the [Tensorflow implementation](https://github.com/tensorflow/probability/blob/master/tensorflow_probability/python/bijectors/rational_quadratic_spline.py), with some inspiration from [`nflows`](https://github.com/bayesiains/nflows/).

Neural Spline Flows are based on the following papers:

  > [NICE: Non-linear Independent Components Estimation](https://arxiv.org/abs/1410.8516)\
  > Laurent Dinh, David Krueger, Yoshua Bengio\
  > _arXiv:1410.8516_

  > [Density estimation using Real NVP](https://arxiv.org/abs/1605.08803)\
  > Laurent Dinh, Jascha Sohl-Dickstein, Samy Bengio\
  > _arXiv:1605.08803_

  > [Neural Spline Flows](https://arxiv.org/abs/1906.04032)\
  > Conor Durkan, Artur Bekasov, Iain Murray, George Papamakarios\
  > _arXiv:1906.04032_
