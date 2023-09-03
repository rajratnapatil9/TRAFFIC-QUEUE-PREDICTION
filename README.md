<h1>TRAFFIC-QUEUE-PREDICTION</h1>
<p>The QUEUE stuck at a traffic signal is monitored regularly to implement signal optimization. it is essentially important that the Queue should be between designated stop-bars and shouldn't exceed it. </p>
<br>
<h2>Project Statement/Goals</h2>
<br>
<li>How can we leverage existing HiRes stop bar video detection in the City of Detroit to predict performance (queuing ) at Urban intersections?  
</li>
<li>If so, how accurately can that be done relative to existing state of the practice metrics? 
</li>
<li>Are there other existing data that can be leveraged to improve the accuracy of the performance metrics ? 
</li>
<h2>Objective Statement</h2>
<br>

<li>Collect and Visualize existing High Resolution Signal Controller data at an intersections in the city of Detroit. 
</li>
<li>Attempt to create a Methodology to define the performance measure logic using stop bar detection
</li>
<li>Allow method to be able to Scale and measure the performance difference between advanced and stop bar logic.
</li> 

<center><img src = images\hres.png ></center>

<br>
<h2>Methodology</h2>

<li>Data Extraction from Hres - Mio Vision API</l1>
<li>Data Wrangling for Analysis</l1>
<li>Data Analysis and Visualization</li>
<li>Classification Models for test predictions</li>
<li>Project Conclusion</li>
<br><br>
<center><img src = images\method.jpg ></center>

<h2>DATA SET</h2>
<br>

<p> After Data Extraction we sleected the folowing sample</p>
<br>
<h4>DATA DIMENSION: 1343 x 19 (final set)</h4>
<br>
<center><img src= images\dataset.png ></center>

<h2>MODEL BUILDING</h2>
<br>
<li>From the Analysis and statiscal Analysis , it was evident that the Data was non Linear in nature, so some non linear classification models were choosen for model uilding efforts</li> 

<li> To test how linear models will work with non linear  data , some linear classification models were also used.</li>

<h3> Linear Models Tested</h3>
<br>
<li>1. Gaussian Naïve Bayes</li>
<li>2. Logistic Regression</li>
<li>3. Linear Discriminant Analysis</li>

<h3>Non-Linear Models Tested</h3>
<li>1. Decision Tree</li>
<li>2. K nearest Neighbors</li>
<li>3. SVM</li>
<li>4. NN -Multilayer Perceptron</li>

<h2> MODEL COMPARISION</h2>
<br>
<br>

<table align ="center" style ="border: 2px solid black">
<caption style ="font-size: 18px; font-weight: bold ;color: green; padding: 10px">Model Statistics</caption>
<th>SR</th>
<th>MODEL</th>
<th>TRAINING ACCURACY</th>
<th>TESTING ACCURACY</th>
<tr >
<td style="text-align: center">1</td>
<td style="text-align: center">Gaussian Naïve Bayes</td>
<td style="text-align: center">0.52</td>
<td style="text-align: center">0.52</td>
</tr>



<tr >
<td style="text-align: center">2</td>
<td style="text-align: center">Logistic Regression</td>
<td style="text-align: center">0.82</td>
<td style="text-align: center">0.83</td>
</tr>



<tr >
<td style="text-align: center">3</td>
<td style="text-align: center">Linear Discriminant Analysis</td>
<td style="text-align: center">0.81</td>
<td style="text-align: center">0.82</td>
</tr>


<tr >
<td style="text-align: center">4</td>
<td style="text-align: center"> Decision Tree</td>
<td style="text-align: center">1</td>
<td style="text-align: center">0.75</td>
</tr>

<tr >
<td style="text-align: center ">5</td>
<td style="text-align: center;background-color: green"> K nearest Neighbors</td>
<td style="text-align: center; background-color: green">0.85</td>
<td style="text-align: center;background-color: green">0.82</td>
</tr>


<tr >
<td style="text-align: center">6</td>
<td style="text-align: center;background-color: green">SVM</td>
<td style="text-align: center;background-color: green">0.85</td>
<td style="text-align: center;background-color: green">0.85</td>
</tr>

<tr >
<td style="text-align: center">7</td>
<td style="text-align: center;background-color: green">NN -Multilayer Perceptron</td>
<td style="text-align: center;background-color: green">0.85</td>
<td style="text-align: center;background-color: green">0.85</td>
</tr>

</td>
</table>

<p>After running comparative study on the three top models (higlighted in green) it was evidet for this dataset that KNN was a winning model<p>

<br>

<img src= images\modelwin.png>

<br>
<img src= images\modelwin2.png>
<br>
<h2>Choosing the Appropriate KNN</h2>
<p> It is time to choose appropriate K Value for the KNN Model</p>
<img src = code_snippits\knn_neigbours_code.png>
<br>
<img src= images\knn_choice.png>
<br>
<h2> ROC Curves</h2>
<br>

<img src = code_snippits\plotting_roc_code.png>
<br>
<img src= images\roc_curve.png>
<br>
<br>
<h2>CLASSIFICATION BOUNDARY</h2>
<br>
<img src = code_snippits\classification_boundary_code.png>
<br>
<p> This is how the Classification Boundary looked </p>
<br>
<img src = images\classification_boundary.png>

<h2>CONCLUSION</h2>
<br>
<li>Difficult to predict Queue length solely from Stop bar detection</li>
<li>This project is a first attempt at doing so with a single low investment single-source detection <ul><li>(potential trade: accuracy for price and effort)</li></ul>
</li>
<li>Various prediction classification models were tested to provide a comparison. 
</li>
<li><b>Top-performing Models: KNN-K-Nearest Neighbors, SVM, NN-Perceptron</b>
</li>
<li>
<b>K nearest neighbor (KNN) seems to be outperforming the other methods</b>
<ul>
<li>Predicting NQ and LQ classes: model was accurate.</li>
<li>Predicting FQ class: fell short in all methods and needs further investigation.
</li>
</ul>
</li>
<li><b>Potential reason why results were not as strongly predicted along the three classes: </b>
<ul>
<li>Uneven class distribution (with much lower instances of FQ compared with the other two classes)
</li>
<li>potential data accuracy issues
</li>
<li>Further review and refinement  of analysis methods and configurations needed 
</li>
</ul>
</li>


