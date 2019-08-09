# Cannot import pandas?

My python / jupyter notebook has been working fine since I started using it. That is to say, for
about one year. I encoutered some minor issues, none of which cannot be solved by
uninstall and reinstall packages.
  
I recently learnt how to create a virtual environment in anaconda prompt to avoid
conflicts created by different package versions (might cover it in some other
article since I am also trying to take notes of things I have already learnt). Long
story short, I created an virtual environment to install tensorflow yesterday. 
Everything was fine back then.

Then a problem occured. Today I launched my Jupyter Notebook, only (surprisingly) 
to find that it did not even let me import pandas. That simple code returned the 
following error:

```python
>>> import pandas as pd
ImportError: No module named pandas
```

This is weird. Since I was using my base environment, which contains about all the
packages I need. However, I tried the most straightfoward solution first.

```bash
pip install pandas
```
The above line did not work. Actually, Jupyter told me that all requirements are already 
satisfied. 

I tried several different ways. Upgrade the package, uninstall and reinstall, try 
to install a different version, try pip install and conda install, switch to a 
different virtual environment, use Jupyter Notebook with / without Anaconda, ..., 
all methods did not work. And I was pretty sure that the pandas package was in the 
site-packages folder, and the folder was added to the system 'PATH'.

Finally I decided to directly using python without using Jupyter Notebook (that is,
directly type in *python* using the Anaconda Prompt). Guess what, this time I 
successfully impoted pandas.

That is rather weird. I also noticed that when I directly ran python through 
Anaconda prompt, my python version is 3.6.9, and in my Jupyter Notebook my python 
version is 3.7.3.

```python
>>> from platform import python_version
>>> print(python_version())
```

This really pointed me to the right direction. After wandering on the internet for 
a while googling how to change the python directory Jupyter Notebook used, I found 
the following command

```bash
sys.executable
```

I still do not know how now, but it looked like the Jupyter Notebook was pointing 
to one of my test virtual environment, which barely have any packages. On the
other hand, since my current virtual environment does have the packages I need,
Jupyter decided there was no need to install those packages.

Then there was just one simple question left: let Jupyter know the right python to
use. No need to mention the rest googling in details. But the following steps saved
my life finally.

- Type in 
```bash
jupyter kernelspec list
```
to find the available kernel's location.

- Entered the location and find the `kernel.json` file. Change the first argument
  of `argv` to where your preferred python's location.

It is as simple as that. 

## Things yet to learn

- [ ] It has been a unresolved pain for me I admit, that my Jupyter notebook never allows me to switch kernels once I opend a jupyter notebook file. Though based on some of today's research, maybe I need to register the kernels first?

- [ ] I upgraded python in my base environment, but it is currently still version 3.6.9 instead of 3.7.3. Gotta find a way to make that right!


