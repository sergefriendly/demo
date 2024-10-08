# Модель движения тела переменной массы

**С непрерывно истекающим веществом по линейному закону в поле тяжести Земли перпендикулярно её поверхности с учётом диссипативной силы сопротивления среды, также с учётом изменения плотности воздуха с высотой по барометрическому закону и температурой линейно убывающей с высотой.**

*Моделировалось явление и исследовалось дифференциальное уравнение*

```math
m\frac{d^2s}{dt^2}=-m\frac{g_0}{\left(1+\frac{s}{R_\oplus}\right)^2} - \frac{1}{2}\frac{p_0\mu}{R\left(T_0-\theta s\right)}\exp\left(-\frac{\mu g_0s}{R\left(T_0-\theta s\right)\left(1+\frac{s}{R_\oplus}\right)^2}\right)C_dA\left(\frac{ds}{dt}\right)^2+u\frac{dm}{dt},
```

где  
$m=m(t)=m_0-\beta t$ — масса тела переменной массы \[**кг**\];  
$\beta$ — расходы массы в единицу времени \[**кг/с**\];  
$u$ — скорость истечения газа (скорость отделяющихся частей) относительно тела переменной массы \[**м/с**\];  
$v=v(t)$ — скорость (функция от времени) тела переменной массы \[**м/с**\];  
$s=s(t)$ — путь (или высота применительно к этой модели, также функция от времени) тела переменной массы \[**м**\];  
$g_0/\left(1+s/R_\oplus\right)^2=g$ — ускорение свободного падения как фунция высоты $s$ \[**м/с²**\];  
$g_0$ — ускорение свободного падения у поверхности Земли (небесного тела: планеты) равное 9,81 **м/с²**;  
$R_\oplus$ — радиус Земли (небесного тела), равный  6 371 000 **м**;  
$p_0$ — атмосферное давление над уровнем моря, равное 101 325 **Па**;  
$\mu$ — молярная масса воздуха (атмосферы планеты), равная 0,02896 **кг/моль**;  
$R$ — универсальная газовая постоянная, равная 8,31 **Дж/(моль ⋅ К)**;  
$T_0-\theta s=T$ — температура атмосферы Земли (планеты) (упрощённая модель) \[**К**\];  
$T_0$ — температура воздуха атмосферы близ литосферы Земли (планеты) \[**К**\];  
$\theta$ — коэффициент изменения температуры атмосферы Земли (планеты) с высотой \[**К/м**\];  
$C_d$ — коэффициент лобового сопротивления поферхности тела в атмосфере Земли (планеты) \[**безразмерная величина**\];  
$A$ — площадь поперечного сечения этой поверхности \[**м²**\].  

