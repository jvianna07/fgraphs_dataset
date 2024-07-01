# Function Graphs dataset description
This dataset contains a set of 14500 images of elementary mathematical functions labeled as:
```Python
{
0:'linear',
1:'quadratic',
2:'cubic',
3:'exponential',
4:'logaritmic',
5:'root',
6:'sine',
7:'cosine',
8:'tangent',
9:'cotangent'
}
```

Data are divided in train, validation and test. To read files, follow these steps:


1. Download file from:

https://anonymous.4open.science/r/fgraphs_dataset-FE19/fg_dataset.pkl.zip

2. Unpack zip file 'fg_dataset.pkl.zip'

3. Import necessary libraries
   
```Python
import pickle
import numpy as np
import matplotlib.pyplot as plt
```

4. Open and read dataset

```Python
# Replace 'fg_dataset.pkl' with path to the file
with open('fg_dataset.pkl','rb') as f:
    data = pickle.load(f)
```

5. Load data 

```Python
(x_train, y_train), (x_validation, y_validation), (x_test, y_test) = data
```

1. Reshape data 

```Python
x_train = np.array([image.reshape((128, 128, 3)) for image in x_train])
x_validation = np.array([image.reshape((128, 128, 3)) for image in x_validation])
x_test = np.array([image.reshape((128, 128, 3)) for image in x_test])
```

7. View a sample data
```Python
# Choose an integer number from 0 to 11600 for img_nr
img_nr=29
plt.imshow(x_train[img_nr])        
plt.show()
print ("This image belongs to class: ", np.argmax(y_train[img_nr]))
```