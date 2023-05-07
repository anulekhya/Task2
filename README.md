# Task2
library(ggplot2)
library(cluster)
data<-data.frame(iris)
head(data)
library(dplyr)
p<-ggplot(data=iris,aes(x=Petal.Length,y=Petal.Width))+geom_point(aes(col=Species))
print(p)
set.seed(128)
datacluster<-kmeans(data[,2:4],3,nstart=20)
print(datacluster)
table(datacluster$cluster,data$Species)
clusplot(data,datacluster$cluster,color=T,shade=T,labels=0,lines=0)
