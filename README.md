# Facial-recognition
Machine Learning project that detects face, for a given image we can tell the subject id. Our dataset was 40 subjects and 10 images per subject. <br />
1) We Converted every image into a vector of of 10304 (92x112) values corresponding to the image Size. <br />
2) Stacked the 400 vectors into a single Data Matrix D and generated the label vector y.The labels are integers from 1:40 corresponding to the subject id. <br />
3) Then splitted the dataset into training and test sets. <br />
a.Kept odd rows From the Data Matrix D 400x10304 are for training and the even rows
for testing. This gave nstances per person for training and 5 instances er person for testing. <br />
b.Splitted labels vector accordingly. <br />
4) Then, classified using PCA. <br />
a. computed projection matrix U according to these steps: <br />
1)Computed mean of data matrix D 2)Centered data 3)Computed covariance matrix 4)Computed d eigen values 5) Computed d eigen vectors 6)Got fraction of total variance f(r)for all r=1,2,..,d where d is the number of eigenvalues &eigenvectors 7)Chose dimensionality which is smallest r such that f(r)< alpha,alpha ={0.8,0.85,0.9,0.95} 8)Reduced the number of eigen vectors to r instead of d 9)Got the reduced dimensionality data by multiplying the reduced eigen vectors by the original matrix. <br />
b. Projected training set and test sets separately using the same projection matrix. <br />
c. Used simple classifier (first Nearest Neighbor to determine the class labels). <br />
d. Reported accuracy for ever value of alpha seperately. <br />
6) Finally did the classifier tunning using KNN classifier. <br />
a. Set the number of neighbors in the K-NN classifier to 1,3,5,7. <br />
b. Tie-breaking. <br />
c. Plotted performance measure (accuracy) against the K value. <br />
