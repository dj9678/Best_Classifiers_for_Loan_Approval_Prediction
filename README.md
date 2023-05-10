<h1>Best Classifiers for Loan Approval Prediction</h1>								
<p>By Dongsuk Jeong | April 2023</p>

<h2>Purpose</h2>
<p>
  - Through EDA, Find out the insightful facts from the loan approve dataset<br>
  - To investigate which Classifiers among Logistic Regression, Decision Tree, Random Forest, SVM, and Guassian NB perform the best with dataset
</p>

<h2>Methodology</h2>								
<span class="image main"><img src="images/Portfolio_Methodology3.jpg" alt="" /></span>
<h2>Data Collection & Wrangling</h2>
<p>
  - Collected the loan approval dataset from Kaggle<br>
  - Response variable(loan status) is binary type, which is "Approved" or "Denied"<br>
  - Predictor variable include loan status, Dependents, education, self employed, application income, loan amount, and credit history<br>
  - Removed null and duplicate data entries<br>
  - Removed the outliers using z-score method<br>
  - Transformed the quantitative variables to numerical value for analysis
</p>

<h2>Exploratory Data Analysis</h2>
<p>
  - Found out that male tend to have more loan approval than female<br>
  - Marriage actually makes it easier to get loan approval compared to non marriage<br>
  - More dependents makes it hard to get loan approval<br>
  - Education degree makes it easy to get loan approved and self employee person tend to get less loan approved<br>
  - Semi-urban area showe the most loan approval than urban and rural area
</p>
<span class="image main"><img src="images/Portfolio_Methodology3_1.jpg" alt="" /></span>
<p>
  - From the applicant income density plot below, it indicates that lower range of applicant income showed the most loan approved rate, then decreased grdaually. However, increased again dramatically at the range of high income range<br>
  - For loan amount density plot, it seems like middle range of loan amount tend to get approved than other amounts. It also decreased grdually after reaching the peak around $150,000, but increased again around the laon amaount of $250,000. 
    This indicates that people in high income range tend to borrow higher amount than other income range
</p>
<span class="image main"><img src="images/Portfolio_Methodology3_2.jpg" alt="" /></span>
<p>
  - From the correlation heatmap below, it shows that relationship between loan amount and applicant income and relationship between credit history and loan status 
  have relatively high correlation than others, but since it is 0.49 and 0.54 respectively, it is considered okay to include in the model
</p>
<span class="image main"><img src="images/Portfolio_Methodology3_3.jpg" style="	width:70%; margin-bottom: 50px;" /></span>

<h2>Performance Comparison Table</h2>
<span class="image main"><img src="images/Portfolio_Methodology3_4.jpg" style="	width:70%; margin-bottom: 50px;" /></span>
<p>
  - Splited data 80% for training and 20% for test<br>
  - Used 5 fold Cross Validation to find the optimal value for hyperparameter if needed<br>
  - For Decision Tree, set up the optimal max depth to 2<br>
  - For Random Forest, set up the optimal max depth to 6 and the minimum sample split size to 8<br>
  - Used default setting for other classifiers<br>
  - Used accuracy rate, Confusion matrix and ROC curve for model evaluation									
</p>

<h2>Conclusion</h2>
<p>
  - As a result, Gaussian NB showed the best performance with 0.16 misclassification rate and 0.99 true positive rate (TPR)<br>
  - Logistic regression performed the second best	except TPR since SVM has 0.99 which is same with Gaussian NB
    since our dataset only has the two class in response variable, this would be the reason that logistic regression performed well<br>
  - Random forest and SVM have the same accuracy score, but CV score and AUC of random forest is higher than SVM<br>
  - Decision tree overall showed the worst performance among 5 classifiers 
</p>
