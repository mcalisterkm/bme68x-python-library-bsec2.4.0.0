# bme68x-python-library-bsec2.4.0.0
Update of the PI3G python wrapper for the Bosch Sensortec BME688 and BSEC 2.4.0.0.

***Please see the readme in the code directory for installation and getting started instructions.***

__Update 11/01/2024.__

Be aware that raspbian __bookworm__ (aka Debian 12) has made changes to how it expects Python to be used, that impact the bme68x package.
There are over 800 debian python-* packages that are managed using apt/dpkg and considered to be site-wide/core packages.
Python packages managed by pip working with Python Index (PYPI) are to be installed in a virtual environment (i.e. pip for local packages and apt for site-wide/core packages), as described here: 
[https://www.raspberrypi.com/documentation/computers/os.html#python-on-raspberry-pi](https://www.raspberrypi.com/documentation/computers/os.html#python-on-raspberry-pi)
```
To create a venv with the built in env package, with access to system-wide packages (change /path/to/env to your desired location)
$ python -m venv --system-site-packages /path/to/env

To activate an environment:
$ source /path/to/env/bin/activate
(env) $

To quit
(env) $ deactivate
$
```

All python/pip commands run in an virtual environment (venv) will act locally, avoiding any impact on the site-wide/core packages.

This will impact on any shell scripts, and the venv documentation [https://docs.python.org/3/library/venv.html](https://docs.python.org/3/library/venv.html) offers the the following advice:
```
In a shell script you don’t specifically need to activate a virtual environment.
You can just specify the full path to that environment’s Python interpreter when invoking Python.
Furthermore, all scripts installed in the environment should be runnable without activating it.
In order to achieve this, a python script installed into virtual environments has a “shebang” line which points to the environment’s Python interpreter, i.e. #!/<path-to-venv>/bin/python.
A shell script just needs to run python with the full environment path: <path-to-venv>/bin/python <commad.py>
```
