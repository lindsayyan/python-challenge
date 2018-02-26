
## Python Homework Pyboss
### Loading Data in 


```python
import pandas as pd 
employee1=pd.read_csv('employee_data1.csv',sep=',')
employee2=pd.read_csv('employee_data2.csv',sep=',')
```


```python
employee=pd.concat([employee1,employee2])
```


```python
employee.head()
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
      <th>Emp ID</th>
      <th>Name</th>
      <th>DOB</th>
      <th>SSN</th>
      <th>State</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>214</td>
      <td>Sarah Simpson</td>
      <td>1985-12-04</td>
      <td>282-01-8166</td>
      <td>Florida</td>
    </tr>
    <tr>
      <th>1</th>
      <td>15</td>
      <td>Samantha Lara</td>
      <td>1993-09-08</td>
      <td>848-80-7526</td>
      <td>Colorado</td>
    </tr>
    <tr>
      <th>2</th>
      <td>411</td>
      <td>Stacy Charles</td>
      <td>1957-12-20</td>
      <td>658-75-8526</td>
      <td>Pennsylvania</td>
    </tr>
    <tr>
      <th>3</th>
      <td>166</td>
      <td>Michelle Roy</td>
      <td>1978-07-29</td>
      <td>794-25-3944</td>
      <td>Michigan</td>
    </tr>
    <tr>
      <th>4</th>
      <td>39</td>
      <td>Joseph Rogers</td>
      <td>1985-03-28</td>
      <td>525-40-3515</td>
      <td>Minnesota</td>
    </tr>
  </tbody>
</table>
</div>



### Splitting Name column into First and Last name 


```python
df = employee['Name'].apply(lambda x: pd.Series(x.split(' ')))
```


```python
df.columns=['First Name','Last Name']
employee=pd.concat([employee,df],axis=1)
del employee['Name']
employee.head()
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
      <th>Emp ID</th>
      <th>DOB</th>
      <th>SSN</th>
      <th>State</th>
      <th>First Name</th>
      <th>Last Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>214</td>
      <td>1985-12-04</td>
      <td>282-01-8166</td>
      <td>Florida</td>
      <td>Sarah</td>
      <td>Simpson</td>
    </tr>
    <tr>
      <th>1</th>
      <td>15</td>
      <td>1993-09-08</td>
      <td>848-80-7526</td>
      <td>Colorado</td>
      <td>Samantha</td>
      <td>Lara</td>
    </tr>
    <tr>
      <th>2</th>
      <td>411</td>
      <td>1957-12-20</td>
      <td>658-75-8526</td>
      <td>Pennsylvania</td>
      <td>Stacy</td>
      <td>Charles</td>
    </tr>
    <tr>
      <th>3</th>
      <td>166</td>
      <td>1978-07-29</td>
      <td>794-25-3944</td>
      <td>Michigan</td>
      <td>Michelle</td>
      <td>Roy</td>
    </tr>
    <tr>
      <th>4</th>
      <td>39</td>
      <td>1985-03-28</td>
      <td>525-40-3515</td>
      <td>Minnesota</td>
      <td>Joseph</td>
      <td>Rogers</td>
    </tr>
  </tbody>
</table>
</div>



### Reformatting DOB Column 


```python
list_DOB=[]
for x in employee['DOB']:
    Day=x[-2:]
    Month=x[-5:-3]
    Year=x[0:4]
    list_DOB.append(str(Day)+'/'+str(Month)+'/'+str(Year))
```


