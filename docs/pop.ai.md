<h1> Pop.AI </h1>
Pop.AI is easy and fast education Library for artificial intelligence. This Librariy supported Linear Regression, Logistic Regression, Perceptron, Artificial Neural Network(ANN), Deep Neural Network(DNN), Convolutional Neural Network(CNN) and Deep Q-Network(DQN).
<br>

<!-- # Class & Method Description-->
<hr/>

## <span class="title">Class</span> <span class="title_accent">**Linear_Regression**</span>    

<blockquote class="desc">A simple Linear Regression class for one to one datasets.</blockquote>

The code to import the Linear_Regression Class :

``` python
from pop.AI import Linear_Regression
```

<h5>&emsp;Initialization</h5>

&emsp;<code class="code_accent">Linear_Regression(restore=False, ckpt_name="linear_regression_models")</code> : Linear Regression Object<br>
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`restore` : Load the recently trained model.   
&emsp;&emsp;&emsp;`ckpt_name` : Custom model name for saving and loading.

<h5>&emsp;Variables</h5>  

&emsp;<code class="code_accent">X_data</code> : Input data for training and prediction. It must be a 1-Dimensional Array. (ex, [0, 1, 2, 3])    
&emsp;<code class="code_accent">Y_data</code> : Result data for training and prediction. It must be a 1-Dimensional Array. (ex, [0, 2, 4, 6])     

<h5>&emsp;Methods</h5>

&emsp;<code class="code_accent">train(times=100, print_every=10)</code> : Train datasets as Linear Regression.  
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`times` : Number of training. ( = Epochs )   
&emsp;&emsp;&emsp;`print_every` : Training status printing cycle.  

&emsp;<code class="code_accent">run(inputs=X_data)</code> : Predict as trained Linear Regression.   
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`inputs` : Data to predict.   

&emsp;<code class="code_accent">save(path=ckpt_name)</code> : Save current model of this object.   
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`path` : Path to save. 

&emsp;<code class="code_accent">load(path=ckpt_name)</code> : Load a model in path.   
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`path` : Path to load. 

---

## <span class="title">Class</span> <span class="title_accent">**Logistic_Regression**</span>    

<blockquote class="desc">A simple Logistic Regression class for many to one datasets.</blockquote>

The code to import the Logistic_Regression Class :

``` python
from pop.AI import Logistic_Regression
```

<h5>&emsp;Initialization</h5>

&emsp;<code class="code_accent">Logistic_Regression(input_size=1, restore=False, ckpt_name="logistic_regression_models")</code> : Logistic Regression Object<br>
&emsp;&emsp;**Params**  
&emsp;&emsp;&emsp;`input_size` : Size of one dataset input.   
&emsp;&emsp;&emsp;`restore` : Load the recently trained model.   
&emsp;&emsp;&emsp;`ckpt_name` : Custom model name for saving and loading.

<h5>&emsp;Variables</h5>  

&emsp;<code class="code_accent">X_data</code> : Input data for training and prediction. It must be a 2-Dimensional Array. (ex, [[0, 1], [3, 2]])      
&emsp;<code class="code_accent">Y_data</code> : Result data for training and prediction. It must be a 2-Dimensional Array. (ex, [[0], [1]])       

<h5>&emsp;Methods</h5>

&emsp;<code class="code_accent">train(times=100, print_every=10)</code> : Train datasets as Logistic Regression.  
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`times` : Number of training. ( = Epochs )   
&emsp;&emsp;&emsp;`print_every` : Training status printing cycle.  

&emsp;<code class="code_accent">run(inputs=X_data)</code> : Predict as trained Logistic Regression.   
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`inputs` : Data to predict.   

&emsp;<code class="code_accent">save(path=ckpt_name)</code> : Save current model of this object.   
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`path` : Path to save. 

&emsp;<code class="code_accent">load(path=ckpt_name)</code> : Load a model in path.   
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`path` : Path to load. 

---

## <span class="title">Class</span> <span class="title_accent">**Perceptron**</span>    

<blockquote class="desc">A simple Perceptron class for many to many datasets.</blockquote>

The code to import the Perceptron Class :

``` python
from pop.AI import Perceptron
```

<h5>&emsp;Initialization</h5>

&emsp;<code class="code_accent">Perceptron(input_size, output_size=1, restore=False, ckpt_name="perceptron_models", softmax=True)</code> : Perceptron Object<br>
&emsp;&emsp;**Params**  
&emsp;&emsp;&emsp;`input_size` : Size of one dataset input.   
&emsp;&emsp;&emsp;`output_size` : Size of one dataset output.  
&emsp;&emsp;&emsp;`restore` : Load the recently trained model.   
&emsp;&emsp;&emsp;`ckpt_name` : Custom model name for saving and loading.   
&emsp;&emsp;&emsp;`softmax` : Process output as Softmax Function. However, process as Sigmoid Function if output size is 1.   

<h5>&emsp;Variables</h5>  

&emsp;<code class="code_accent">X_data</code> : Input data for training and prediction. It must be a 2-Dimensional Array. (ex, [[0, 1], [3, 2]])      
&emsp;<code class="code_accent">Y_data</code> : Result data for training and prediction. It must be a 2-Dimensional Array. (ex, [[0], [1]])       

<h5>&emsp;Methods</h5>

&emsp;<code class="code_accent">train(times=100, print_every=10)</code> : Train datasets as Logistic Regression.  
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`times` : Number of training. ( = Epochs )   
&emsp;&emsp;&emsp;`print_every` : Training status printing cycle.  

&emsp;<code class="code_accent">run(inputs=X_data)</code> : Predict as trained Logistic Regression.   
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`inputs` : Data to predict.   

&emsp;<code class="code_accent">save(path=ckpt_name)</code> : Save current model of this object.   
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`path` : Path to save. 

&emsp;<code class="code_accent">load(path=ckpt_name)</code> : Load a model in path.   
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`path` : Path to load. 

---