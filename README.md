# That´s your diamos price! - IronHack Proyect module 3
Ironhack Madrid - Data Analytics Part Time - April 2021 - Project Module 3 - Antonio Huerta
<p align="left"><img src="https://cdn-images-1.medium.com/max/184/1*2GDcaeYIx_bQAZLxWM4PsQ@2x.png"></p>

## BRIEFING  📌

Create an algorithm to predict the price of diamonds based on their characteristics. This will allow users to make their budget for their weddings 

Diamonds have some features that our solution 

- **price:**  price in USD
- **carat:**  weight of the diamond
- **cut:**  quality of the cut (Fair, Good, Very Good, Premium, Ideal)
- **color:**  diamond colour, from J (worst) to D (best)
- **clarity:**  a measurement of how clear the diamond is (I1 (worst), SI2, SI1, VS2, VS1, VVS2, VVS1, IF (best))
- **x:**  length in mm
- **y:**  width in mm
- **z:**  depth in mm
- **depth_**  total depth percentage = z / mean(x, y) = 2 * z / (x + y) (43--79)
- **table:**  width of top of diamond relative to widest point (43--95)
- **cit:y**  city where the diamonds is reported to be sold.


### WorkFlow Description  📋

To train our algorithm we where provide from two main datasources:

## RAW DATA COLLECTED

- **Training dataset:** diamonds_train.db 
- **Test dataset:** diamonds_test.csv
- **Sample submission file in the correct format:** sample_submission.csv

## DATA PROCESING

You can find at [data] folder a file, called [diamondssql.csv]: I used Dbeaver to manipulate de database s the result of a Query on SQL 

I used Dbeaver to manipulate the database and export [diamondssql.csv].

The query I used to create the data procesed is:

```
SELECT tr.index_id, c.clarity, cl.color, ct.cut, dm.depth, dm.'table', dm.x, dm.y, dm.z, tr.price, ci.city, tr.carat
FROM diamonds_properties pr
   INNER JOIN diamonds_clarity c ON pr.clarity_id = c.clarity_id 
   INNER JOIN diamonds_color cl on pr.color_id = cl.color_id 
   INNER JOIN diamonds_cut ct on pr.cut_id = ct.cut_id 
   INNER JOIN diamonds_dimensions dm on pr.index_id = dm.index_id
   INNER JOIN diamonds_transactional tr on pr.index_id = tr.index_id
   INNER JOIN diamonds_city ci on tr.city_id = ci.city_id

```
Once I have my dataset ready to manipulate and get clean for train my model.

## DATA PROCESING
You will find [exercise.ipynb] in the main folder of the proyect. To process my data i follow the next steeps:

- Import libraries
- Export dataset of train and test dataset
- Train Dataset manipulation: Erase city columnd and used encoder to transform categorical features in numerical features (Cut,Color,Cut and clarity)


## MODEL ML PROCESS
- Define target and features
- Separate dataset (80/20) for train the model.
- Select Model: RandomForest
- Execute model
- Evaluate RMSE 

## SUMBISSION
- Execute model on test dataset.
- Submit cvs fil with the result

### Into the box - Folders & files  📦

In This repo you will find the following folders:

- Data - Where info from source is hosted as bicimad.
- Submision - Here you will find the result of your exercise
- exercise.ipynb - Where you will find algorithm scripts


### Requirements: Install libraries ⚙️

You will need to install the following libraries in your project enviroment to execute **ShowmyBike**

- [Python 3.7](https://www.python.org/) - Lenguaje principal
- [Pandas](https://pandas.pydata.org/pandas-docs/stable/reference/index.html)
- [sklearn](https://docs.python.org/3.7/library/argparse.html)
- [Numpy](https://docs.python.org/3.7/library/argparse.html)
- [Matplotlib](https://docs.python.org/3.7/library/argparse.html)


### Tools & Frameworks 🛠️

This tools help me to works better: 

* [Python](https://www.python.org/) - Lenguaje principal
* [GitHub](https://jupyter.org/) - Usado como repositorio de código.
* [Visual Studio Code](https://code.visualstudio.com/) - Usado como editor de código.
* [Kaggle](https://www.kaggle.com/competitions/dataptmad1121/code) - Used to manage the competition
* [DBeaver](https://dbeaver.io//) - Used to manipulate SQL and transform Raw data.


### Thanks to 🎁

* Tito Gerva, who works with me with a lot of patience and a bunch of good humor when things are not going well.
* Pablo Montes, Withouth his help I will still learning my model with the wrong dataset.
* Diego Merello, Panda´s Ninja, Github Jedi, Gandalf of diamonds. His advice is always a great choice.     
* All Ironhack Datamates, smart, solidary and great people!
* I owe you some beers guys!🍺🍺🍺🍺🍺  


### Author ✒️

* **Antonio Huerta** - *Proyecto 1 IronHack*: Showmybike
---
⌨️ con ❤️ por [Antonio Huerta](https://github.com/napoleonthevitzla)🤓