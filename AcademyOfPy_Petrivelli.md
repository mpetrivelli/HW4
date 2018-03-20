

```python
# Import Dependencies
import pandas as pd
import numpy as np
import os as os
```


```python
# Set path for file
schools_csv = os.path.join("..", "HW4", "schools_complete.csv")
students_csv = os.path.join("..", "HW4", "students_complete.csv")

```


```python
# Read our Data file with the pandas library
# Not every CSV requires an encoding, but be aware this can come up
first_schools_df = pd.read_csv(schools_csv, encoding = "UTF-8")
first_students_df = pd.read_csv(students_csv, encoding = "UTF-8")

```


```python
# Using .rename(columns={}) in order to rename columns
schools_df = first_schools_df.rename(columns={"name":"School Name", "type":"School Type", "size":"Total Students","budget":"Total Budget"})

schools_df
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
      <th>School ID</th>
      <th>School Name</th>
      <th>School Type</th>
      <th>Total Students</th>
      <th>Total Budget</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>Figueroa High School</td>
      <td>District</td>
      <td>2949</td>
      <td>1884411</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>Shelton High School</td>
      <td>Charter</td>
      <td>1761</td>
      <td>1056600</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>Hernandez High School</td>
      <td>District</td>
      <td>4635</td>
      <td>3022020</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>Griffin High School</td>
      <td>Charter</td>
      <td>1468</td>
      <td>917500</td>
    </tr>
    <tr>
      <th>5</th>
      <td>5</td>
      <td>Wilson High School</td>
      <td>Charter</td>
      <td>2283</td>
      <td>1319574</td>
    </tr>
    <tr>
      <th>6</th>
      <td>6</td>
      <td>Cabrera High School</td>
      <td>Charter</td>
      <td>1858</td>
      <td>1081356</td>
    </tr>
    <tr>
      <th>7</th>
      <td>7</td>
      <td>Bailey High School</td>
      <td>District</td>
      <td>4976</td>
      <td>3124928</td>
    </tr>
    <tr>
      <th>8</th>
      <td>8</td>
      <td>Holden High School</td>
      <td>Charter</td>
      <td>427</td>
      <td>248087</td>
    </tr>
    <tr>
      <th>9</th>
      <td>9</td>
      <td>Pena High School</td>
      <td>Charter</td>
      <td>962</td>
      <td>585858</td>
    </tr>
    <tr>
      <th>10</th>
      <td>10</td>
      <td>Wright High School</td>
      <td>Charter</td>
      <td>1800</td>
      <td>1049400</td>
    </tr>
    <tr>
      <th>11</th>
      <td>11</td>
      <td>Rodriguez High School</td>
      <td>District</td>
      <td>3999</td>
      <td>2547363</td>
    </tr>
    <tr>
      <th>12</th>
      <td>12</td>
      <td>Johnson High School</td>
      <td>District</td>
      <td>4761</td>
      <td>3094650</td>
    </tr>
    <tr>
      <th>13</th>
      <td>13</td>
      <td>Ford High School</td>
      <td>District</td>
      <td>2739</td>
      <td>1763916</td>
    </tr>
    <tr>
      <th>14</th>
      <td>14</td>
      <td>Thomas High School</td>
      <td>Charter</td>
      <td>1635</td>
      <td>1043130</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Filter by district schools only
#district_schools_df = schools_df[schools_df["School Type"]=='District']
#district_schools_df
```


```python
# Using .rename(columns={}) in order to rename columns
students_df = first_students_df.rename(columns={"name":"Student Name", "gender":"Gender", "grade":"Grade","school":"School Name", "reading_score":"Avg Reading Score", "math_score":"Avg Math Score"})
students_df.head()
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
      <th>Student ID</th>
      <th>Student Name</th>
      <th>Gender</th>
      <th>Grade</th>
      <th>School Name</th>
      <th>Avg Reading Score</th>
      <th>Avg Math Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Paul Bradley</td>
      <td>M</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>66</td>
      <td>79</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>Victor Smith</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>94</td>
      <td>61</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>Kevin Rodriguez</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>90</td>
      <td>60</td>
    </tr>
    <tr>
      <th>3</th>
      <td>3</td>
      <td>Dr. Richard Scott</td>
      <td>M</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>67</td>
      <td>58</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>Bonnie Ray</td>
      <td>F</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>97</td>
      <td>84</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Reorganize and get rid of unnecessary columns
students_df = students_df[["Student Name", "Grade", "School Name", "Avg Reading Score", "Avg Math Score"]]
students_df.head()
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
      <th>Student Name</th>
      <th>Grade</th>
      <th>School Name</th>
      <th>Avg Reading Score</th>
      <th>Avg Math Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Paul Bradley</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>66</td>
      <td>79</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Victor Smith</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>94</td>
      <td>61</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Kevin Rodriguez</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>90</td>
      <td>60</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Dr. Richard Scott</td>
      <td>12th</td>
      <td>Huang High School</td>
      <td>67</td>
      <td>58</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Bonnie Ray</td>
      <td>9th</td>
      <td>Huang High School</td>
      <td>97</td>
      <td>84</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Merge the two DataFrames together based on the Dates they share
merge2_df = pd.merge(schools_df, students_df, on="School Name")
merge2_df.head()
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
      <th>School ID</th>
      <th>School Name</th>
      <th>School Type</th>
      <th>Total Students</th>
      <th>Total Budget</th>
      <th>Student Name</th>
      <th>Grade</th>
      <th>Avg Reading Score</th>
      <th>Avg Math Score</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>Paul Bradley</td>
      <td>9th</td>
      <td>66</td>
      <td>79</td>
    </tr>
    <tr>
      <th>1</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>Victor Smith</td>
      <td>12th</td>
      <td>94</td>
      <td>61</td>
    </tr>
    <tr>
      <th>2</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>Kevin Rodriguez</td>
      <td>12th</td>
      <td>90</td>
      <td>60</td>
    </tr>
    <tr>
      <th>3</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>Dr. Richard Scott</td>
      <td>12th</td>
      <td>67</td>
      <td>58</td>
    </tr>
    <tr>
      <th>4</th>
      <td>0</td>
      <td>Huang High School</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>Bonnie Ray</td>
      <td>9th</td>
      <td>97</td>
      <td>84</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Reorganize columns
merge_df = merge2_df[["School Name", "Avg Reading Score", "Avg Math Score", "School Type", "Total Students", "Total Budget", "Grade", "Student Name"]]
merge_df.head()
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
      <th>School Name</th>
      <th>Avg Reading Score</th>
      <th>Avg Math Score</th>
      <th>School Type</th>
      <th>Total Students</th>
      <th>Total Budget</th>
      <th>Grade</th>
      <th>Student Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Huang High School</td>
      <td>66</td>
      <td>79</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>9th</td>
      <td>Paul Bradley</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Huang High School</td>
      <td>94</td>
      <td>61</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>12th</td>
      <td>Victor Smith</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Huang High School</td>
      <td>90</td>
      <td>60</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>12th</td>
      <td>Kevin Rodriguez</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Huang High School</td>
      <td>67</td>
      <td>58</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>12th</td>
      <td>Dr. Richard Scott</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Huang High School</td>
      <td>97</td>
      <td>84</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>9th</td>
      <td>Bonnie Ray</td>
    </tr>
  </tbody>
</table>
</div>




```python
district_merge_df = merge_df[merge_df["School Type"]=='District']
district_merge_df.head()
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
      <th>School Name</th>
      <th>Avg Reading Score</th>
      <th>Avg Math Score</th>
      <th>School Type</th>
      <th>Total Students</th>
      <th>Total Budget</th>
      <th>Grade</th>
      <th>Student Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Huang High School</td>
      <td>66</td>
      <td>79</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>9th</td>
      <td>Paul Bradley</td>
    </tr>
    <tr>
      <th>1</th>
      <td>Huang High School</td>
      <td>94</td>
      <td>61</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>12th</td>
      <td>Victor Smith</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Huang High School</td>
      <td>90</td>
      <td>60</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>12th</td>
      <td>Kevin Rodriguez</td>
    </tr>
    <tr>
      <th>3</th>
      <td>Huang High School</td>
      <td>67</td>
      <td>58</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>12th</td>
      <td>Dr. Richard Scott</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Huang High School</td>
      <td>97</td>
      <td>84</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>9th</td>
      <td>Bonnie Ray</td>
    </tr>
  </tbody>
