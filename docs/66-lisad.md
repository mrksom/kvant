




# (APPENDIX) LISA {-}

# Tavaline lineaarne regressioon maatriksarvutusena


Lahendame Piaaci andmestiku põhjal regressioonivõrrandi:

$$\hat{y}_{sissetulek}=\beta_0+\beta_1 \times numeracy + \beta_2 \times naine$$

Meil on vaja leida: 

1. Regressioonikoefitsiendid ($\beta$-d) 
2. Koefitsientide standardvead (*se*) ja neist tulenevad koefitsientide t-statistikud ning p-väärtused, See eeldab koefitsientide variatsiooni-kovariatsioonimaatriksi ($\sigma^2_\beta$) leidmist
3. Mudeli jääkide standarviga (RSE)
4. Mudeli $R^2$ 
5. Mudeli F-statistik ja F-testi p-väärtus


Kui meil on sõltuv tunnus $y$ ja sõltumatute tunnuste maatriksi (*model matrix*) $X$ (mille hulgas on ka vabaliikme veerg 1-tedega) ehk regressioonivõrrand

$$\mathbf{y} = \mathbf{X} \boldsymbol{\beta} + \boldsymbol{\epsilon}$$

siis tavalise lineaarse regressiooni hinnangu (*OLS estimator*) **regressioonikoefitsientide** ($\mathbf{\beta}$-de) vektor on leitav järgmiselt:

$$\widehat{\boldsymbol{\beta}} = (\mathbf{X}^\intercal\mathbf{X})^{-1}\mathbf{X}^\intercal\mathbf{y}$$


```r
## Andmestiku

piaac <- read_csv("https://github.com/mrksom/kvant/raw/master/data/piaac.csv")

## Andmete ettevalmistus

dat <- piaac %>% 
  # Valime välja tunnused
  select(sissetulek, numeracy, sugu) %>%
  # Jätame välja vaatlused kus on mõni NA
  na.omit() %>% 
  # Teeme soo dummy-tunnuseks, kus mees on referentsgrupp
  mutate(naine = recode(sugu, Mees = 0, Naine = 1)) %>% 
  # Lisame vabaliikme tunnuse
  mutate(vabaliige = 1)

# Sõltuva tunnuse maatriks
y <- as.matrix(dat['sissetulek'])

# Sõltumatute tunnuste maatriks (disainimaatriks või ka mudelimaatriks)
X <- as.matrix(dat[c('vabaliige', 'numeracy', 'naine')])

# Vaatluste arv ja koefitsientide arv
n <- nrow(X)
k <- ncol(X)

## Regressioonikoefitsiendid

# Arvutame beta'd
beta <- solve(t(X) %*% X) %*% t(X) %*% y
```




**Jääkide dispersioon** (*mean squared error* ehk MSE) on

\begin{equation}
  MSE = \sigma^2_\epsilon=\frac{\sum_{i=1}^{n}(y_i-\hat{y}_i)^2}{n-k}
\end{equation}

kus $n$ on vaatluste arv ja $k$ on regressioonikoefitsientide arv (kaasa arvatud vabaliige). Maatriksnotatsioonis on sama asi väljendatav nii:

$$MSE = \frac{\mathbf{e}^\intercal\mathbf{e}}{n-k}$$

Ja jääkide standardviga (*residual standard error* või RSE) on

$$RSE = \sqrt{MSE}$$



```r
## Jääkide standardviga (RSE)

# Jäägid
e = y - X %*% beta

# Jääkide ruutude summa (residual sum of squares)
rss = t(e) %*% e

# vabadusastmed on n - k (vaatluste arv - koefitsientide arv)
df_resid = n - k

# MSE
mse = rss / df_resid

# Residual standard error
rse <- sqrt(mse)
```



**Koefitsientide variatsiooni-kovariatsioonimaatriks**, millest saame kätte koefitsientide standardvead, on defineeritud kui:


$$\sigma^2_\beta = \sigma^2_\epsilon(\mathbf{X}^\intercal\mathbf{X})^{-1}$$
Koefitsientide standardvead on ruutjuur variatsiooni-kovariatsioonimaatriksi diagonaali elementidest;

$$\sqrt{diag(\sigma^2_\beta)}$$


```r
## Koefitsientide standardvead

# Koefitsientide variatsiooni-kovariatsioonimaatriks
beta_vcov <- as.numeric(mse) * solve(t(X) %*% X)

# Koefitsientide standardvead
beta_se <- diag(beta_vcov) %>% sqrt()

# t-statistikud
beta_t <- (beta - 0) / beta_se

# p-väärtused
beta_p <- pt(abs(beta_t), df = df_resid, lower.tail = F) * 2
```




**Determinatsioonikordaja** ehk $R^2$ on: 

