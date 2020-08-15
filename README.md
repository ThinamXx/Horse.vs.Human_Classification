# **Horse and Human Classification with CNN**

**Convolutional Neural Network**
- In deep learning, a convolutional neural network is a class of deep neural networks, most commonly applied to analyzing visual imagery. They are also known as shift invariant or space invariant artificial neural networks, based on their shared-weights architecture and translation invariance characteristics.

#### **Getting the Data**
- I have downloaded the Data and stored in a specific directories using following lines of code.

- **For Training Data**

```javascript
!wget --no-check-certificate \
    https://storage.googleapis.com/laurencemoroney-blog.appspot.com/horse-or-human.zip \
    -O /tmp/horse-or-human.zip
```

- **For Validation Data**

```javascript
!wget --no-check-certificate \
    https://storage.googleapis.com/laurencemoroney-blog.appspot.com/validation-horse-or-human.zip \
    -O /tmp/validation-horse-or-human.zip
```

#### **Looking the Data or Data Visualization**
- I have presented the 8 pictures of horses and 8 pictures of humans which is presented below:

![Image](https://res.cloudinary.com/dge89aqpc/image/upload/v1597117520/Image_pzpzrn.png)

### **Convolutional Neural Network**
- In deep learning, a convolutional neural network is a class of deep neural networks, most commonly applied to analyzing visual imagery. They are also known as shift invariant or space invariant artificial neural networks, based on their shared-weights architecture and translation invariance characteristics.
- Building Convolutional Neural Network from scratch using Tensorflow and Keras API.
- Since it is a two class Classification problem i.e a Binary Classfication problem, I will use sigmoid activation so that the output of my network will be a single scalar between 0 and 1, encodig the probability of the images.

**Snapshot of the Model Summary**

![Image](https://res.cloudinary.com/dge89aqpc/image/upload/v1597117769/12_ly1rxg.png)

**Data Processing**
- I have used ImageDataGenerator to perform Data Processing. I will process our images by normalizing pixel values in range of [0, 1] which is originally in range of [0, 255]

```javascript
train_datagen = ImageDataGenerator(rescale=1./255)

train_generator = train_datagen.flow_from_directory(
    "/tmp/horse-or-human",
    target_size=(300, 300),
    batch_size=128,
    class_mode="binary"
)
```

**Model in Production**
-  I have used the picture of myself and the model predicted human, so the model is accurate in classification of human vs horse.

- **Snapshot of the Result**
![Image](https://res.cloudinary.com/dge89aqpc/image/upload/v1597118304/oUt_fiiyi9.png)

