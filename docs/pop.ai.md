<h1> Pop.AI </h1>
Pop.AI is easy and fast education Library for artificial intelligence. This Librariy supported Linear Regression, Logistic Regression, Perceptron, Artificial Neural Network(ANN), Deep Neural Network(DNN), Convolutional Neural Network(CNN) and Deep Q-Network(DQN).
<br>

<!-- # Class & Method Description-->
<hr/>

## <span class="title">Class</span> <span class="title_accent">**Linear_Regression**</span>    

<blockquote class="desc">A simple Linear Regression class for one to one datasets.</blockquote>

``` python
from pop.AI import Linear_Regression
```

<h5>&emsp;Initialization</h5>

&emsp;<code class="code_accent">Linear_Regression(restore=False, ckpt_name="linear_regression")</code> : Linear Regression Object<br>
&emsp;&emsp;**Params**    
&emsp;&emsp;&emsp;`restore` : Load a recently trained model.   
&emsp;&emsp;&emsp;`ckpt_name` : Custom model name for saving and loading.

<h5>&emsp;Definitions</h5>  

&emsp;<code class="code_accent">X_data</code> : Input data for training and prediction.    
&emsp;<code class="code_accent">Y_data</code> : Result data for training and prediction.     

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