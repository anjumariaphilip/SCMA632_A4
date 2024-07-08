library(readr)
library(stats)
setwd("C:\\Users\\HP\\Documents\\ns")
data <- read.csv("icecream.csv", header = TRUE)
head(data)
distance_matrix <- dist(data)
mds_result <- cmdscale(distance_matrix, k = 2)
mds_df <- as.data.frame(mds_result)
colnames(mds_df) <- c("Dim1", "Dim2")
library(ggplot2)
ggplot(mds_df, aes(x = Dim1, y = Dim2)) +
  geom_point() +
  ggtitle("MDS Plot of Ice Cream Data") +
  xlab("Dimension 1") +
  ylab("Dimension 2")