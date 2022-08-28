Notes from DearJohn-2
=====
<a href="https://dearjohnsonny.github.io/Notes-from-DearJohn/">Notes from DearJohn</a>

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/187057747-7cb5e02e-5596-4bc4-a9b4-219cb731ee6c.png" width="1500">
</div>


## 基于CRISPR的基因编辑
基于CRISPR的基因编辑方式主要有四种，包括：**nucleases(核酸酶), base editors(碱基编辑器)**, transposases/recombinases(转座子/重组酶类) and prime editors(引物编辑器).

Homology-directed repair (HDR); cytosine base editor (CBE); adenine base editor (ABE); end-joining (EJ); prime editor (PE); uracil glycosylase inhibitor (UGI); **protospacer adjacent motif (PAM)**.

![1](https://user-images.githubusercontent.com/111955215/187057959-382192c9-397a-4806-9f42-76560272313f.png)

### 通过CRISPR–Cas核酸酶来实现基因编辑
家族Ⅰ用多种蛋白质进行核酸的切割，而家族Ⅱ用一种蛋白质进行切割（下图还应该补充下，classⅡ中还有typeⅣ，如Cas-13）

![image](https://user-images.githubusercontent.com/111955215/187058140-b2c8f4a8-70f9-4476-a906-cbe32609aa85.png)
#### Cas9家族
Cas9在protospacer序列上产生切割，大约在PAM前3bp的位置，且会用Cas9上两个不同的结构域（RuvC and HNH）进行切割产生非粘性末端。目前使用最广泛的 CRISPR-Cas 核酸酶 SpCas9含有1,368个氨基酸，识别相对常见的 NGG PAM，可以与 sgRNA 或 crRNA/tracrRNA 对一起使用，与20-nt 间隔物最佳地起作用，具有强大的 DNA 靶向和切割活性，并支持相对高水平的脱靶编辑

![image](https://user-images.githubusercontent.com/111955215/187072763-d23e58d2-bbbd-4ebd-9e5c-5eb508856bb0.png)

#### Cas12家族
Cas12在远离PAM序列的位置产生切割，且只有RuvC进行切割，导向核酸也是crRNA而不是gRNA；Cas12核酸酶通常产生交错切割，这与Cas9的blunt切割不同。**Cas12a**通常使用富含T的PAM，这与大多数 Cas9的PAM不同。一般而言，Cas12a 变异体已被报道与许多 Cas9直系同源物相比产生少量脱靶编辑事件。

#### 修复方法
* 修复方法有两种：**非同源末端连接**（Non-homologous End Joining, **NHEJ**)和**同源引导修复**homology-directed repair(**HDR**)；
* 非同源末端连接又分为经典非同源末端连接(classical nonhomologous end-joining, **c-NHEJ**)和微同源末端连接(microhomology-mediated end-joining, **MMEJ or alt-NHEJ**)
* 同源引导修复又分为单链寡核苷酸供体（single-stranded oligonucleotide donors, ssODNs）和双链DNA供体

![image](https://user-images.githubusercontent.com/111955215/187058510-3ce609ca-8e92-44a2-a1b4-3ae0f0271c15.png)

#### 其他相关
高浓度的dsDNA容易产生毒性，而ssODN会好很多。
**以RNP复合物形式递送 CRISPR-Cas 系统通常导致更低水平的脱靶修饰（如下图）**

* 电转的方式将RNP和dsDNA一起递送

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/187063342-9f486748-b1b0-45c3-85d4-7b4384a25ed2.png" width="600">
</div>

* 在RNP上修饰一个NLS（细胞核定向序列），帮助定向到细胞核中

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/187063236-27eb9bbf-f091-4b78-a684-87cb053f21bb.png" width="600">
</div>



### 通过碱基编辑器来实现基因编辑
* 碱基编辑器精确地导致靶点突变，而不需要 DSB 或供体 DNA 模板，也不依赖 HDR。
* 目前的碱基编辑器包含与单链 DNA 脱氨酶融合的几乎丧失催化能力的CRISPR-Cas核酸酶(不能制造DSB) ，在某些情况下还会与能修复DNA的蛋白机器融合。
* 迄今为止已经开发了两类主要的碱基编辑器: 胞嘧啶碱基编辑器(CBE) ，其催化C•G碱基对转化为T•A碱基对；和腺嘌呤碱基编辑器(ABEs)，其催化A•T到G•C转化。CBE 和 ABE 可以有效地介导所有四种可能的转换突变(C → T，A → G，T → C，G → A) ，这些突变约占目前注释的人类致病变体的30%
* 在CBE和ABE中，催化受损的Cas核酸酶结构域将ssDNA脱氨酶定位到感兴趣的基因组靶序列。在Cas结合后，引导RNA间隔区与目标DNA链的杂交导致含有PAM的基因组DNA链的位移以形成ssDNA的R环。PAM远端核苷酸暴露为ssDNA并且可以进入碱基编辑器的脱氨酶结构域。
#### CBE
CBE使用**胞苷脱氨酶**将R环内的胞嘧啶转化为尿嘧啶，聚合酶将其读作胸腺嘧啶。但是在实际使用时，这种突变有可能会被修复，这种突变出来的尿嘧啶会被尿嘧啶糖基化酶(uracil DNA N-glycosylase, UNG2)从基因组中切除掉，因此CBE往往会引入尿嘧啶糖基化酶抑制蛋白(UGI)以减少尿嘧啶的清除

![image](https://user-images.githubusercontent.com/111955215/187060191-7240f4b4-a781-489f-b955-36f3c5822089.png)
#### ABE
类似地，ABE使用实验室进化的 TadA**脱氧腺苷脱氨酶**将R环内的腺苷转化为肌苷，通过聚合酶将其读作鸟嘌呤。而肌苷清除的速率远低于尿嘧啶，所以不需要其他的修饰。

![image](https://user-images.githubusercontent.com/111955215/187060202-02d09a03-f312-4170-8a20-abf8eb9e324c.png)

#### 碱基编辑器的选择
碱基编辑器可以根据几个标准来选择，包括所需的编辑(C•G-to-T•A或A•T-to-G•C)，目标序列中合适的 PAM 的可用性，围绕目标核苷酸的序列基序，目标核苷酸在原型间隔区内的位置，不希望的旁观者突变的可能性以及需要尽量减少脱靶DNA或RNA编辑。该流程图可以指导候选基本编辑器的识别。根据应用程序的不同，一些标准将优先于其他标准，可能需要在效率和特定性之间进行权衡。SpCas9 CBE 的标准编辑窗口通常是原型间隔区位置4-8，对于SaCas9 CBE 是位置3-12，对于 Cas12a CBE 是位置8-13。SpCas9 ABEs 的标准编辑窗口通常是原型间隔区位置4-7，对于 SaCas9 ABEs 是位置6-12，对于 Cas12a ABEs 是位置8-13。

![image](https://user-images.githubusercontent.com/111955215/187060579-48a2284c-6ca5-4a66-87a0-bb3583a00b04.png)

## 转座子
