# python-build-definitions

Custom [`python-build`](https://github.com/pyenv/pyenv/blob/master/plugins/python-build/README.md) (`pyenv/plugins/python-build`) definitions.


## No GIL, Experimental JIT `3.13.0b1+`

### Install

```
# Clone
git clone https://github.com/yyolk/python-build-definitions
cd python-build-definitions
# Install
pyenv install ./3.13.0b1+
```

### Test

```
pyenv virtualenv 3.13.0b1+ 3.13-nogil-jit
pyenv activate $_
python -Xgil=0 -c'import sysconfig,sys;print(sysconfig.get_config_var("JIT_DEPS")and"Hello, JIT!",not sys.flags.gil and"Hello, NOGIL!")'
```
