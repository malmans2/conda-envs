# conda-envs
Collection of conda environments.

Export environment:
```bash
export ENVNAME=jupyter
conda activate $ENVNAME && conda env export --from-history > $ENVNAME.yml && sed -i '/^prefix:/d' $ENVNAME.yml
```

Create/update environment:
```bash
export ENVNAME=jupyter
mamba env create -f https://raw.githubusercontent.com/malmans2/conda-envs/main/$ENVNAME.yml || mamba env update -f https://raw.githubusercontent.com/malmans2/conda-envs/main/$ENVNAME.yml
```
