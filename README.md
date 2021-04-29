# conda-envs
Collection of conda environments.

Export environment:
```bash
ENVNAME=jupyter
conda env export --from-history -n $ENVNAME | sed '/^prefix:/d' > $ENVNAME.yml && conda env export -n $ENVNAME | sed -ne '/pip:/,$ p' | sed '/^prefix:/d' | sed 's/\=.*//' >> $ENVNAME.yml
```
This is a workaround because `--from-history` does not return pip installed packages.

Create/update environment:
```bash
ENVNAME=jupyter
mamba env create -f https://raw.githubusercontent.com/malmans2/conda-envs/main/$ENVNAME.yml || mamba env update -f https://raw.githubusercontent.com/malmans2/conda-envs/main/$ENVNAME.yml
```
