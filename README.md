### Решение рекуррентного соотношения

Дано рекуррентное соотношение для последовательности $\Delta_n$:

#### 1. Вывод рекуррентной формулы

Исходя из определения, получаем:
$$
\Delta_n = 3 \cdot \Delta_{n-1} + 1 \cdot \begin{vmatrix}
-2 & -1 & 0 & \dots & 0 \\
0 & -2 & 3 & -1 & \dots \\
0 & 0 & -2 & 3 & -1 \\
\vdots & \vdots & \ddots & \ddots & \ddots \\
0 & 0 & \dots & 0 & -2
\end{vmatrix}_{(n-1) \times (n-1)} = 3 \cdot \Delta_{n-1} - 2 \cdot \Delta_{n-2}
$$

Таким образом, рекуррентное соотношение имеет вид:
$$
\Delta_n = 3 \Delta_{n-1} - 2 \Delta_{n-2}
$$

---

#### 2. Характеристическое уравнение

Предполагаем решение в виде $\Delta_n = \lambda^n$. Подставляем в рекуррентное соотношение:
$$
\lambda^n = 3 \lambda^{n-1} - 2 \lambda^{n-2}
$$

Делим обе части на $\lambda^{n-2}$ (при условии $\lambda \neq 0$):
$$
\lambda^2 = 3\lambda - 2
$$

Переносим все в одну сторону:
$$
\lambda^2 - 3\lambda + 2 = 0
$$

Решаем квадратное уравнение. По теореме Виета:
$$
\begin{cases}
\lambda_1 + \lambda_2 = 3 \\
\lambda_1 \cdot \lambda_2 = 2
\end{cases}
\quad \Rightarrow \quad
\begin{cases}
\lambda_1 = 2 \\
\lambda_2 = 1
\end{cases}
$$

Корни различны ($\lambda_1 \neq \lambda_2$), поэтому общее решение имеет вид:
$$
\Delta_n = C_1 \cdot \lambda_1^n + C_2 \cdot \lambda_2^n = C_1 \cdot 2^n + C_2 \cdot 1^n = C_1 \cdot 2^n + C_2
$$

---

#### 3. Нахождение констант $C_1$ и $C_2$

Используем начальные условия:
- $\Delta_1 = 3$
- $\Delta_2 = 7$

Подставляем в общее решение:
$$
\begin{cases}
\Delta_1 = C_1 \cdot 2^1 + C_2 = 2C_1 + C_2 = 3 \\
\Delta_2 = C_1 \cdot 2^2 + C_2 = 4C_1 + C_2 = 7
\end{cases}
$$

Вычитаем первое уравнение из второго:
$$
(4C_1 + C_2) - (2C_1 + C_2) = 7 - 3 \Rightarrow 2C_1 = 4 \Rightarrow C_1 = 2
$$

Подставляем $C_1 = 2$ в первое уравнение:
$$
2 \cdot 2 + C_2 = 3 \Rightarrow 4 + C_2 = 3 \Rightarrow C_2 = -1
$$

Таким образом, частное решение:
$$
\Delta_n = 2 \cdot 2^n - 1 = 2^{n+1} - 1
$$

---

#### 4. Вычисление $\Delta_7$

Подставляем $n=7$:
$$
\Delta_7 = 2^{7+1} - 1 = 2^8 - 1 = 256 - 1 = 255
$$