\begin{equation}
  R^2=\frac{TSS-RSS}{TSS}=1-\frac{RSS}{TSS}
\end{equation}

kus

\begin{equation}
  TSS=\sum_{i=1}^{n}(y_i-\bar{y})^2
\end{equation}

\begin{equation}
  ESS=\sum_{i=1}^{n}(\hat{y}_i-\bar{y})^2
\end{equation}

\begin{equation}
  RSS=\sum_{i=1}^{n}(y_i-\hat{y}_i)^2
\end{equation}


Maatriksnotatsioonis on sama asi väljendatav:

\begin{equation}
  TSS=(\mathbf{y}-\mathbf{\bar{y}})^2 = (\mathbf{y}-\mathbf{\bar{y}})^\intercal(\mathbf{y}-\mathbf{\bar{y}})
\end{equation}

\begin{equation}
  ESS=(\mathbf{\widehat{y}}-\mathbf{\bar{y}})^2 = (\mathbf{\widehat{y}}-\mathbf{\bar{y}})^\intercal(\mathbf{\widehat{y}}-\mathbf{\bar{y}})
\end{equation}

\begin{equation}
  RSS=\mathbf{e}^2 = \mathbf{e}^\intercal\mathbf{e}
\end{equation}

Kui $\mathbf{y}$ on keskmistatud, st see on vektor $y$ erinevustega keskmisest $y$-st, mis tähendab, et $\mathbf{\bar{y}} = 0$ siis muutub asi veel lihtsamaks, kuna sel juhul $\mathbf{y}-\mathbf{\bar{y}} = \mathbf{y}-0 = \mathbf{y}$ ja

\begin{equation}
  TSS=\mathbf{y}^\intercal\mathbf{y}
\end{equation}

\begin{equation}
  ESS=\mathbf{\widehat{y}}^\intercal\widehat{y}
\end{equation}

\begin{equation}
  RSS=\mathbf{e}^\intercal\mathbf{e}
\end{equation}



```r
## R2

# keskmistatud y
my <- y - mean(y)
 
# Total sums of squares
tss <- t(my) %*% my

# Expected sums of squares
ess <- t(my) %*% X %*% beta

# Residual sums of squares
rss <- t(e) %*% e
# või
rss <- tss - ess

# R2
r2 <- 1 - rss/tss

# Adjusted R2
r2_adjusted <- 1 - ((n - 1) / (n-k)) * (1 - r2)
```




```r
## F-test

msr <- rss/(n - k)
mse <- ess/(k - 1)

f_stat <- mse/msr

f_p <- 1-pf(f_stat, df1 = (k-1), df2 = (n-k))
```



```r
## Tulemused

# Paneme tulemid printimiseks kokku

res <- cbind(beta, beta_se, beta_t, beta_p)
colnames(res) <- c('beta', 'se', 't', 'p')

print_out <- function(){
  print(round(res, 4))
  cat(
    '\n',
    'RSE:', round(as.numeric(rse), 0), ' kus df on ', df_resid, '\n',
    'R2:', round(as.numeric(r2), 4),'; R2 (adjusted):', round(as.numeric(r2_adjusted), 4), '\n',
    'F-value: ', f_stat, '; df: ', k-1, ' ja ', n-k, '; p-value: ', f_p, sep = '')
}

print_out()
```

```
##                beta      se        t      p
## vabaliige  140.7631 55.0470   2.5571 0.0106
## numeracy     3.3533  0.1915  17.5094 0.0000
## naine     -365.0623 16.9196 -21.5763 0.0000
## 
## RSE:526 kus df on 3981
## R2:0.171; R2 (adjusted):0.1706
## F-value: 410.6503; df: 2 ja 3981; p-value: 0
```



Kontrollime lm() funktsiooniga kas saame samad tulemused:


```r
summary(lm(sissetulek ~ numeracy + sugu, data = piaac))
```

```
## 
## Call:
## lm(formula = sissetulek ~ numeracy + sugu, data = piaac)
## 
## Residuals:
##      Min       1Q   Median       3Q      Max 
## -1181.73  -323.46   -98.77   167.86  2813.48 
## 
## Coefficients:
##              Estimate Std. Error t value Pr(>|t|)    
## (Intercept)  140.7631    55.0470   2.557   0.0106 *  
## numeracy       3.3533     0.1915  17.509   <2e-16 ***
## suguNaine   -365.0623    16.9196 -21.576   <2e-16 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
## 
## Residual standard error: 526 on 3981 degrees of freedom
##   (3648 observations deleted due to missingness)
## Multiple R-squared:  0.171,	Adjusted R-squared:  0.1706 
## F-statistic: 410.7 on 2 and 3981 DF,  p-value: < 2.2e-16
```


# Delta meetod
