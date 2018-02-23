
## Option 1 PyBank
### Loading Data in 


```python
import pandas as pd
budget_data_1=pd.read_csv('budget_data_1.csv',sep=',')
budget_data_2=pd.read_csv('budget_data_2.csv',sep=',')

```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Revenue</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Jan-2009</td>
      <td>943690</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Feb-2009</td>
      <td>1062565</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Mar-2009</td>
      <td>210079</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Apr-2009</td>
      <td>-735286</td>
    </tr>
    <tr>
      <th>4</th>
      <td>May-2009</td>
      <td>842933</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Jun-2009</td>
      <td>358691</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Jul-2009</td>
      <td>914953</td>
    </tr>
    <tr>
      <th>7</th>
      <td>Aug-2009</td>
      <td>723427</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Sep-2009</td>
      <td>-837468</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Oct-2009</td>
      <td>-146929</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Nov-2009</td>
      <td>831730</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Dec-2009</td>
      <td>917752</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Jan-2010</td>
      <td>800038</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Feb-2010</td>
      <td>1117103</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Mar-2010</td>
      <td>181220</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Apr-2010</td>
      <td>120968</td>
    </tr>
    <tr>
      <th>16</th>
      <td>May-2010</td>
      <td>844012</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Jun-2010</td>
      <td>307468</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Jul-2010</td>
      <td>502341</td>
    </tr>
    <tr>
      <th>19</th>
      <td>Aug-2010</td>
      <td>-748679</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Sep-2010</td>
      <td>-1063151</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Oct-2010</td>
      <td>111367</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Nov-2010</td>
      <td>889322</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Dec-2010</td>
      <td>1028794</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Jan-2011</td>
      <td>-705201</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Feb-2011</td>
      <td>457393</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Mar-2011</td>
      <td>358440</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Apr-2011</td>
      <td>110092</td>
    </tr>
    <tr>
      <th>28</th>
      <td>May-2011</td>
      <td>1111337</td>
    </tr>
    <tr>
      <th>29</th>
      <td>Jun-2011</td>
      <td>691712</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>56</th>
      <td>Sep-2013</td>
      <td>339680</td>
    </tr>
    <tr>
      <th>57</th>
      <td>Oct-2013</td>
      <td>809253</td>
    </tr>
    <tr>
      <th>58</th>
      <td>Nov-2013</td>
      <td>924494</td>
    </tr>
    <tr>
      <th>59</th>
      <td>Dec-2013</td>
      <td>998347</td>
    </tr>
    <tr>
      <th>60</th>
      <td>Jan-2014</td>
      <td>-524902</td>
    </tr>
    <tr>
      <th>61</th>
      <td>Feb-2014</td>
      <td>747765</td>
    </tr>
    <tr>
      <th>62</th>
      <td>Mar-2014</td>
      <td>197783</td>
    </tr>
    <tr>
      <th>63</th>
      <td>Apr-2014</td>
      <td>131625</td>
    </tr>
    <tr>
      <th>64</th>
      <td>May-2014</td>
      <td>1016992</td>
    </tr>
    <tr>
      <th>65</th>
      <td>Jun-2014</td>
      <td>-930753</td>
    </tr>
    <tr>
      <th>66</th>
      <td>Jul-2014</td>
      <td>714387</td>
    </tr>
    <tr>
      <th>67</th>
      <td>Aug-2014</td>
      <td>201005</td>
    </tr>
    <tr>
      <th>68</th>
      <td>Sep-2014</td>
      <td>655535</td>
    </tr>
    <tr>
      <th>69</th>
      <td>Oct-2014</td>
      <td>845108</td>
    </tr>
    <tr>
      <th>70</th>
      <td>Nov-2014</td>
      <td>101736</td>
    </tr>
    <tr>
      <th>71</th>
      <td>Dec-2014</td>
      <td>-93063</td>
    </tr>
    <tr>
      <th>72</th>
      <td>Jan-2015</td>
      <td>984921</td>
    </tr>
    <tr>
      <th>73</th>
      <td>Feb-2015</td>
      <td>-362343</td>
    </tr>
    <tr>
      <th>74</th>
      <td>Mar-2015</td>
      <td>940457</td>
    </tr>
    <tr>
      <th>75</th>
      <td>Apr-2015</td>
      <td>216399</td>
    </tr>
    <tr>
      <th>76</th>
      <td>May-2015</td>
      <td>363036</td>
    </tr>
    <tr>
      <th>77</th>
      <td>Jun-2015</td>
      <td>672160</td>
    </tr>
    <tr>
      <th>78</th>
      <td>Jul-2015</td>
      <td>783533</td>
    </tr>
    <tr>
      <th>79</th>
      <td>Aug-2015</td>
      <td>1079882</td>
    </tr>
    <tr>
      <th>80</th>
      <td>Sep-2015</td>
      <td>288933</td>
    </tr>
    <tr>
      <th>81</th>
      <td>Oct-2015</td>
      <td>894500</td>
    </tr>
    <tr>
      <th>82</th>
      <td>Nov-2015</td>
      <td>411593</td>
    </tr>
    <tr>
      <th>83</th>
      <td>Dec-2015</td>
      <td>789575</td>
    </tr>
    <tr>
      <th>84</th>
      <td>Jan-2016</td>
      <td>355838</td>
    </tr>
    <tr>
      <th>85</th>
      <td>Feb-2016</td>
      <td>437489</td>
    </tr>
  </tbody>
