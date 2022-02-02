# conda-envs
Collection of conda environments.

Export environment:
```bash
ENVNAME=jupyter
conda env export --from-history -n $ENVNAME | sed '/^prefix:/d' > $ENVNAME.yml && conda env export -n $ENVNAME | sed -ne '/pip:/,$ p' | sed '/^prefix:/d' | sed 's/\=.*//' >> $ENVNAME.yml
```
The command above uses a workaround because `--from-history` does not return pip installed packages.  
Feature request issue: https://github.com/conda/conda/issues/9628

Create/update environment:
```bash
ENVNAME=jupyter
mamba env create -f https://raw.githubusercontent.com/malmans2/conda-envs/main/$ENVNAME.yml --force
```
