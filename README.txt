# Bug

## 字体不显示中文 https://rpubs.com/maomaoworm/679092 
###install.packages("showtext")
options(tidyverse.quiet = TRUE)
library(tidyverse) # Easily Install and Load the 'Tidyverse'
library(showtext) # Using Fonts More Easily in R Graphs
showtext_auto() 
ziti="Microsoft YaHei"


pdf('test.pdf')
ggplot(mtcars, aes(x=wt, y=mpg)) + geom_point() +
  ggtitle("Fuel Efficiency of 32 Cars",
          subtitle = "32种汽车的燃油效率") +
  xlab("Weight (x1000 lb)") + ylab("Miles per Gallon") +
  theme(text=element_text(size=10, family=ziti),
        plot.title = element_text(size = 12, family=ziti),
        plot.subtitle = element_text(size = 16,    family=ziti))
dev.off()
