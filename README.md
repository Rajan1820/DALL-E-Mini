# Text-to-Image conversion using diffusion models

Bhuminjay Soni(B20CS009) \
Rajandeep Singh (B20CS049)


# Problem Formulation

Since the start of the Silicon Age \, there has been an increased trend to automate the tedious tasks of day\-to\-day life

Small things like the automatic doors at supermarkets to Self\-driving electric vehicles are the result of automation

This sudden and uprising urge of automate things took us to the domain of art and visualization

Using the power of AI to quickly turn our thoughts or imagination to real images just by entering our text

Getting any image we want \, in any format just a few clicks away

# Adopted Solution

Use of Text\-to\-Image Diffusion models to convert text prompt into a image which matches the user’s requirement

There are various ML models which make use of Diffusion models for conversion from text to images like DALL\-E and Imagen

The model that we work on is a mini version of DALL\-E which strips the bells and whistles of the very powerful and resource hungry DALL\-E into a more light weight version

# Diffusion Models

![alt text](https://github.com/Rajan1820/DALL-E-Mini/blob/master/img/pp10.png)

Diffusion Models are a subclass of generative models\, which are used to produce new data\, frequently pictorial data

Diffusion models are trained by introducing Gaussian noise to training pictures over a number of timesteps

After that Diffusion models learn how to remove that noise to generate new images

Learning to reverse the forward process can be reduced to learning to denoise the created noisy image into an estimation of the original data
![alt text](https://github.com/Rajan1820/DALL-E-Mini/blob/master/img/pp11.png)


# DALL-E Architecture

DALLE uses an OpenAI model called CLIP\(Contrastive Language\-Image Pre\-training\) to link the textual semantics to the image\.CLIP is trained on a large dataset of text and image pairs \, it maps the image and its associated captions to a higher dimensional space\.

DALLE now freezes the CLIP model &  reverses the image\-caption encoding of CLIP learned previously\.The connection between captions and visual encodings is easier to understand in a higher dimensional space\.

To perform the semantically correct image generation from visual encodings DALLE uses another model called GLIDE\(Guided Language\-to\-Image Diffusion for Generation and Editing\)\.
![alt text](https://github.com/Rajan1820/DALL-E-Mini/blob/master/img/pp12.png)


To connect the textual semantics to visual semantics DALLE uses a model called “prior” which is Diffusion model\, that connects the textual encodings of image captions to image encodings of the semantically related output image\.

Converts the text description into tokens which then maps the CLIP text encoding of these tokens to a semantically related CLIP image encoding\.

A Penguin riding bicycle at the coliseum of rome\, Digital art oil painting

![alt text](https://github.com/Rajan1820/DALL-E-Mini/blob/master/img/pp13.png)

_Working of DALL\-E_

# DALL-E Mini Architecture

![alt text](https://github.com/Rajan1820/DALL-E-Mini/blob/master/img/pp14.png)

Datasets used :  _[Conceptual Captions](https://github.com/google-research-datasets/conceptual-captions)_  \,  _[Conceptual 12M](https://github.com/google-research-datasets/conceptual-12m)_

VQGAN as the Image encoder

BART encoder as the text encoder

BART decoder as the image decoder

Data fed for training is image\-caption pairs

VQGAN converts the input image into a higher dimensional image encoding tokens

BART Encoder converts the text prompt into tokens which are then used by BART Decoder to create new image encodings

The loss is calculated through the cross\-entropy function

The text prompt is encoded by BART encoder into tokens

BART Decoder convert the above tokens into image encodings

VQGAN Decoder converts the image encodings into actual images

CLIP is used to rank the images based on the cosine similarity between text prompt and the generated images

![alt text](https://github.com/Rajan1820/DALL-E-Mini/blob/master/img/pp15.jpg)

_Working of DALL\-E Mini_

# Results on Custom Inputs

![alt text](https://github.com/Rajan1820/DALL-E-Mini/blob/master/img/pp16.png)

![alt text](https://github.com/Rajan1820/DALL-E-Mini/blob/master/img/pp17.png)

![alt text](https://github.com/Rajan1820/DALL-E-Mini/blob/master/img/pp18.png)

_“Eiffel tower at moon”_

_“Sunset at the Statue Of Liberty”_

_“Sunrise view from the Empire State building”_

# Limitations
![alt text](https://github.com/Rajan1820/DALL-E-Mini/blob/master/img/pp19.png)

![alt text](https://github.com/Rajan1820/DALL-E-Mini/blob/master/img/pp110.png)


Human Face

Animals

_Output for “Oil Painting of Marilyn Monroe”\(left\) versus the actual portrait of Marilyn Monroe\(right\)_
![alt text](https://github.com/Rajan1820/DALL-E-Mini/blob/master/img/pp111.png)


_“A cheetah and rabbit playing together”_

# References and Resources

_[https://arxiv\.org/abs/1910\.13461](https://arxiv.org/abs/1910.13461)_

_[https://medium\.com/nightcafe\-creator/vqgan\-clip\-tutorial\-a411402cf3ad](https://medium.com/nightcafe-creator/vqgan-clip-tutorial-a411402cf3ad)_

_[https://arxiv\.org/pdf/2205\.11487\.pdf](https://arxiv.org/pdf/2205.11487.pdf)_

_[https://openai\.com/blog/clip/](https://openai.com/blog/clip/)_

