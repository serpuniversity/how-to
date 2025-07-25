# How To Setup Jupyter Notebook in VS Code (w/ Virtual Env & Kernels)

Figuring out how to how setup a `jupyter notebook` is pretty easy - you just open your terminal, install jupyter & run `jupyter notebook`.

But figuring out how to do it inside of VS CODE was not very intuitive (at least not for me, as I am kind of a newb with python).

But learning from newbies is the best thing you can do because, as you will find out, we are so “dumb” that our processes need to be so detailed that a monkey could run them, so it’s unlikely we will leave out some critical step that just ruins your whole day.

So here is my process, compiled from digging, reading, and banging my head against a wall until i nailed it.

Let’s get to it.

# Watch the video 👇

<a href="https://www.youtube.com/watch?v=-j6y-5t37os" target="_blank">
<img src="https://raw.githubusercontent.com/devinschumacher/uploads/refs/heads/main/images/how-to-setup-run-jupyter-notebooks-in-vs-code-w-virtual-environment-kernels-remote-local.jpg" width="700px">
</a>


## Prerequisites

### Install jupyter

First, you obviously need jupyter installed.

If you haven’t done that, then do that first.

Not going to cover that here because i don’t know what system you’re on, or package manager you use.

Onwards.

### VS Code jupyter extensions

i don’t know enough about extensions to recommend “the perfect setup”, but here’s what I have installed.

so if you feel like just being a lemming and following my lead, here ya go:

1.  Jupyter (extension ID: `ms-toolsai.jupyter`)
2.  Jupyter Notebook Renderers (extension ID: `ms-toolsai.jupyter-renderers`)
3.  Jupyter Keymap (extension ID: `ms-toolsai.jupyter-keymap`)
4.  VS Code Jupyter Notebook Previewer (extension ID: `jithurjacob.nbpreviewer`)
* * *

## Process

### Step 1. Create project folder

First you need a project folder, so create that.

You can use Finder, Terminal, or do it in VS Code.

I like doing it without the GUI because “practice makes progress”.

Tweet that. You’ll look clever & sophisticated.

And then get back to work because you aren’t here to be dickin’ around on social media.

Create your project folder:

```
# syntax
mkdir <folder name>

# example
mkdir myproject
```

### Step 2. Create, activate & select your virtual environment

Navigate to / open your project folder and create a virtual environment inside of it:

```
# syntax
python3 -m venv <virtual environment name>

# example
# that would create a virtual environment named 'myenv'
python3 -m venv myenv
```

Now activate the virtual environment and when VS CODE prompts you to set it as default for the project, hit yes.

```
# syntax
source <virtual environment name>/bin/activate

# example
source myenv/bin/activate
```

### Step 3. Install `ipykernel`

Now that your virtual environment is activated, install `ipykernel`

```
pip3 install ipykernel
```

### Step 4. Create new kernel

Now you can create a new kernel to be used for your project:

```
# syntax
python3 -m ipykernel install --user --name=<projectname>

# example
# That would create a kernel named 'myproject'
python3 -m ipykernel install --user --name=myproject
```

### Step 5. Start jupyter

Now you can start Jupyter. I do it from the VS Code terminal.

```
jupyter notebook
```

**If you did this right you should see something like this in your terminal:
**

```bash
To access the notebook, open this file in a browser: 

file:///Users//Library/Jupyter/runtime/nbserver-15044-open.html or copy and paste one of these URLs: [https://localhost:8889/?token=f1ae910e56381c26a62cfb18f83241076bd11d84f7e8e36e](https://localhost:8889/?token=f1ae910e56381c26a62cfb18f83241076bd11d84f7e8e36e) [https://127.0.0.1:8889/?token=f1ae910e56381c26a62cfb18f83241076bd11d84f7e8e36e](https://127.0.0.1:8889/?token=f1ae910e56381c26a62cfb18f83241076bd11d84f7e8e36e)
```

### Step 6. Select kernel for project

Now you can assign the kernel to the project in VS CODE.

#### Step 6.1: Create a new Jupyter notebook

-   Open the VSCODE search bar: `cmd+shift+p`
-   Type in & choose: “Create: New Jupyter Notebook”

#### Step 6.2: Choose your kernel

-   Open the VSCODE search bar: `cmd+shift+p`
-   Type in & choose: “Notebook: Select Notebook Kernel”

At the bottom of your VS Code window, you should see “Jupyter Server: Local”

![](https://devinschumacher.com/images/jupyter-server-local-vs-code-1024x665.png)

Click that, and a dropdown will appear.

Now, you will simply enter one of the URLs you received when you ran the Jupyter command back in Step 5:

```
To access the notebook, open this file in a browser:

file:///Users/<your username>/Library/Jupyter/runtime/nbserver-15044-open.html

Or copy and paste one of these URLs:
        
http://localhost:8889/?token=f1ae910e56381c26a62cfb18f83241076bd11d84f7e8e36e

or

https://127.0.0.1:8889/?token=f1ae910e56381c26a62cfb18f83241076bd11d84f7e8e36e
```

