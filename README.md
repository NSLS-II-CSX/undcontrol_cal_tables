# undcontrol_cal_tables
Python code for generating and uploading epu calbration tables to the `undcontrol` IOC

[Original IOC repo](https://github.com/NSLS-II-CSX/undcontrol/)

[Python from updated branch](https://github.com/NSLS-II-CSX/undcontrol/tree/six/python)

## Usage Python tools instructions at 23ID-1 (CSX):

1. Start ipython session (`analysis`) 
2. `%run -i maketable.py`
3. Develop the fits to data and determine paramters fr `set_EPUioc_table()` 
4. if you encounter an issue with "memory" you may need to set the maximum sized array allow for EPICS. I am not sure if ! export.... commnad will work in ipython session. you may need to exit the session to run export EPICS_CA_MAX_ARRAY_BYTES=100000000. 
5. pyepics has not been imported as a fail safe. When ready, you will need to `import epics`


## Example Usage:

testing w/ conversion of first harmonic data to third harmonic data without writing lookup values to the IOC table

    `set_EPUioc_table('20190813_Gap_1stH_Phase28p5.csv', Emin=600, Emax=2000, Epts=22500, third_fm_first=True)`          

writing lookup values to ioc table 6 with default setttings

    `set_EPUioc_table('20190813_Gap_1stH_Phase28p5.csv',22500, 6, True)`