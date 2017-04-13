# BEGAN implementation in Tensorflow

Paper[BEGAN: Boundary Equilibrium Generative Adversarial Networks](https://arxiv.org/abs/1703.10717).

![alt tag](./readme/network.png)
![alt tag](./readme/paperresult.png)

## Requirements

- Python 2.7
- Pillow
- prettytensor
- scipy
- progressbar
- TensorFlow 0.2.0 (or higher)


## Usage

1. First, download the [CelebA](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html) dataset

2. Second, extract the dataset and cut the image into 64x64

3. Third, the dataset folder should be like:
	dataset_folder
	|
	------xx.jpg
	|
	------aa.jpg
4. Four, train the model:
   $ python main.py --working_directory='A_PATH_TO_PLACE_YOUR_MODEL' --data_directory='A_PATH_TO_YUR_DATASET'
   fe:
   $ python main.py --working_directory='./celebA_train' --data_directory='../data/dataset'
   
5. Five, to view the result:
   the image generated by the model will be saved every 100 batch training.
   and the image will be place at:A_PATH_TO_PLACE_YOUR_MODEL/imgs/

6. Six, the model will be train and saved every 100 batch. You can go on training:
   $ python main.py --working_directory='A_PATH_TO_PLACE_YOUR_MODEL'
   no data_directory needed this time.
   
   Agg.png are the images generated by the generator and the Agg_d.png are the images generated by autoencoder.

## Results

### [CelebA dataset] Autoencoded Generator outputs (after only 6.2k step)

<img src="./readme/Agg_d.png" width="50%">


### [CelebA dataset] Generator and Discriminator outputs (after only 6.2k step)

<img src="./readme/Agg.png" width="50%">


### [Mnist dataset] Autoencoded Generator outputs (after only 3.4k step)

<img src="./readme/Agg_d_mnist.png" width="50%">


### [Mnist dataset] Generator and Discriminator outputs (after only 3.4k step)

<img src="./readme/Agg_mnist.png" width="50%">


### [custom dataset] Autoencoded Generator outputs (after only 1.2k step)

<img src="./readme/Agg_d_cust.png" width="50%">


###

For lack of training the model is still far from convergence.
In my experiment, began can convergent faster in CelebA dataset.
But it perform poorly in some really wild dataset.

My custom dataset is a set of shotcut built from over 156 cartoon videos.
BEGAN can not show any convergence clues in mine custom dataset.
However dcgan with batch discriminator can convergent on that.

I will update the result soon.

![alt tag](./readme/pro.png)

## Author

Yuletian