</table>
<p>86 rows × 2 columns</p>
</div>




```python
budget_data= pd.concat([budget_data_1,budget_data_2])
budget_data
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Date</th>
      <th>Revenue</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Oct-12</td>
      <td>1154293</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Nov-12</td>
      <td>885773</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Dec-12</td>
      <td>-448704</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Jan-13</td>
      <td>563679</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Feb-13</td>
      <td>555394</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Mar-13</td>
      <td>631974</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Apr-13</td>
      <td>957395</td>
    </tr>
    <tr>
      <th>7</th>
      <td>May-13</td>
      <td>1104047</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Jun-13</td>
      <td>693464</td>
    </tr>
    <tr>
      <th>9</th>
      <td>Jul-13</td>
      <td>454932</td>
    </tr>
    <tr>
      <th>10</th>
      <td>Aug-13</td>
      <td>727272</td>
    </tr>
    <tr>
      <th>11</th>
      <td>Sep-13</td>
      <td>125016</td>
    </tr>
    <tr>
      <th>12</th>
      <td>Oct-13</td>
      <td>339251</td>
    </tr>
    <tr>
      <th>13</th>
      <td>Nov-13</td>
      <td>78523</td>
    </tr>
    <tr>
      <th>14</th>
      <td>Dec-13</td>
      <td>977084</td>
    </tr>
    <tr>
      <th>15</th>
      <td>Jan-14</td>
      <td>1158718</td>
    </tr>
    <tr>
      <th>16</th>
      <td>Feb-14</td>
      <td>332681</td>
    </tr>
    <tr>
      <th>17</th>
      <td>Mar-14</td>
      <td>-341227</td>
    </tr>
    <tr>
      <th>18</th>
      <td>Apr-14</td>
      <td>173826</td>
    </tr>
    <tr>
      <th>19</th>
      <td>May-14</td>
      <td>742611</td>
    </tr>
    <tr>
      <th>20</th>
      <td>Jun-14</td>
      <td>1189806</td>
    </tr>
    <tr>
      <th>21</th>
      <td>Jul-14</td>
      <td>607363</td>
    </tr>
    <tr>
      <th>22</th>
      <td>Aug-14</td>
      <td>-1172384</td>
    </tr>
    <tr>
      <th>23</th>
      <td>Sep-14</td>
      <td>587993</td>
    </tr>
    <tr>
      <th>24</th>
      <td>Oct-14</td>
      <td>295198</td>
    </tr>
    <tr>
      <th>25</th>
      <td>Nov-14</td>
      <td>-300390</td>
    </tr>
    <tr>
      <th>26</th>
      <td>Dec-14</td>
      <td>468995</td>
    </tr>
    <tr>
      <th>27</th>
      <td>Jan-15</td>
      <td>698452</td>
    </tr>
    <tr>
      <th>28</th>
      <td>Feb-15</td>
      <td>967828</td>
    </tr>
    <tr>
      <th>29</th>
      <td>Mar-15</td>
      <td>-454873</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>56</th>
      <td>Sep-2013</td>
      <td>339680</td>
    </tr>
    <tr>
      <th>57</th>
      <td>Oct-2013</td>
      <td>809253</td>
    </tr>
    <tr>
      <th>58</th>
      <td>Nov-2013</td>
      <td>924494</td>
    </tr>
    <tr>
      <th>59</th>
      <td>Dec-2013</td>
      <td>998347</td>
    </tr>
    <tr>
      <th>60</th>
      <td>Jan-2014</td>
      <td>-524902</td>
    </tr>
    <tr>
      <th>61</th>
      <td>Feb-2014</td>
      <td>747765</td>
    </tr>
    <tr>
      <th>62</th>
      <td>Mar-2014</td>
      <td>197783</td>
    </tr>
    <tr>
      <th>63</th>
      <td>Apr-2014</td>
      <td>131625</td>
    </tr>
    <tr>
      <th>64</th>
      <td>May-2014</td>
      <td>1016992</td>
    </tr>
    <tr>
      <th>65</th>
      <td>Jun-2014</td>
      <td>-930753</td>
    </tr>
    <tr>
      <th>66</th>
      <td>Jul-2014</td>
      <td>714387</td>
    </tr>
    <tr>
      <th>67</th>
      <td>Aug-2014</td>
      <td>201005</td>
    </tr>
    <tr>
      <th>68</th>
      <td>Sep-2014</td>
      <td>655535</td>
    </tr>
    <tr>
      <th>69</th>
      <td>Oct-2014</td>
      <td>845108</td>
    </tr>
    <tr>
      <th>70</th>
      <td>Nov-2014</td>
      <td>101736</td>
    </tr>
    <tr>
      <th>71</th>
      <td>Dec-2014</td>
      <td>-93063</td>
    </tr>
    <tr>
      <th>72</th>
      <td>Jan-2015</td>
      <td>984921</td>
    </tr>
    <tr>
      <th>73</th>
      <td>Feb-2015</td>
      <td>-362343</td>
    </tr>
    <tr>
      <th>74</th>
      <td>Mar-2015</td>
      <td>940457</td>
    </tr>
    <tr>
      <th>75</th>
      <td>Apr-2015</td>
      <td>216399</td>
    </tr>
    <tr>
      <th>76</th>
      <td>May-2015</td>
      <td>363036</td>
    </tr>
    <tr>
      <th>77</th>
      <td>Jun-2015</td>
      <td>672160</td>
    </tr>
    <tr>
      <th>78</th>
      <td>Jul-2015</td>
      <td>783533</td>
    </tr>
    <tr>
      <th>79</th>
      <td>Aug-2015</td>
      <td>1079882</td>
    </tr>
    <tr>
      <th>80</th>
      <td>Sep-2015</td>
      <td>288933</td>
    </tr>
    <tr>
      <th>81</th>
      <td>Oct-2015</td>
      <td>894500</td>
    </tr>
    <tr>
      <th>82</th>
      <td>Nov-2015</td>
      <td>411593</td>
    </tr>
    <tr>
      <th>83</th>
      <td>Dec-2015</td>
      <td>789575</td>
    </tr>
    <tr>
      <th>84</th>
      <td>Jan-2016</td>
      <td>355838</td>
    </tr>
    <tr>
      <th>85</th>
      <td>Feb-2016</td>
      <td>437489</td>
    </tr>
  </tbody>
</table>
<p>127 rows × 2 columns</p>
</div>



### Changing Data Format to make them all uniform


```python
Data=budget_data['Date'].replace({'-20':'-'}, regex=True)
Data_org=pd.concat([Data,budget_data['Revenue']], axis=1)
Data_org2=Data_org.groupby(['Date']).agg('sum')
Data_org2=Data_org2.reset_index()
```

### Converting string Date to Number Date


```python
list_a=[]
for x in Data_org2['Date']:
  
    if 'Jan' in x:
        a='01'
        list_a.append('20'+ x[-2:] +a )
    elif 'Feb' in x:
        a='02'
        list_a.append('20'+ x[-2:] +a )
    elif 'Mar' in x:
        a='03'
        list_a.append('20'+ x[-2:] +a )
    elif 'Apr' in x:
        a='04'
        list_a.append('20'+ x[-2:] +a )
    elif 'May' in x:
        a='05'
        list_a.append('20'+ x[-2:] +a )
    elif 'Jun' in x:
        a='06'
        list_a.append('20'+ x[-2:] +a )
    elif 'Jul' in x:
        a='07'
        list_a.append('20'+ x[-2:] +a )
    elif 'Aug' in x:
        a='08'
        list_a.append('20'+ x[-2:] +a )
    elif 'Sep' in x:
        a='09'
        list_a.append('20'+ x[-2:] +a )
    elif 'Oct' in x:
        a='10'
        list_a.append('20'+ x[-2:] +a )
    elif 'Nov' in x:
        a='11'
        list_a.append('20'+ x[-2:] +a )
    elif 'Dec' in x:
        a='12'
        list_a.append('20'+ x[-2:] +a )
