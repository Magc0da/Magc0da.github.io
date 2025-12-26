---
title: "固态Abel群的六函子"
date: 2025-12-26
draft: false
math: true  # 必须开启，否则公式不渲染
---

# 1. 上同调想要成为层论, 层论想要变成六函子.

代数几何以其多得批爆的上同调理论令人呃呃, 我们目前已知的就有
1. ~~J.K.Love~~ , ~~ming~~, 凝. 凝聚层做系数的凝聚上同调 $H_{\text{Coh}}^{\ast}(-,\mathcal{O})$. 最简单的情况就是取结构层自身, 其它不外是拼好层 $\mathcal{O}^{\oplus n}$. 
2.   奇异/ Betti 上同调 $H_{\text{B}}^{\ast}(-,\mathbb{Z})$.
3.   $\ell$-adic 上同调 $H_{\ell}(-,\mathbb{Z}_{\ell})$, 如果你想翻译那个 adic 也可以叫它 $\ell$ 进. (我觉得这几个符号写来写去纯水字数的,,,最多强调系数和概形定义所取的环/域不一样)
4.   代数 de Rham 上同调 $H_{\text{dR}}^{\ast}(-/k)$. 
5.   刚性上同调 $H_{\text{rig}}(-/K)$.
   
纵使聚焦在代数几何, 各家上同调理论说的道理也不完全一样. 这点主要是因为负责解决的问题以及相应代数工具不一样.

对于凝聚层上同调, 它谈论的是任意环 $R$ 上的任意概形, 作为代数的结果, 计算得到的产物是 $R$-模. 本文从简, 不考虑病态反例而只观 finite type $R$-scheme with $R$ Noetherian. 代数几何的 Betti 上同调则试着去计算 finite type $\mathbb{C}$-scheme 的代数不变量, 产出 Abel 群. 而到了格人力作 $\ell$ 进上同调时则是需要在特征非 $\ell$ 的代数闭域 $k$ 上产出 $\mathbb{Z}_{\ell}$-模. 代数 de Rham 上同调则需要域特征保持不正时方能有效料理 finite type $k$-scheme (话说迄今有 non finite 的吗? 恼), 产物是 $k$-向量空间. 说到这你都不觉得有那么点来回流水线吗? "刚性上同调为定义在特征 $0$ 非 Archimedean 赋值域 $K$ 的特征 $p$ 剩余域上取有理点的代数簇服务的",  平安时代的数学家 John Tate 的格言, 想必大家也都不由自主回想起来了吧个头啊. 反正产物也是 $K$-向量空间就对了. 

实际上这套流程的共通点是如此之多, 乃至于我们看上去像在进行一个巨大的废话文学先锋实验. 那么数学家不是傻子, 历史上我们敬爱的格人13 (哦 Grothendieck! 我们赞美你!) 作为若干上同调企划的主创, 看着它们 (虽然实际上只是 Betti 到刚性) 这黑道复制人一样都共享一套 Kunneth 公式, Poincare 对偶, 于是擅作主张给它们找了个妈: 这窝上同调是 Weil 生的, 所以就愉快决定叫做 Weil 上同调好了. 好吧, 实际上是 Weil 猜测正特征光滑射影簇也有个上同调,  这些上同调还巨大性情(当然, 完整的证明还需要 Deligne 使用行列式绝技肘死抽象废话) 地干掉了 Weil zeta over finfield 的一系列猜想.   

但这时候有人就要问了, 主播主播, 这不是从代数拓扑嗯偷的吗? 唉, May 学派激烈的斗争! 那么实际上只有 Betti 上同调是代数拓扑派来的内鬼, 而其它三个的乘积和对偶并不是很代数拓扑道理.  话虽如此, Betti 上同调提供的直觉依然在今天帮我们老法之后重走数学. 顺便刚性这个词是格人quit以后出现的, 最早还是晶体上同调.

对于当时无法用代数拓扑道尽一切的相似性, 格人认为这是不自然的. 那么既然强找的妈不压抑, 格人干脆直接根据他手操代数圈苦练 $K$-理论的感悟, 直接一步到位, 虚空造妈, 妈题范畴, 堂堂登场! 虽然历史证明妈题解决了零个技术困难, 但这种神秘的, 让人蒙古而在意的相似性, 始终若即若离, 仿佛一个来自 20 世纪虚空和反战主义的幽灵徘徊在数学界上空. 也正因如此, 我们即将回到梦开始的地方, 从 Betti 上同调一窥几何直观并偷偷扔掉技术困难. 一个很神奇的事情是, 从 Betti 出发到其它上同调能走全整屋子 Weil 上同调.

