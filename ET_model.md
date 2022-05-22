[toc]

# Calibration-free complementary relationship (CR) model

非线性CR方法通过一下方式关联两个无量纲蒸散量项：
$$
y=(2-X)X^2\tag{1.1}
$$
其中，X与y定义为
$$
X = \frac{E^{max}_p-E_p}{E^{max}_p-E_w}\frac{E_w}{E_p} \tag{1.2}
$$

$$
y = \frac{ET}{E_p} \tag{1.3}
$$

> $ET~(mm~d^{-1}):~Actual~evapotranspiration~rate$
>
> $E_p~(mm~d^{-1}):~Potential~evapotranspiration~rate$

$E_p$通常由Penman（1948）模型表示
$$
E_p = \frac{\Delta}{\Delta + \gamma}(R_n-G)+\frac{\gamma}{\Delta + \gamma}f_u(e^*-e_a)\tag{1.4}
$$

> $\Delta~(kPa~℃):~Slope~of~the~saturation~vapor~pressure~curve~at~the~measured~temperature$
>

$E_w$是Priestley-Taylor（PT）方程，区域范围内的湿润表面的潮湿环境蒸发率（完全潮湿环境），即为
$$
E_w = \alpha\frac{\Delta(T_w)}{\Delta(T_w)+\gamma}(R_n - G)\tag{1.5}
$$

> $\alpha:~PT~coefficient$
>
> $T_w~(℃):~wet~environment~temperature$

通过利用通常在潮湿环境中可观察到的可忽略的垂直空气温度梯度，$T_w$可近似为$T_{ws}$

> $T_{ws}~(℃):~wet~surface~temperature$

$T_{ws}$与面积范围无关，因此可以用Penman方程有效的小湿表面的Bowen比中获得$T_{ws}$即
$$
\beta_p = \frac{R_n - G - E_p}{E_p}\approx\gamma\frac{T_{ws} - T_a}{e^*(T_{ws}) - e_a}\tag{1.6}
$$

>$\beta_p:~水分充足斑块的波文比（假设湿斑块表面的可用能量接近周围干燥斑块的可用能量）$
>
>$e^*~(T_{ws}):~T_{ws}下评估的饱和水汽压$

**请注意，当空气接近饱和时，通过方程（1.6）获得的$T_{ws}$可能大于$T_a$，这种情况下$T_{ws}$应以$T_a$为上限**

对于大型模型应用，在$\alpha$校准中经常缺少测量的ET，可采用Szilagyi等人（2017）的方法，通过使用湿网格单元及其相应的网格$T_a$和湿度数据识别湿网格单元，为其分配适当的空间和时间常数值（有关程序的详细说明，请参见Ma和Szilagyi，2019年附录B）。

方程（1.2）中的$E^{max}_p$是环境完全干燥时$E_p$可以达到的最大值（$e_a\approx0$），即
$$
E^{max}_p = \frac{\Delta(T_{dry})}{\Delta(T_{dry})+\gamma}(R_n - G) + 
\frac{\gamma}{\Delta(T_{dry})+\gamma}f_ue^*(T_{dry})\tag{1.7}
$$
其中，$\Delta$、$e^*$在干燥环境空气温度$T_{dry}$下进行评估。对于绝热过程，后者可以估计为
$$
T_{dry} = T_wb + \frac{e^*(T_{wb})}{\gamma}\tag{1.8}
$$

> $T_{wb}:~湿球温度$

绝热条件下的$T_{wb}$可以从另一个推导式中推导出来，即
$$
\gamma\frac{T_{wb} - T_a}{e^*(T_{wb}) - e^*(T_d)} = -1\tag{1.9}
$$

> $T_d:~dew-point~temperature$

关于方程（1.1）的更详细的热力学推导，请参见Szilagyi（2021）。

[Ning Ma, 2021, Calibration-Free Complementary Relationship Estimates Terrestrial Evapotranspiration Globally](https://agupubs.onlinelibrary.wiley.com/doi/full/10.1029/2021WR029691)