</table>
</div>




```python
# DISTRICT SUMMARY
# Create high level snapshot (in table form) of the district's key metrics, including:
# Total Schools, Total Students, Total Budget, Avg Math score, Avg Reading Score, % Passing Math, % Passing Reading
# Overall Passing Rage (average of the above two)
```


```python
# Get Index of columns
index_school_names = district_merge_df.columns
index_school_names
```




    Index(['School Name', 'Avg Reading Score', 'Avg Math Score', 'School Type',
           'Total Students', 'Total Budget', 'Grade', 'Student Name'],
          dtype='object')




```python
# Total Schools
count_schools = district_merge_df["School Name"].unique()
student_total_schools = len(count_schools)
student_total_schools
```




    7




```python
# Total Students
count_students = district_merge_df["Total Students"].unique()
total_students = count_students.sum()
total_students
```




    26976




```python
# Count Budget
count_budget = district_merge_df["Total Budget"].unique()
count_budget
```




    array([1910635, 1884411, 3022020, 3124928, 2547363, 3094650, 1763916])




```python
# Total Budget
total_budget = count_budget.sum()
total_budget
```




    17347923




```python
# Make sure data is clean and there are no missing rows
clean_academy_df = district_merge_df.dropna(how="any")
clean_academy_df.count()
```




    School Name          26976
    Avg Reading Score    26976
    Avg Math Score       26976
    School Type          26976
    Total Students       26976
    Total Budget         26976
    Grade                26976
    Student Name         26976
    dtype: int64




```python
# Count students at each school
total_schools = district_merge_df["School Name"].value_counts()
total_schools.head()
```




    Bailey High School       4976
    Johnson High School      4761
    Hernandez High School    4635
    Rodriguez High School    3999
    Figueroa High School     2949
    Name: School Name, dtype: int64




```python
# Average Math Score
avg_math_score = district_merge_df["Avg Math Score"].mean()
avg_math_score
```




    76.98702550415184




```python
# Average Reading Score
avg_reading_score = district_merge_df["Avg Reading Score"].mean()
avg_reading_score
```




    80.96248517200475




```python
# Count those Passing Math
count_pass_math = district_merge_df.loc[(merge_df["Avg Math Score"] >69)]
count_pass_math.head()
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
      <th>School Name</th>
      <th>Avg Reading Score</th>
      <th>Avg Math Score</th>
      <th>School Type</th>
      <th>Total Students</th>
      <th>Total Budget</th>
      <th>Grade</th>
      <th>Student Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>Huang High School</td>
      <td>66</td>
      <td>79</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>9th</td>
      <td>Paul Bradley</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Huang High School</td>
      <td>97</td>
      <td>84</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>9th</td>
      <td>Bonnie Ray</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Huang High School</td>
      <td>94</td>
      <td>94</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>9th</td>
      <td>Bryan Miranda</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Huang High School</td>
      <td>82</td>
      <td>80</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>11th</td>
      <td>Sheena Carter</td>
    </tr>
    <tr>
      <th>8</th>
      <td>Huang High School</td>
      <td>95</td>
      <td>87</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>10th</td>
      <td>Michael Roth</td>
    </tr>
  </tbody>
</table>
</div>




```python
math_number_pass = len(count_pass_math.index)
math_number_pass
```




    17944




```python
# Percent Passing Math
percent_pass_math = math_number_pass/total_students
percent_pass_math
```




    0.66518386714116251




```python
# Count those Passing Reading
count_pass_reading = district_merge_df.loc[(district_merge_df["Avg Reading Score"] >69)]
count_pass_reading.head()
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
      <th>School Name</th>
      <th>Avg Reading Score</th>
      <th>Avg Math Score</th>
      <th>School Type</th>
      <th>Total Students</th>
      <th>Total Budget</th>
      <th>Grade</th>
      <th>Student Name</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>1</th>
      <td>Huang High School</td>
      <td>94</td>
      <td>61</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>12th</td>
      <td>Victor Smith</td>
    </tr>
    <tr>
      <th>2</th>
      <td>Huang High School</td>
      <td>90</td>
      <td>60</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>12th</td>
      <td>Kevin Rodriguez</td>
    </tr>
    <tr>
      <th>4</th>
      <td>Huang High School</td>
      <td>97</td>
      <td>84</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>9th</td>
      <td>Bonnie Ray</td>
    </tr>
    <tr>
      <th>5</th>
      <td>Huang High School</td>
      <td>94</td>
      <td>94</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>9th</td>
      <td>Bryan Miranda</td>
    </tr>
    <tr>
      <th>6</th>
      <td>Huang High School</td>
      <td>82</td>
      <td>80</td>
      <td>District</td>
      <td>2917</td>
      <td>1910635</td>
      <td>11th</td>
      <td>Sheena Carter</td>
    </tr>
  </tbody>
</table>
</div>




```python
reading_number_pass = len(count_pass_reading.index)
reading_number_pass
```




    21825




```python
# Percent Passing Reading
percent_pass_reading = reading_number_pass/total_students
percent_pass_reading
```




    0.80905249110320288




```python
# Average Overall Passing Rate (average of reading and math pass percentages)
overall_passing = ((percent_pass_math + percent_pass_reading)/2)
overall_passing
```




    0.73711817912218269




```python
#DROP SCHOOL TYPE = DISTRICT
#merge_df.dropna(axis=0, how='all')
```