```python
list_DOB2=pd.DataFrame(list_DOB)
employee2=pd.DataFrame(employee)
employee2.head()
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
      <th>Emp ID</th>
      <th>DOB</th>
      <th>SSN</th>
      <th>State</th>
      <th>First Name</th>
      <th>Last Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>214</td>
      <td>1985-12-04</td>
      <td>282-01-8166</td>
      <td>Florida</td>
      <td>Sarah</td>
      <td>Simpson</td>
    </tr>
    <tr>
      <th>1</th>
      <td>15</td>
      <td>1993-09-08</td>
      <td>848-80-7526</td>
      <td>Colorado</td>
      <td>Samantha</td>
      <td>Lara</td>
    </tr>
    <tr>
      <th>2</th>
      <td>411</td>
      <td>1957-12-20</td>
      <td>658-75-8526</td>
      <td>Pennsylvania</td>
      <td>Stacy</td>
      <td>Charles</td>
    </tr>
    <tr>
      <th>3</th>
      <td>166</td>
      <td>1978-07-29</td>
      <td>794-25-3944</td>
      <td>Michigan</td>
      <td>Michelle</td>
      <td>Roy</td>
    </tr>
    <tr>
      <th>4</th>
      <td>39</td>
      <td>1985-03-28</td>
      <td>525-40-3515</td>
      <td>Minnesota</td>
      <td>Joseph</td>
      <td>Rogers</td>
    </tr>
  </tbody>
</table>
</div>




```python
Employee2=employee2[['Emp ID','DOB','SSN','State','First Name','Last Name']]

```


```python
Employee2=Employee2.reset_index()
df2=pd.concat([Employee2,list_DOB2],axis=1)
df2=df2.rename(columns={0:"DOB2"})
```


```python
del df2['index']
del df2['DOB']
df2.head()
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
      <th>Emp ID</th>
      <th>SSN</th>
      <th>State</th>
      <th>First Name</th>
      <th>Last Name</th>
      <th>DOB2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>214</td>
      <td>282-01-8166</td>
      <td>Florida</td>
      <td>Sarah</td>
      <td>Simpson</td>
      <td>04/12/1985</td>
    </tr>
    <tr>
      <th>1</th>
      <td>15</td>
      <td>848-80-7526</td>
      <td>Colorado</td>
      <td>Samantha</td>
      <td>Lara</td>
      <td>08/09/1993</td>
    </tr>
    <tr>
      <th>2</th>
      <td>411</td>
      <td>658-75-8526</td>
      <td>Pennsylvania</td>
      <td>Stacy</td>
      <td>Charles</td>
      <td>20/12/1957</td>
    </tr>
    <tr>
      <th>3</th>
      <td>166</td>
      <td>794-25-3944</td>
      <td>Michigan</td>
      <td>Michelle</td>
      <td>Roy</td>
      <td>29/07/1978</td>
    </tr>
    <tr>
      <th>4</th>
      <td>39</td>
      <td>525-40-3515</td>
      <td>Minnesota</td>
      <td>Joseph</td>
      <td>Rogers</td>
      <td>28/03/1985</td>
    </tr>
  </tbody>
</table>
</div>



### Reformating SSN Column 


```python
list_SSN=[]
for x in df2['SSN']:
    last4=x[-4:]
    list_SSN.append('***-**-'+str(last4))
```


```python
list_SSN2=pd.DataFrame(list_SSN)
```


```python
df2=pd.concat([df2,list_SSN2],axis=1)
```


