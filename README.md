# conda-envs
Collection of conda environments

Export environment:
```bash
export ENVTOEXPORT=jupyter
conda activate $ENVTOEXPORT && conda env export --from-history > $ENVTOEXPORT.yml && sed -i '/^prefix:/d' $ENVTOEXPORT.yml
```