```python
# Make dictionary with answers
table_district_summary = pd.DataFrame(data={
    "Total Schools": student_total_schools,
    "Total Students": total_students,
    "Total Budget": total_budget,
    "Average Math Score": avg_math_score,
    "Average Reading Score": avg_reading_score,
    "% Passing Math": percent_pass_math,
    "% Passing Reading": percent_pass_reading,
    "% Overall Passing Rate": overall_passing,
    },index=[0])

table_district_summary
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
      <th>% Overall Passing Rate</th>
      <th>% Passing Math</th>
      <th>% Passing Reading</th>
      <th>Average Math Score</th>
      <th>Average Reading Score</th>
      <th>Total Budget</th>
      <th>Total Schools</th>
      <th>Total Students</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0.737118</td>
      <td>0.665184</td>
      <td>0.809052</td>
      <td>76.987026</td>
      <td>80.962485</td>
      <td>17347923</td>
      <td>7</td>
      <td>26976</td>
    </tr>
  </tbody>
</table>
</div>




```python
#**School Summary**

# Create an overview table that summarizes key metrics about each school, including:
  #* School Name
  #* School Type
  #* Total Students
  #* Total School Budget
  #* Per Student Budget
  #* Average Math Score
  #* Average Reading Score
  #* % Passing Math
  #* % Passing Reading
  #* Overall Passing Rate (Average of the above two)
```


```python
# Groupby
merge_df.groupby("School Name")["School Type"].min()

```




    School Name
    Bailey High School       District
    Cabrera High School       Charter
    Figueroa High School     District
    Ford High School         District
    Griffin High School       Charter
    Hernandez High School    District
    Holden High School        Charter
    Huang High School        District
    Johnson High School      District
    Pena High School          Charter
    Rodriguez High School    District
    Shelton High School       Charter
    Thomas High School        Charter
    Wilson High School        Charter
    Wright High School        Charter
    Name: School Type, dtype: object




```python
type_group = merge_df.groupby("School Name")["School Type"].min()
type_group
```




    School Name
    Bailey High School       District
    Cabrera High School       Charter
    Figueroa High School     District
    Ford High School         District
    Griffin High School       Charter
    Hernandez High School    District
    Holden High School        Charter
    Huang High School        District
    Johnson High School      District
    Pena High School          Charter
    Rodriguez High School    District
    Shelton High School       Charter
    Thomas High School        Charter
    Wilson High School        Charter
    Wright High School        Charter
    Name: School Type, dtype: object




```python
# Total students by school
total_students_school_name = merge_df.groupby("School Name")["Total Students"].min()
total_students_school_name
```




    School Name
    Bailey High School       4976
    Cabrera High School      1858
    Figueroa High School     2949
    Ford High School         2739
    Griffin High School      1468
    Hernandez High School    4635
    Holden High School        427
    Huang High School        2917
    Johnson High School      4761
    Pena High School          962
    Rodriguez High School    3999
    Shelton High School      1761
    Thomas High School       1635
    Wilson High School       2283
    Wright High School       1800
    Name: Total Students, dtype: int64




```python
# Total budget by school
total_budget_school_name = merge_df.groupby("School Name")["Total Budget"].min()
total_budget_school_name
```




    School Name
    Bailey High School       3124928
    Cabrera High School      1081356
    Figueroa High School     1884411
    Ford High School         1763916
    Griffin High School       917500
    Hernandez High School    3022020
    Holden High School        248087
    Huang High School        1910635
    Johnson High School      3094650
    Pena High School          585858
    Rodriguez High School    2547363
    Shelton High School      1056600
    Thomas High School       1043130
    Wilson High School       1319574
    Wright High School       1049400
    Name: Total Budget, dtype: int64




```python
# Per student budget
per_student = total_budget_school_name / total_students_school_name
per_student
```




    School Name
    Bailey High School       628.0
    Cabrera High School      582.0
    Figueroa High School     639.0
    Ford High School         644.0
    Griffin High School      625.0
    Hernandez High School    652.0
    Holden High School       581.0
    Huang High School        655.0
    Johnson High School      650.0
    Pena High School         609.0
    Rodriguez High School    637.0
    Shelton High School      600.0
    Thomas High School       638.0
    Wilson High School       578.0
    Wright High School       583.0
    dtype: float64




```python
# Average Math Score
avg_math_by_school = merge_df.groupby("School Name")["Avg Math Score"].mean()
avg_math_by_school
```




    School Name
    Bailey High School       77.048432
    Cabrera High School      83.061895
    Figueroa High School     76.711767
    Ford High School         77.102592
    Griffin High School      83.351499
    Hernandez High School    77.289752
    Holden High School       83.803279
    Huang High School        76.629414
    Johnson High School      77.072464
    Pena High School         83.839917
    Rodriguez High School    76.842711
    Shelton High School      83.359455
    Thomas High School       83.418349
    Wilson High School       83.274201
    Wright High School       83.682222
    Name: Avg Math Score, dtype: float64




```python
# Average Reading Score

