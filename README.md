# CS235-Data-Mining
Dear students,
As you may be aware of, in your final project deliverable you are currently required to 
include an implementation correctness component for your method. In its current 
format, the proposed process for demonstrating that your from-scratch 
implementation is correct is by closely comparing its behavior to some off-the-shelf 
implementation of the same method. However, we have realized that due to various 
optimizations and modifications that many off-the-shelf implementations may 
contain, it can sometimes be hard to provide a meaningful comparison when the fromscratch implementation is based on a simplified vanilla version of a method.
Therefore, we have decided to modify this process to demonstrating that your method 
performs correctly by inspecting its behavior on a specially designed artificial dataset. 
You can find this dataset both in the "Important Documents" module and also 
attached in this announcement. It contains 17 datapoints with 2 features along with 
their designated class. Specifically, the implementation correctness modifications are 
as follows:
• Instead of submitting the implementation correctness report as a separate 
document from the final report, please include a separate section at the end 
of your final report in which you include the implementation correctness 
component. In other words, no implementation correctness report pdf 
needs to be submitted.
• Depending on the method you implement you will have to perform the 
following:
• k-NN: For k=3, no data pre-processing, and a test datapoint 
[1.4 , 3]
1. show a scatterplot of the dataset including the test 
datapoint where
• points in different classes are shown in 
different colors
• the test data point is shown in different 
color than all other datapoints
• based on Euclidean distance you denote 
the 3 closest neighbors of the test 
datapoint with filled circles and all other 
points with open circles
2. report which class the test data point is classified as 
and why
3. repeat steps 1 and 2 by using Manhattan distance 
instead
• Decision Tree: Explain
1. the order of the features selected by the tree and 
why it is correct
2. which feature value each split is based on and why 
it is correct
• Random Forest:
1. Follow the steps above to demonstrate the 
correctness of your individual base trees as if you 
were implementing just a single decision tree
2. Construct a random forest
▪ with 20 base trees each of which is 
trained on 12 randomly selected 
datapoints and on all features
▪ and then consider the test datapoint [4, 
4] and then report
I. the number of base trees that 
classify it as class 1 and class 
2, respectively
II. the final classification that 
the random forest produces. 
Explain if the classification 
makes sense and why.
• Single-linkage:
1. show the scatterplot of the dataset with a unique 
integer number on top of each point
2. show the corresponding dendrogram where on each 
leaf the same integer number as the corresponding 
point of the scatterplot is indicated
3. explain if and how exactly we can obtain clusters 
identical to the ground-truth clusters shown in the 
dataset
• DBSCAN: for min_pts = 2 and and eps = 1.25
1. create the scatterplot of the dataset with an integer 
on top of each point showing the order in which it 
was visited by the algorithm. Explain why this 
order is correct.
2. denote with filled circles the core points and with 
empty circles the non-core points. Explain why
each core and non-core point was designated as 
such.
3. use different colors for points belonging to different 
clusters as obtained by DBSCAN (do not color 
based on the ground-truth clusters given in the 
dataset).
• Spectral Clustering:
1. Create from scratch the adjacency matrix of the 
unweighted undirected similarity graph where node 
i and node j are connected with an edge if
▪ datapoint i is among the 2 nearest 
neighbors of datapoint j,
OR
▪ datapoint j is among the 2 nearest 
neighbors of datapoint i
2. Calculate the spectral embeddings of dimension 2 
based on the Normalized Laplacian, and
▪ report them numerically in a latex table 
in your report
3. Explain if and why these embeddings provide any 
benefit in terms of clustering the original datapoints 
as compared to clustering the original datapoints 
directly
4. Run k-means for k=2 and show a plot such that
▪ its horizontal axis corresponds to 
iterations of k-means
▪ and its vertical axis indicates the 
objective function of k-means at that 
iteration.
Please denote the updates of the 
centroids and the updates of the 
assignments as different iterations. For 
example, if iteration i corresponds to an 
update of cluster assignments, then 
iteration i+1 should correspond to an 
update of the centroids where the cluster 
assignments remain the same as in 
iteration i.
5. Show a scatterplot showing
▪ the spectral embeddings (drawn as 
circles) and color them based on the 
cluster that k-means assigned them in
▪ the calculated centroids (drawn as x's) 
having the same color as the cluster they 
represent
o Support Vector Machines (SVM): Consider the test datapoint [4, 4]
1.
1. Show a scatterplot of the dataset including the test 
datapoint where
o points in different classes are shown in 
different colors
o the test data point is shown in different 
color than all other datapoints
2. Train your SVM with linear kernel. If no issues 
come up proceed to step 3. Otherwise, explain what 
went wrong and why, and proceed directly to step 
5.
3. While training your SVM show a plot such that
o its horizontal axis corresponds to 
iterations of optimization updates
o and its vertical axis indicates the value 
of the objective function of SVM at that 
iteration
o Explain if and why the behavior shown 
in this plot is correct or not
4. After training is finished,
▪ report the calculated values of w and b 
(as defined in the course slides)
▪ If you implemented a hard-margin 
SVM, then in your scatterplot denote 
with filled circles ALL the support 
vectors, and with empty circles the rest 
of the points
▪ in your scatterplot draw the separating 
hyperplane
▪ Show exactly how your trained SVM 
decides the class of the test datapoint 
and what class it assigns it in
5. Define the mapping [a, b] -> [a, b, 2*a*b/(a+b)] and 
transform all datapoints accordingly. Then repeat 
steps 1-4 for the transformed dataset. What do you 
observe? Explain if and why your SVM b
