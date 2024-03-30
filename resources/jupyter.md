## Jupyter interactive access

**Please remember not to run anything too computationally intensive on the math-alderaan head node.**

On a computer on the campus network, ssh to math-alderaan. Off campus, you can use VPN, or VMware Horizon as described above in [How to log in](#logging-in).

Start a Python environment with jupyter installed, such as in one of our singularity containers, or your own Anaconda installation, and then start jupyter hub or notebook. For example,
  
    singularity shell /storage/singularity/tensorflow.sif

then

    jupyter notebook --no-browser

or (if available)

    jupyter hub --no-browser

You should see instructions with a link similar to

    http://127.0.0.1:8888/?token=cbdfb610423a3e58f6ab9132db0cf00ef02d1b455cb21a13

The port number, here 8888, may be different at different times. 

Open another shell window and type, with 8888 replaced by the actual port number jupyter gave you,

    ssh -L 8888:127.0.0.1:8888 username@math-alderaan

and log in again. You need to keep *both* ssh connections open. On VMware Horizon, you can omit the username.

Open a web browser (Firefox recomended) on the same computer where you run the ssh connections, and go the the link from jupyter above. (Use copy/paste or course.)
  
You should see a Jupyter screen in the browser. You can navigate your file tree, open shell windows, run computation in jupyter notebooks (remember nothing too computationally intensive), etc. 