avg_reading_score = merge_df.groupby("School Name")["Avg Reading Score"].mean().tolist()
avg_reading_score
```




    [81.03396302250803,
     83.97578040904197,
     81.15801966768396,
     80.74625775830594,
     83.816757493188,
     80.9344120819849,
     83.81498829039812,
     81.18272197463148,
     80.96639361478681,
     84.04469854469855,
     80.74468617154288,
     83.72572402044293,
     83.84892966360856,
     83.98948751642575,
     83.955]




```python
# Count those Passing Reading
passed_reading_total = merge_df.loc[merge_df["Avg Reading Score"] >69]
passed_reading_total.count()
```




    School Name          33610
    Avg Reading Score    33610
    Avg Math Score       33610
    School Type          33610
    Total Students       33610
    Total Budget         33610
    Grade                33610
    Student Name         33610
    dtype: int64




```python
# Get % Passing Reading
by_school_pass_read = passed_reading_total.groupby("School Name")["Total Students"].count()
by_school_pass_read
```




    School Name
    Bailey High School       4077
    Cabrera High School      1803
    Figueroa High School     2381
    Ford High School         2172
    Griffin High School      1426
    Hernandez High School    3748
    Holden High School        411
    Huang High School        2372
    Johnson High School      3867
    Pena High School          923
    Rodriguez High School    3208
    Shelton High School      1688
    Thomas High School       1591
    Wilson High School       2204
    Wright High School       1739
    Name: Total Students, dtype: int64




```python
by_school_pct_pass_read = by_school_pass_read/total_students_school_name
by_school_pct_pass_read
```




    School Name
    Bailey High School       0.819333
    Cabrera High School      0.970398
    Figueroa High School     0.807392
    Ford High School         0.792990
    Griffin High School      0.971390
    Hernandez High School    0.808630
    Holden High School       0.962529
    Huang High School        0.813164
    Johnson High School      0.812224
    Pena High School         0.959459
    Rodriguez High School    0.802201
    Shelton High School      0.958546
    Thomas High School       0.973089
    Wilson High School       0.965396
    Wright High School       0.966111
    Name: Total Students, dtype: float64




```python
# Count those passing math
# Count those Passing Reading
passed_math_total = merge_df.loc[merge_df["Avg Math Score"] >69]
passed_math_total.count()
```




    School Name          29370
    Avg Reading Score    29370
    Avg Math Score       29370
    School Type          29370
    Total Students       29370
    Total Budget         29370
    Grade                29370
    Student Name         29370
    dtype: int64




```python
# Get % Passing Reading
by_school_pass_math = passed_math_total.groupby("School Name")["Total Students"].count()
by_school_pass_math
```




    School Name
    Bailey High School       3318
    Cabrera High School      1749
    Figueroa High School     1946
    Ford High School         1871
    Griffin High School      1371
    Hernandez High School    3094
    Holden High School        395
    Huang High School        1916
    Johnson High School      3145
    Pena High School          910
    Rodriguez High School    2654
    Shelton High School      1653
    Thomas High School       1525
    Wilson High School       2143
    Wright High School       1680
    Name: Total Students, dtype: int64




```python
by_school_pct_pass_math = by_school_pass_math/total_students_school_name
by_school_pct_pass_math
```




    School Name
    Bailey High School       0.666801
    Cabrera High School      0.941335
    Figueroa High School     0.659885
    Ford High School         0.683096
    Griffin High School      0.933924
    Hernandez High School    0.667530
    Holden High School       0.925059
    Huang High School        0.656839
    Johnson High School      0.660576
    Pena High School         0.945946
    Rodriguez High School    0.663666
    Shelton High School      0.938671
    Thomas High School       0.932722
    Wilson High School       0.938677
    Wright High School       0.933333
    Name: Total Students, dtype: float64




```python
# (IGNORE) COUNT THOSE PASSING READING BY SCHOOL
#Loc and Iloc also allow for conditional statments to filter rows of data
#only_Huang_reading = merge_df.loc[(merge_df["School Name"] == "Huang High School") & (merge_df["Avg Reading Score"] > 69),:]
#only_Huang_reading.head()
```


```python
#Huang_read_pass = len(only_Huang_reading)
#Huang_read_pass
```


```python
#Huang_percent_pass_reading = Huang_read_pass/2917
#Huang_percent_pass_reading
```


```python
by_school_overall_pass_pct = ((by_school_pct_pass_math + by_school_pct_pass_read)/2)
by_school_overall_pass_pct
```




    School Name
    Bailey High School       0.743067
    Cabrera High School      0.955867
    Figueroa High School     0.733639
    Ford High School         0.738043
    Griffin High School      0.952657
    Hernandez High School    0.738080
    Holden High School       0.943794
    Huang High School        0.735002
    Johnson High School      0.736400
    Pena High School         0.952703
    Rodriguez High School    0.732933
    Shelton High School      0.948609
    Thomas High School       0.952905
    Wilson High School       0.952037
    Wright High School       0.949722
    Name: Total Students, dtype: float64




```python
table_school_summary = pd.DataFrame(data={
    "District or Charter": type_group,
    "Total Students": total_students_school_name,
    "Total School Budget": total_budget_school_name,
    "Per Student Budget": per_student,
    "Avg Math Score": avg_math_by_school,
    "Avg Reading Score": avg_reading_score,
    "% Pass Reading": by_school_pct_pass_read,
    "% Pass Math": by_school_pct_pass_math,
    "Overall Passing Rate": by_school_overall_pass_pct
})
table_school_summary
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
      <th>% Pass Math</th>
      <th>% Pass Reading</th>
      <th>Avg Math Score</th>
      <th>Avg Reading Score</th>
      <th>District or Charter</th>
      <th>Overall Passing Rate</th>
      <th>Per Student Budget</th>
      <th>Total School Budget</th>
      <th>Total Students</th>
    </tr>
    <tr>
      <th>School Name</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bailey High School</th>
      <td>0.666801</td>
      <td>0.819333</td>
      <td>77.048432</td>
      <td>81.033963</td>
      <td>District</td>
      <td>0.743067</td>
      <td>628.0</td>
      <td>3124928</td>
      <td>4976</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <td>0.941335</td>
      <td>0.970398</td>
      <td>83.061895</td>
      <td>83.975780</td>
      <td>Charter</td>
      <td>0.955867</td>
      <td>582.0</td>
      <td>1081356</td>
      <td>1858</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <td>0.659885</td>
      <td>0.807392</td>
      <td>76.711767</td>
      <td>81.158020</td>
      <td>District</td>
      <td>0.733639</td>
      <td>639.0</td>
      <td>1884411</td>
      <td>2949</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <td>0.683096</td>
      <td>0.792990</td>
      <td>77.102592</td>
      <td>80.746258</td>
      <td>District</td>
      <td>0.738043</td>
      <td>644.0</td>
      <td>1763916</td>
      <td>2739</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <td>0.933924</td>
      <td>0.971390</td>
      <td>83.351499</td>
      <td>83.816757</td>
      <td>Charter</td>
      <td>0.952657</td>
      <td>625.0</td>
      <td>917500</td>
      <td>1468</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <td>0.667530</td>
      <td>0.808630</td>
      <td>77.289752</td>
      <td>80.934412</td>
      <td>District</td>
      <td>0.738080</td>
      <td>652.0</td>
      <td>3022020</td>
      <td>4635</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <td>0.925059</td>
      <td>0.962529</td>
      <td>83.803279</td>
      <td>83.814988</td>
      <td>Charter</td>
      <td>0.943794</td>
      <td>581.0</td>
      <td>248087</td>
      <td>427</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <td>0.656839</td>
      <td>0.813164</td>
      <td>76.629414</td>
      <td>81.182722</td>
      <td>District</td>
      <td>0.735002</td>
      <td>655.0</td>
      <td>1910635</td>
      <td>2917</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <td>0.660576</td>
      <td>0.812224</td>
      <td>77.072464</td>
      <td>80.966394</td>
      <td>District</td>
      <td>0.736400</td>
      <td>650.0</td>
      <td>3094650</td>
      <td>4761</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <td>0.945946</td>
      <td>0.959459</td>
      <td>83.839917</td>
      <td>84.044699</td>
      <td>Charter</td>
      <td>0.952703</td>
      <td>609.0</td>
      <td>585858</td>
      <td>962</td>
    </tr>
    <tr>
      <th>Rodriguez High School</th>
      <td>0.663666</td>
      <td>0.802201</td>
      <td>76.842711</td>
      <td>80.744686</td>
      <td>District</td>
      <td>0.732933</td>
      <td>637.0</td>
      <td>2547363</td>
      <td>3999</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <td>0.938671</td>
      <td>0.958546</td>
      <td>83.359455</td>
      <td>83.725724</td>
      <td>Charter</td>
      <td>0.948609</td>
      <td>600.0</td>
      <td>1056600</td>
      <td>1761</td>
    </tr>
    <tr>
      <th>Thomas High School</th>
      <td>0.932722</td>
      <td>0.973089</td>
      <td>83.418349</td>
      <td>83.848930</td>
      <td>Charter</td>
      <td>0.952905</td>
      <td>638.0</td>
      <td>1043130</td>
      <td>1635</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <td>0.938677</td>
      <td>0.965396</td>
      <td>83.274201</td>
      <td>83.989488</td>
      <td>Charter</td>
      <td>0.952037</td>
      <td>578.0</td>
      <td>1319574</td>
      <td>2283</td>
    </tr>
    <tr>
      <th>Wright High School</th>
      <td>0.933333</td>
      <td>0.966111</td>
      <td>83.682222</td>
      <td>83.955000</td>
      <td>Charter</td>
      <td>0.949722</td>
      <td>583.0</td>
      <td>1049400</td>
      <td>1800</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Sort by Highest Overall Passing Rate

