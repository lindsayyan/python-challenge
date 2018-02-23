
## Option 1 PyBank
### Loading Data in 


```python
import pandas as pd
budget_data_1=pd.read_csv('budget_data_1.csv',sep=',')
budget_data_2=pd.read_csv('budget_data_2.csv',sep=',')

```


```python
budget_data= pd.concat([budget_data_1,budget_data_2])
budget_data.head()
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
  </tbody>
</table>
</div>



### Changing Data Format to make them all uniform


```python
Data=budget_data['Date'].replace({'-20':'-'}, regex=True)
Data_org=pd.concat([Data,budget_data['Revenue']], axis=1)
Data_org2=Data_org.groupby(['Date']).agg('sum')
Data_org2=Data_org2.reset_index()
Data_org2.head()
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
      <td>Apr-09</td>
      <td>-735286</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Apr-10</td>
      <td>120968</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Apr-11</td>
      <td>110092</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Apr-12</td>
      <td>594289</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Apr-13</td>
      <td>1482637</td>
    </tr>
  </tbody>
</table>
</div>



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
Data_org2.head()
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
      <th>Date2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Jan-09</td>
      <td>943690</td>
      <td>200901</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Feb-09</td>
      <td>1062565</td>
      <td>200902</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Mar-09</td>
      <td>210079</td>
      <td>200903</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Apr-09</td>
      <td>-735286</td>
      <td>200904</td>
    </tr>
    <tr>
      <th>4</th>
      <td>May-09</td>
      <td>842933</td>
      <td>200905</td>
    </tr>
  </tbody>
</table>
</div>




```python
d={"diff":range(len(Data_org2))}
d['diff'] = Data_org2['Revenue'] - Data_org2['Revenue'].shift(1)
```


```python
d2=pd.DataFrame(d)
Data_org_final=pd.concat([Data_org2,d2],axis=1)
Data_org_final.head()
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
      <th>Date2</th>
      <th>diff</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Jan-09</td>
      <td>943690</td>
      <td>200901</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Feb-09</td>
      <td>1062565</td>
      <td>200902</td>
      <td>118875.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Mar-09</td>
      <td>210079</td>
      <td>200903</td>
      <td>-852486.0</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Apr-09</td>
      <td>-735286</td>
      <td>200904</td>
      <td>-945365.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>May-09</td>
      <td>842933</td>
      <td>200905</td>
      <td>1578219.0</td>
    </tr>
  </tbody>
</table>
</div>



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


