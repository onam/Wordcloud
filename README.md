Wordcloud
=========

Simple use of wordcloud package on Adwords data
library(wordcloud)
library(RColorBrewer)
token <- read.csv("filename", sep="," , skip=1)
pal <- brewer.pal(8, "Dark2")

token1 <- token[which(token$Clicks > 100), ]
pdf()
wordcloud(token1$Word, token1$Clicks, random.order=FALSE, colors= pal, rot.per = 0 )
wordcloud(token1$Word, token1$Avg.CTR, random.order=FALSE, colors= pal, rot.per = 0 )
wordcloud(token1$Word, token1$Impressions, random.order=FALSE, colors= pal, rot.per = 0 )
dev.off()