table_school_summary.sort_values("Overall Passing Rate", 0, 0)
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
      <th>% Pass Math</th>
      <th>% Pass Reading</th>
      <th>Avg Math Score</th>
      <th>Avg Reading Score</th>
      <th>District or Charter</th>
      <th>Overall Passing Rate</th>
      <th>Per Student Budget</th>
      <th>Total School Budget</th>
      <th>Total Students</th>
    </tr>
    <tr>
      <th>School Name</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Cabrera High School</th>
      <td>0.941335</td>
      <td>0.970398</td>
      <td>83.061895</td>
      <td>83.975780</td>
      <td>Charter</td>
      <td>0.955867</td>
      <td>582.0</td>
      <td>1081356</td>
      <td>1858</td>
    </tr>
    <tr>
      <th>Thomas High School</th>
      <td>0.932722</td>
      <td>0.973089</td>
      <td>83.418349</td>
      <td>83.848930</td>
      <td>Charter</td>
      <td>0.952905</td>
      <td>638.0</td>
      <td>1043130</td>
      <td>1635</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <td>0.945946</td>
      <td>0.959459</td>
      <td>83.839917</td>
      <td>84.044699</td>
      <td>Charter</td>
      <td>0.952703</td>
      <td>609.0</td>
      <td>585858</td>
      <td>962</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <td>0.933924</td>
      <td>0.971390</td>
      <td>83.351499</td>
      <td>83.816757</td>
      <td>Charter</td>
      <td>0.952657</td>
      <td>625.0</td>
      <td>917500</td>
      <td>1468</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <td>0.938677</td>
      <td>0.965396</td>
      <td>83.274201</td>
      <td>83.989488</td>
      <td>Charter</td>
      <td>0.952037</td>
      <td>578.0</td>
      <td>1319574</td>
      <td>2283</td>
    </tr>
    <tr>
      <th>Wright High School</th>
      <td>0.933333</td>
      <td>0.966111</td>
      <td>83.682222</td>
      <td>83.955000</td>
      <td>Charter</td>
      <td>0.949722</td>
      <td>583.0</td>
      <td>1049400</td>
      <td>1800</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <td>0.938671</td>
      <td>0.958546</td>
      <td>83.359455</td>
      <td>83.725724</td>
      <td>Charter</td>
      <td>0.948609</td>
      <td>600.0</td>
      <td>1056600</td>
      <td>1761</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <td>0.925059</td>
      <td>0.962529</td>
      <td>83.803279</td>
      <td>83.814988</td>
      <td>Charter</td>
      <td>0.943794</td>
      <td>581.0</td>
      <td>248087</td>
      <td>427</td>
    </tr>
    <tr>
      <th>Bailey High School</th>
      <td>0.666801</td>
      <td>0.819333</td>
      <td>77.048432</td>
      <td>81.033963</td>
      <td>District</td>
      <td>0.743067</td>
      <td>628.0</td>
      <td>3124928</td>
      <td>4976</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <td>0.667530</td>
      <td>0.808630</td>
      <td>77.289752</td>
      <td>80.934412</td>
      <td>District</td>
      <td>0.738080</td>
      <td>652.0</td>
      <td>3022020</td>
      <td>4635</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <td>0.683096</td>
      <td>0.792990</td>
      <td>77.102592</td>
      <td>80.746258</td>
      <td>District</td>
      <td>0.738043</td>
      <td>644.0</td>
      <td>1763916</td>
      <td>2739</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <td>0.660576</td>
      <td>0.812224</td>
      <td>77.072464</td>
      <td>80.966394</td>
      <td>District</td>
      <td>0.736400</td>
      <td>650.0</td>
      <td>3094650</td>
      <td>4761</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <td>0.656839</td>
      <td>0.813164</td>
      <td>76.629414</td>
      <td>81.182722</td>
      <td>District</td>
      <td>0.735002</td>
      <td>655.0</td>
      <td>1910635</td>
      <td>2917</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <td>0.659885</td>
      <td>0.807392</td>
      <td>76.711767</td>
      <td>81.158020</td>
      <td>District</td>
      <td>0.733639</td>
      <td>639.0</td>
      <td>1884411</td>
      <td>2949</td>
    </tr>
    <tr>
      <th>Rodriguez High School</th>
      <td>0.663666</td>
      <td>0.802201</td>
      <td>76.842711</td>
      <td>80.744686</td>
      <td>District</td>
      <td>0.732933</td>
      <td>637.0</td>
      <td>2547363</td>
      <td>3999</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Sort by Lowest Overall Passing Rate

table_school_summary.sort_values("Overall Passing Rate", 0, 1)
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
      <th>% Pass Math</th>
      <th>% Pass Reading</th>
      <th>Avg Math Score</th>
      <th>Avg Reading Score</th>
      <th>District or Charter</th>
      <th>Overall Passing Rate</th>
      <th>Per Student Budget</th>
      <th>Total School Budget</th>
      <th>Total Students</th>
    </tr>
    <tr>
      <th>School Name</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Rodriguez High School</th>
      <td>0.663666</td>
      <td>0.802201</td>
      <td>76.842711</td>
      <td>80.744686</td>
      <td>District</td>
      <td>0.732933</td>
      <td>637.0</td>
      <td>2547363</td>
      <td>3999</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <td>0.659885</td>
      <td>0.807392</td>
      <td>76.711767</td>
      <td>81.158020</td>
      <td>District</td>
      <td>0.733639</td>
      <td>639.0</td>
      <td>1884411</td>
      <td>2949</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <td>0.656839</td>
      <td>0.813164</td>
      <td>76.629414</td>
      <td>81.182722</td>
      <td>District</td>
      <td>0.735002</td>
      <td>655.0</td>
      <td>1910635</td>
      <td>2917</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <td>0.660576</td>
      <td>0.812224</td>
      <td>77.072464</td>
      <td>80.966394</td>
      <td>District</td>
      <td>0.736400</td>
      <td>650.0</td>
      <td>3094650</td>
      <td>4761</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <td>0.683096</td>
      <td>0.792990</td>
      <td>77.102592</td>
      <td>80.746258</td>
      <td>District</td>
      <td>0.738043</td>
      <td>644.0</td>
      <td>1763916</td>
      <td>2739</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <td>0.667530</td>
      <td>0.808630</td>
      <td>77.289752</td>
      <td>80.934412</td>
      <td>District</td>
      <td>0.738080</td>
      <td>652.0</td>
      <td>3022020</td>
      <td>4635</td>
    </tr>
    <tr>
      <th>Bailey High School</th>
      <td>0.666801</td>
      <td>0.819333</td>
      <td>77.048432</td>
      <td>81.033963</td>
      <td>District</td>
      <td>0.743067</td>
      <td>628.0</td>
      <td>3124928</td>
      <td>4976</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <td>0.925059</td>
      <td>0.962529</td>
      <td>83.803279</td>
      <td>83.814988</td>
      <td>Charter</td>
      <td>0.943794</td>
      <td>581.0</td>
      <td>248087</td>
      <td>427</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <td>0.938671</td>
      <td>0.958546</td>
      <td>83.359455</td>
      <td>83.725724</td>
      <td>Charter</td>
      <td>0.948609</td>
      <td>600.0</td>
      <td>1056600</td>
      <td>1761</td>
    </tr>
    <tr>
      <th>Wright High School</th>
      <td>0.933333</td>
      <td>0.966111</td>
      <td>83.682222</td>
      <td>83.955000</td>
      <td>Charter</td>
      <td>0.949722</td>
      <td>583.0</td>
      <td>1049400</td>
      <td>1800</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <td>0.938677</td>
      <td>0.965396</td>
      <td>83.274201</td>
      <td>83.989488</td>
      <td>Charter</td>
      <td>0.952037</td>
      <td>578.0</td>
      <td>1319574</td>
      <td>2283</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <td>0.933924</td>
      <td>0.971390</td>
      <td>83.351499</td>
      <td>83.816757</td>
      <td>Charter</td>
      <td>0.952657</td>
      <td>625.0</td>
      <td>917500</td>
      <td>1468</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <td>0.945946</td>
      <td>0.959459</td>
      <td>83.839917</td>
      <td>84.044699</td>
      <td>Charter</td>
      <td>0.952703</td>
      <td>609.0</td>
      <td>585858</td>
      <td>962</td>
    </tr>
    <tr>
      <th>Thomas High School</th>
      <td>0.932722</td>
      <td>0.973089</td>
      <td>83.418349</td>
      <td>83.848930</td>
      <td>Charter</td>
      <td>0.952905</td>
      <td>638.0</td>
      <td>1043130</td>
      <td>1635</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <td>0.941335</td>
      <td>0.970398</td>
      <td>83.061895</td>
      <td>83.975780</td>
      <td>Charter</td>
      <td>0.955867</td>
      <td>582.0</td>
      <td>1081356</td>
      <td>1858</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Math Scores by grade

