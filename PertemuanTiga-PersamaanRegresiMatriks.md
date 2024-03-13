## Persamaan Regresi Bentuk Matriks

Perhatikan model linear

$$Y = \alpha + \beta x + \varepsilon$$

karena terdiri dari $n$ pengamatan yang berpasangan maka model di atas menjadi

$$Y_i = \alpha + \beta x_i + \varepsilon_i$$

atau

$$Y_1 = \alpha + \beta x_1 + \varepsilon_1 \\
Y_2 = \alpha + \beta x_2 + \varepsilon_2 \\
. \\
. \\
. \\
Y_n = \alpha + \beta x_n + \varepsilon_n

$$

apabila ditulis dalam bentuk matriks diperoleh

$$
\underrightarrow{Y} = \widetilde{X}\underrightarrow{\beta} + \underrightarrow{\varepsilon}$$

dengan

$$
\underrightarrow{Y} = \begin{pmatrix}
Y_1 \\
 Y_2\\
\vdots \\
Y_n \\

\end{pmatrix} ; 
\widetilde{X} = \begin{pmatrix}
1 & X_1 \\
1 &  X_2\\
\vdots & \vdots \\
1 & X_n
\end{pmatrix}\\

\underrightarrow{\beta}=\begin{pmatrix}
\alpha & \beta
\end{pmatrix};
\underrightarrow{\varepsilon}=\begin{pmatrix}
\varepsilon_1 \\
\varepsilon_2\\
\vdots \\
\varepsilon_n
\end{pmatrix}
$$

untuk memperoleh taksiran dari $\underrightarrow{\beta},$ dipergunakan metode kuadrat terkecil, maka dari persamaan di atas

$$
\underrightarrow{Y} = \widetilde{X}\underrightarrow{\beta} + \underrightarrow{\varepsilon} \\

\underrightarrow{\varepsilon} = \underrightarrow{Y} - \widetilde{X}\underrightarrow{\beta}
$$

