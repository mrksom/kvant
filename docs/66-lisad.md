




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


``` r
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



``` r
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


``` r
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



``` r
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




``` r
## F-test

msr <- rss/(n - k)
mse <- ess/(k - 1)

f_stat <- mse/msr

f_p <- 1-pf(f_stat, df1 = (k-1), df2 = (n-k))
```



``` r
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


``` r
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


# Robust and clustered standard errors

Regressioonimudeli jäägid peaksid hinnatud väärtuste lõikes olema homogeense ja konstantse variatiivsusega, st ühtlaselt jaotunud kõikide $\hat{y}$ väärtuste ümber (jääkide dispersiooni homogeensuse eeldus ehk *homoscedasticity*). Selle eelduse rikkumine mõjutab eelkõige standardvigu (need ei kehti enam kõikidele $\hat{y}$ väärtustele ühtlaselt) ja seeläbi loomulikult ka usaldusintervalle ning *p*-väärtusi. Lahenduseks võivad olla nn **robustsed standardvead** (*robust standard errors*), mis võtavad varieeruvuse erinevust arvesse.

Vaatluse jäägid ei tohiks olla ka korreleeritud. Selline olukord võib tekkida näiteks siis, kui hindame näiteks õpilaste testiskoore lähtuvalt nende õppimisele kulunud ajast, kuid ei arvesta, et õpilased tulevad erinevatest koolidest, kus võib olla erinev õppetase jne. Seega õpilaste tulemused ei ole enam sõltumatud, vaid sõltuvad koolist. Regressioonikoefitsientide standardvigade arvutamisel lähtutakse aga eeldusest, et jäägid on sõltumatud. Kui jäägid on korreleeritud, siis võib juhtuda, et me alahindame standardvigade suurust ehk siis oleme oma tulemustes ülemäära kindlad (usaldusintervallid ning *p*-väärtused tulevad liialt väikesed) ning võime näha seoseid seal kus neid tegelikult ei ole. Lahenduseks saab olla mitmetasandiline mudel või **klasterdatud standardvead** (*clustered standard errors* või ka *cluster-robust standard errors*).

Üheks võimaluseks standardvigu korrigeerida on kasutada paketti `sandwitch`, mis võimaldab olemasoleva mudeli variatsiooni-kovariatsiooni maatriksi põhjal arvutada nn robustne variatsiooni-kovariatsiooni maatriks. Sellest saame omakorda tuletada koefitsientide robustsed dispersioonid ning neist omakorda robustsed standardvead. `sandwich` paketis on erinevaid standardvigade korrigeerimise funktsioone: `vcovHC()` (*heteroskedasticity-consistent (HC) errors*), `vcovHAC()` (*heteroskedastiticy- and autocorrelation-consistent (HAC) errors*),  `vcovCL()` (*clustered errors*) jne, mida saab vastavalt vajadusele (millist korrektsiooni tahame) kasutada.

Defineerime kõigepealt tavalise regressioonimudeli:


``` r
piaac <- read_csv("https://github.com/mrksom/kvant/raw/master/data/piaac.csv")

# Defineerime regressioonimudeli 
mudel <- lm(numeracy ~ literacy * sugu, 
             data = piaac)

# tidy() funktsiooniga saame kätte tavalised standardvead ja usalduspiirid
broom::tidy(mudel, conf.int = T)
```

```
## # A tibble: 4 × 7
##   term               estimate std.error statistic  p.value conf.low conf.high
##   <chr>                 <dbl>     <dbl>     <dbl>    <dbl>    <dbl>     <dbl>
## 1 (Intercept)         36.1      2.62        13.8  9.65e-43  31.0      41.3   
## 2 literacy             0.872    0.00942     92.5  0          0.853     0.890 
## 3 suguNaine            4.60     3.62         1.27 2.04e- 1  -2.50     11.7   
## 4 literacy:suguNaine  -0.0449   0.0130      -3.46 5.35e- 4  -0.0704   -0.0195
```

## Robust standard errors

Robustsete standardvigade jaoks tuleb meil arvutada uus 'robustne' koefitsientide variatsiooni-kovariatsiooni maatriks ehk nn *Heteroscedasticity-Consistent Covariance Matrix*. Saame kasutada `sandwitch` paketti ja selle funktsiooni `vcovHC()`.

Variatsiooni-kovariatsiooni maatriksi diagonaalis on koefitsientide dispersioonid (variance). Ruutjuur dispersioonist annab koefitsiendi standardhälbe, mis on ongi parameetri standardviga. Seega saame robustsed standardvead kätte nii:


