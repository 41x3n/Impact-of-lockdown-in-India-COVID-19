```python
import numpy as np 
import pandas as pd
```


```python
#https://www.kaggle.com/sudalairajkumar/covid19-in-india
df = pd.read_csv('covid_19_india.csv')
```


```python
df = df.drop(columns=['ConfirmedIndianNational', 'ConfirmedForeignNational'])
```


```python
#lc stands for latest count
lc = df.loc[df['Date'] == "18/04/20"]
lc
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Sno</th>
      <th>Date</th>
      <th>Time</th>
      <th>State/UnionTerritory</th>
      <th>Cured</th>
      <th>Deaths</th>
      <th>Confirmed</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1058</th>
      <td>1059</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Andaman and Nicobar Islands</td>
      <td>11</td>
      <td>0</td>
      <td>12</td>
    </tr>
    <tr>
      <th>1059</th>
      <td>1060</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Andhra Pradesh</td>
      <td>42</td>
      <td>15</td>
      <td>603</td>
    </tr>
    <tr>
      <th>1060</th>
      <td>1061</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Arunachal Pradesh</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1061</th>
      <td>1062</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Assam</td>
      <td>9</td>
      <td>1</td>
      <td>35</td>
    </tr>
    <tr>
      <th>1062</th>
      <td>1063</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Bihar</td>
      <td>37</td>
      <td>2</td>
      <td>85</td>
    </tr>
    <tr>
      <th>1063</th>
      <td>1064</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Chandigarh</td>
      <td>9</td>
      <td>0</td>
      <td>21</td>
    </tr>
    <tr>
      <th>1064</th>
      <td>1065</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Chhattisgarh</td>
      <td>24</td>
      <td>0</td>
      <td>36</td>
    </tr>
    <tr>
      <th>1065</th>
      <td>1066</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Delhi</td>
      <td>72</td>
      <td>42</td>
      <td>1707</td>
    </tr>
    <tr>
      <th>1066</th>
      <td>1067</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Goa</td>
      <td>6</td>
      <td>0</td>
      <td>7</td>
    </tr>
    <tr>
      <th>1067</th>
      <td>1068</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Gujarat</td>
      <td>88</td>
      <td>48</td>
      <td>1272</td>
    </tr>
    <tr>
      <th>1068</th>
      <td>1069</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Haryana</td>
      <td>43</td>
      <td>3</td>
      <td>225</td>
    </tr>
    <tr>
      <th>1069</th>
      <td>1070</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Himachal Pradesh</td>
      <td>16</td>
      <td>1</td>
      <td>38</td>
    </tr>
    <tr>
      <th>1070</th>
      <td>1071</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Jammu and Kashmir</td>
      <td>42</td>
      <td>5</td>
      <td>328</td>
    </tr>
    <tr>
      <th>1071</th>
      <td>1072</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Jharkhand</td>
      <td>0</td>
      <td>2</td>
      <td>33</td>
    </tr>
    <tr>
      <th>1072</th>
      <td>1073</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Karnataka</td>
      <td>92</td>
      <td>13</td>
      <td>371</td>
    </tr>
    <tr>
      <th>1073</th>
      <td>1074</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Kerala</td>
      <td>255</td>
      <td>3</td>
      <td>396</td>
    </tr>
    <tr>
      <th>1074</th>
      <td>1075</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Ladakh</td>
      <td>14</td>
      <td>0</td>
      <td>18</td>
    </tr>
    <tr>
      <th>1075</th>
      <td>1076</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Madhya Pradesh</td>
      <td>69</td>
      <td>69</td>
      <td>1355</td>
    </tr>
    <tr>
      <th>1076</th>
      <td>1077</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Maharashtra</td>
      <td>331</td>
      <td>201</td>
      <td>3323</td>
    </tr>
    <tr>
      <th>1077</th>
      <td>1078</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Manipur</td>
      <td>1</td>
      <td>0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1078</th>
      <td>1079</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Meghalaya</td>
      <td>0</td>
      <td>1</td>
      <td>11</td>
    </tr>
    <tr>
      <th>1079</th>
      <td>1080</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Mizoram</td>
      <td>0</td>
      <td>0</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1080</th>
      <td>1081</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Nagaland#</td>
      <td>0</td>
      <td>0</td>
      <td>0</td>
    </tr>
    <tr>
      <th>1081</th>
      <td>1082</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Odisha</td>
      <td>21</td>
      <td>1</td>
      <td>60</td>
    </tr>
    <tr>
      <th>1082</th>
      <td>1083</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Puducherry</td>
      <td>3</td>
      <td>0</td>
      <td>7</td>
    </tr>
    <tr>
      <th>1083</th>
      <td>1084</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Punjab</td>
      <td>27</td>
      <td>13</td>
      <td>202</td>
    </tr>
    <tr>
      <th>1084</th>
      <td>1085</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Rajasthan</td>
      <td>183</td>
      <td>11</td>
      <td>1229</td>
    </tr>
    <tr>
      <th>1085</th>
      <td>1086</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Tamil Nadu</td>
      <td>283</td>
      <td>15</td>
      <td>1323</td>
    </tr>
    <tr>
      <th>1086</th>
      <td>1087</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Telengana</td>
      <td>186</td>
      <td>18</td>
      <td>791</td>
    </tr>
    <tr>
      <th>1087</th>
      <td>1088</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Tripura</td>
      <td>1</td>
      <td>0</td>
      <td>2</td>
    </tr>
    <tr>
      <th>1088</th>
      <td>1089</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Uttarakhand</td>
      <td>9</td>
      <td>0</td>
      <td>42</td>
    </tr>
    <tr>
      <th>1089</th>
      <td>1090</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>Uttar Pradesh</td>
      <td>86</td>
      <td>14</td>
      <td>969</td>
    </tr>
    <tr>
      <th>1090</th>
      <td>1091</td>
      <td>18/04/20</td>
      <td>5:00 PM</td>
      <td>West Bengal</td>
      <td>55</td>
      <td>10</td>
      <td>287</td>
    </tr>
  </tbody>
</table>
</div>




```python
total_cases = lc['Confirmed'].sum()
total_cured = lc['Cured'].sum()
total_death = lc['Deaths'].sum()
total_active = total_cases - total_cured - total_death
```


```python
print(f"Total Confirmed Cases - {total_cases}")
print(f"Total Active Cases - {total_active}")
print(f"Total Deaths - {total_death}")
print(f"Total Cured - {total_cured}")
```

    Total Confirmed Cases - 14792
    Total Active Cases - 12289
    Total Deaths - 488
    Total Cured - 2015
    


```python
#https://www.kaggle.com/nxrprime/styling-data-frames-covid-19-vs-conferences
lc.style.background_gradient(cmap='Reds',subset=['Cured', 'Deaths', 'Confirmed'])
```




<style  type="text/css" >
    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row0_col4 {
            background-color:  #fff0e8;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row0_col5 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row0_col6 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row1_col4 {
            background-color:  #fee0d2;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row1_col5 {
            background-color:  #fee8de;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row1_col6 {
            background-color:  #fdd0bc;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row2_col4 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row2_col5 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row2_col6 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row3_col4 {
            background-color:  #fff1ea;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row3_col5 {
            background-color:  #fff4ef;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row3_col6 {
            background-color:  #fff4ee;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row4_col4 {
            background-color:  #fee3d6;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row4_col5 {
            background-color:  #fff4ee;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row4_col6 {
            background-color:  #fff1ea;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row5_col4 {
            background-color:  #fff1ea;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row5_col5 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row5_col6 {
            background-color:  #fff4ef;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row6_col4 {
            background-color:  #fee9df;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row6_col5 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row6_col6 {
            background-color:  #fff4ee;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row7_col4 {
            background-color:  #fdc5ae;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row7_col5 {
            background-color:  #fdc7b2;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row7_col6 {
            background-color:  #fa6547;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row8_col4 {
            background-color:  #fff2ec;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row8_col5 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row8_col6 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row9_col4 {
            background-color:  #fcb69b;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row9_col5 {
            background-color:  #fcbea5;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row9_col6 {
            background-color:  #fc9070;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row10_col4 {
            background-color:  #fedfd0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row10_col5 {
            background-color:  #fff3ed;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row10_col6 {
            background-color:  #feeae0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row11_col4 {
            background-color:  #ffede5;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row11_col5 {
            background-color:  #fff4ef;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row11_col6 {
            background-color:  #fff4ee;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row12_col4 {
            background-color:  #fee0d2;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row12_col5 {
            background-color:  #fff1ea;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row12_col6 {
            background-color:  #fee5d8;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row13_col4 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row13_col5 {
            background-color:  #fff4ee;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row13_col6 {
            background-color:  #fff4ee;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row14_col4 {
            background-color:  #fcb296;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row14_col5 {
            background-color:  #feeae1;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row14_col6 {
            background-color:  #fee3d6;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row15_col4 {
            background-color:  #c4161c;
            color:  #f1f1f1;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row15_col5 {
            background-color:  #fff3ed;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row15_col6 {
            background-color:  #fee1d4;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row16_col4 {
            background-color:  #ffeee7;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row16_col5 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row16_col6 {
            background-color:  #fff4ef;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row17_col4 {
            background-color:  #fdc7b2;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row17_col5 {
            background-color:  #fc9d7f;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row17_col6 {
            background-color:  #fc8767;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row18_col4 {
            background-color:  #67000d;
            color:  #f1f1f1;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row18_col5 {
            background-color:  #67000d;
            color:  #f1f1f1;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row18_col6 {
            background-color:  #67000d;
            color:  #f1f1f1;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row19_col4 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row19_col5 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row19_col6 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row20_col4 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row20_col5 {
            background-color:  #fff4ef;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row20_col6 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row21_col4 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row21_col5 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row21_col6 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row22_col4 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row22_col5 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row22_col6 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row23_col4 {
            background-color:  #feeae1;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row23_col5 {
            background-color:  #fff4ef;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row23_col6 {
            background-color:  #fff2ec;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row24_col4 {
            background-color:  #fff4ee;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row24_col5 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row24_col6 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row25_col4 {
            background-color:  #fee8dd;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row25_col5 {
            background-color:  #feeae1;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row25_col6 {
            background-color:  #ffebe2;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row26_col4 {
            background-color:  #f6563d;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row26_col5 {
            background-color:  #ffece3;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row26_col6 {
            background-color:  #fc9474;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row27_col4 {
            background-color:  #ab1016;
            color:  #f1f1f1;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row27_col5 {
            background-color:  #fee8de;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row27_col6 {
            background-color:  #fc8b6b;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row28_col4 {
            background-color:  #f5533b;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row28_col5 {
            background-color:  #fee7db;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row28_col6 {
            background-color:  #fcbfa7;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row29_col4 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row29_col5 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row29_col6 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row30_col4 {
            background-color:  #fff1ea;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row30_col5 {
            background-color:  #fff5f0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row30_col6 {
            background-color:  #fff3ed;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row31_col4 {
            background-color:  #fcb89e;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row31_col5 {
            background-color:  #feeae0;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row31_col6 {
            background-color:  #fcae92;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row32_col4 {
            background-color:  #fdd4c2;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row32_col5 {
            background-color:  #ffede5;
            color:  #000000;
        }    #T_dfcb67c0_822f_11ea_9459_847beb43ac05row32_col6 {
            background-color:  #fee7db;
            color:  #000000;
        }</style><table id="T_dfcb67c0_822f_11ea_9459_847beb43ac05" ><thead>    <tr>        <th class="blank level0" ></th>        <th class="col_heading level0 col0" >Sno</th>        <th class="col_heading level0 col1" >Date</th>        <th class="col_heading level0 col2" >Time</th>        <th class="col_heading level0 col3" >State/UnionTerritory</th>        <th class="col_heading level0 col4" >Cured</th>        <th class="col_heading level0 col5" >Deaths</th>        <th class="col_heading level0 col6" >Confirmed</th>    </tr></thead><tbody>
                <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row0" class="row_heading level0 row0" >1058</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row0_col0" class="data row0 col0" >1059</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row0_col1" class="data row0 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row0_col2" class="data row0 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row0_col3" class="data row0 col3" >Andaman and Nicobar Islands</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row0_col4" class="data row0 col4" >11</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row0_col5" class="data row0 col5" >0</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row0_col6" class="data row0 col6" >12</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row1" class="row_heading level0 row1" >1059</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row1_col0" class="data row1 col0" >1060</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row1_col1" class="data row1 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row1_col2" class="data row1 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row1_col3" class="data row1 col3" >Andhra Pradesh</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row1_col4" class="data row1 col4" >42</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row1_col5" class="data row1 col5" >15</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row1_col6" class="data row1 col6" >603</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row2" class="row_heading level0 row2" >1060</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row2_col0" class="data row2 col0" >1061</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row2_col1" class="data row2 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row2_col2" class="data row2 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row2_col3" class="data row2 col3" >Arunachal Pradesh</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row2_col4" class="data row2 col4" >0</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row2_col5" class="data row2 col5" >0</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row2_col6" class="data row2 col6" >1</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row3" class="row_heading level0 row3" >1061</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row3_col0" class="data row3 col0" >1062</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row3_col1" class="data row3 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row3_col2" class="data row3 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row3_col3" class="data row3 col3" >Assam</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row3_col4" class="data row3 col4" >9</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row3_col5" class="data row3 col5" >1</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row3_col6" class="data row3 col6" >35</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row4" class="row_heading level0 row4" >1062</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row4_col0" class="data row4 col0" >1063</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row4_col1" class="data row4 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row4_col2" class="data row4 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row4_col3" class="data row4 col3" >Bihar</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row4_col4" class="data row4 col4" >37</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row4_col5" class="data row4 col5" >2</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row4_col6" class="data row4 col6" >85</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row5" class="row_heading level0 row5" >1063</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row5_col0" class="data row5 col0" >1064</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row5_col1" class="data row5 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row5_col2" class="data row5 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row5_col3" class="data row5 col3" >Chandigarh</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row5_col4" class="data row5 col4" >9</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row5_col5" class="data row5 col5" >0</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row5_col6" class="data row5 col6" >21</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row6" class="row_heading level0 row6" >1064</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row6_col0" class="data row6 col0" >1065</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row6_col1" class="data row6 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row6_col2" class="data row6 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row6_col3" class="data row6 col3" >Chhattisgarh</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row6_col4" class="data row6 col4" >24</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row6_col5" class="data row6 col5" >0</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row6_col6" class="data row6 col6" >36</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row7" class="row_heading level0 row7" >1065</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row7_col0" class="data row7 col0" >1066</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row7_col1" class="data row7 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row7_col2" class="data row7 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row7_col3" class="data row7 col3" >Delhi</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row7_col4" class="data row7 col4" >72</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row7_col5" class="data row7 col5" >42</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row7_col6" class="data row7 col6" >1707</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row8" class="row_heading level0 row8" >1066</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row8_col0" class="data row8 col0" >1067</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row8_col1" class="data row8 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row8_col2" class="data row8 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row8_col3" class="data row8 col3" >Goa</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row8_col4" class="data row8 col4" >6</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row8_col5" class="data row8 col5" >0</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row8_col6" class="data row8 col6" >7</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row9" class="row_heading level0 row9" >1067</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row9_col0" class="data row9 col0" >1068</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row9_col1" class="data row9 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row9_col2" class="data row9 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row9_col3" class="data row9 col3" >Gujarat</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row9_col4" class="data row9 col4" >88</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row9_col5" class="data row9 col5" >48</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row9_col6" class="data row9 col6" >1272</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row10" class="row_heading level0 row10" >1068</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row10_col0" class="data row10 col0" >1069</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row10_col1" class="data row10 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row10_col2" class="data row10 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row10_col3" class="data row10 col3" >Haryana</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row10_col4" class="data row10 col4" >43</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row10_col5" class="data row10 col5" >3</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row10_col6" class="data row10 col6" >225</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row11" class="row_heading level0 row11" >1069</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row11_col0" class="data row11 col0" >1070</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row11_col1" class="data row11 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row11_col2" class="data row11 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row11_col3" class="data row11 col3" >Himachal Pradesh</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row11_col4" class="data row11 col4" >16</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row11_col5" class="data row11 col5" >1</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row11_col6" class="data row11 col6" >38</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row12" class="row_heading level0 row12" >1070</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row12_col0" class="data row12 col0" >1071</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row12_col1" class="data row12 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row12_col2" class="data row12 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row12_col3" class="data row12 col3" >Jammu and Kashmir</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row12_col4" class="data row12 col4" >42</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row12_col5" class="data row12 col5" >5</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row12_col6" class="data row12 col6" >328</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row13" class="row_heading level0 row13" >1071</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row13_col0" class="data row13 col0" >1072</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row13_col1" class="data row13 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row13_col2" class="data row13 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row13_col3" class="data row13 col3" >Jharkhand</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row13_col4" class="data row13 col4" >0</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row13_col5" class="data row13 col5" >2</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row13_col6" class="data row13 col6" >33</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row14" class="row_heading level0 row14" >1072</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row14_col0" class="data row14 col0" >1073</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row14_col1" class="data row14 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row14_col2" class="data row14 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row14_col3" class="data row14 col3" >Karnataka</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row14_col4" class="data row14 col4" >92</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row14_col5" class="data row14 col5" >13</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row14_col6" class="data row14 col6" >371</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row15" class="row_heading level0 row15" >1073</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row15_col0" class="data row15 col0" >1074</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row15_col1" class="data row15 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row15_col2" class="data row15 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row15_col3" class="data row15 col3" >Kerala</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row15_col4" class="data row15 col4" >255</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row15_col5" class="data row15 col5" >3</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row15_col6" class="data row15 col6" >396</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row16" class="row_heading level0 row16" >1074</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row16_col0" class="data row16 col0" >1075</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row16_col1" class="data row16 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row16_col2" class="data row16 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row16_col3" class="data row16 col3" >Ladakh</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row16_col4" class="data row16 col4" >14</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row16_col5" class="data row16 col5" >0</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row16_col6" class="data row16 col6" >18</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row17" class="row_heading level0 row17" >1075</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row17_col0" class="data row17 col0" >1076</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row17_col1" class="data row17 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row17_col2" class="data row17 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row17_col3" class="data row17 col3" >Madhya Pradesh</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row17_col4" class="data row17 col4" >69</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row17_col5" class="data row17 col5" >69</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row17_col6" class="data row17 col6" >1355</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row18" class="row_heading level0 row18" >1076</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row18_col0" class="data row18 col0" >1077</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row18_col1" class="data row18 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row18_col2" class="data row18 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row18_col3" class="data row18 col3" >Maharashtra</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row18_col4" class="data row18 col4" >331</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row18_col5" class="data row18 col5" >201</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row18_col6" class="data row18 col6" >3323</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row19" class="row_heading level0 row19" >1077</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row19_col0" class="data row19 col0" >1078</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row19_col1" class="data row19 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row19_col2" class="data row19 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row19_col3" class="data row19 col3" >Manipur</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row19_col4" class="data row19 col4" >1</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row19_col5" class="data row19 col5" >0</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row19_col6" class="data row19 col6" >2</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row20" class="row_heading level0 row20" >1078</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row20_col0" class="data row20 col0" >1079</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row20_col1" class="data row20 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row20_col2" class="data row20 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row20_col3" class="data row20 col3" >Meghalaya</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row20_col4" class="data row20 col4" >0</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row20_col5" class="data row20 col5" >1</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row20_col6" class="data row20 col6" >11</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row21" class="row_heading level0 row21" >1079</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row21_col0" class="data row21 col0" >1080</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row21_col1" class="data row21 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row21_col2" class="data row21 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row21_col3" class="data row21 col3" >Mizoram</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row21_col4" class="data row21 col4" >0</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row21_col5" class="data row21 col5" >0</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row21_col6" class="data row21 col6" >1</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row22" class="row_heading level0 row22" >1080</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row22_col0" class="data row22 col0" >1081</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row22_col1" class="data row22 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row22_col2" class="data row22 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row22_col3" class="data row22 col3" >Nagaland#</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row22_col4" class="data row22 col4" >0</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row22_col5" class="data row22 col5" >0</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row22_col6" class="data row22 col6" >0</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row23" class="row_heading level0 row23" >1081</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row23_col0" class="data row23 col0" >1082</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row23_col1" class="data row23 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row23_col2" class="data row23 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row23_col3" class="data row23 col3" >Odisha</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row23_col4" class="data row23 col4" >21</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row23_col5" class="data row23 col5" >1</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row23_col6" class="data row23 col6" >60</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row24" class="row_heading level0 row24" >1082</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row24_col0" class="data row24 col0" >1083</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row24_col1" class="data row24 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row24_col2" class="data row24 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row24_col3" class="data row24 col3" >Puducherry</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row24_col4" class="data row24 col4" >3</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row24_col5" class="data row24 col5" >0</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row24_col6" class="data row24 col6" >7</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row25" class="row_heading level0 row25" >1083</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row25_col0" class="data row25 col0" >1084</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row25_col1" class="data row25 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row25_col2" class="data row25 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row25_col3" class="data row25 col3" >Punjab</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row25_col4" class="data row25 col4" >27</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row25_col5" class="data row25 col5" >13</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row25_col6" class="data row25 col6" >202</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row26" class="row_heading level0 row26" >1084</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row26_col0" class="data row26 col0" >1085</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row26_col1" class="data row26 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row26_col2" class="data row26 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row26_col3" class="data row26 col3" >Rajasthan</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row26_col4" class="data row26 col4" >183</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row26_col5" class="data row26 col5" >11</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row26_col6" class="data row26 col6" >1229</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row27" class="row_heading level0 row27" >1085</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row27_col0" class="data row27 col0" >1086</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row27_col1" class="data row27 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row27_col2" class="data row27 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row27_col3" class="data row27 col3" >Tamil Nadu</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row27_col4" class="data row27 col4" >283</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row27_col5" class="data row27 col5" >15</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row27_col6" class="data row27 col6" >1323</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row28" class="row_heading level0 row28" >1086</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row28_col0" class="data row28 col0" >1087</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row28_col1" class="data row28 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row28_col2" class="data row28 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row28_col3" class="data row28 col3" >Telengana</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row28_col4" class="data row28 col4" >186</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row28_col5" class="data row28 col5" >18</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row28_col6" class="data row28 col6" >791</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row29" class="row_heading level0 row29" >1087</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row29_col0" class="data row29 col0" >1088</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row29_col1" class="data row29 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row29_col2" class="data row29 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row29_col3" class="data row29 col3" >Tripura</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row29_col4" class="data row29 col4" >1</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row29_col5" class="data row29 col5" >0</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row29_col6" class="data row29 col6" >2</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row30" class="row_heading level0 row30" >1088</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row30_col0" class="data row30 col0" >1089</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row30_col1" class="data row30 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row30_col2" class="data row30 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row30_col3" class="data row30 col3" >Uttarakhand</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row30_col4" class="data row30 col4" >9</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row30_col5" class="data row30 col5" >0</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row30_col6" class="data row30 col6" >42</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row31" class="row_heading level0 row31" >1089</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row31_col0" class="data row31 col0" >1090</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row31_col1" class="data row31 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row31_col2" class="data row31 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row31_col3" class="data row31 col3" >Uttar Pradesh</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row31_col4" class="data row31 col4" >86</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row31_col5" class="data row31 col5" >14</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row31_col6" class="data row31 col6" >969</td>
            </tr>
            <tr>
                        <th id="T_dfcb67c0_822f_11ea_9459_847beb43ac05level0_row32" class="row_heading level0 row32" >1090</th>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row32_col0" class="data row32 col0" >1091</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row32_col1" class="data row32 col1" >18/04/20</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row32_col2" class="data row32 col2" >5:00 PM</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row32_col3" class="data row32 col3" >West Bengal</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row32_col4" class="data row32 col4" >55</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row32_col5" class="data row32 col5" >10</td>
                        <td id="T_dfcb67c0_822f_11ea_9459_847beb43ac05row32_col6" class="data row32 col6" >287</td>
            </tr>
    </tbody></table>




```python

```
