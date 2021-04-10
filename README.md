
**Product Categorisation with Supervised Learnining**
 

**Introduction**

So in this case we have to do a multi-class text classification using supervised learning methods which is quite a harder version of usual binary classification.We are going to classify a product into a classes based on the dataset provided.First we need to just have a look of the dataset to find some ways to get more insight into it  and try to relate more with real life scenarios if we can find out some way to solve problem.So yeah let us dive right into my approach for solving the problem
Approach,Data cleaning and pre-processing
For this project, we need only two columns — category and description.And our main goal is to predict the category of the product.We will remove missing values in description column, and add a  column encoding the category an integer because categorical variables(category_id in this case)are often better represented by integers than strings.Now one of the main challenges is to figure out  the main category for which we used simple string manipulation tasks.So I split string the based on the occurrence of ‘>’ inf the product_category_tree column and then take  1st element from there which is indeed the primary category for most of the dataset while few were still giving long and weird categories.You can see most of the products now have their category as their primary categoryi.e. Clothing,Furniture,Footwear,Baby Care.Now for visualisation of Data:-This is representing the Number of rows  of every unique category of product.(going max upto around 6000 for some categoriesand even very less for others)

**Classification**
The classifiers and learning algorithms can not directly process the text documents in their original form, as most of them expect numerical feature vectors with a fixed size rather than the raw text documents with variable length. Therefore, during the preprocessing step, the texts are converted to a more manageable representation.One common approach for extracting features from text is to use the bag of words model: a model where for each document, a complaint narrative in our case, the presence (and often the frequency) of words is taken into consideration, but the order in which they occur is ignored.Specifically, for each term in our dataset, we will calculate a measure called Term Frequency, Inverse Document Frequency, abbreviated to Tf-Idf.So we see that every category has around 19998 product descriptions are represented by 26910 feautures.

**Multi-Class Classifier: Features and Design:**                                                 
To train supervised classifiers, we first transformed the “description” into a vector of numbers. We explored vector representations such as TF-IDF weighted vectors.After having this vector representations of the text we can train supervised classifiers to train unseen “description” and predict the “category” on which they fall.After all the above data transformation, now that we have all the features and labels, it is time to train the classifiers. There are a number of algorithms we can use for this type of problem.So we are using Naive Bayes algorithm and also the multinomial variant of it as it is better and then we train and test the data.So after having fitted the training data we did the test and indeed got correct output based on the description(i.e  Clothing).Now let us try out different new models and find their accuracies and also visualise them using bloxplot.

**Model Selection**
We are now ready to experiment with different machine learning models, evaluate their accuracy and find the source of any potential issues.We will benchmark the following four models:
1)Logistic Regression(Multinomial)
2)Naive BayesLinear 
3)Support Vector Machine
4)Random Forest
Now we find out the accuracy of each of these models and compare them.
So we come to the understanding that LinearSVC( ) model gives the highest accuracy.

**Research Analysis:**
So from this we conclude that looking at data will give us insights only if we try to associate the problem with real life scenarios  and then apply algorithms  and models based on that which is vary suitable in NLP.As we saw that using TF-IDF was more convenient over BagWords because of the issue of underfitting and overfitting.Also that LinearSVC() is the best model for the purpose of Multi-class text classification.
