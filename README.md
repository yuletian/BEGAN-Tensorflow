# BEGAN implementation in Tensorflow

Paper: [BEGAN: Boundary Equilibrium Generative Adversarial Networks](https://arxiv.org/abs/1703.10717).

![alt tag](./readme/network.png)
![alt tag](./readme/paperresult.png)

## Requirements

- Python 2.7
- [Pillow](https://pillow.readthedocs.io/en/4.0.x/)
- [prettytensor](https://github.com/google/prettytensor)
- [scipy](https://github.com/scipy/scipy)
- progressbar
- TensorFlow 0.2.0 (or higher)


## Usage

First, download the [CelebA](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html) dataset

Second, extract the dataset and cut the image into 64x64

Third, the dataset folder should be like:

	dataset_folder
	|
	------xx.jpg
	|
	------aa.jpg

Fourth, train the model:

    $ python main.py --working_directory='A_PATH_TO_PLACE_YOUR_MODEL' --data_directory='A_PATH_TO_YUR_DATASET'
    fe:
    $ python main.py --working_directory='./celebA_train' --data_directory='../data/dataset'
   
Fifth, to view the result:

    the image generated by the model will be saved every 100 batch training.
    and the image will be place at:A_PATH_TO_PLACE_YOUR_MODEL/imgs/

Sixth, the model will be train and saved every 100 batch. You can continue your training:

    $ python main.py --working_directory='A_PATH_TO_PLACE_YOUR_MODEL'
    no data_directory needed this time.
   
    Agg.png are the images generated by the generator and the Agg_d.png are the images generated by autoencoder.

## Results

### [CelebA dataset] Autoencoded outputs (only after 4k step)

<img src="./readme/Agg_d.png" width="50%">


### [CelebA dataset] Generator outputs (only after 4k step)

<img src="./readme/Agg.png" width="50%">


### [Mnist dataset] Autoencoded outputs (only after 1.6k step)

<img src="./readme/Agg_d_mnist.png" width="50%">


### [Mnist dataset] Generator outputs (only after 1.6k step)

<img src="./readme/Agg_mnist.png" width="50%">


### [custom dataset] Autoencoded outputs (only after 1.2k step)

<img src="./readme/Agg_d_cust.png" width="50%">


###

For lack of training the model is still far from convergence.
In my experiment, began can convergent faster in CelebA dataset.
But it perform poorly in some really wild dataset.

My custom dataset is a set of shotcut built from over 156 cartoon videos.
BEGAN can not show any convergence clues in mine custom dataset.
However dcgan with batch discriminator can convergent on that.

### [custom dataset] DCGAN+BD Generator outputs (after 148k step)

![alt tag](./readme/Agg_148400.png)

### Measure of Convergence

![alt tag](./readme/pro.png)

I will update the result soon.
## Author

Yuletian
