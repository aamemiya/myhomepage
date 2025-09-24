---
title: "大気重力波の分散関係・偏波関係"
date: 2020-05-04T10:10:20+09:00
draft: false
type: parmanent
layout: base_research
---

大気重力波は、数学的には線形化した基礎方程式系の解として記述される。その解の満たす条件が分散関係と偏波関係である。重力波に注目するのに適した基礎方程式系と、線形化した方程式の解の表現、分散関係と偏波関係の導出について述べる。また大気の場合に問題となる背景場の密度成層の高度依存性の扱いについても説明する。  

## 基礎方程式

3次元直交座標系にて、大気が従う力学的・熱力学的法則を最も基本的な形で記述すると、次のように運動方程式、質量保存の式、熱力学第一法則の3つの式から書ける。

運動方程式
$$ \frac{du}{dt} = fv - \frac{1}{\rho}\frac{\partial p}{\partial x}  $$
$$ \frac{dv}{dt} = - fu - \frac{1}{\rho}\frac{\partial p}{\partial y}  $$
$$ \frac{dw}{dt} =  - \frac{1}{\rho}\frac{\partial p}{\partial z} - g $$

質量保存の式
$$ \frac{1}{\rho} \frac{d\rho}{dt} = - \nabla \cdot \bv{v}$$

熱力学第一法則の式
$$ \frac{d\theta}{dt} = \frac{\theta}{C_p T} Q$$ 

ただし、
$$ \frac{d}{dt} \equiv \frac{\partial}{\partial t} + u \frac{\partial}{\partial x} + v \frac{\partial}{\partial y} + w \frac{\partial}{\partial z} $$
は流れに乗った系での時間変化を表す物質時間微分である。  
また、$g$は重力加速度、$f$はコリオリパラメータ、$C_p$は定圧比熱、$Q$は非断熱加熱($Ws^{-1}$)である。  

この方程式系は非線形であり（連続体としての扱いが可能な）どのようなスケールのどんな現象についても成り立つ式である。  
ここから、大気重力波に注目するために、**その現象の時空間スケールと振幅に適した近似を行い**、重力波が解となるような線形の方程式系を導く。

### 非弾性近似

例として、境界層の中で風の水平収束があるような状態における質量保存の式の各項を考える。
$$ \frac{1}{\rho} \frac{d\rho}{dt} = - \left( \frac{\partial u}{\partial x} + \frac{\partial v}{\partial y} \right) - \frac{\partial w}{\partial z}$$

風の水平収束があるとき右辺の第1項の括弧内が負となるが、上式のみでは、それが左辺の時間変化の項と、右辺第2項の鉛直発散のいずれによって釣り合っているかを特定することができない。  
しかし直感的には、時間スケールによって異なる挙動をすることが容易に推測できる。  

 - 水平収束が瞬間的に起こる場合はその場で空気の圧縮が起きると考えられる。すなわち右辺第一項の分だけ左辺が大きくなりそうである。
 - 一方、水平収束がある程度の時間にわたって緩やかに続く場合は、同程度の鉛直流が発生してつりあう状態となりそうに思える。すなわち、右辺第1項の括弧と第2項がほぼ同じ大きさで打ち消しあい、左辺は0に近い状態が予想される。

気象学的に興味のある現象は、後者のような、局所的な収束・発散による圧縮・膨張のない時間スケールにおいて起こる。  

仮に、密度を時間変化しない背景場の成分$\rho\_0(z)$と微小な時間変化の成分$\rho'\equiv\rho-\rho\_0$とに分けることができるとすると、考えている時間空間スケールにおいて、下の式がそれぞれ別々に成り立つ。  

