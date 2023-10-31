# BME68X and BSEC2.4 for Python by pi3g

This is a temporary clone of the PI3G repository updated to support the BOSCH BSEC 2.4.0.0 library (BSEC2.4.0.0_Generic_Release_23012023) only. 
BOSCH Sensortec at BSEC 2.4.0.0 have introduced support for multiple sensors which this python wrapper does not support, also this release will not import config/status files from earlier releases they need to be re-created. 
For more information on the library please see the original PI3G repository [here] (https://github.com/pi3g/bme68x-python-library) which works with the 2.0.6.1 release of the BOSCH BSEC Library. Once PI3G extend their support to the later BOSCH releases I expect this repo will be removed.


### How to install the extension with BSEC
- clone [this repo](https://github.com/pi3g/bme68x-python-library) to a desired location on you hard drive
- download the licensed BSEC2 library [from BOSCH](https://www.bosch-sensortec.com/software-tools/software/bme688-software/)<br>
- unzip it into the *bme68x-python-library-main* folder, next to this *README.md*
- open a new terminal window inside the *bme68x-python-library-main* folder
Note: Only the BSEC2.4.0.0_Generic_Release_23012023.zip (January 2023) is supported.
```bash
sudo python3 setup.py install
```
or to install under venv use
```bash
path/to/venv/bin/python3 setup.py install
```
### How to use the extension
- to import in Python
```python
import bme68x
```
or
```python
from bme68x import BME68X
```
- see PythonDocumentation.md for reference
- to test the installation make sure you connected your BME68X sensor via I2C
- run the following code in a Python3 interpreter
```python
from bme68x import BME68X

# Replace I2C_ADDR with the I2C address of your sensor
# Either 0x76 (default for BME680) or 0x77 (default for BME688)
bme68x = BME68X(I2C_ADDR, 0)
bme68x.set_heatr_conf(1, 320, 100, 1)
data = bme68x.get_data()
```

The data collection collection tool bmerawdata.py has multiple issues: segment violations, data output format is no longer compliant to the BOSCH specification, and the file naming is incorrect (model generation fails).   Data collection from a single sensor is limited, however the abiltiy to run AI models is working - See my (mcalisterkm) repository "teach-your-pi-to-sniff-with-bme688: for a tutorial and all the data needed to try this out.  

#### For documentation and examples please refer to our [GitHub](https://github.com/pi3g/bme68x-python-library)<br>
#### For feedback, bug reports or functionality requests send an E-mail to nathan@pi3g.com<br>


![pi3g logo](https://pi3g.com/wp-content/uploads/2015/06/pi3g-150px-only-transparent-e1622110450400.png)<br>
pi3g is an official approved Raspberry Pi reseller, and a Coral Machine Learning Platform (from Google) distribution partner.<br>
We take care of all your Raspberry Pi and Coral related hardware and software development, sourcing, accessory and consulting needs!<br>
Check out [our homepage](https://pi3g.com) and file your personal software or hardware request.<br>
Also visit [our shop](https://buyzero.de).<br>