```


```python
list_a2=pd.DataFrame(list_a)
```


```python
Data_org2=pd.concat([Data_org2,list_a2], axis=1)
Data_org2=Data_org2.rename(columns={0:"Date2"})
```


```python
Data_org2=Data_org2.sort_values(['Date2'])
```


```python
Data_org2=Data_org2.reset_index()
del Data_org2['index']
#Data_org2_copy=Data_org2[:]
```


```python
d={"diff":range(len(Data_org2))}
d['diff'] = Data_org2['Revenue'] - Data_org2['Revenue'].shift(1)
```


```python
d2=pd.DataFrame(d)
Data_org_final=pd.concat([Data_org2,d2],axis=1)
```

### Getting Final Summary


```python
Total_Month=Data_org_final['Date'].count()
Total_Revenue=Data_org_final['Revenue'].sum()
Average_Revenue_Change=Data_org_final['diff'].mean()
Greatest_Increase=Data_org_final['diff'].max()
Greatest_Decrease=Data_org_final['diff'].min()
```


```python
Final_Analysis=pd.DataFrame({'Total_Month':[Total_Month],
                             'Total_Revenue':[Total_Revenue],
                             'Average_Revenue_Change':[Average_Revenue_Change],
                             'Greatest_Increase':[Greatest_Increase],
                             'Greatest_Decrease':[Greatest_Decrease]
                             })
Final_Analysis=Final_Analysis.transpose()
Final_Analysis.columns=['Analysis']
Final_Analysis=Final_Analysis.round({'Analysis': 0})
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Average_Revenue_Change</th>
      <th>Greatest_Decrease</th>
      <th>Greatest_Increase</th>
      <th>Total_Month</th>
      <th>Total_Revenue</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>4443.917647</td>
      <td>-2293129.0</td>
      <td>2214907.0</td>
      <td>86</td>
      <td>55945323</td>
    </tr>
  </tbody>
</table>
</div>




```python
Final_Analysis
```




<div>
<style>
    .dataframe thead tr:only-child th {
        text-align: right;
    }

    .dataframe thead th {
        text-align: left;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Analysis</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Average_Revenue_Change</th>
      <td>4444.0</td>
    </tr>
    <tr>
      <th>Greatest_Decrease</th>
      <td>-2293129.0</td>
    </tr>
    <tr>
      <th>Greatest_Increase</th>
      <td>2214907.0</td>
    </tr>
    <tr>
      <th>Total_Month</th>
      <td>86.0</td>
    </tr>
    <tr>
      <th>Total_Revenue</th>
      <td>55945323.0</td>
    </tr>
  </tbody>
</table>
</div>