```python
df2=df2.rename(columns={0:"SSN2"})
del df2['SSN']
df2.head()
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
      <th>Emp ID</th>
      <th>State</th>
      <th>First Name</th>
      <th>Last Name</th>
      <th>DOB2</th>
      <th>SSN2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>214</td>
      <td>Florida</td>
      <td>Sarah</td>
      <td>Simpson</td>
      <td>04/12/1985</td>
      <td>***-**-8166</td>
    </tr>
    <tr>
      <th>1</th>
      <td>15</td>
      <td>Colorado</td>
      <td>Samantha</td>
      <td>Lara</td>
      <td>08/09/1993</td>
      <td>***-**-7526</td>
    </tr>
    <tr>
      <th>2</th>
      <td>411</td>
      <td>Pennsylvania</td>
      <td>Stacy</td>
      <td>Charles</td>
      <td>20/12/1957</td>
      <td>***-**-8526</td>
    </tr>
    <tr>
      <th>3</th>
      <td>166</td>
      <td>Michigan</td>
      <td>Michelle</td>
      <td>Roy</td>
      <td>29/07/1978</td>
      <td>***-**-3944</td>
    </tr>
    <tr>
      <th>4</th>
      <td>39</td>
      <td>Minnesota</td>
      <td>Joseph</td>
      <td>Rogers</td>
      <td>28/03/1985</td>
      <td>***-**-3515</td>
    </tr>
  </tbody>
</table>
</div>



### Reformatting State Column 


```python
us_state_abbrev = {
    'Alabama': 'AL',
    'Alaska': 'AK',
    'Arizona': 'AZ',
    'Arkansas': 'AR',
    'California': 'CA',
    'Colorado': 'CO',
    'Connecticut': 'CT',
    'Delaware': 'DE',
    'Florida': 'FL',
    'Georgia': 'GA',
    'Hawaii': 'HI',
    'Idaho': 'ID',
    'Illinois': 'IL',
    'Indiana': 'IN',
    'Iowa': 'IA',
    'Kansas': 'KS',
    'Kentucky': 'KY',
    'Louisiana': 'LA',
    'Maine': 'ME',
    'Maryland': 'MD',
    'Massachusetts': 'MA',
    'Michigan': 'MI',
    'Minnesota': 'MN',
    'Mississippi': 'MS',
    'Missouri': 'MO',
    'Montana': 'MT',
    'Nebraska': 'NE',
    'Nevada': 'NV',
    'New Hampshire': 'NH',
    'New Jersey': 'NJ',
    'New Mexico': 'NM',
    'New York': 'NY',
    'North Carolina': 'NC',
    'North Dakota': 'ND',
    'Ohio': 'OH',
    'Oklahoma': 'OK',
    'Oregon': 'OR',
    'Pennsylvania': 'PA',
    'Rhode Island': 'RI',
    'South Carolina': 'SC',
    'South Dakota': 'SD',
    'Tennessee': 'TN',
    'Texas': 'TX',
    'Utah': 'UT',
    'Vermont': 'VT',
    'Virginia': 'VA',
    'Washington': 'WA',
    'West Virginia': 'WV',
    'Wisconsin': 'WI',
    'Wyoming': 'WY',
}
```


```python
list_state=[]
for x in df2['State']:
    abb=us_state_abbrev[x]
    list_state.append(abb)
```


```python
list_state2=pd.DataFrame(list_state)
```


```python
df2=pd.concat([df2,list_state2],axis=1)
```


```python
df2=df2.rename(columns={0:"State2"})
del df2['State']
df2.head()
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
      <th>Emp ID</th>
      <th>First Name</th>
      <th>Last Name</th>
      <th>DOB2</th>
      <th>SSN2</th>
      <th>State2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>214</td>
      <td>Sarah</td>
      <td>Simpson</td>
      <td>04/12/1985</td>
      <td>***-**-8166</td>
      <td>FL</td>
    </tr>
    <tr>
      <th>1</th>
      <td>15</td>
      <td>Samantha</td>
      <td>Lara</td>
      <td>08/09/1993</td>
      <td>***-**-7526</td>
      <td>CO</td>
    </tr>
    <tr>
      <th>2</th>
      <td>411</td>
      <td>Stacy</td>
      <td>Charles</td>
      <td>20/12/1957</td>
      <td>***-**-8526</td>
      <td>PA</td>
    </tr>
    <tr>
      <th>3</th>
      <td>166</td>
      <td>Michelle</td>
      <td>Roy</td>
      <td>29/07/1978</td>
      <td>***-**-3944</td>
      <td>MI</td>
    </tr>
    <tr>
      <th>4</th>
      <td>39</td>
      <td>Joseph</td>
      <td>Rogers</td>
      <td>28/03/1985</td>
      <td>***-**-3515</td>
      <td>MN</td>
    </tr>
  </tbody>
</table>
</div>


