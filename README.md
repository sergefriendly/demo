# Модель движение тела переменной массы

С непрерывно истекающим веществом по линейному закону в поле тяжести Земли перпендикулярно её поверхности с учётом диссипативной силы сопротивления среды, также с учётом изменения плотности воздуха с высотой по барометрическому закону и температурой линейно убывающей с высотой.

*Моделировалось явление и исследовалось дифференциальное уравнение*

$$ m\frac{d^2s}{dt^2}=-m\frac{g_0}{\left(1+\frac{s}{R_\oplus}\right)^2} - \frac{1}{2}\frac{p_0\mu}{R\left(T_0-\theta s\right)}\exp\left(-\frac{\mu g_0s}{R\left(T_0-\theta s\right)\left(1+\frac{s}{R_\oplus}\right)^2}\right)C_dA\left(\frac{ds}{dt}\right)^2+u\frac{dm}{dt} $$

$$ x = y $$

где
$m=m(t)=m_0-\beta t$ — масса тела переменной массы \[кг\];  
$\beta$ — расходы массы в единицу времени \[кг/с\];  
$u$ — скорость истечения газа (скорость отделяющихся частей) \[м/с\];  
$v=v(t)$ — скорость (функция от времени) тела переменной массы \[м/с\];  
$s=s(t)$ — путь (или высота применительно к этой модели, также функция от времени) тела переменной массы \[м\];  
$g_0/\left(1+s/R_\oplus\right)^2=g$ — ускорение свободного падения как фунцияя высоты $s$ \[м/с²\];  
$g_0$ — ускорение свободного падения у поверхности Земли (небесного тела: планеты) \[м/с²\];  
$R_\oplus$ — радиус Земли (небесного тела), равный  6 371 000 м;  
$p_0$ — атмосферное давление над уровнем моря, равное 101 325 Па;  
$\mu$ — молярная масса воздуха (атмосферы планеты), равная 0,02896 кг/моль;  
$R$ — универсальная газовая постоянная, равная 8,31 Дж/(моль ⋅ К);  
$T_0-\theta s=T$ — температура атмосферы Земли (планеты) (упрощённая модель) \[К\];  
$\theta$ — коэффициент изменения температуры атмосферы Земли (планеты) с высотой \[К/м\];  
$C_d$ — коэффициент лобового сопротивления поферхности тела в атмосфере Земли (планеты) \[безразмерная величина\];  
$A$ — площадь поперечного сечения этой поверхности \[м²\].  

# Замечания
Замечание 1. Уравнение выводилось на основе [уравнения Мещерского (Википедия)](https://ru.wikipedia.org/wiki/Уравнение_Мещерского)  

