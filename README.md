# aws-certifed-machine-learning-specialty-exam-notes

## 1 Data Collection
- Introduction
- Concepts
- General Data Terminology
- Machine Learning Terminology
- AWS Data Stores
- AWS Migration tools
- AWS Helper Tools

### Reference
- https://d1.awsstatic.com/whitepapers/Size-Cloud-Data-Warehouse-on-AWS.pdf
- http://d0.awsstatic.com/whitepapers/Big_Data_Analytics_Options_on_AWS.pdf
- https://d1.awsstatic.com/whitepapers/enterprise-data-warehousing-on-aws.pdf
- https://d1.awsstatic.com/whitepapers/Migrating_to_Apache_Hbase_on_Amazon_S3_on_Amazon_EMR.pdf
- https://d1.awsstatic.com/whitepapers/RDS/AWS_Database_Migration_Service_Best_Practices.pdf
- AWS Reinvent 2018 Modern Cloud Data Warehousing https://www.youtube.com/watch?v=QZ4LAZCbsrQ
- AWS Reivnent 2018 Effective Data Lakes Challenges and Design Pattern https://www.youtube.com/watch?v=v5lkNHib7bw
- https://aws.amazon.com/blogs/big-data/build-a-data-lake-foundation-with-aws-glue-and-amazon-s3/

## 2 Streaming Data Collection
- Introduction
- Concepts
- Kinesis Data Streams
- Kinesis Firehose
- Kinesis Video Streams
- Kinesis Data Analytics

## 3 Data Preparation
- Introduction
- Concepts
- Categorical Encoding
- Text Feature Engineering
- Numeric Feature Engineering
- Other Feature Engineering
- Handling Missing Values
- Feature Selection
- Helper Tools

## 4 Data Analysis and Visualization
- Introduction
- Concepts
- Relationships
- Comparisons
- Distributions
- Compositions
- Choosing a Visualization

## 5 Modeling
- Introduction
- Concepts
- Data Preparation
- Sagemaker Modeling
- Sagemaker Training

## 6 Algorithims
### Introduction
```
Generate Example Data   |  Train the Model   | Deploy the Model
Fetch > Clean > Prepare > *Train* > Evaluate > Deploy > Monitor
```

### Concepts
- Algo: A Set of steps to follow to solve a specific problem intented to be repeatable with the same outcome.
- Heuristic: A mental shortcut or "rule of thumb" that provides guidance on doing a task but does now guarantee a consistent outcome.
- Components: Model, Data, Computations, Algorithms, Feedback, Generalization
- Developing a Good Model
```
           | Supervised Learning            | Unsupervised Learning       | Reinforcement Learning
-----------  -------------------------------  ----------------------------  -----------------------------
Training   | Training Data and Testing Data | No Training                 | How to Maximize Reward
Discrete   | Classification                 | Clustering                  | Simulation-based Optimization
Continuous | Regression                     | Reduction of Dimentionality | Autonomous Devices
```
- Supervised Learning: A teacher or parent supervises the learning process by providing model examples and feedback on quizzes.
- Unsupervised Learning: You are totally unsupervised and must rely on alternative methods to learn other than prior experience.
- Reinforcement Learning: A model seeks to maximize reward, often through trial and error. We want to reinforce the desired behavior.
- Algorithims: Used Sagemaker Built-in Algorithim, Purchase from AWS Marketplace, Build Your own via Docker Image

### Regression

#### Linear Learner Algorithm
- Linear models are supervised learning algorithims for regression, binary classification or multiclass classification problems. You give the model labels (x, y) with x being high-dimensional vector and y is a numerical label. the algorithm learns a linear function, or, for classification problems, a linear threshold function, and maps a vector x to an approximation of label y.
- To use this algo, you need a number or list of numbers which yields some other number, the answer you're after. You can use it to predict a specific value or threshold for grouping purposes.
- Supervised
- Stochastic Gradient Descent: Local Minimum and Global Minimum
- Very Flexible: Linear Learner can be used to explore different training objectives and choose the best one. Well suited for discrete or continuous inferences.
- Build in Tuning: Linear Learner algorithm has an internal mechanism for tuning hyperparameters separate from the automatic tuning feature.
- Good First Choice: If your data and objective meets the requirements, Linear Learner is a good first choice to try for your model.
- Use Case: Predict quantitative value basde on given numeric input. Example: Based on last five years ROI from marketing spend, what can we expect to be this year's ROI?
- Use Case: Discrete Binary Classification Problem. Example: Based on past customer response, show I mail this particular customer? Yes or No?
- Use Case: Discrete Multiclass Classification Problem. Example: Based on past customer response, how should I reach this customer? Email, Direct Mail, Phone Call

#### Factorization Machines Algorithim
- General purposed supervised learning algorithm for both binary classification and regression. Captures interaction between features with high dimensional sparse datasets.
- To use this algorithm you need a number or list of numbers which yields some other number. The answer you're after. You can use it to predict a specific value or a threshold for placing into one or two groups. It is a good choice when you have "holes" in your data.
- Considers ony pair-wise features. Amazon SageMaker's implementation of factorization machines will only analyze relationships of two pairs of features at a time.
- CSV is not supported. CSV is not a good choice for sparse dimensions. File and Pipe mode training are supported using recordIO-protobuf format with Float32 tensors.
- Doesn't work for Multiclass Problems. Factorization Machines algorithm can be run in either binary classification mode or regression mode.
- Really needs LOTS of data. To make up for the sparseness, needs lots of data. Recommended dimension of the input feature space is between 10,000 and 10,000,000
- CPUs rock sparse data better. AWS recommends CPU's with factorization machines for the most efficient experience.
- Don't perform well on dense data. Other algorithms are much mode performant when you have a full set of data.
- https://docs.aws.amazon.com/sagemaker/latest/dg/fact-machines-howitworks.html


### Clustering
### Classification
### Image Analysis
### Anomaly Detection
### Text Analytics
### Reinforcement Learning
### Forecasting
### Ensemble Learning

## 7 Evaluation and Optimization
- Introduction
- Concepts
- Monitoring and Analyzing Training Data
- Evaluating Model Acccuracy
- Model Tuning

## 8 Implementation and Operations
- Introduction
- Concepts
- AI Developer Services
- Amazon SageMaker Deployment
- Security
- Monitor and Evaluate
