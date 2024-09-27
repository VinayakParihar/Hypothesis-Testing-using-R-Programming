#### T Statistic is a test statistic that helps deciding whether to reject or do not reject null hypothesis.
#### Eg: If we can reject null hypothesis Ho : B = 0, then we can surely say that income does have an effect on consumption.


## R studio

library(Tidyverse)
library(gapminder)
view(gapminder)

Here we are first filtering the data to extract Africa and Euorope among the continents and then using t.test command to test life expectencies for the given continents.
## Note : most softwares use Ho = 0 and Ha not = 0 automatically . If we want to perform other hypothesis we have to include that command (eg Ho = B1-B2 = 0) while performing the T test.
gapminder %>%
  filter(continent %in% c("Africa", "Europe")) %>% 
  t.test(lifeExp ~ continent, data = .)


Result:
Welch Two Sample t-test

data:  lifeExp by continent
t = -49.551, df = 981.2, p-value < 2.2e-16
alternative hypothesis: true difference in means between group Africa and group Europe is not equal to 0
95 percent confidence interval:
 -23.95076 -22.12595
sample estimates:
mean in group Africa mean in group Europe 
            48.86533             71.90369 

### interpretation 
##### Her we can compare the calculated t test value with the tabulated one for significance or we can also directly see that the p-value < 2.2e-16 is very small which means that the possiblity that our result has occured by chance is very low. 
##### Therefore We can reject null hypothesis and our result is significant
