# Data-Visualization-on-titanic-dataset
## Survived by ages
```
import matplotlib.pyplot as plt

ages_dict = {}
for i in survived_data['Age']:
  if i not in ages_dict:
    ages_dict[i] = 1
  else:
    ages_dict[i] += 1

ages_values = ages_dict.values()
ages_keys = ages_dict.keys()

plt.figure(figsize=(10,8))
plt.bar(ages_keys, ages_values)
plt.xticks(np.arange(0, 85, 5))
plt.yticks(np.arange(0, 16, 1))
plt.title('Survived ages')
plt.xlabel('Ages')
plt.ylabel('Total')
plt.show()
```
[![data-visualization-survived-titanic-by-ages.jpg](https://i.postimg.cc/brvhqXHm/data-visualization-survived-titanic-by-ages.jpg)](https://postimg.cc/qhWYG5FK)

## Survived by sex
```
sex_dict = {}

for i in survived_data['Sex']:
  if i not in sex_dict:
    sex_dict[i] = 1
  else:
    sex_dict[i] += 1

fig, ax = plt.subplots(figsize=(8,6))
ax.bar(sex_dict.keys(),sex_dict.values())
ax.set_title("Survived: Male vs Female")
ax.set_yticks(np.arange(0,201,50))
plt.show()
```
[![data-visualization-survived-titanic-by-sex.jpg](https://i.postimg.cc/VLbhnL6j/data-visualization-survived-titanic-by-sex.jpg)](https://postimg.cc/GHdz1Rv2)

## Survived by embarked
```
embarked_dict = {}

for i in survived_data['Embarked'].astype('string').dropna():
  if i not in embarked_dict:
    embarked_dict[i] = 1
  else:
    embarked_dict[i] += 1

fig, ax = plt.subplots(figsize=(8,6))
ax.bar(embarked_dict.keys(),embarked_dict.values())
ax.set_title("Survived by embarked")
ax.set_xticklabels(["Cherbourgh\n"+str(embarked_dict["C"]),"Southampton\n"+str(embarked_dict['S']),"Queenstown\n"+str(embarked_dict["Q"])])
plt.show()
```
[![data-visualization-survived-titanic-by-embarked-bar.jpg](https://i.postimg.cc/HkVm7CM5/data-visualization-survived-titanic-by-embarked-bar.jpg)](https://postimg.cc/DSkHtHBy)
```
plt.figure(figsize=(10,8))
plt.title("Percentage survived from embarked")
plt.pie(embarked_dict.values(),labels=["Cherbourgh","Southampton","Queenstown"],autopct='%.0f%%')
plt.show()
```
[![data-visualization-survived-titanic-by-embarked-pie.jpg](https://i.postimg.cc/qqJVBf0N/data-visualization-survived-titanic-by-embarked-pie.jpg)](https://postimg.cc/ph61k6mv)
