# What is this project?
I've been learning a great deal of machine learning in my summer research scholarship at the Westmead Institute of Medical Research (WIMR) where I'm developing a radiomics tool for clinicians. In short, it's an application that will utilise machine learning to predict certain clinical outcome such as whether cancer will spread after treatment or is a tissue cancerous or benign. These predictions hopefully will help doctors by providing additional insights using past CT data.
I want to consolidate my learnings with a fun personal project and what better way than to make a Pokemon and Digimon classifier. When I have kids, I would want them to be able to know the difference between Pokemons or Digimons. (Pokemons are clearly more diverse and interesting)

TL;DR I wanted a fun project to summarise what I've learnt so far in my summer research scholarship.

# Where did I get the images from?
I downloaded the image of every Digimon from https://wikimon.net/Visual_List_of_Digimon and every Pokemon (up to Generation 7/Sun and Moon) from https://www.pokemon.com/us/pokedex/ using a chrome extension https://chrome.google.com/webstore/detail/download-all-images/ifipmflagepipjokmbdecpmjbibjnakm?hl=en.

# What did I do (in summary)?
I made sure to filter out useless images such as logos/banners that might have been in the website since the chrome extensions downloads all images on a website. Converted them into PNG so that a python package, resizeimage, will be able to make them into a consistent pixel size (I chose 215 x 215 pixels since most pokemon images was that size). Converted them into numbers into a numpy array, did some feature scaling and shoved them up a logistic regression model with ridge regularisation. 
```shell
It ended up having an accuracy of 0.8 and an AUC of 0.878 on the validation set.
```
AUC close to 1 is good and it's bad when it's around 0.5.I then performed a grid search and found that the large datasets take significantly more time so I made the images smaller into 40 x 40 pixels. The grid search returned values of penalty = 'l2' and C= 0.0020235896477251557.
```shell
This gave an accuracy of 0.8 and AUC of 0.877 which did not really improve on the model.
```

# What I've learnt and future steps?
This was great because it helped me familiarise myself with machine learning packages such as scikitlearn and also how to deal with image data.

Logistic regression worked better than I thought but I wanna be the best, Like no one ever was. I'll have to try more complex models than this to improve the prediction.

The value of refactoring code!! (Add more about this later)
