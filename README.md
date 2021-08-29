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