## Замечания
**Замечание 1**. Уравнение выводилось на основе [уравнения Мещерского (Википедия)](https://ru.wikipedia.org/wiki/Уравнение_Мещерского)  

<!-- ![Распределение сил, действующих на тело переменной массы](https://github.com/sergefriendly/demo/raw/main/forces_2024-09-03_18-45-54.jpg) -->
<p align="center"><img src="https://github.com/sergefriendly/demo/raw/main/forces_2024-09-03_18-45-54.jpg" alt="Распределение сил, действующих на тело переменной массы"></p>

```math
m(t)\frac{d^2\vec{s}}{dt^2}=\vec{F}_{\text{внеш}}-\vec{u}\frac{dm}{dt},
```
где
```math
\vec{F}_{\text{внеш}}=\vec{F}_{\text{тяж}}+\vec{F}_{\text{сопрот}}=m(t)\vec{g}-\frac{1}{2} C_d \rho A v^2\vec{e}_v
```
где $\vec{e}_v = \frac{\vec{v}}{v}$ — орт вектора скорости. В проекции на ось $z$ уравнение примет вид
```math
m(t)\frac{d^2 s}{dt^2}=-m(t)g-\frac{1}{2} C_d \rho A v^2+u\frac{dm}{dt}
```

**Замечание 2**. Если учесть, что давление воздуха падает с высотой по [бараметрической формуле (Википедия)](https://ru.wikipedia.org/wiki/%D0%91%D0%B0%D1%80%D0%BE%D0%BC%D0%B5%D1%82%D1%80%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%B0%D1%8F_%D1%84%D0%BE%D1%80%D0%BC%D1%83%D0%BB%D0%B0), то в таком случае плотность воздуха (атмосферы) выразится формулой:
```math
\rho=\frac{p_0\mu}{RT}\exp\left(-\frac{\mu gs}{RT}\right)
```

**Замечание 3**. Если учесть, что [ускорение свободного падения также изменяется с высотой (Википедия)](https://ru.wikipedia.org/wiki/%D0%A3%D1%81%D0%BA%D0%BE%D1%80%D0%B5%D0%BD%D0%B8%D0%B5_%D1%81%D0%B2%D0%BE%D0%B1%D0%BE%D0%B4%D0%BD%D0%BE%D0%B3%D0%BE_%D0%BF%D0%B0%D0%B4%D0%B5%D0%BD%D0%B8%D1%8F), т.е.
```math
g(s)=\frac{GM_\oplus}{\left(R_\oplus+s\right)^2},
```
где  
$M_\oplus$ — масса Земли (или планеты). Вклад данной поправки очень мал, действительно:
```math
g(s)=\frac{GM_\oplus}{R_{\oplus}^{2}\left(1+\frac{s}{R_\oplus}\right)^2}=\frac{g_0}{\left(1-\left(-\frac{s}{R_\oplus}\right)\right)^2} \approx g_0 \left(1-2\left(\frac{s}{R_\oplus}\right)+\left(\frac{s}{R_\oplus}\right)^2\right)
```
Оценим выражение $s/R_\oplus$ применительно к планете Земля, для ориентировки возьмём высоту МКС равную 408 000 м:
```math
0 \le s \le 408 000 \quad [\textbf{м}]
```
```math
0 \le \frac{s}{R_\oplus} \le 0,064
```
Возьмём лишь линейную часть разложения и вычислим
```math
9,81 \ge g_0 \left(1-2\left(\frac{s}{R_\oplus}\right)\right) \ge 8,55 \quad [м/с^2]
```
Изменение не велико, так что можно довольствоваться линейной частью разложения. И учитывая, что планета планете рознь, также как и модель модели в особенности, с целью сохранить форму дифференциального уравнения модели — оставим всё как есть в первоначальном варианте.

**Замечание 4**. Если учесть, что [температура атмосферы Земли с высотой изменяется (Википедия)](https://ru.wikipedia.org/wiki/%D0%A1%D1%82%D0%B0%D0%BD%D0%B4%D0%B0%D1%80%D1%82%D0%BD%D0%B0%D1%8F_%D0%B0%D1%82%D0%BC%D0%BE%D1%81%D1%84%D0%B5%D1%80%D0%B0): так в тропосфере — в первом относительно литосферы слое атмосферы — температура падает, затем в стратосфере возрастает и, наконец, в мезосфере снова падает, и глядя на [график (Википедия)](https://commons.wikimedia.org/wiki/File:Comparison_International_Standard_Atmosphere_space_diving.svg?uselang=ru) — кривую температуры можно разбить на линейные участки, разница у которых будет в коэффициенте $\theta$, то закономерность температуры атмосферы с высотой можно выразить зависимостью
```math
T=T_0-\theta s
```
В данной моделе учитывается только падение температуры для того, чтобы изучить форму дифференциального уравнения. Безусловно, можно учесть всё, как обстоит дело в реальности, также как и для различных планет, которые могут находиться на иных расстояниях от своей звезды (или тесной двойной звезды), также как и сама звезда может быть иных размеров и иной температуры — более горячая или менее горячая по сравнению с Солнцем.