#Count those passing math
# Count those Passing Reading
math_takers_9th_grade = merge_df.loc[merge_df["Grade"] == "9th"]
math_takers_9th_grade.count()

# Get % Passing Reading
#by_school_pass_math = passed_math_total.groupby("School Name")["Total Students"].count()
#by_school_pass_math
```




    School Name          11408
    Avg Reading Score    11408
    Avg Math Score       11408
    School Type          11408
    Total Students       11408
    Total Budget         11408
    Grade                11408
    Student Name         11408
    dtype: int64




```python
avg_math_score_by_grade = merge_df.groupby("Grade")["Avg Math Score"].mean()
avg_math_score_by_grade
```




    Grade
    10th    78.941483
    11th    79.083548
    12th    78.993164
    9th     78.935659
    Name: Avg Math Score, dtype: float64




```python
pd.DataFrame({"Avg Math Score": avg_math_score_by_grade})
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
      <th>Avg Math Score</th>
    </tr>
    <tr>
      <th>Grade</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>10th</th>
      <td>78.941483</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>79.083548</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>78.993164</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>78.935659</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Reading Scores by grade

avg_read_score_by_grade = merge_df.groupby("Grade")["Avg Reading Score"].mean()
avg_read_score_by_grade
```




    Grade
    10th    81.874410
    11th    81.885714
    12th    81.819851
    9th     81.914358
    Name: Avg Reading Score, dtype: float64




```python
pd.DataFrame({"Avg Reading Score": avg_read_score_by_grade})
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
      <th>Avg Reading Score</th>
    </tr>
    <tr>
      <th>Grade</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>10th</th>
      <td>81.874410</td>
    </tr>
    <tr>
      <th>11th</th>
      <td>81.885714</td>
    </tr>
    <tr>
      <th>12th</th>
      <td>81.819851</td>
    </tr>
    <tr>
      <th>9th</th>
      <td>81.914358</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Scores by School Budget
# Create the bins in which Data will be held
# Bins are 0 to 25, 25 to 50, 50 to 75, 75 to 100
bins = [0, 1000000, 2000000, 3000000, 4000000]

# Create the names for the four bins
group_names = ['Low', 'Moderate', 'High', 'Extremely High']
```


```python
# Cut Total Budget and place the values into bins
budget_binning = pd.cut(table_school_summary["Total School Budget"], bins, labels=group_names)
budget_binning.head()
```




    School Name
    Bailey High School      Extremely High
    Cabrera High School           Moderate
    Figueroa High School          Moderate
    Ford High School              Moderate
    Griffin High School                Low
    Name: Total School Budget, dtype: category
    Categories (4, object): [Low < Moderate < High < Extremely High]




```python
# Scores by School Spending (Total Budget)
table_school_summary["Budget Summary"] = pd.cut(table_school_summary["Total School Budget"], bins, labels=group_names)
table_school_summary
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
      <th>% Pass Math</th>
      <th>% Pass Reading</th>
      <th>Avg Math Score</th>
      <th>Avg Reading Score</th>
      <th>District or Charter</th>
      <th>Overall Passing Rate</th>
      <th>Per Student Budget</th>
      <th>Total School Budget</th>
      <th>Total Students</th>
      <th>Budget Summary</th>
    </tr>
    <tr>
      <th>School Name</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bailey High School</th>
      <td>0.666801</td>
      <td>0.819333</td>
      <td>77.048432</td>
      <td>81.033963</td>
      <td>District</td>
      <td>0.743067</td>
      <td>628.0</td>
      <td>3124928</td>
      <td>4976</td>
      <td>Extremely High</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <td>0.941335</td>
      <td>0.970398</td>
      <td>83.061895</td>
      <td>83.975780</td>
      <td>Charter</td>
      <td>0.955867</td>
      <td>582.0</td>
      <td>1081356</td>
      <td>1858</td>
      <td>Moderate</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <td>0.659885</td>
      <td>0.807392</td>
      <td>76.711767</td>
      <td>81.158020</td>
      <td>District</td>
      <td>0.733639</td>
      <td>639.0</td>
      <td>1884411</td>
      <td>2949</td>
      <td>Moderate</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <td>0.683096</td>
      <td>0.792990</td>
      <td>77.102592</td>
      <td>80.746258</td>
      <td>District</td>
      <td>0.738043</td>
      <td>644.0</td>
      <td>1763916</td>
      <td>2739</td>
      <td>Moderate</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <td>0.933924</td>
      <td>0.971390</td>
      <td>83.351499</td>
      <td>83.816757</td>
      <td>Charter</td>
      <td>0.952657</td>
      <td>625.0</td>
      <td>917500</td>
      <td>1468</td>
      <td>Low</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <td>0.667530</td>
      <td>0.808630</td>
      <td>77.289752</td>
      <td>80.934412</td>
      <td>District</td>
      <td>0.738080</td>
      <td>652.0</td>
      <td>3022020</td>
      <td>4635</td>
      <td>Extremely High</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <td>0.925059</td>
      <td>0.962529</td>
      <td>83.803279</td>
      <td>83.814988</td>
      <td>Charter</td>
      <td>0.943794</td>
      <td>581.0</td>
      <td>248087</td>
      <td>427</td>
      <td>Low</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <td>0.656839</td>
      <td>0.813164</td>
      <td>76.629414</td>
      <td>81.182722</td>
      <td>District</td>
      <td>0.735002</td>
      <td>655.0</td>
      <td>1910635</td>
      <td>2917</td>
      <td>Moderate</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <td>0.660576</td>
      <td>0.812224</td>
      <td>77.072464</td>
      <td>80.966394</td>
      <td>District</td>
      <td>0.736400</td>
      <td>650.0</td>
      <td>3094650</td>
      <td>4761</td>
      <td>Extremely High</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <td>0.945946</td>
      <td>0.959459</td>
      <td>83.839917</td>
      <td>84.044699</td>
      <td>Charter</td>
      <td>0.952703</td>
      <td>609.0</td>
      <td>585858</td>
      <td>962</td>
      <td>Low</td>
    </tr>
    <tr>
      <th>Rodriguez High School</th>
      <td>0.663666</td>
      <td>0.802201</td>
      <td>76.842711</td>
      <td>80.744686</td>
      <td>District</td>
      <td>0.732933</td>
      <td>637.0</td>
      <td>2547363</td>
      <td>3999</td>
      <td>High</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <td>0.938671</td>
      <td>0.958546</td>
      <td>83.359455</td>
      <td>83.725724</td>
      <td>Charter</td>
      <td>0.948609</td>
      <td>600.0</td>
      <td>1056600</td>
      <td>1761</td>
      <td>Moderate</td>
    </tr>
    <tr>
      <th>Thomas High School</th>
      <td>0.932722</td>
      <td>0.973089</td>
      <td>83.418349</td>
      <td>83.848930</td>
      <td>Charter</td>
      <td>0.952905</td>
      <td>638.0</td>
      <td>1043130</td>
      <td>1635</td>
      <td>Moderate</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <td>0.938677</td>
      <td>0.965396</td>
      <td>83.274201</td>
      <td>83.989488</td>
      <td>Charter</td>
      <td>0.952037</td>
      <td>578.0</td>
      <td>1319574</td>
      <td>2283</td>
      <td>Moderate</td>
    </tr>
    <tr>
      <th>Wright High School</th>
      <td>0.933333</td>
      <td>0.966111</td>
      <td>83.682222</td>
      <td>83.955000</td>
      <td>Charter</td>
      <td>0.949722</td>
      <td>583.0</td>
      <td>1049400</td>
      <td>1800</td>
      <td>Moderate</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Scores by School Size