聪明的读者已经注意到, 笔者废话半天, 开 $\text{im}$ party 却不带凝聚层上同调玩, 立刻开除代数几何学籍! 但这货和后面几个上同调实则望之不似一母所生:

### Example 1.1 Affine line
 
$H_{\text{B}}^{\ast}(\mathbb{A}_{\mathbb{C}}^1,\mathbb{Z}) = H_{\text{sing}}^{\ast}(\mathbb{C},\mathbb{Z}) = H_{\text{sing}}^0(\mathbb{C},\mathbb{Z}) = \mathbb{Z}[0]$.

这是因为 $\mathbb{C}$ 可缩, 但凝聚层上同调就不一样了, 它长这样:

$H_{\text{Coh}}^{\ast}(\mathbb{A}_{A}^1, \mathcal{O}) =H_{\text{Coh}}^{0}(\mathbb{A}_{A}^1) =  \mathcal{O}_{\mathbb{A}_{A}^1} = (A[t]) [0]$

于是在 Weil 上同调看来仿射直线可缩, 而凝聚层上同调看不见这点. 这也同样说明, finite type $k$-scheme 的 Weil 上同调群必有限生成, 但 finite type $R$-scheme 的凝聚层上同调就未必有限 $R$-生成了. 

### Example 1.2 Tate twist

$H_{\text{B}}^{\ast}(\mathbb{P}_{\mathbb{C}}^1,\mathbb{Z}) = H_{\text{sing}}^{\ast}(S^2,\mathbb{Z}) =  \mathbb{Z}[0] \oplus H_{\text{B}}^{2}(\mathbb{P}_{\mathbb{C}}^1)$.

$H_{\text{B}}^{2}(\mathbb{P}_{\mathbb{C}}^1)$ 这个秩 $1$ 自由 Abel 群也被称作 Tate twist $\mathbb{Z}(1)$, 可见 Tate 是个扭曲沉重的主唱(草). 对所有 Weil 上同调, $H^2(\mathbb{P}^1)$ 都贡献了上同调的成分, 成为研究 Weil 上同调的必经之路. 但凝聚上同调有零个 Tate twist:  $H_{\text{Coh}}^{\ast}(\mathbb{P}_{A}^1, \mathcal{O}) = A[0]$.

### Example 1.3 Non-reducedness

这一回轮到 Weil 上同调样衰了. Weil 上同调在观察既约性质的时候表现不佳. 比如还是 finite type 但 non reduced 的 $\mathbb{C}$-代数 $R$, (比如 $\mathbb{C}(x)/(x^2)$) 解析化其素谱 $\text{Spec}(R)^{\text{an}}$ 得到的等同于对既约部分解析化 $\text{Spec}(R_{\text{red}}^{\text{an}})$, Betti 上同调又分不清解析化前后区别, 从这个层面就误判两者, 得到 $H_{\text{B}}^{\ast}(\text{Spec}(R),\mathbb{Z}) =H_{\text{B}}^{\ast}(\text{Spec}(R_{\text{red}}),\mathbb{Z}) $, 但凝聚上同调直接来自代数, 它分得清: $H_{\text{Coh}}^{\ast}(\text{Spec}(R), \mathcal{O}) =R[0] \neq R_{\text{red}}[0]= H_{\text{Coh}}^{\ast}(\text{Spec}(R_{\text{red}}), \mathcal{O})$, 类似的情况是凝聚上同调也拎得清 universal homeomorphism $f:X\to Y$ 联系的 $X,Y$ 的两个上同调, 而 Weil 上同调不行.

以上论述其实告诉我们两点: 如果有一个真正的上同调大一统理论, 那么不仅可以用很神棍/美好的方式整合语言, 还能让上同调优势互补, ~~战力~~结构的良性直接起飞. 而尽管差异确实存在, 这两个上同调理论在合适的观念下的确能够归一, 而解释这种共性的责任落在了数学界最新最酷抽象废话: 范畴论身上.

一言以蔽之, Weil 上同调和凝聚上同调的共同点在于, 它们都蕴含丰富的函子性. 而这个函子性的充分解释, 来自六函子公理.

