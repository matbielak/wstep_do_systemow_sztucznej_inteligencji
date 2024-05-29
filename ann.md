### Creating ANN
```python
def createANN(n_layers, per_layer,input):
  neurons = []
  neurons.append([Neuron(0,value=input[i]) for i in range(per_layer[0])])
  for i in range(1,n_layers):
    neurons.append([Neuron(per_layer[i-1]) for _ in range(per_layer[i])])
  
  for i in range(1,n_layers):
    xs = [i.value for i in neurons[i-1]] 
    for j in range(per_layer[i]):
      value = neurons[i][j].__call__(xs)


# output - wartosc neuronu z ostatniej layer
  return value
```



### Visualising ANN
```python
import matplotlib.pyplot as plt
from matplotlib.patches import Circle
from matplotlib.lines import Line2D
perLayer = [3,4,4,1]
fig, ax = plt.subplots(figsize=(len(perLayer),max(perLayer)))
ax.axis('off')
for i in range(1,len(perLayer)):
  for j in range(perLayer[i]):
    for k in range(perLayer[i-1]):
      ax.add_artist(Line2D([(i)/(len(perLayer)+1)*len(perLayer),(i+1)/(len(perLayer)+1)*len(perLayer)], [(k+1)/(perLayer[i-1]+1)*max(perLayer),(j+1)/(perLayer[i]+1)*max(perLayer)], color='black', linewidth=1))

for i in range(len(perLayer)):
  for j in range(perLayer[i]):
    ax.add_patch(Circle(((i+1)/(len(perLayer)+1)*len(perLayer),(j+1)/(perLayer[i]+1)*max(perLayer)), 0.1, edgecolor='black', facecolor='green',zorder=5))
ax.set_aspect('equal', adjustable='box')
ax.set_xlim(0, len(perLayer))
ax.set_ylim(0, max(perLayer))
plt.show()
```
![image](https://github.com/matbielak/wstep_do_systemow_sztucznej_inteligencji/assets/100089973/19161bb6-27e6-42c2-a65b-43b9fbd02cf8)