# Create the bins in which Data will be held
# Bins are 0 to 25, 25 to 50, 50 to 75, 75 to 100
student_bins = [0, 1000, 2000, 4000, 5000]

# Create the names for the four bins
student_group_names = ['Low', 'Moderate', 'High', 'Extremely High']
```


```python
# Cut Total Budget and place the values into bins
student_binning = pd.cut(table_school_summary["Total Students"], student_bins, labels=student_group_names)
student_binning.head()
```




    School Name
    Bailey High School      Extremely High
    Cabrera High School           Moderate
    Figueroa High School              High
    Ford High School                  High
    Griffin High School           Moderate
    Name: Total Students, dtype: category
    Categories (4, object): [Low < Moderate < High < Extremely High]




```python
# Scores by School Spending (Total Budget)
table_school_summary["Total Students Summary"] = pd.cut(table_school_summary["Total Students"], student_bins, labels=student_group_names)
table_school_summary
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
      <th>% Pass Math</th>
      <th>% Pass Reading</th>
      <th>Avg Math Score</th>
      <th>Avg Reading Score</th>
      <th>District or Charter</th>
      <th>Overall Passing Rate</th>
      <th>Per Student Budget</th>
      <th>Total School Budget</th>
      <th>Total Students</th>
      <th>Budget Summary</th>
      <th>Total Students Summary</th>
    </tr>
    <tr>
      <th>School Name</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bailey High School</th>
      <td>0.666801</td>
      <td>0.819333</td>
      <td>77.048432</td>
      <td>81.033963</td>
      <td>District</td>
      <td>0.743067</td>
      <td>628.0</td>
      <td>3124928</td>
      <td>4976</td>
      <td>Extremely High</td>
      <td>Extremely High</td>
    </tr>
    <tr>
      <th>Cabrera High School</th>
      <td>0.941335</td>
      <td>0.970398</td>
      <td>83.061895</td>
      <td>83.975780</td>
      <td>Charter</td>
      <td>0.955867</td>
      <td>582.0</td>
      <td>1081356</td>
      <td>1858</td>
      <td>Moderate</td>
      <td>Moderate</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <td>0.659885</td>
      <td>0.807392</td>
      <td>76.711767</td>
      <td>81.158020</td>
      <td>District</td>
      <td>0.733639</td>
      <td>639.0</td>
      <td>1884411</td>
      <td>2949</td>
      <td>Moderate</td>
      <td>High</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <td>0.683096</td>
      <td>0.792990</td>
      <td>77.102592</td>
      <td>80.746258</td>
      <td>District</td>
      <td>0.738043</td>
      <td>644.0</td>
      <td>1763916</td>
      <td>2739</td>
      <td>Moderate</td>
      <td>High</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <td>0.933924</td>
      <td>0.971390</td>
      <td>83.351499</td>
      <td>83.816757</td>
      <td>Charter</td>
      <td>0.952657</td>
      <td>625.0</td>
      <td>917500</td>
      <td>1468</td>
      <td>Low</td>
      <td>Moderate</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <td>0.667530</td>
      <td>0.808630</td>
      <td>77.289752</td>
      <td>80.934412</td>
      <td>District</td>
      <td>0.738080</td>
      <td>652.0</td>
      <td>3022020</td>
      <td>4635</td>
      <td>Extremely High</td>
      <td>Extremely High</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <td>0.925059</td>
      <td>0.962529</td>
      <td>83.803279</td>
      <td>83.814988</td>
      <td>Charter</td>
      <td>0.943794</td>
      <td>581.0</td>
      <td>248087</td>
      <td>427</td>
      <td>Low</td>
      <td>Low</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <td>0.656839</td>
      <td>0.813164</td>
      <td>76.629414</td>
      <td>81.182722</td>
      <td>District</td>
      <td>0.735002</td>
      <td>655.0</td>
      <td>1910635</td>
      <td>2917</td>
      <td>Moderate</td>
      <td>High</td>
    </tr>
    <tr>
      <th>Johnson High School</th>
      <td>0.660576</td>
      <td>0.812224</td>
      <td>77.072464</td>
      <td>80.966394</td>
      <td>District</td>
      <td>0.736400</td>
      <td>650.0</td>
      <td>3094650</td>
      <td>4761</td>
      <td>Extremely High</td>
      <td>Extremely High</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <td>0.945946</td>
      <td>0.959459</td>
      <td>83.839917</td>
      <td>84.044699</td>
      <td>Charter</td>
      <td>0.952703</td>
      <td>609.0</td>
      <td>585858</td>
      <td>962</td>
      <td>Low</td>
      <td>Low</td>
    </tr>
    <tr>
      <th>Rodriguez High School</th>
      <td>0.663666</td>
      <td>0.802201</td>
      <td>76.842711</td>
      <td>80.744686</td>
      <td>District</td>
      <td>0.732933</td>
      <td>637.0</td>
      <td>2547363</td>
      <td>3999</td>
      <td>High</td>
      <td>High</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <td>0.938671</td>
      <td>0.958546</td>
      <td>83.359455</td>
      <td>83.725724</td>
      <td>Charter</td>
      <td>0.948609</td>
      <td>600.0</td>
      <td>1056600</td>
      <td>1761</td>
      <td>Moderate</td>
      <td>Moderate</td>
    </tr>
    <tr>
      <th>Thomas High School</th>
      <td>0.932722</td>
      <td>0.973089</td>
      <td>83.418349</td>
      <td>83.848930</td>
      <td>Charter</td>
      <td>0.952905</td>
      <td>638.0</td>
      <td>1043130</td>
      <td>1635</td>
      <td>Moderate</td>
      <td>Moderate</td>
    </tr>
    <tr>
      <th>Wilson High School</th>
      <td>0.938677</td>
      <td>0.965396</td>
      <td>83.274201</td>
      <td>83.989488</td>
      <td>Charter</td>
      <td>0.952037</td>
      <td>578.0</td>
      <td>1319574</td>
      <td>2283</td>
      <td>Moderate</td>
      <td>High</td>
    </tr>
    <tr>
      <th>Wright High School</th>
      <td>0.933333</td>
      <td>0.966111</td>
      <td>83.682222</td>
      <td>83.955000</td>
      <td>Charter</td>
      <td>0.949722</td>
      <td>583.0</td>
      <td>1049400</td>
      <td>1800</td>
      <td>Moderate</td>
      <td>Moderate</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Scores by School Type (District)
