# end2end-nlp-project
End 2 End NLP Project with Python


https://iverjaycel-capstone2-streamlit-app-wy5xs1.streamlitapp.com/


![[Pasted image 20220422125432.png]]
# Data preparation
Remove all username using this 
![image](https://user-images.githubusercontent.com/53965169/218959805-d997f7b5-18db-41a9-a86d-2406ba4b3030.png)
“stop words” usually refers to the most common words in a language.
remove special characters
# BUILD MODEL/PIPELINE
Built the model using linear mdoel logistic regression 
![image](https://user-images.githubusercontent.com/53965169/218959975-14320ad3-93f6-46ee-a980-3bf9416eabe3.png)

Data splitting, or commonly known as train-test split, is the partitioning of data into subsets for model training and evaluation separately.
## split before making the model
![image](https://user-images.githubusercontent.com/53965169/218960037-c9b793d4-a349-41d9-ac40-5506c86593a9.png)

The purpose of the pipeline is to assemble several steps that can be cross-validated together while setting different parameters. For this, it enables setting parameters of the various steps using their names and the parameter name separated by a `'__'`, as in the example below. A step’s estimator may be replaced entirely by setting the parameter with its name to another estimator, or a transformer removed by setting it to `'passthrough'` or `None`.
logistic regression pipeline
  
the estimator and  then the transformer
transforemer count vectorizer LogisticRegression model r
![image](https://user-images.githubusercontent.com/53965169/218960115-0617f036-92d9-4314-b74d-ad6b35530768.png)

Training data is also known as training dataset, learning set, and training set. It's an essential component of every machine learning model and helps them make accurate predictions or perform a desired task.
Simply put, training data builds the machine learning model. It teaches what the expected output looks like. The model analyzes the dataset repeatedly to deeply understand its characteristics and adjust itself for better performance.
![[Pasted image 20220422125145.png]]
Checking the accuracy
![[Pasted image 20220422125247.png]]

![[Pasted image 20220422125321.png]]

![[Pasted image 20220422125338.png]]

![[Pasted image 20220422125357.png]]
### What is pickling?[](https://flynn.gg/blog/machine-learning-model-serialization/#what-is-pickling)

Pickling is a way to write Python objects to a bytestream, which can then be written to disk as a file. One can take this file and load it back into a separate Python interpreter at a later date, recovering the objects from the previous session.

Pickled files are tightly coupled with the environment in which they were created. There is no guarantee that a pickled object in one version of Python will work in a previous or newer version. Similarly the imported objects that are used in pickled Python objects must also be available when deserializing. In general, the destination environment for a pickle file should have all of the dependencies and definitions required in the pickled objects.

### What can be pickled?[](https://flynn.gg/blog/machine-learning-model-serialization/#what-can-be-pickled)

According to [the documentation](https://docs.python.org/3/library/pickle.html), the following types can be pickled:

-   `None`, `True`, and `False`
-   integers, floating point numbers, complex numbers
-   strings, bytes, bytearrays
-   tuples, lists, sets, and dictionaries containing only picklable objects
-   functions defined at the top level of a module (using `def`, not `lambda`)
-   built-in functions defined at the top level of a module
-   classes that are defined at the top level of a module
-   instances of such classes whose `__dict__` or the result of calling `__getstate__()` is picklable (see section Pickling Class Instances for details).

_Note that functions (built-in and user-defined) are pickled by “fully qualified” name reference, not by value. This means that only the function name is pickled, along with the name of the module the function is defined in. Neither the function’s code, nor any of its function attributes are pickled. Thus the defining module must be importable in the unpickling environment, and the module must contain the named object, otherwise an exception will be raised._

The above implies that it is a necessary condition that classes and functions be importable in order to be unpicklable. This means that any custom function made in your script cannot be deserialized in another environment, unless it is part of an importable module in the unpickling environment.

### pickle[](https://flynn.gg/blog/machine-learning-model-serialization/#pickle)

The built in `pickle` module allows for the serialization of Python objects into a bytestream. This means you can save a Python object like a class instance to a file, send it to another environment or computer, and deserialize it back into a Python object to be interacted with again.

The `pickle` module can save and load class instances. However, when deserializing, the class definition must be importable from the same module path as in the original environment. If we try to pickle a `pytorch` model in a research environment, and then load it into a production environment that doesn’t have `pytorch` installed, the model will fail to deserialize.

### joblib[](https://flynn.gg/blog/machine-learning-model-serialization/#joblib)

The `joblib` package provides `dump` and `load` functions for serializing Python objects, with particular optimizations for large `numpy` arrays. It is intended to be a drop-in replacement for pickle and can be effective for `sklearn` models which store lots of data internally, such as random forest or cluster-based classifiers.
![[Pasted image 20220422125618.png]]
# Configure mode to streamlit
![[Pasted image 20220422125921.png]]
Max number of array is used to get confidence
![[Pasted image 20220422132214.png]]

# Delpoy the model in the web
Using github to push thru streamlit.io for deployment 