``` r
library(sandwich)
library(lmtest)

# Robustsete standardvigade jaoks tuleb meil arvutada uus 
#  'robustne' koefitsientide variatsiooni-kovariatsiooni maatriks ehk nn 
#  Heteroscedasticity-Consistent Covariance Matrix. sandwitch paketis
#  on selleks funktsioon vcovHC().


vcovHC(mudel) %>% # arvutame 'robustse' variatsiooni-kovariatsiooni maatriks
  diag() %>% # võtame selle diagonaali (ehk pasrameetrite dispersioonid)
  sqrt() # ruutjuur dispersioonist annab standardhälbe, mis on ongi standardviga
```

```
##        (Intercept)           literacy          suguNaine literacy:suguNaine 
##        2.788735004        0.009897618        3.831308067        0.013555193
```



``` r
# Et neid koos koefitsientide ja vastavate testidega kuvada, võime kasutada
#  lmtest paketi funktsiooni coeftest()
coeftest(mudel, vcov. = vcovHC(mudel))
```

```
## 
## t test of coefficients:
## 
##                      Estimate Std. Error t value  Pr(>|t|)    
## (Intercept)        36.1290294  2.7887350 12.9553 < 2.2e-16 ***
## literacy            0.8715229  0.0098976 88.0538 < 2.2e-16 ***
## suguNaine           4.5967288  3.8313081  1.1998 0.2302621    
## literacy:suguNaine -0.0449372  0.0135552 -3.3151 0.0009203 ***
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```

``` r
# Usalduspiirid robustsete standardvigade alusel saame kätte lmtest paketi 
# coefci() funktsiooniga
lmtest::coefci(mudel, vcov. = vcovHC(mudel))
```

```
##                          2.5 %     97.5 %
## (Intercept)        30.66233656 41.5957223
## literacy            0.85212087  0.8909250
## suguNaine          -2.91369599 12.1071535
## literacy:suguNaine -0.07150916 -0.0183653
```

## Clustered standard errors

Klasterdatud standardvigade jaoks tuleb meil arvutada uus 'klasterdatud' koefitsientide variatsiooni-kovariatsiooni maatriks ehk nn *Clustered Covariance Matrix*. Saame kasutada `sandwitch` paketti ja selle funktsiooni `vcovCL()`.



``` r
# Klasterdatud standardvigade arvutamiseks kasutame jälle sandwitch paketti ja
# selle funktsiooni vcovCL()
library(sandwich)
library(lmtest)

# Eeldame, et valim on klasterdatud haridusvaldkonna alusel
# Defineerime regressioonimudeli 
#  (jätame välja kõik vaatlused, kus haridusvaldkond on NA)
mudel <- lm(numeracy ~ literacy * sugu, 
             data = piaac[!is.na(piaac$hvaldkond),])


# Robustsete standardvigade jaoks tuleb meil arvutada uus 
#  'klasterdatud' koefitsientide variatsiooni-kovariatsiooni maatriks ehk nn 
#  Clustered Covariance Matrix. sandwitch paketis
#  on selleks funktsioon vcovCL(). Peame selles lisaks mudeliobjektile
#  määrama ka klastritunnuse
vcovCL(mudel, cluster = ~hvaldkond) %>% 
  diag() %>% 
  sqrt()
```

```
##        (Intercept)           literacy          suguNaine literacy:suguNaine 
##         7.69411746         0.02019249         5.63277113         0.01773446
```



``` r
# Et neid koos koefitsientide ja vastavate testidega kuvada, võime kasutada
#  jällegi lmtest paketi funktsiooni coeftest()
coeftest(mudel, vcov. = vcovCL(mudel, cluster = ~hvaldkond))
```

```
## 
## t test of coefficients:
## 
##                     Estimate Std. Error t value  Pr(>|t|)    
## (Intercept)        35.718804   7.694117  4.6424 3.503e-06 ***
## literacy            0.872964   0.020192 43.2321 < 2.2e-16 ***
## suguNaine           5.006361   5.632771  0.8888  0.374143    
## literacy:suguNaine -0.046464   0.017734 -2.6200  0.008812 ** 
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```

``` r
# Usalduspiirid robustsete standardvigade alusel saame kätte lmtest paketi 
# coefci() funktsiooniga
coefci(mudel, vcov. = vcovCL(mudel, cluster = ~hvaldkond))
```

```
##                          2.5 %      97.5 %
## (Intercept)        20.63618128 50.80142590
## literacy            0.83338131  0.91254716
## suguNaine          -6.03544613 16.04816773
## literacy:suguNaine -0.08122814 -0.01169913
```


# Delta meetod
