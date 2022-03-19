#### Autor: Samuel Farias
#### Curso: Mestrado em Mecatronica
#### Disciplina: Controle da Qualidade

#### 9.2 Control Charts for Variables
  ## 9.2.2 Estimation of σ for Control Charts
  ## 9.2.3 Control Charts for Grouped Data


## bibliotecas

library(qcc)
library(SixSigma)

agg = aggregate(thickness ~ ushift, data = ss.data.thickness2, FUN = mean)

samples.thick <- qcc.groups(data = ss.data.thickness2$thickness,
                          sample = ss.data.thickness2$ushift)

## amostras
samples.thick

## plot
xbar.thick <- qcc(data = samples.thick, type = "xbar")

## resumo
summary(xbar.thick)

plot(xbar.thick)

names(xbar.thick)



## novo grafico

qcc.options("beyond.limits" = list(pch = 20, col = "red3" ))

qcc.options(bg.margin = "azure2")

plot(xbar.thick, 
     axes.las = 1, 
     digits = 3, 
     title = "X-bar chart metal plates thickness", 
     xlab = "Shift", 
     ylab = "Sample mean",
     ylim = c(0.70, 0.80))


## grafico - curva

thick.betas <- oc.curves(xbar.thick)
1/(1 - thick.betas[row.names(thick.betas) == "1", 1])

## novo plot

r.thick <- qcc(data = samples.thick, type = "R")

r.thick <- qcc(data = samples.thick, type = "S")


## novas amostras

set.seed(1)

new.sample <- matrix(round(rnorm(6, 0.75, 0.05), 3), nrow = 1, ncol = 6)

mean(new.sample)

## grafico

ccxbar <- qcc(data = samples.thick, type = "xbar", 
              newdata = new.sample, newlabels = "8.1")

ccs <- qcc(data = samples.thick, type = "S", 
           newdata = new.sample, newlabels = "8.1")

par(mfrow = c(2, 1))


plot(ccxbar, restore.par = FALSE, add.stats = FALSE)
plot(ccs, add.stats = FALSE)


## novo grafico

thickness2days <- ss.data.thickness2$thickness[1:24]
mov.samples <- cbind(thickness2days[1:23], thickness2days[2:24])
cci <- qcc(thickness2days, type = "xbar.one")
ccmr <- qcc(mov.samples, type = "R")

par(mfrow = c(2, 1))
plot(cci, restore.par = FALSE, add.stats = FALSE)
plot(ccmr, add.stats = FALSE)

##################################################################

cusum.thick <- cusum(data = thickness2days)
summary(cusum.thick)


ewma.thick <- ewma(data = thickness2days)






























































