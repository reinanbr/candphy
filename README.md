
<h1 align='center'>Candphy</h1>
<p align='center'>
<img height='275px' width='260px' src='https://raw.githubusercontent.com/perseu912/candphy/main/img/Candphy.png' style='height:450; witdh:200'>
 <br/>
<a href="https://twitter.com/BezerraReinan"><img title="Autor" src="https://img.shields.io/badge/Autor-reinan_br-blue.svg?style=for-the-badge&logo=twitter"></a>
<br/>
<p align='center'>
<!-- github dados -->
<a href='https://python.org'><img src='https://img.shields.io/github/pipenv/locked/python-version/perseu912/candphy'></a>
<a href='#'><img src='https://img.shields.io/github/languages/code-size/perseu912/candphy'></a>
<a href='#'><img src='https://img.shields.io/github/commit-activity/y/perseu912/candphy'></a><br/>
<a href='https://pypi.org/project/candphy/'><img src='https://img.shields.io/pypi/v/candphy'></a>
<a href='#'><img alt="PyPI - Downloads" src="https://img.shields.io/pypi/dm/candphy"></a>
</p>
</p>
<p align='center'> <b>Library from Python3.+ for development,  works, researches, and more other works and projects on the more points of physic  📈📊</b></p>

## First time
<br/>

<!--### About
This lib find make a resume of the important's tools and mechanism presnets in the area's from the phyisics world, as the computational physical, mechanical sthatistics, waves and micro-waves, signals of radio, quantum, astronomy, study of scientifcal data, eletronic, eletrodynamics, modern physics, mechanical analithics, and other's -->


## Installation:
<hr/>

this lib is found on the site of packages for python the <a href='https://pypi.org'>pypi</a> and on the site that is a repository for the codes and softwares with licenses from majority business of the word, the <a href='https://github.com'>github</a>.
### Linux
```bash
$ pip3 install candphy -U
```
### Windows
```cmd
C\:> python3 -m pip3 install candphy -U
```
<br/><br/>
#  Examples
<hr/>

# Waves

## Signal Radio 
(need the RTL-SDR driver)

```py
from candphy.waves import get_signal_radio as gr
from candphy.waves import plot_signal as ps
from candphy.logs import show_console 

#showing the logs from work lib
show_console(False)

#getting signals samples from 
#the around of the frequency 99.9Mhz
#(raio from space get is of 3.1Mhz)
s = gr(99.9)

print('signal radio: \n',s)

#plotting this signal radio
ps(s)
'''

```
output:
```sh
Detached kernel driver
Found Rafael Micro R820T tuner
[R82XX] PLL not locked!
Exact sample rate is: 3100000.092387 Hz
Reattached kernel driver
signal radio:
{'freq_center': 99900000.0, 'freq_rate': 3100000.0, 'bytes': 1024, 'order': 1000000.0, 'size_signal': 262144, 'samples': array([-0.00392157-0.00392157j, -0.00392157-0.00392157j,
       -0.00392157-0.00392157j, ...,  0.1372549 -0.0745098j ,
       -0.10588235+0.15294118j, -0.16078431+0.10588235j]), 'type': 'signal_radio'}    
```
<img height='270px' src='https://raw.githubusercontent.com/perseu912/candphy/main/tests/signal_radio_plot.png' >

<hr>

## Gravitational Waves

### working data

getting the data:
```py
from candphy.waves import gwaves

gw = gwaves.Gwaves_Data()
pd_gw = gw.data_gw
```
showing the DataFrame:
```py
#printing the DataFrame of Gravitational Waves
print('type:',type(pd_gw))
print(pd_gw)
```