district_table_school_summary = table_school_summary[table_school_summary["District or Charter"]=='District']
district_table_school_summary.head()
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
      <th>% Pass Math</th>
      <th>% Pass Reading</th>
      <th>Avg Math Score</th>
      <th>Avg Reading Score</th>
      <th>District or Charter</th>
      <th>Overall Passing Rate</th>
      <th>Per Student Budget</th>
      <th>Total School Budget</th>
      <th>Total Students</th>
      <th>Budget Summary</th>
      <th>Total Students Summary</th>
    </tr>
    <tr>
      <th>School Name</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Bailey High School</th>
      <td>0.666801</td>
      <td>0.819333</td>
      <td>77.048432</td>
      <td>81.033963</td>
      <td>District</td>
      <td>0.743067</td>
      <td>628.0</td>
      <td>3124928</td>
      <td>4976</td>
      <td>Extremely High</td>
      <td>Extremely High</td>
    </tr>
    <tr>
      <th>Figueroa High School</th>
      <td>0.659885</td>
      <td>0.807392</td>
      <td>76.711767</td>
      <td>81.158020</td>
      <td>District</td>
      <td>0.733639</td>
      <td>639.0</td>
      <td>1884411</td>
      <td>2949</td>
      <td>Moderate</td>
      <td>High</td>
    </tr>
    <tr>
      <th>Ford High School</th>
      <td>0.683096</td>
      <td>0.792990</td>
      <td>77.102592</td>
      <td>80.746258</td>
      <td>District</td>
      <td>0.738043</td>
      <td>644.0</td>
      <td>1763916</td>
      <td>2739</td>
      <td>Moderate</td>
      <td>High</td>
    </tr>
    <tr>
      <th>Hernandez High School</th>
      <td>0.667530</td>
      <td>0.808630</td>
      <td>77.289752</td>
      <td>80.934412</td>
      <td>District</td>
      <td>0.738080</td>
      <td>652.0</td>
      <td>3022020</td>
      <td>4635</td>
      <td>Extremely High</td>
      <td>Extremely High</td>
    </tr>
    <tr>
      <th>Huang High School</th>
      <td>0.656839</td>
      <td>0.813164</td>
      <td>76.629414</td>
      <td>81.182722</td>
      <td>District</td>
      <td>0.735002</td>
      <td>655.0</td>
      <td>1910635</td>
      <td>2917</td>
      <td>Moderate</td>
      <td>High</td>
    </tr>
  </tbody>
</table>
</div>




```python
# Scores by School Type (Charter)
charter_table_school_summary = table_school_summary[table_school_summary["District or Charter"]=='Charter']
charter_table_school_summary.head()
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
      <th>% Pass Math</th>
      <th>% Pass Reading</th>
      <th>Avg Math Score</th>
      <th>Avg Reading Score</th>
      <th>District or Charter</th>
      <th>Overall Passing Rate</th>
      <th>Per Student Budget</th>
      <th>Total School Budget</th>
      <th>Total Students</th>
      <th>Budget Summary</th>
      <th>Total Students Summary</th>
    </tr>
    <tr>
      <th>School Name</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>Cabrera High School</th>
      <td>0.941335</td>
      <td>0.970398</td>
      <td>83.061895</td>
      <td>83.975780</td>
      <td>Charter</td>
      <td>0.955867</td>
      <td>582.0</td>
      <td>1081356</td>
      <td>1858</td>
      <td>Moderate</td>
      <td>Moderate</td>
    </tr>
    <tr>
      <th>Griffin High School</th>
      <td>0.933924</td>
      <td>0.971390</td>
      <td>83.351499</td>
      <td>83.816757</td>
      <td>Charter</td>
      <td>0.952657</td>
      <td>625.0</td>
      <td>917500</td>
      <td>1468</td>
      <td>Low</td>
      <td>Moderate</td>
    </tr>
    <tr>
      <th>Holden High School</th>
      <td>0.925059</td>
      <td>0.962529</td>
      <td>83.803279</td>
      <td>83.814988</td>
      <td>Charter</td>
      <td>0.943794</td>
      <td>581.0</td>
      <td>248087</td>
      <td>427</td>
      <td>Low</td>
      <td>Low</td>
    </tr>
    <tr>
      <th>Pena High School</th>
      <td>0.945946</td>
      <td>0.959459</td>
      <td>83.839917</td>
      <td>84.044699</td>
      <td>Charter</td>
      <td>0.952703</td>
      <td>609.0</td>
      <td>585858</td>
      <td>962</td>
      <td>Low</td>
      <td>Low</td>
    </tr>
    <tr>
      <th>Shelton High School</th>
      <td>0.938671</td>
      <td>0.958546</td>
      <td>83.359455</td>
      <td>83.725724</td>
      <td>Charter</td>
      <td>0.948609</td>
      <td>600.0</td>
      <td>1056600</td>
      <td>1761</td>
      <td>Moderate</td>
      <td>Moderate</td>
    </tr>
  </tbody>
</table>
</div>


