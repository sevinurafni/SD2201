## Varians Koefisien Regresi dan Taksiran Nilai Respon
Dalam analisis regresi, kita menggunakan model regresi untuk memprediksi atau menjelaskan hubungan antara variabel independen dan variabel dependen. Dalam konteks ini, penting untuk memahami seberapa akurat dan stabil perkiraan koefisien regresi dari model. Varians koefisien regresi adalah salah satu ukuran yang digunakan untuk mengevaluasi stabilitas dan ketepatan estimasi koefisien regresi.


Varians koefisien regresi mengacu pada variabilitas atau ketidakpastian dalam estimasi koefisien regresi dari model. Ada dua koefisien regresi yang umumnya diperkirakan dalam regresi linier:

1. **Koefisien Kemiringan $(b)$**: Merepresentasikan seberapa besar perubahan dalam variabel dependen yang diharapkan akibat satu unit perubahan dalam variabel independen.

2. **Koefisien Perpotongan $(a)$**: Merepresentasikan nilai variabel dependen ketika semua variabel independen adalah nol.

3. **Varians Variabel Dependennya $(y)$**: Varians ini mengukur seberapa bervariasinya nilai-nilai variabel dependen $(y)$ dalam dataset.

Varians koefisien regresi memberikan informasi penting tentang seberapa akurat dan stabilnya estimasi koefisien regresi dari model regresi. Dengan memahami variabilitas ini, kita dapat mengevaluasi keandalan model regresi dan tingkat kepastian dalam prediksi yang dihasilkan oleh model.

Interpretasi Varians Koefisien Regresi

1. **Varians Koefisien Kemiringan $(var(b))$**: Menunjukkan seberapa bervariasinya estimasi koefisien kemiringan dalam model regresi terhadap variasi dalam data. Semakin rendah varians ini, semakin stabil dan konsisten perkiraan koefisien kemiringan dari model regresi.

2. **Varians Koefisien Perpotongan $(var(a))$**: Menunjukkan seberapa bervariasinya estimasi koefisien perpotongan dalam model regresi terhadap variasi dalam data. Varians ini juga mencerminkan seberapa konsisten estimasi perpotongan tersebut dalam berbagai sampel.

3. **Varians Variabel Dependennya $(var (y))$**: Menunjukan seberapa jauh data tersebar dari nilai rata-rata variabel dependen, atau seberapa besar variasi yang terdapat dalam variabel dependen.


### Varians dari $b$

$$
\begin{align*}
b &=& \frac{\Sigma (x_i - \bar{x})(Y_i - \bar{Y})}{\Sigma(x_i - \bar{x})^2} \\

&=& \frac{\Sigma\{(x_i - \bar{x})Y_i - (x_i - \bar{x})\bar{Y}\}}{\Sigma(x_i - \bar{x})^2} \\

&=& \frac{\Sigma(x_i - \bar{x})Y_i - \Sigma(x_i - \bar{x})\bar{Y}}{\Sigma(x_i - \bar{x})^2} \\

&=& \frac{\Sigma(x_i - \bar{x})Y_i }{\Sigma(x_i - \bar{x})^2} \\

&=& \frac{(x_1-\bar{x})Y1 + (x_2-\bar{x})Y2 + ...+(x_n-\bar{x})Yn}{\Sigma (x_i-\bar{X})^2}  \\
(1)

\end{align*}
$$

maka

$$
V(b) = V[\frac{(x_1-\bar{x})Y1 + (x_2-\bar{x})Y2 + ...+(x_n-\bar{x})Yn}{\Sigma (x_i-\bar{X})^2}]

(2)
$$

karena $Y_1, Y_2,...,Y_n$ saling bebas maka

$$
\begin{align*}
V(b) =\frac{(x_1 - \bar{x})^2V(Y_1) + (x_2 - \bar{x})^2V(Y_2)+...+(x_n - \bar{x})^2V(Y_n)}{[\Sigma(x_i - \bar{x})^2]^2}
\end{align*}
$$

atau 
$$
\begin{align*}
V(b) = \frac{[(x_1-\bar{x})^2+...+(x_n-\bar{x})^2]V(Y_i)}{[\Sigma(x_i - \bar{x})^2]^2}
\end{align*}
(3)
$$

dan $V(Y_i) = \sigma^2$

maka
$$
\begin{align*}
V(b) = \frac{\Sigma (x_i-\bar{x})^2 . \sigma^2}{[\Sigma(x_i - \bar{x})^2]^2} = \frac{\sigma^2}{\Sigma(x_i - \bar{x})^2}
(\star)
\end{align*}
$$

Sedangkan $\sigma^2$ ditaksir oleh standar error yang diperoleh dari daftar Anova.

### Varians dari $a$

Perhatikan persamaan berikut

$$
\bar{y} = a + b \bar{x} \\
a = \bar{y} - b \bar{x}
$$
 maka
$$
\begin{align*}
V(a) &=& V(\bar{y} - b\bar{x}) \\

&=& V[\frac{\Sigma y_i}{n} - b\bar{x}] \\

&=& \frac{\Sigma V(y_i)}{n^2} + \bar{x}^2V(b)\\

kov(b,\bar{y}) &=& E (b . \bar{y}) - E(b)E(\bar{y})
\end{align*}
$$

karena $kov(b,\bar{y} = 0)$ \
dan $V(y_i) = \sigma^2  \hspace{1cm} \forall _i$ maka

$$
\begin{align*}
V(a) &=& \frac{n\sigma^2}{n^2} + \bar{x}^2 V(b) \\
&=& \frac{\sigma^2}{n} + \bar{x}\frac{\sigma^2}{\Sigma(x_i-\bar{x})^2}
\end{align*}
$$

atau

$$
\begin{align*}
V(a) = \frac{\sigma^2 \Sigma{x_i^2}}{n\Sigma(x_i-\bar{x})^2}
(\star)
\end{align*}
$$

### Varians dari $\hat{Y}$

Persamaan regresi yang sudah kita peroleh

$$
\hat{Y} = \bar{y} + b(x - \bar{x})
$$

dengan $\bar{y}$ dan $b$ merupakan variabel yang mempengaruhi $\bar{Y},$ maka

$$
\begin{align*}
V(\hat{Y}) &=& V [\bar{y} + b(x-\bar{x})] \\

&=& V(\bar{y}) + (x-\bar{x})V(b) \\

&=& \frac{1}{n^2} \Sigma V(y_i) + (x - \bar{x})^2\frac{\sigma^2}{\Sigma(x_i-\bar{x})^2} \\

&=& \frac{\sigma^2}{n} + \frac{(x-\bar{x})^2 \sigma^2}{\Sigma(x_i-\bar{x})^2} \\

&=& \sigma^2 [\frac{1}{n}+\frac{(x-\bar{x})^2}{\Sigma(x_i-\bar{x})^2}] (\star)

\end{align*}
$$