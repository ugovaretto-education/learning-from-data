
# Add Virtual Environment to Jupyter Notebook

Jupyter Notebook makes sure that the IPython kernel is available, but you have to manually add a 
kernel with a different version of Python or a virtual environment. First, make sure your 
environment is activated with conda activate myenv. Next, install ipykernel which 
provides the IPython kernel for Jupyter:


## Create virtual environment

```
python -m venv myenv
```

After you have created your virtual environment, you can activate the virtual environment with:

```
source myenv/bin/activate
```

## Connfigure Jupyter kernel

```
pip install --user ipykernel
```

Next you can add your virtual environment to Jupyter by typing:

```
python -m ipykernel install --user --name=myenv
```
This should print the following:

Installed kernelspec myenv in /home/user/.local/share/jupyter/kernels/myenv

In this folder you will find a kernel.json file which should look the following way
if you did everything correctly:


```
{
 "argv": [
  "/home/user/anaconda3/envs/myenv/bin/python",
  "-m",
  "ipykernel_launcher",
  "-f",
  "{connection_file}"
 ],
 "display_name": "myenv",
 "language": "python"
}
```
That’s all to it! Now you are able to choose the conda environment as a kernel in Jupyter.
Here is what that would look like in JupyterLab:

Jupyter Virtual Environment

# Remove Virtual Environment from Jupyter Notebook

After you deleted your virtual environment, you’ll want to remove it also from Jupyter.
Let’s first see which kernels are available. You can list them with:


```
jupyter kernelspec list
```

This should return something like:

```
Available kernels:
  myenv      /home/user/.local/share/jupyter/kernels/myenv
  python3    /usr/local/share/jupyter/kernels/python3
```

Now, to uninstall the kernel, you can type:

```
jupyter kernelspec uninstall myenv
```