output:
```sh
type: <class 'pandas.core.frame.DataFrame'>
 
               Name Version           Release           GPS              Mass 1 (M☉)  ...                  Redshift False Alarm Rate (yr-1)          Final Mass (M☉)                     Date                                               Link
0   GW200322_091133      v1  GWTC-3-confident  1.268904e+09       34.0  34  +48  -18  ...   0.6  0.60  +0.84  -0.30              140.0  140       53.0  53  +38  -26  2020-03-22T09:12:10.300  https://www.gw-openscience.org/eventapi/html/G...
1   GW200316_215756      v1  GWTC-3-confident  1.268431e+09  13.1  13.1  +10.2  -2.9  ...  0.22  0.22  +0.08  -0.08       1e-05  ≤  1.0e-05   20.2  20.2  +7.4  -1.9  2020-03-16T21:58:33.100  https://www.gw-openscience.org/eventapi/html/G...
2   GW200311_115853      v1  GWTC-3-confident  1.267963e+09   34.2  34.2  +6.4  -3.8  ...  0.23  0.23  +0.05  -0.07       1e-05  ≤  1.0e-05   59.0  59.0  +4.8  -3.9  2020-03-11T11:59:30.300  https://www.gw-openscience.org/eventapi/html/G...
3   GW200308_173609      v1  GWTC-3-confident  1.267724e+09  36.4  36.4  +11.2  -9.6  ...  0.83  0.83  +0.32  -0.35                2.4  2.4  47.4  47.4  +11.1  -7.7  2020-03-08T17:36:46.700  https://www.gw-openscience.org/eventapi/html/G...
4   GW200306_093714      v1  GWTC-3-confident  1.267523e+09  28.3  28.3  +17.1  -7.7  ...  0.38  0.38  +0.24  -0.18                24.0  24  41.7  41.7  +12.3  -6.9  2020-03-06T09:37:51.100  https://www.gw-openscience.org/eventapi/html/G...
..              ...     ...               ...           ...                      ...  ...                       ...                     ...                      ...                      ...                                                ...
88         GW170608      v3  GWTC-1-confident  1.180922e+09   11.0  11.0  +5.5  -1.7  ...  0.07  0.07  +0.02  -0.02       1e-07  ≤  1.0e-07   17.8  17.8  +3.4  -0.7  2017-06-08T02:01:53.500  https://www.gw-openscience.org/eventapi/html/G...
89         GW170104      v2  GWTC-1-confident  1.167560e+09   30.8  30.8  +7.3  -5.6  ...   0.2  0.20  +0.08  -0.08       1e-07  ≤  1.0e-07   48.9  48.9  +5.1  -4.0  2017-01-04T10:12:35.600  https://www.gw-openscience.org/eventapi/html/G...
90         GW151226      v2  GWTC-1-confident  1.135136e+09   13.7  13.7  +8.8  -3.2  ...  0.09  0.09  +0.04  -0.04       1e-07  ≤  1.0e-07   20.5  20.5  +6.4  -1.5  2015-12-26T03:39:29.600  https://www.gw-openscience.org/eventapi/html/G...
91         GW151012      v3  GWTC-1-confident  1.128679e+09  23.2  23.2  +14.9  -5.5  ...  0.21  0.21  +0.09  -0.09        0.00792  7.9e-03  35.6  35.6  +10.8  -3.8  2015-10-12T09:55:19.400  https://www.gw-openscience.org/eventapi/html/G...
92         GW150914      v3  GWTC-1-confident  1.126259e+09   35.6  35.6  +4.7  -3.1  ...  0.09  0.09  +0.03  -0.03       1e-07  ≤  1.0e-07   63.1  63.1  +3.4  -3.0  2015-09-14T09:51:21.400  https://www.gw-openscience.org/eventapi/html/G...

[93 rows x 17 columns]
```

the columns in the data:
```py
print('columns:')
print(pd_gw.columns)
```

output:
```sh
columns:
Index(['Name', 'Version', 'Release', 'GPS', 'Mass 1 (M☉)', 'Mass 2 (M☉)',
       'Network SNR', 'Distance (Mpc)', 'χeff', 'Total Mass (M☉)',
       'Chirp Mass (M☉)', 'Detector Frame Chirp Mass (M☉)', 'Redshift',
       'False Alarm Rate (yr-1)', 'Final Mass (M☉)', 'Date', 'Link'],
      dtype='object')
```
### plotting signal
```py
from candphy.waves import gwaves

#instanciamint the data of graviatitonal waves
gw = gwaves.Gwaves_Data()

#getting the name of last gwave from data
gw_name = gw.data_gw['Name'][0]

#getting the gwave of this name
gwave = gw.get_gwave(name_gwave=gw_name)

#ploting the gwave signal
plt_signal = gw.plot_gwave(gwave)

plt_signal.savefig(f'signal_{gw_name}.png',dpi=900)
plt_signal.show()
```
output:
<img height='400px' width='800px' src='https://raw.githubusercontent.com/perseu912/candphy/main/tests/gwave/signal_GW200322_091133.png' >



<img src="https://reysofts.com.br/engine/libs/save_table_access_libs.php?lib_name=candphy">