$$ \frac{d \rho'}{d t} = - w \frac{d \rho\_0}{\partial z}$$
$$ \frac{\partial u}{\partial x} + \frac{\partial v}{\partial y} + \frac{\partial w}{\partial z} = 0$$

また、同様に気圧も背景場$p\_0(z)$と時間変化成分$p'$とに分解すると、鉛直方向の運動方程式から背景場の成分を除くことができ、次のように書ける。
$$ \frac{dw}{dt} = -\frac{1}{\rho_0}\frac{\partial p'}{\partial z} -g \frac{\rho'}{\rho\_0} $$

ここで$-g \frac{\rho'}{\rho\_0}$は背景の（静水圧平衡の状態にある）密度成層の中での密度差に起因する鉛直加速度、すなわち**浮力**である。  

このように、密度変化のうち圧縮性に伴う部分を無視し、基準となる成層状態からのずれにより浮力をもたらす密度差のみを表現するような近似が**ブジネスク(Bousinnesque)近似**である。ブジネスク近似は音波を除き重力波のような非圧縮的な運動のみを考えるための基礎方程式として非常に便利である。

海洋のように密度が圧力によらない系では、ブジネスク近似が鉛直流を伴う運動の良い近似となる。しかし大気では、状態方程式が表す通り密度は気圧に大きく依存しており、興味のある高度範囲において気圧が幅広い値の範囲をとるときは密度の値も大きく変化する。例えば対流圏全体にわたる深い対流においては、地表付近の空気が対流圏界面付近まで持ち上げられると密度が約1/4になる。  

ブジネスク近似において無視していた背景場の密度$\rho\_0(z)$の鉛直変化の運動量輸送への影響を考慮し、なおかつ音波に関わる圧縮性を無視する近似が、**非弾性近似**である。非弾性近似は、メソ気象や大気重力波に関する理論における基礎方程式として頻繁に用いられる。  
非弾性近似の導出は小倉義光「メソ気象の基礎理論」(1997)に詳しく記述されている。なお、本稿では背景場の温位一定と近似する通常の非弾性近似の代わりに、温位$\theta\_0(z)$が鉛直方向に緩やかに変化する状況へと拡張した、より一般的な近似に基づく下記の方程式系(Lipps and Hemler, 1982)を用いる。  

$$ \frac{du}{dt} - fv = -\frac{1}{\rho_0}\frac{\partial p'}{\partial x}  $$
$$ \frac{dv}{dt} + fu = -\frac{1}{\rho_0}\frac{\partial p'}{\partial y}  $$
$$ \frac{dw}{dt}      = -\frac{\partial}{\partial z}\left(\frac{p'}{\rho_0}\right)+ g \frac{\theta'}{\theta_0} $$
$$ \frac{d \theta'}{\partial t} + w \frac{d \theta_0}{dz} = 0 $$
$$ \frac{\partial u}{\partial x} + \frac{\partial v}{\partial y} + \frac{1}{\rho_0}\frac{\partial}{\partial z}\left( \rho_0w \right) = 0 $$

### 方程式の線形化

上の方程式系において、水平風速を次のように背景場と擾乱に分解する。

$$ u = \overline{u} + u' ,\ \ v = \overline{v} + v' $$ 

ここで背景場$\overline{u}$、$\overline{v}$は一般に定数とは限らず、時間・空間の関数である場合も考えられる。背景場が時間・空間的に「緩やかに変化する」場合も、重力波の解を近似的に用いて議論することができる。その場合の理論も、背景場が一様である場合の基本的な重力波の性質を発展させたものとなる。  
以下では、まずは$\overline{u}$、$\overline{v}$が時空間的に一様な定数であるとして扱うこととする。  
擾乱$u'$、$v'$ が 微小であるとして2次の項を無視し、擾乱に関する方程式を線形化する。  

ただし、非弾性近似の場合、背景場の密度$\rho\_0$が鉛直微分の中に入っている部分の扱いに工夫が必要である。この$\rho\_0$の扱いについては慣習的な手法があるが、それについては後に述べることにする。先に分散関係の導出を単純な状況で説明するため、**さしあたり、ブジネスク近似が成り立つ状況を考える。**すなわち考えている領域で$\rho\_0(z)$が大きく変化しないとして定数とみなす。このとき、線形化した方程式は以下のようになる。

$$ \frac{\partial u'}{\partial t} + \overline{u} \frac{\partial u'}{\partial x} + \overline{v} \frac {\partial u'}{\partial y} - fv' = -\frac{1}{\rho_0}\frac{\partial p'}{\partial x}  $$
$$ \frac{\partial v'}{\partial t} + \overline{u} \frac{\partial v'}{\partial x} + \overline{v} \frac {\partial v'}{\partial y} + fu' = -\frac{1}{\rho_0}\frac{\partial p'}{\partial y}  $$
$$ \frac{\partial w'}{\partial t} + \overline{u} \frac{\partial w'}{\partial x} + \overline{v} \frac {\partial w'}{\partial y}      = -\frac{1}{\rho_0}\frac{\partial p'}{\partial z}+ b'  $$
$$ \frac{\partial b'}{\partial t} + \overline{u} \frac{\partial b'}{\partial x} + \overline{v} \frac {\partial b'}{\partial y} + N^2 w' = 0 $$
$$ \frac{\partial u'}{\partial x} + \frac{\partial v'}{\partial y} + \frac{\partial w'}{\partial z} = 0 $$

なお、$w$については基本的に背景場を定義する必要がない（重力波より大きなスケールの鉛直流は無視できるほど小さい）が、便宜的に$u',v'$と同様に$w'$と表した。第4式には両辺に$g / \theta\_0$を掛け、$b'\equiv g \theta' / \theta\_0$ を浮力(buoyancy)の擾乱として定義した。また、

$$ N^2 \equiv \frac{g}{\theta\_0} \frac{\partial \theta\_0}{\partial z} $$  
が背景場の**ブラント・バイサラ振動数**（浮力振動数）である。  


## 分散関係

線形化した方程式系から分散関係・偏波関係を求める方法はさまざまであるが、以後の説明の導入を容易にするため、ここでは一般的なフーリエ変換から導く方法をとることにする。  
変数$u'$、$v'$、$w'$、$b'$ および $p'$が時間・空間方向に境界なしの無限領域で定義されており、上の方程式を満たしていると考える。  また、背景場の変数$\overline{u}$、$\overline{v}$、$f$、$\rho\_0$および$N^2$は時間・空間的に一様であるとする。  

時間空間方向の合計4次元全てについてフーリエ変換すると、例えば$u'$は次のように書ける。  
$$u'(x,y,z,t) =\left(2\pi\right)^{-4} \int\int\int\int \hat{u}(k,l,m,\omega) \exp (ikx+ily+imz-i\omega t)\,  dk dl dm d\omega $$

$k,l,m$ はそれぞれ$x,y,z$方向の波数、$\omega$は周波数である。指数部で$\omega$につく符号のみ負としているが、これは位相速度の向きの直感的概念と整合させるためである。  
時空間的に無限領域を考えているので、$\hat{u}(k,l,m,\omega)$も波数・周波数について無限領域で定義される。積分もすべて無限小から無限大までの範囲である。  
フーリエ変換を用いると、時間・空間に関しての偏微分を次のように周波数・波数の掛け算で置き換えることができる。
$$\frac{\partial u'}{\partial t} =\left(2\pi\right)^{-4} \int\int\int\int -i\omega \hat{u}(k,l,m,\omega) \exp (ikx+ily+imz-i\omega t)\,  dk dl dm d\omega $$
$$\frac{\partial u'}{\partial x} =\left(2\pi\right)^{-4} \int\int\int\int ik \hat{u}(k,l,m,\omega) \exp (ikx+ily+imz-i\omega t)\,  dk dl dm d\omega $$

これらを用いて、元の線形化した方程式の各項をすべてフーリエ変換で表現し、一つの式にまとめると次のようになる。
$$ \int\int\int\int \left[N^2(k^2+l^2)+f^2 m^2 - \left( k^2+l^2+m^2 \right) \left( \omega-k\overline{u}-l\overline{v} \right) \right] \hat{w}(k,l,m,\omega) \exp (ikx+ily+imz-i\omega t)\,  dk dl dm d\omega = 0 $$

これは、物理空間すなわち任意の$x,y,z,t$で成り立つ恒等式である。これをフーリエ逆変換することで、**$\hat{w}\ne 0$である限り**、任意の$k,l,m,\omega$が次の式を満たす。
$$ N^2(k^2+l^2)+f^2 m^2 - \left( k^2+l^2+m^2 \right) \left( \omega-k\overline{u}-l\overline{v} \right) = 0 $$

簡単のため、次の**固有周波数**$\hat{\omega}$を定義しておく。この物理的意味は後に述べる。
$$ \hat{\omega} \equiv \omega -k \overline{u} -l \overline{v} $$

以上を整理して、重力波の解を平面波として表現するとき、各方向の波数と周波数が満たすべき条件として、次の分散関係が得られた。

$$ \hat{\omega}^2 = \frac{N^2(k^2+l^2)+f^2m^2}{k^2+l^2+m^2} $$

## 偏波関係

偏波関係は、ある波数・周波数を持つ波の異なる変数の間に成り立つ関係である。各変数をフーリエ変換したものを方程式系に代入し、二つの変数の間の関係を求めることができる。例えば$\hat{w}$から他の変数を求める式はそれぞれ次のようになる。
$$ \hat{b}= - i \frac{N^2}{\hat{\omega}}\hat{w}$$
$$ \hat{p}= -\frac{\rho\_0(N^2-\hat{\omega}^2)}{m\hat{\omega}}\hat{w}$$
$$ \hat{u}= -\frac{(k\omega+ilf)(N^2-\hat{\omega}^2)}{m\hat{\omega}(\omega^2-f^2)}\hat{w}$$
$$ \hat{v}= -\frac{(l\omega-ikf)(N^2-\hat{\omega}^2)}{m\hat{\omega}(\omega^2-f^2)}\hat{w}$$

## 固有周波数・固有位相速度

重力波の**位相速度**は、周波数と波数の比で定義される。例えばx方向の位相速度は次のように定義される。  
$$ c_{px} = \omega / k $$
これは実体として流体が動く速度ではなく、波の見掛けの擾乱のパターンが移動する速度である。（また情報が伝わる速度でもない）  

固有周波数$\hat{\omega}$は、流れに乗った座標系で観測される波の周波数であるとみなすことができる。例えば波が$x$方向の波数のみを持ち、x方向に流れ$\overline{u}$がある場合、**固有位相速度**は定義より次のようになり、単純に波のパターンの変化から流れによる移動の効果を差し引いて見ていることになる。
$$ \hat{c}\_{px} = \hat{\omega} / k = c\_{px} - \overline{u} $$

## 振幅の微小パラメータ

ここで、後の議論のために振幅に関する微小パラメータを導入しておく。  
方程式を線形化する際に、まず（拡張した）非弾性近似を行い、その上で風速に関しても2次の項を無視できるとする近似を行った。  
ここまで重力波の解である($'$)付きの変数の値は「十分に微小である」としてきたが、本来なら何か基準の量との比として相対的なパラメータを定義し、そのパラメータが微小であるとすべきである。  

本稿全体を通して、重力波の表現のための微小パラメータは全部で3個導入することになる。この振幅の微小パラメータはそのうちの1個目である。  

振幅に関してはその基準の置き方が一通りではないが、最も自然な定義として、重力波における復元力である背景場の浮力$N^2$を基準とすることにすると、満たすべき式は次のようになる。
$$ \left|\frac{g}{\theta\_0} \frac{\partial \theta'}{\partial z}\right| \ll \frac{g}{\theta\_0} \frac{\partial \theta\_0}{\partial z} $$ 
これは、「重力波による擾乱が背景場の成層を乱さない程度に小さい」と理解できる。両者が同程度に大きい状況では、重力波による擾乱で成層が局所的に不安定となり、近似的な重力波の解が成り立たなくなる。  

重力波の解を用いると上の式は次のように書ける。
$$ \left| m\hat{b} \right| \ll N^2 $$ 
さらに、偏波関係を用いると
$$ \left| \hat{w} \right| \ll \frac{m}{\hat{\omega}} $$ 
これは「鉛直速度の擾乱が鉛直位相速度より十分小さい」ことを意味する。

## 密度成層の扱い

ここまで簡単のため無視していたが、大気重力波で問題となる高度範囲では$\rho\_0(z)$、$\theta\_0(z)$はいずれも高度の関数であり、全体でほぼ一定とする近似が成り立たないことが多い。  
成層圏上部や中間圏まで考慮する場合、$\theta_0(z)$は地表での値の2倍～3倍まで大きな値をとりうる。ただし$\theta_0(z)$については、鉛直方向の変化の長さスケールが比較的大きく、局所的には変化を無視して背景場一定とみなすWKB近似によって対応することが一般的である。  
一方、$\rho_0(z)$については中間圏では地表付近とは3桁以上異なる値であり、変化の鉛直スケール(スケールハイト)も重力波の波長に比べて必ずしも大きくはない。そこで、$\rho_0(z)$の鉛直構造は次のような手法で考慮する。  
まず、
$$\rho_0(z) = \rho\_{00} \exp\left(-\frac{z}{H}\right)$$
とおく。ここで$\rho\_{00}$は定数、$H$は密度に関するスケールハイトである。  
次に、各変数を
$$ [ \tilde{u}, \tilde{v}, \tilde{w}, \tilde{b} ] \equiv [ u', v', w', b' ] \exp\left(-\frac{z}{2H}\right)$$
$$   \tilde{p} \equiv p' \exp\left(\frac{z}{2H}\right)$$
と定義しなおし、これらを用いて方程式を書き直すと次のようになる。

$$ \frac{\partial \tilde{u}}{\partial t} + \overline{u} \frac{\partial \tilde{u}}{\partial x} + \overline{v} \frac {\partial \tilde{u}}{\partial y} - f\tilde{v} = -\frac{\partial \tilde{p}}{\partial x}  $$
$$ \frac{\partial \tilde{v}}{\partial t} + \overline{u} \frac{\partial \tilde{v}}{\partial x} + \overline{v} \frac {\partial \tilde{v}}{\partial y} + f\tilde{u} = -\frac{\partial \tilde{p}}{\partial y}  $$
$$ \frac{\partial \tilde{w}}{\partial t} + \overline{u} \frac{\partial \tilde{w}}{\partial x} + \overline{v} \frac {\partial \tilde{w}}{\partial y}      = -\left(\frac{\partial}{\partial z}-\frac{1}{2H}\right)\tilde{p}  $$
$$ \frac{\partial \tilde{b}}{\partial t} + \overline{u} \frac{\partial \tilde{b}}{\partial x} + \overline{v} \frac {\partial \tilde{b}}{\partial y} + N^2 \tilde{w} = 0 $$
$$ \frac{\partial \tilde{u}}{\partial x} + \frac{\partial \tilde{v}}{\partial y} + \left(\frac{\partial}{\partial z}+\frac{1}{2H}\right)\tilde{w} = 0 $$
上式に$[ \tilde{u}, \tilde{v}, \tilde{w}, \tilde{b}, \tilde{p} ]$をフーリエ変換したものを代入すると、同様に分散関係・偏波関係の式を得ることができる。  

スケールハイト$H$は、実際のデータに合わせて適当な値を与えるか、気温$T$(K)を用いて
$$ H = \frac{R_d T}{g}$$
と求めることができる。このとき実際上は$H$を空間の関数として用い、WKB近似を適用することになる。  
表記を簡単にするため $\alpha\equiv 1 / (2H) $ を導入すると、新たな分散関係は次のようになる。  

$$ \hat{\omega}^2 = \frac{N^2(k^2+l^2)+f^2(m^2+\alpha^2)}{k^2+l^2+m^2+\alpha^2} $$

変換した変数$\tilde{u}$などが振幅が全空間で一定の平面波の解をもつため、元の物理量に戻した$u',v',w',b'$は$\exp(z/2H)$に比例して振幅が高さとともに増大する。例えば密度が地表の$10^{-4}$倍となる高度においては振幅は100倍となる。この理由で、対流圏で発生し上空に伝播した重力波は、元々小さな振幅でも、成層圏・中間圏では著しく大きな風や温度の擾乱をもたらす。

