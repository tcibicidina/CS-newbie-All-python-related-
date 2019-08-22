# The followup for the 'ModuleImportError.md' - Solve the problem!

Problem 1, as listed at the end of the file, can be solved like below:

```
$ conda activate cenv

(myenv)$ conda install ipykernel

(myenv)$ ipython kernel install --user --name=tfcpu

(myenv($ conda deactivate
```

The above code register your conda environment so now Jupyter Notebook can switch kernel to 'tfcpu'.
Now only one problem to go!
