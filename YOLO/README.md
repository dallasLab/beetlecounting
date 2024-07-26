


```{r}
# from the train labels folder to get the true number of beetles labeled
files <- lapply(list.files(), read.delim)
truth <- sapply(files, nrow)
# preds gotten manually in python as below
preds <- c(217, 219, 122, 161, 118, 200, 178, 146)

pdf('truePred.pdf', height=4,width=4)
par(mar=c(4,4,0.5,0.5))
plot(truth, preds, 
  pch=16, col='dodgerblue',
  las=1, xlab='True number of beetles', 
  ylab='Predicted number of beetles', 
  ylim=c(100,370), 
  xlim=c(100,370))
abline(a=0, b=1)
dev.off()

```




```{python}

# from the runs/detect/train5/weights/ folder
model = YOLO('best.pt')
model('path/to/img')

```



```
