Overview:
This assignment focuses on learning a probability density function (PDF) from real-world air quality data using a roll-number-parameterized non-linear transformation.
We need to-
1. Transform NO₂ concentration values using a non-linear function dependent on the university roll number.
2. Learn the parameters of a given probability density function from the transformed data.
3. Validate and visualize the learned PDF.

Dataset:
The dataset used is the India Air Quality Dataset from kaggle, and NO₂ concentration is considered as the input feature.

Methodology:
1. Preprocessing - Missing values in the NO₂ column are removed and Data is treated as a one-dimensional continuous variable.

2. Roll Number Parameterized Transformation -
Let x denote the original NO₂ concentration values. Each value is transformed using the following non-linear function:
ar=0.05*(r mod 7)
br=0.3*(r mod 5 + 1)
r is university roll number.
This transformation introduces a controlled non-linearity into the data while keeping the original scale intact.

3. Probability Density Function Model-
The transformed variable z is modeled using the following PDF:
p(z)=c*e^(-lambda(z-mu)^2)
mu is mean of the distribution , lambda controls the spread, c is the normalisation constant.

4.Parameter Estimation-
Using Maximum Likelihood Estimation, parameters are estimated as:
mu=mean(z)
variance=var(z)
lambda= 1/(2*variance)
To ensure that the PDF integrates to 1, the normalization constant is derived analytically:
c=sqrt(lambda/pi)

Results-
Learned Parameters:
mu=25.810838442217115
lambda=0.0014605237358096261
c=0.021561519986176458