大致来说, 六函子公理的定位如同其在香蕉空间或 Scholze 讲义上的写法一样, 是炮制上同调的流水线. 但之所以能炮制肯定还是因为它触碰到了上同调理论的根基共性本身. 我们会看到六函子公理如何统一及推广两侧的两大对偶定理, 即凝聚侧的 Serre 对偶与 Weil 侧的 Poincare 对偶. 这正印证数学金曲 [跟平展爆了](https://www.bilibili.com/video/BV1im421W7in/) 所论及的 "脚踢对偶定理". 所谓六函子, 也就是层的导出范畴上的六个操作 $f_{\ast}, f^{\ast}, f_!, f^!, \underline{\text{Hom}}, \otimes$. 具体的含义后面会逐一道来. 顺带一提, 这个东西的前身来自格人的六操作.

故事某种程度上还是说回格, 他其实从凝聚侧的对偶定理多少意识到两者(凝聚与 Weil )的[共性](https://link.springer.com/book/10.1007/BFb0080482), 而这个相似性在 Weil 上同调发展到平展/ $\ell$ 进 (SGA4, 5) 时更一眼丁真, 后来 Verdier 也干了 [Betti](https://www.numdam.org/item/SB_1964-1966__9__337_0.pdf) 侧的故事. 但很不幸, 经典拟凝聚层导出范畴相容不了六函子, 只能相容 $5$ 个, 问题主要出在没法按经典去定义紧支凝聚上同调这个东西, 也就无 $f_!$ 可言了. [文献](https://link.springer.com/book/10.1007/BFb0080482) 的证明是纯粹技术性嗯证, 不如 Betti 和 $\ell$ 进那么自然. 

故事来到今天, 饱受同人女推崇(推崇在哪?)的王道数学 CP Clausen, Scholze 发明了"这才是真正的数学"的 [condensed math]( https://www.math.uni-bonn.de/people/scholze/Analytic.pdf) (也就是主页上那个Coagula in Condensatum所指的"在凝聚中凝结"). 这从本质上允许了一个为解析几何而设立的拟凝聚层六函子理论, 此处的解析几何兼顾了复与刚性, 给他典范深刻完了. 

此刻, 对于凝聚上同调, 和 Weil 上同调的形似将不再止步于直觉, 而是彻底从凝聚态的固态 Abel 群及固态模理论上获取它期待已久的完整版六函子公理. 六函子公理在算术几何/代数几何上的应用都很广泛, 至少就这次讨论的两方, 凝聚侧概形导出范畴的范畴等价以及刻画这些等价的函子基本都是 Fourier-向井变换给出, 而这个变换的构造完全来自六函子, [参考](https://doi.org/10.1093/acprof:oso/9780199296866.001.0001). 
对 Weil 侧而言, 则莫过于 (还是) $\ell$ 进上同调消灭 Weil 猜想, 这些在 SGA 5 和 Delgine 的经典工作里面都能看见. 至于 Betti 侧的六函子, 则被争议风云人物传奇数学家柏原正树做去了, 参考[此书](https://doi.org/10.1007/978-3-662-02661-8) 第 $2-3$ 章. 想专门看六函子的话可以 [Scholze原文](https://people.mpim-bonn.mpg.de/scholze/SixFunctors.pdf) 或者 [B站](https://www.bilibili.com/video/BV1qrcGe4EGs/?spm_id_from=333.337.search-card.all.click&vd_source=97577a0e11aaf82cdf5b70317089a813).  



<!-- {{< theorem type="Lemma" >}} 

{{< /theorem >}}

cite a link [菜鸟教程](https://www.runoob.com)  

{{< proof >}}
这里写具体的证明步骤...
{{< /proof >}}

-->


# 2. 上同调: 我来成为层

对于一个 finite type $R$-scheme $X$, 我们有结构态射 $\pi_X: X\to \text{Spec}(R)$, 于是对 $X$ 上的拟凝聚层 $\mathcal{F}\in \text{QCoh}(X)$, 凝聚上同调 $H_{\text{Coh}}^{i}(X, \mathcal{F})\cong R^i {\pi_X}_{\ast}\mathcal{F}:\text{QCoh}(X) \to \text{QCoh}(R)\cong R-\text{Mod}$, 后者是前推函子 ${\pi_X}_{\ast}:\text{QCoh}(X) \to \text{QCoh}(R) $ 的第 $i$ 次导出函子. 各度上同调皆可封装到 $X$ 的 Zariski 层复形的导出范畴 $D_{\text{qcoh}}(X)$, 导出范畴内凝聚上同调是拟同构的. 任意概形之间的态射 $f:X\to Y$ 诱导相应的导出前推函子: 
$$
R f_{\ast}: D_{\text{qcoh}}(X) \to D_{\text{qcoh}}(Y)
$$

以及作为左伴随的导出拉回函子: 
$$
Lf^{\ast}: D_{\text{qcoh}}(Y) \to D_{\text{qcoh}}(X)
$$ 