jika kedua ruas dikuadratkan diperoleh
$$
\underrightarrow{\varepsilon}\underrightarrow{\varepsilon'} = (\underrightarrow{Y} - \widetilde{X}\underrightarrow{\beta})(\underrightarrow{Y} - \widetilde{X}\underrightarrow{\beta})'
$$

atau 

$$
\underrightarrow{\varepsilon}\underrightarrow{\varepsilon'} = \underrightarrow{Y}\underrightarrow{Y'} - 2\widetilde{X'}\underrightarrow{Y}\underrightarrow{\beta} + \widetilde{X}\underrightarrow{\beta}\underrightarrow{\beta'}\underrightarrow{X'}
$$

apabila $\underrightarrow{\varepsilon}\underrightarrow{\varepsilon'}$ diturunkan terhadap parameter $\underrightarrow{\beta}$ diperoleh:

$$
\frac{\partial (\underrightarrow{\varepsilon}\underrightarrow{\varepsilon'})}{\partial{\beta}} = -2 \widetilde{X'}\underrightarrow{Y} + 2\underrightarrow{\beta}\widetilde{X'}\widetilde{X}
$$

kemudian disamakan dengan nol diperoleh

$$
\underrightarrow{\beta}\widetilde{X'}\widetilde{X} =  \widetilde{X'}\underrightarrow{Y}
$$

atau 

$$
\underrightarrow{\beta} = (\widetilde{X'}\widetilde{X})^{-1} (\widetilde{X'}\underrightarrow{Y})
$$

sedangkan

$$
(\widetilde{X'}\widetilde{X})=\begin{pmatrix}
1 & 1 & \cdots  & 1 \\
\vdots  &  &  &  \\
X_1& X_2 & \cdots  & X_n 
\end{pmatrix}
\begin{pmatrix}
1 & X_1 \\
1 & X_2 \\
\vdots & \vdots  \\
1 & X_n
\end{pmatrix} = 
\begin{pmatrix}
 n & \Sigma X_i \\
 \Sigma X_i & \Sigma X_i^2
\end{pmatrix} (\star)
$$

$$
(\widetilde{X'}\underrightarrow{Y}) =\begin{pmatrix}
1 & 1 & \cdots  & 1 \\
\vdots  &  &  &  \\
X_1& X_2 & \cdots  & X_n 
\end{pmatrix}
\begin{pmatrix}
Y_1 \\
Y_2 \\
\vdots \\
Y_n
\end{pmatrix} = 
\begin{pmatrix}
\Sigma Y_i \\
\Sigma X_i Y_i 
\end{pmatrix}(\star)
$$

apabila $\underrightarrow{\beta}$ ditaksir oleh $\underrightarrow{b} = \begin{pmatrix}
a \\
b
\end{pmatrix}$ maka

$$
\underrightarrow{b} = (\widetilde{X}'\widetilde{X})^{-1}(\widetilde{X}'\underrightarrow{}{Y})(\star)
$$

untuk menguji koefisien regresi dengan menggunakan daftar Anova diperoleh sebagai berikut

$$
\begin{align*}
\text{jk}(b/a) &=&  b[\Sigma X_iY_i - \frac{\Sigma X_iY_i}{n}] \\

&=& b[\Sigma X_iY_i - n \bar{X}\bar{Y}] \\

\text{jk(a)} &=& \frac{(\Sigma Y_i)^2}{n} \\

&=& n\bar{Y}^2

\end{align*}
$$

Sedangkan derajat kebenaran untuk jk di atas adalah satu, maka

$$
\begin{align*}
\text{jk(b/a)}+\text{jk(a)} &=& b \Sigma X_iY_i - nx\bar{X}\bar{Y} + n\bar{Y}^2 \\

&=& b \Sigma X_iY_i + n\bar{Y}(\bar{Y} - b\bar{X}) \\

&=& b \Sigma X_iY_i + n\bar{Y} . a \\

&=& a\Sigma Y_i + b\Sigma X_i Y_i \\

&=& \begin{pmatrix}
a & b 
\end{pmatrix}
\begin{pmatrix}
\Sigma Y_i \\
\Sigma X_iY_i
\end{pmatrix} \\

&=& b'(\widetilde{X}'\underrightarrow{Y})
\end{align*}
$$

sedangkan jk total adalah

$$
\begin{align*}
\Sigma Y_i^2 &=& Y_1^2 + Y_2^2 + \cdots +Y_n^2 \\

&=& \begin{pmatrix}
Y_1 & Y_2 & \cdots  & Y_n
\end{pmatrix}
\begin{pmatrix}
Y_1 \\
Y_2 \\
\vdots \\
Y_n
\end{pmatrix}\\

&=& \underrightarrow{Y'}\underrightarrow{Y} (\star)

\end{align*}
$$

### Varians dari $b$ dalam Bentuk Matriks

$$
\begin{align*}
V(\underrightarrow{b}) &=& \sigma^2 (\widetilde{X'}\widetilde{X})^{-1}
(\star)
\end{align*}
$$

sedangkan

$$
(\widetilde{X'}\widetilde{X}) = \begin{pmatrix}
 n & \Sigma X_i \\
 \Sigma X_i & \Sigma X_i^2
\end{pmatrix} (\star)\\
$$
$$
(\widetilde{X'}\widetilde{X})^{-1} = \begin{pmatrix}
\frac{\Sigma x_i^2}{n\Sigma (x_i - \bar{x})^2} & \frac{-\bar{X}}{\Sigma (x_i - \bar{x})^2} \\
\end{pmatrix} (\star)
$$

### Varians $\underrightarrow{\bar{Y}}$ dengan menggunakan matriks

Misal $X_k$ merupakan nilai yang dipilih dari $X$.
Maka varians nya adalah

$$
V(\hat{Y_k}) = \underrightarrow{X_k} (\widetilde{X'}\widetilde{X})^{-1})\widetilde{X_k}\sigma^2 (\star)
$$
