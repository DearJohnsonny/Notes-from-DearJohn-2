Notes from DearJohn-2
=====
<a href="https://dearjohnsonny.github.io/Notes1-Biotech/">Notes1-Biotech</a>

<a href="https://dearjohnsonny.github.io/Notes3-Statistics/">Notes3-Statistics</a>

<a href="https://dearjohnsonny.github.io/Notes4-Linear-Algebra/">Notes4-Linear-Algebra</a>

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/187057747-7cb5e02e-5596-4bc4-a9b4-219cb731ee6c.png" width="1500">
</div>

# 基础知识
* 等温滴定量热法（ITC）：可用于直接测定配体溶液加入蛋白质溶液中时所释放的热量，从而得到熵和焓，从而得到热力学相关指标。
* R·L —— R + L，Kd = [R][L]/[RL], Ka = [RL]/[R][L]，配体浓度越高，则R的利用率越高。因此配体即药物的浓度需要高过Kd10倍，从而[RL]:[R]大于10，超过90%的受体将被结合
* on-rate = Kon[R][L],off-rate = Koff[RL]，Kd = Kon/Koff
* crLacZ一般用作non-targeting control，作为没有靶向互补序列但可以招募Cas蛋白的阴性对照，序列为cgaatacgcccacgcgatgggt


# 杂谈
##  Xeno Nucleic Acids (XNAs) 

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/197179127-8fbcda6e-0f18-48c3-9785-d683d96765ab.png" width="900">
</div>

### XNA polymerase的筛选方法

#### 传统的Compartmentalized Self-Tagging(CST)

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/197184198-fba181f6-8654-4daf-acf3-3ff3dc605b2b.png" width="1500">
</div>

需要在细胞中实现，判断是否有聚合活性靠的是再捕获，若有活性则可以延伸，从而与质粒可以结合配对

同时由于质粒可以被recover，从而所获得的质粒编码的序列就是有活性的酶序列。这样可以实现具有活性的酶与其序列的对应性

**Overview of the CST protocol**：
* Polymerase repertoires are generated (A10) and expressed (B14) in bacterial cells. 
* Bacterial cells are compartmentalized in a water-in-oil emulsion with synthetic nucleotide triphosphates (xNTP) and a short biotinylated selection primer (C22) for isolating genotype-phenotype combinations.
* Cells are disrupted by heat denaturation, allowing polymerase access to substrates (C23).
* Active polymerases, capable of incorporating the xNTPs, extend the selection primer, stabilizing its interaction with the plasmid. Inactive polymerase variants do not extend the primer (or do so poorly).
* Emulsions are disrupted and all plasmid DNA isolated. Excess unextended selection primers are removed by gel filtration (D27), and remaining biotinylated primers are captured (E33), using streptavidin-coated paramagnetic beads. 
* Recovery of biotinylated primers also recovers plasmids still bound to the primer. Beads are washed in stringent conditions (TBT2 supplemented with 20% v/v formamide) to remove loosely bound plasmids, enriching the population for the genetic information of active polymerases (E34). 
* Recovered plasmid DNA is amplified and used to start a new round of selection or screening.

#### 新的筛选方法

本方法使用珠子上的特有序列来分别捕获质粒、以及作为延伸引物来合成新的XNA链，同时用这种级联放大的方式来增强荧光

本方法好在既可以将phenotype and genotype联系起来，又可以不破坏珠子

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/197186288-7d92fcdd-b10c-40ba-b921-aa796c88c78c.png" width="1500">
</div>

### XNA polymerase和逆转录酶都被筛出来啦

根据以上的CST方案，研究者以TgoT为模板突变出来了Pol6G12等酶，从而实现了以XNA为模板的复制和逆转录

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/197190385-24a17f58-672b-492b-8577-d1415d197a95.png" width="1500">
</div>

### 在上述基础上筛选XNAZymes
XNAZymes的好处之一是可以减少被体内核酸酶切掉的现象，延长半衰期

下图是大概的筛选流程：

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/197193321-55f22407-4d5b-486d-a923-78952fbeaf0f.png" width="1500">
</div>


针对不同的筛选目的（看不懂可以看看<a href="https://www.nature.com/articles/nprot.2015.104">原文</a>），可以设计不同的模板（后续的步骤也比较类似就不展开了）

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/197194321-ba863fa5-5529-46ce-91af-861a4305535a.png" width="1500">
</div>

## TALE protein
### 简介
TALE (Transcription Activator Like Effectors)植物致病菌Xanthomonas通过III型分泌系统注入到宿主细胞内的一种蛋白质。

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/196022733-2b860e11-e161-4527-a049-69fe7f1190a9.png" width="900">
</div>

TALE蛋白的奇特之处在于它的DNA结合结构域——该DNA结合结构域不同于其他已知的DNA结合结构域。它是由不同数量的重复单元组成，每一个重复单元特异识别一个DNA碱基对。大多数情况下**每个重复单元由34个氨基酸**组成。这34个氨基酸中除了第12，13位的氨基酸变化较大之外，其他氨基酸高度保守。这**两个不保守的氨基酸被命名为RVD**（repeat variable diresidue）。

![image](https://user-images.githubusercontent.com/111955215/196022435-b52cd1e5-b924-45f7-aee0-3785bdcbb33d.png)

每个重复序列中12，13位的氨基酸和识别的核苷酸种类有特殊的一一对应关系。(NI for A, HD for C, NG for T, and NN for G)。

下图为TALE文库的构建：

![image](https://user-images.githubusercontent.com/111955215/196022466-e97c8fdb-7204-45bb-a4be-7ba9a4857879.png)
### 应用
TALE蛋白的特异DNA序列识别以及灵活的可组装性为它们在分子生物学中的应用提供了巨大的前景，科学家们可以设计组装任意的TALE单元去识别目标DNA双螺旋序列。这一特性已经被用来构造切割特异双链DNA序列的**DNA酶TALEN** (TALE nuclease)，成功用于在细胞基因组中引入定点突变、定点敲除等操作（引入双链DNA断裂DSB之后用NHEJ或者HDR的方法进行编辑即可）。

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/196022931-fe60aab6-5cd5-4179-bcc9-4297229973d9.png" width="900">
</div>

## BRD4蛋白
BET（Bromodomains and Extraterminal）家族成员，BRD4的特征是有两个串联溴结构域（BD1 and BD2）。

### 关于溴结构域和BET家族

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/193969353-d77671e5-0ee0-4ab4-a81e-3dab04e18f70.png" width="1500">
</div>

* **与组蛋白赖氨酸残基的的乙酰化部位结合**：溴结构域家族的蛋白可以与沿染色质的高乙酰化组蛋白区域相互作用，结合乙酰化的赖氨酸残基，包括组蛋白。**BRD4调节转录很大程度上依赖于其能和组蛋白赖氨酸残基的乙酰化部位结合的特性**。

* **募集转录调节复合物**：BET家族可以招募转录机器，从而上调转录；而TFⅡD也含有BRD亚基，其通过与核心启动子序列结合并募集其他转录调节因子来促进转录起始（ZMYND8和NuRD是下调转录的）

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/193974002-1028bdd2-5167-4d68-abad-efa826dd3acd.png" width="800">
</div>

(A) Brd2和Brd3促进基因转录。组蛋白中它们的溴结构域 (BD) 与乙酰化赖氨酸 (Ac) 之间的相互作用促进了RNA Pol II通过高乙酰化核小体延长新生转录本。箭头指示转录的方向;

(B) Brd4在起始和延伸过程中调节基因转录。在启动子近端区域，由于正转录延伸因子b (P-TEFb) 的失活，RNA Pol II暂停，与7SK小核RNA (snRNA) 和HEXIM1蛋白形成复合物。Brd4增强对P-TEFb的募集会导致Pol II中的Ser2磷酸化，从而导致Pol II从转录延伸的停顿中释放出来。P-TEFb与Brd4和JMJD6与远端增强剂相关的相互作用也支持了暂停释放。Brd4通过其溴结构域 (Brd4中的红色圆圈) 与乙酰化赖氨酸相互作用，而P-TEFb与Brd4 CTD (Brd4中的绿色区域) 相互作用。此外，Brd4通过其溴结构域促进沿超乙酰化核小体上基因的新生RNA合成。

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/193975036-fad31cf1-88ba-4c60-854c-285341b0795e.png" width="800">
</div>

* BRD4与组蛋白和TFs的同时结合将稳定TFs与ENHs的结合，从而维持这些元件的转录活性。

**总结一下：**

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/193976853-143eeffd-88e4-403d-97a8-beaf90a707d8.png" width="1500">
</div>

抑制BET家族的蛋白活性之后可以降低其激活效应，可以通过下图的方式抑制BET家族蛋白作用

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/193970686-bf380918-8a10-4f12-aea7-a48e55d9d4f9.png" width="800">
</div>

### BRD4的具体作用
#### BRD4在炎症和免疫调节NF-κb途径中的作用
BRD4通过至少四个途径调节TLR配体引起的NF-κb途径的激活:(1) BRD4通过其非典型组蛋白乙酰转移酶活性直接乙酰化RELA; 

(2)BRD4直接促进RELA的磷酸化；

(3-4)BRD4通过抑制NFKBIA的翻译和增加NFKBIA和IKBKB的磷酸化来促进RELA的磷酸化。

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/193994186-6ee17905-c934-45ab-87f3-285b6450601b.png" width="1500">
</div>

缩写: CDK9，细胞周期蛋白依赖性激酶9; CHUK，核因子κB激酶复合物的抑制剂; CycT1，cyclin T1; IKBKB，核因子κB激酶调节亚基β的抑制剂; IKBKG，核因子κB激酶调节亚基γ的抑制剂; NFKBIA，NFKB抑制剂α；NFKB1，核因子κB亚基1; p-TEFb，正转录延伸因子b; RELA，RELA原癌基因; RNA pol II，RNA聚合酶II; TLR，toll样受体

#### BRD4在炎症和焦化中调节NLRP3途径的作用
a在TNF引发的大鼠髓核细胞中，尿酸钠诱导急性痛风性关节炎，大脑中动脉闭塞诱导神经胶质活化，BRD4抑制RELA介导的NLRP3转录和随后的CASP1-dependent炎症小体活化。b在肾细胞癌组织和细胞中，RELA介导的NLRP3转录和随后的CASP1-dependent炎性体激活和GSDMD介导的焦磷酸病需要BRD4。

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/193994919-159b85cf-d5fe-4d67-b38f-f500f886d26d.png" width="1500">
</div>

缩写: BETi，bromodomain和extraterminal抑制剂; CASP1，caspase 1; GSDMD，gasdermin D; GSDMD-NT，gasdermin D的N-末端结构域; IL1B，白细胞介素1β; IL18，白细胞介素18; NLRP3，NOD样受体热蛋白结构域相关蛋白3（NLRP3）; PYCARD，PYD和CARD结构域; RELA，RELA原癌基因; TNF，肿瘤坏死因子

#### BRD4在抗病毒免疫中调节STING1途径的作用

来源于各种病毒的细胞质DNA激活CGAS，产生内源性环二核苷酸cGAMP，与位于内质网的STING1结合，进而促进STING1从ER到核周区的二聚和易位。在转运过程中，STING1招募并激活TBK1，刺激IRF3的磷酸化和核易位，并在较小程度上刺激NFKB1，从而导致1型IFN和其他炎性细胞因子 (例如IL) 的产生。IRF3和NFKB1的核活性被brd4抑制。此外，在BRD4抑制后，DDR的激活可诱导宿主dsDNA从细胞核释放到细胞质，导致CGAS-STING1途径进一步激活以限制病毒感染。

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/193994989-90813bf7-5da5-42f8-9ded-3db5a84e2fe5.png" width="1500">
</div>

缩写: cGAMP，环GMP-AMP; CGAS，环GMP-AMP合酶; DDR，DNA损伤反应; dsDNA，双链DNA; IFN，干扰素; IL，白细胞介素; IRF3，干扰素调节因子3; NFKB1，核因子κB亚基；STING1，干扰素反应刺激因子cGAMP交互因子1; TBK1，TANK结合激酶1

## 糖基化
在蛋白质的多种翻译后修饰中，糖基化（glycosylation）是非常重要的一种。糖基在酶的催化下，与蛋白质上的某些残基形成共价连接，通常是糖苷键。

据估计，哺乳动物中的糖链大约有七千多种结构，其结构单体约为10种单糖（包括糖衍生物）：葡萄糖（Glc）、半乳糖（Gal）、甘露糖（MAN）、木糖（Xyl）、岩藻糖（Fuc）、N-乙酰氨基葡萄糖（GlcNAc）、N-乙酰半乳糖胺（GalNAc）、葡萄糖醛酸（GlcA）、艾杜糖醛酸（IDOA）、唾液酸（SA）。其中两种糖醛酸主要分布在蛋白聚糖中。

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/193834469-4423defd-e218-4670-953b-841a70c161f6.png" width="800">
</div>

在基本氨基酸中，至少有9种氨基酸残基可以被糖基修饰。糖基可以通过多种方式与蛋白质相连，例如与Asn侧链的酰胺键相连（N-糖基化），通过糖苷键与Ser、Thr、羟基赖氨酸（胶原）或Tyr（糖原蛋白）的羟基相连（O-糖基化），或通过C-C键连接到Trp的C2位置（C-甘露糖基化）。另外，还可以通过糖基磷脂酰肌醇（GPI）锚间接与蛋白质相连。

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/193842458-9e9a580d-4ef0-48b8-9c39-7e46a594578f.png" width="1500">
</div>

### 分类
* N-连接的糖基化（N-linked glycosylation）：与天冬酰胺残基的NH₂连接，连接的糖为N-乙酰葡糖胺(GlcNAc)

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/193840066-6f2cc2f5-cd1c-49a0-b252-9f09b6c2a72f.png" width="1500">
</div>

* O-连接的糖基化（O-linked glycosylation）：与Ser、Thr和Hyp的OH连接，连接的糖为半乳糖或N-乙酰半乳糖胺(GalNAc)，在高尔基体上进行O-连接的糖基化。

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/193839249-273f379e-b260-43e3-99f2-1978cbc38319.png" width="700">
</div>
### 功能
糖基化的作用可概括为3点：①使蛋白质能够抵抗消化酶的作用；②赋予蛋白质传导信号的功能；③某些蛋白只有在糖基化之后才能正确折叠。

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/193846567-1cd9d141-98ba-456f-a812-ac8a5a081ad5.png" width="1100">
</div>

## 核糖开关
 核糖开关（Riboswitches）是一类非编码RNA元件，主要存在于细菌mRNA（DNA也有，因此不仅可以影响翻译，还可以影响转录）的5′非编码区（5′UTR），通常由适配体（aptamer）和表达平台（expression platform）两个功能域组成。当特定分子（ligand，配体）结合适配体域时，会引起表达平台域的局部构象发生变化，从而打开或关闭下游基因的表达。核糖开关广泛存在于细菌中，它们在细菌的硫代谢、辅酶合成、氨基酸合成等基础代谢中发挥着非常重要的调控作用，迄今为止，已有20余类感应不同分子的核糖开关在细菌中被确认。

### 常规作用机制

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/192923251-90ece5c4-a1a1-455c-a0f9-031e7c894f56.png" width="1500">
</div>

PS：
* Shine-Dalgarno （SD）是细菌和古细菌中信使RNA中核糖体结合位点序列。通常位于翻译起始密码子AUG上游约8~10个碱基位置。SD序列帮助招募核糖体RNA，并将核糖体比对并结合到信使RNA（mRNA）的起始密码子，从而开始蛋白质合成。

### 非常规的核糖开关作用机制

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/192923743-92565861-64cd-4444-a150-1aed4706cb42.png" width="1500">
</div>

### 总结一下riboswitch的特点

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/192927937-3eb25c40-1e77-4bbf-bdba-4fb139041922.png" width="600">
</div>

* 很少有串联，下面是例外
<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/192928266-76538b52-029d-4611-8f80-9088e0437d52.png" width="1500">
</div>

* 自剪接的情况也不多（PS：大多数核酶的活性都是自剪接的活性），下面是例外
<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/192928082-61a2fec2-d807-45ed-a46a-4c19339261f8.png" width="1500">
</div>

## 黄素Flavin
黄素是大多数生命形式所需要的黄色杂环分子，它们提供多种特定的催化任务。
对于人类来说，黄素是从饮食中获得的维生素 B2。黄素蛋白在细胞中的辅基有黄素单核苷酸（FMN）或黄素腺嘌呤二核苷酸（FAD）。FMN和FAD分别附着有磷酸盐或二磷酸腺苷(ADP)，可以与蛋白质非共价或共价连接

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/192540999-ca281373-dbca-4c69-bd8c-2738cbd2a5f3.png" width="800">
</div>

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/192550807-a5a95a48-e437-48b6-a27f-6a3289b802d0.png" width="400">
</div>


FAD 和 FMN 在 pH7.0溶液中双电子还原的氧化还原电位分别为 -219mV12和 -205mV。相较之下，完全还原/氧化是一个双电子过程，在 pH7的水溶液下，其中点电位约为 -200mV。

氧倾向于参与包含一个电子，一个氢转移的逐步进行的反应。核黄素的化学特性非常适合这种反应。因此，在生物系统中添加含有核黄素的辅因子后，系统可以利用涉及离子氢化物转移(通过 NAD 或 NADP) ，自由基氢离子转移(通过 FMN，FAD)或抗坏血酸和一个电子加一个质子转移(通过 FMN 或 FAD)的机制进行一系列氧化还原反应。比如生物氧化过程中的电子传递链上的复合体Ⅰ和复合体Ⅱ

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/192544648-e47a51cc-a56b-4364-8366-8c362aadf48f.png" width="800">
</div>

## 内含肽
内含肽，即蛋白质内含子，是存在于前体蛋白质中的一段氨基酸序列，在前体蛋白转变为成熟蛋白的过程中，它靠自我剪切的方式从前体蛋白中释放出来，同时两端的肽链以肽键的方式相连，该过程即为蛋白质剪接。蛋白质剪接不同于RNA剪接，前者的剪接发生在蛋白质水平，而后者的剪接发生在RNA水平：它也不同于蛋白质翻译后加工，后者往往只是切除前体蛋白端或C端的一些片段，通常没有多肽链的形成：而且也不同于酶原活化，蛋白质剪接有新肽键的形成。

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/190904759-5b423651-80c8-4afe-91ea-6d90d81e01d9.png" width="500">
</div>

与内含肽相对应的是蛋白质外显肽，即内含肽两侧的氨基酸序列。位于内含肽端的序列称为N-外显肽，位于内含肽C端的序列称为C-外显肽。N-、C-外显肽在内含肽的作用下通过肽键连接成完整的成熟蛋白。内含肽有8种存在状态：剪接反应前称为融合内含肽，剪接反应后称为游离内含肽。两者的一级结构相同但功能却不同，前者可以自催化蛋白质前体的剪接反应，后者可作为归巢核酸内切酶参与内含肽归巢。

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/190904838-b7185854-f114-4257-9c63-74c4978b2d8b.png" width="500">
</div>

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/191238921-251e4acd-3282-4c11-b622-03d3edbadd22.png" width="1500">
</div>

# 非编码RNA
## LncRNA
定义：长于200个核苷酸且没有编码蛋白质的RNA。

来自人类基因编码的统计数据表明，人类基因组包含16,000多个lncRNA基因，但其他估计超过100,000个人类lncRNA。

和mRNA一样，LncRNA也会5'端加帽(7-methyl guanosine, m7G) 和3'端加Poly A的尾巴；也会有剪接

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/197428984-e58b90a5-a506-4793-9063-8ca6a80679af.png" width="600">
</div>

### 生物学功能
#### 染色体调节
招募染色质调节物：如下图中的HOTTIP这种LncRNA招募激活蛋白让HOXA基因激活

![image](https://user-images.githubusercontent.com/111955215/197430279-77b8f395-8699-4d4f-bdf4-1c41b1bc38e7.png)

诱捕染色质调节剂：如下图的lncPRESS1这种LncRNA将一种组蛋白去乙酰化酶SIRT6给抢走了，导致其无法去掉目标基因序列的乙酰化，从而阻止该基因表达

![image](https://user-images.githubusercontent.com/111955215/197430385-607450b9-546e-4c43-ae5f-fa2fe239029e.png)

LncRNA可以与DNA相互作用，并形成RNA-DNA杂交链，例如R环，从而被染色质修饰剂或转录因子识别，并产生激活或抑制靶基因转录的效应

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/197430934-cc53f784-5e32-432f-b7ff-0b12ede5dc5d.png" width="800">
</div>

#### 转录调节

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/197432040-2e855065-da13-4365-a60e-fedeb5aee0ac.png" width="1500">
</div>

#### 细胞核的组织

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/197432155-98ee8311-de5f-498c-81e2-a2ddfe08dd51.png" width="1500">
</div>

#### 转录后修饰

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/197432319-ce6444d7-b023-48a8-a979-05fa044e9809.png" width="1500">
</div>

# 酶进化系统

## PACE
<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/191239383-4fe2630b-c719-4d49-a698-3b8136cba33b.png" width="1000">
</div>

“泻湖”被新鲜宿主细胞的培养物不断地稀释。所有在泻湖内复制的DNA都通过工程诱变质粒进行诱变，以提供遗传多样性。只有编码功能性POI变异体的含SP基因能够比稀释速率更快地复制，从而使它们能够在泻湖中持续存在
为了同时进化和选择功能，宿主细胞还含有诱变质粒(MP)。MP使宿主细胞中的所有DNA发生随机突变，包括SP和宿主细胞基因组，以及细胞含有的任何质粒
MP在阿拉伯糖启动子的控制下表达诱变基因，在生长培养基中加入阿拉伯糖后诱变发生以保证突变的可控性。

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/191239799-d399706d-cf47-4969-a10c-21621fba69c9.png" width="1000">
</div>
阴性选择：由于进化酶的目标包括酶的特异性，因此研究者大多需要将用于进化的初始酶活性排除掉，因此需要阴性选择。即将原活性与一段无法表达的gⅢ基因联系起来，导致具有原活性的酶基因在筛选过程中无法富集

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/191239813-07fd6595-2666-43f2-a20f-ce9d221b11a6.png" width="1000">
</div>

### 用于不同PAM序列的Cas蛋白筛选

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/191392406-41428edb-2d19-48a2-8d1b-9fd065632bfa.png" width="800">
</div>

当突变后的Cas蛋白能够和目标的dsDNA结合并产生一定的构象变化时，与之连接的RNA聚合酶的亚基也会受到激活，从而导致RNA聚合酶的活性，从而gⅢ基因能够表达

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/191392823-957da485-74f5-4e61-9f8c-117500dc9d54.png" width="800">
</div>

由于Cas蛋白激活聚合酶的机制未知，研究者又开发出了更高效的筛选方法——功能化的筛选。由于筛选的Cas蛋白主要用于碱基点突变，因此在筛选时将点突变与Cas蛋白的活性联系起来。此处是有两段内含肽包裹的PAM序列以及中止密码子，只有成功将终止密码子点突变的Cas蛋白才可以使内含肽开始剪接并产生完整的gⅢ蛋白。

提高筛选强度：两个密码子，同时减少数量
<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/191393464-63333f94-7b58-43d8-85af-e413dda0e97a.png" width="1500">
</div>

下图也是一样的思路：
<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/191393552-8e17d94c-4655-4d8b-80b0-59c5b28711b9.png" width="1500">
</div>

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/191239109-5837f53c-9258-4dd1-9ff4-f75127130846.jpg" width="1500">
</div>

# 靶向蛋白降解
靶向蛋白质降解(targeted protein degradation TPD)目前主要通过泛素蛋白酶体和溶酶体降解目标蛋白，根据具体作用原理又可细分为近10个不同技术路线，其中发展最快的是分子胶和PROTAC技术。在真核细胞中，受损的蛋白质或细胞器主要通过两条相互独立，但又相互关联的途径进行清除，即蛋白酶体途径和溶酶体途径。一般来说，蛋白酶体通过泛素-蛋白酶体系统降解短寿命蛋白和可溶性错误折叠的蛋白，而溶酶体则通过内吞、吞噬或自噬途径降解长寿命蛋白、不溶性蛋白聚集体，以及其他大分子化合物和细菌、细胞器等。
![image](https://user-images.githubusercontent.com/111955215/188146827-89721640-25dc-4b3d-b4c0-ca9cf8831aed.png)

## 体内的蛋白酶体途径降解
在生物体内，E3泛素连接酶复合物通过识别degron（降解子）来选择用于降解的蛋白质。

降解子可能是常规序列：degrons是嵌入在促进泛素化和降解的底物中的**特定氨基酸序列**。底物蛋白的N基端的部分短序列是最早发现的降解子，最近（2018）已经<a href="https://www.sciencedirect.com/science/article/pii/S009286741830521X?via%3Dihub">报道</a>
了识别C末端降解子的E3连接酶。


<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/197369621-20b1f8e0-ec04-4b6b-8d29-a942a8335119.png" width="800">
</div>


也可能是翻译后修饰（PTM）产生的**特定基团**。<a href="https://www.nature.com/articles/s41586-022-05333-5">2022年的文章</a>发现CRBN的在生物体内的目标蛋白包括蛋白质C基端通过翻译后修饰产生的环状酰亚胺(cyclic imide)。这些PTM由特定的酶产生，在蛋白质ageing期间或在特定的蛋白质剪接(例如，内蛋白切除) 期间自发环化。

## 分子胶
### 免疫调节的酰亚胺类药物Immunomodulatory imide drugs (IMiDs)
主要包括沙利度胺及衍生物（来那度胺、泊马度胺），其作为分子胶的**单亲性**体现在和E3 ligand（即CRBN）的结合上

沙利度胺及衍生物（来那度胺、泊马度胺）作为分子胶可靶向降解的蛋白质有：Ikaros 锌指蛋白 Ikaros (IKZF1) 、 Aiolos (IKZF3)、casein kinase 1A1 (CK1α)、translation factor GSPT1 (G1 to S phase transition 1)

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/191903012-e751ac03-b66c-4b25-864c-4024ed823662.png" width="800">
</div>

GSPT1 shares no obvious homology to IKZF1,IKZF3, or CK1α and cannot be targeted for degradation by other IMiDs, such as lenalidomide and pomalidomide

### 芳基磺酰胺Aryl Sulfonamide
此药名曰：indisulam

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/191905075-12e86fa2-3ab9-4017-af22-fd7f9cdf81ee.png" width="800">
</div>

E3 ligand为DCAF15，降解的靶蛋白为splicing factor RNA binding motif protein 39 (**RBM39**)

与 IMiD 不同，磺胺类药物是 DCAF15 的弱配体，与DCAF15的亲和力也不强，而 RBM39 与DCAF15的结合亲和力也很弱。但是Indisulam 能够在DCAF15表面诱导一个浅袋并增强两种蛋白质之间的 PPI（主要是非极性相互作用）。

### 直接到DDB1而绕过E3 ligand_CDK12/13:DDB1 glues trigger cyclin K degradation

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/191904547-e8782f1d-247f-44b3-a3ea-20896cb6f89e.png" width="800">
</div>

最近出现了一种有趣的靶向蛋白质降解的替代机制，发现小分子可以将靶蛋白直接招募到 DDB1 衔接蛋白，绕过对专用底物受体的要求

CR8 通过含有 DDB1 的 cullin-RING 连接酶触发细胞周期蛋白 K 的选择性降解

## PROTAC
### 泛素
泛素化作为蛋白翻译后修饰（PTM）的方式之一，不仅参与蛋白质的降解，在调节细胞功能方面也发挥着重要作用

泛素为含76个氨基酸、大小约为8.6 kDa的小蛋白质，在真核生物中普遍存在且高度保守。人类基因组中的四个基因编码泛素：UBB，UBC，UBA52和RPS27A。

泛素氨基酸序列：
MQIFVKTLTGKTITLEVEPSDTIENVKAKIQDKEGIPPDQQRLIFAGKQLEDGRTLSDYNIQKESTLHLVLRLRGG

泛素具有7个赖氨酸残基（K6，K11，K27，K29，K33，K48，K63）和一个甲硫氨酸残基（M1）。泛素之间主要通过赖氨酸残基和甲硫氨酸残基进行各种连接。由此产生的泛素链产生一定的拓扑结构，可通过对蛋白底物进行修饰并决定底物的功能。
泛素蛋白的结构：

![image](https://user-images.githubusercontent.com/111955215/188146930-f1a3176b-1ee8-48e1-9ff7-53822411c14c.png)

泛素的功能位点：

![image](https://user-images.githubusercontent.com/111955215/188147023-32ccb586-94e3-42a0-a09e-e25f97fdc130.png)

泛素系统降解蛋白质的机制：

![image](https://user-images.githubusercontent.com/111955215/188147254-50b82ed7-c8d5-42d9-9096-6c0d24f828d4.png)

### PROTAC的优点
* 极大地扩展了可成药蛋白靶点的范围。目前已鉴定出超过4000种疾病相关蛋白但只有约10%被成功开发，许多蛋白由于结构复杂、没有活性位点等原因无法被传统抑制剂靶向，而PROTAC只要能结合目标蛋白就可以诱导降解，可大大拓展可成药靶点的范围。
* 传统小分子抑制剂只能阻断靶蛋白的部分功能，而PROTACs降解靶蛋白后可消除其所有功能。
* 传统的激酶抑制剂容易因靶蛋白突变或过度上调而耐药，但PROTAC可通过降解靶蛋白来最大限度减少潜在的耐药性。
* PROTAC理论上是可以循环使用的，因此催化剂量即可发挥作用，可提高药物的安全性。

### 应用
* 制备减毒活流感疫苗
将可以靶向VHL（E3 ligand）序列的一段序列TPD（序列为ALAPYIP）插入到病毒基因组，从而将相应的病毒蛋白靶向到泛素-蛋白酶体途径中进行降解；同时为方便生产，再引入一段TEVp序列（序列为ENLYFQG）特定的菌可以表达这种TEVp蛋白，从而将TPD这段序列切掉，因此病毒的基因组完整，正常复制，便于生产。

![image](https://user-images.githubusercontent.com/111955215/188148639-4bd07226-a478-4ab8-9b18-5514b29b5c64.png)

### E3 ligand
#### CRBN的lignand
沙利度胺（其实这几种也可以作为分子胶）：

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/191497823-0683ea0d-f24b-4c12-94d2-405283142865.png" width="400">
</div>

泊马度胺(沙利度胺衍生物)：

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/191496847-fd5eecde-7da7-46c6-acad-ba583ac23c47.png" width="400">
</div>

来那度胺(沙利度胺衍生物)：
<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/191497158-e2f5e5d5-ff81-4a95-ae46-04616430c7a0.png" width="400">
</div>

### 泛素-蛋白酶体系统
E3-E2之间的蛋白复合体有：E3(CRBN VHL MDM2 IAP DCAF15等) - DDB1 - CUL4A/B - N8 - RBX1 - E2
![image](https://user-images.githubusercontent.com/111955215/191650230-5621bd70-8deb-462c-b986-58972fdafe36.png)



## 溶酶体途径
![image](https://user-images.githubusercontent.com/111955215/188148140-5da3caae-dfe1-4a4b-9065-a64ed8686c1e.png)

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/188149424-ad00b3af-8389-441f-9be3-345b14bc192f.png" width="1500">
</div>

# 关于肿瘤
## 肿瘤微环境 Tumor microenvironment
![1](https://user-images.githubusercontent.com/111955215/188036946-1f24a06e-7458-410c-96a9-3df616d4f2d4.png)

肿瘤微环境中**营养**和**氧气**的平衡控制着免疫细胞的功能：
* 肿瘤细胞对葡萄糖和氨基酸的消耗超过浸润免疫细胞，特别是剥夺它们的营养以促进其效应功能。氧气不足的肿瘤微环境会驱动肿瘤细胞、巨噬细胞和 T 细胞中的缺氧反应程序。
* 由于缺氧或其他机制而增加的 HIF-1a 活性促进糖酵解并增加抑制性代谢物的浓度和局部环境的酸化。
* 作为糖酵解的副产物，乳酸浓度增加，被肿瘤细胞协同利用以促进其代谢，促进巨噬细胞极化，并直接抑制 T 细胞功能。
* T细胞靶向肿瘤的能力进一步受限于它们对共抑制受体的上调以及与邻近肿瘤细胞和巨噬细胞上的配体的结合。随着 T 细胞逐渐进入功能失调状态，它们的线粒体质量和氧化能力下降，最终导致它们无法满足维持效应功能和控制肿瘤细胞生长的生物能量需求。

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/188036990-cf90884a-35f9-4b60-914e-c514ac2ddf68.png" width="1500">
</div>

# 关于T细胞和细胞治疗

## T细胞受体信号
![image](https://user-images.githubusercontent.com/111955215/187328881-50cf2797-5fb7-42ca-a9f8-0013f3683008.png)

![image](https://user-images.githubusercontent.com/111955215/187206889-ab90a064-9beb-4b21-8674-b91f0b6d200d.png)

**关于Zap70**：
(A) Lck 和 Zap70 存在于严格的信号层次结构中。 (B) Zap70经历逐步激活，这需要将其募集到 TCR 复合物中的磷酸化免疫受体酪氨酸激活基序 (ITAM) 及其Lck 磷酸化。 (C) Zap70 包含一个对其底物特异性很重要的高度碱性区域。 Zap70 的基本区域充当静电过滤器确保对 LAT 和 SLP-76 中磷酸位点的特异性，并防止 ITAM 和 Zap70 激活环的磷酸化。 (D) Zap70 Y126 的磷酸化是建议使其从 TCR 复合物中释放，使其可以迁移并遇到 LAT 使其磷酸化。同时，额外的Zap70分子能够结合TCR复合物并被激活，表明 TCR 信号放大模式

![1](https://user-images.githubusercontent.com/111955215/187331004-93a57616-8a6a-41fb-8722-1088bf2d4244.png)

### 动态隔离模型“size exclusion” model
 当 TCR 复合物与 pMHC 复合物结合后， 会与抗原提呈细胞之间形成免疫突触。动态隔离模型（kinetic segregation model）可描述为在免疫突触中， TCR 处于中心位置并形成“紧密结合区域”（close contact zones），进而排斥一些大分子蛋白，如磷酸酶 CD45 分子。这种机制最终导致的结果即为TCR/CD3 近端的激酶和磷酸酶平衡失调，从而使得 CD3 被磷酸化，促进 T 细胞活化和信号转导。在CAR 与靶细胞特异性表达抗原结合的表面，CD45 同样处于被排除状态以促进信号转导。因此，动态隔离模型在 CAR 信号中也许同样重要。
 
 天然的TCR长度是相对固定的，但是人工设计的Car的长度可以改变。有研究者提出Car的长度与激活的关系：Car足够短，才能在与抗原peptide和MHC结合时将CD45排除在外，有用的磷酸酶才可以过来将Car磷酸化，产生激活信号。
 
 ![image](https://user-images.githubusercontent.com/111955215/187327934-0a825e56-8dc3-419c-ba2e-3374665df2b7.png)

![image](https://user-images.githubusercontent.com/111955215/187329398-cfe0fe6c-d563-4975-94d6-75772768b771.png)
### 共受体扫描模型
低亲和力的抗原在共受体的扫描下会离去而不会导致信号通路激活。
Lck是一种丝氨酸蛋白激酶，位于胞内且可以和CD4/8共受体结合，其激活也依赖自身被磷酸化。Lck活化越多T细胞越容易被激活。

![image](https://user-images.githubusercontent.com/111955215/187329817-ddd641b8-1de3-4ea6-9d26-2d8527853d12.png)

### 动力学校对模型
![image](https://user-images.githubusercontent.com/111955215/187332536-1958948c-4cf1-4586-bbb8-e55fd973a40a.png)


### 串行参与模型（serial engagement model）
常与动力学校对机制并列提及。该模型阐述 TCR 与pMHC 达成紧密结合就像接力一样，即单个 pMHC 可与多个 TCR 进行连续性的接触，而这些连续性接触积累起来的结果，使得 TCR 与 pMHC 达到紧密结合，最终导致 T 细胞的完全活化
<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/187328231-564c8b09-2b38-4e16-8257-bb5927e61315.png" width="1500">
</div>

## Car-T
![123](https://user-images.githubusercontent.com/111955215/187198651-62752b2b-988d-4f0f-bd8b-037fbd688aeb.png)

按照每个元件所处的位置，CAR主要分为三个功能区域，分别是：胞外结构域 、 跨膜结构域 和 胞内结构域 。

![image](https://user-images.githubusercontent.com/111955215/187200834-9bd29eca-83bf-46e9-84c7-9b6ae890b38d.png)

胞外结构域由负责识别并结合抗原的单克隆抗体的单链可变片段（single-chain variable fragment，scFv）及一段起连接作用的铰链区（Hinge）构成。
scFv由单克隆抗体的轻链（VL）和重链（VH）通过多肽连接而成，保留有抗体对抗原的特异性和亲和力。CAR-T细胞通过scFv对靶抗原的识别结合不依赖MHC抗原呈递，一方面避免了肿瘤细胞通过调节MHC分子发生逃逸，另一方面赋予了CAR-T细胞识别非肽抗原的能力（虽然目前主要还是识别CD19）。

胞内结构域由共刺激结构域（Costimulatory Domain）和信号转导结构域（Signaling Domain）构成。

### Car-T的问题
* **无法深入实体瘤内部，因此对实体瘤作用效果差**：CAR对抗原的亲和力则是极其强大，有时强大到它和抗原拽都拽不开；因为强大的亲和力，CAR-T细胞常常阻滞在实体瘤的外周，而不像TCR-T那样毫无羁绊。同时许多实体瘤内部存在**异质性**，即会有不同类型的肿瘤细胞，这些细胞相互之间携带的抗原和表达水平都有所不同，如果CAR-T仅对部分肿瘤细胞有效，治疗就很难成功。肿瘤细胞适应了瘤内弱酸性、低氧、缺乏营养的**特殊肿瘤微环境**，同时还有不利于CAR-T细胞生存的抑制因子和抑制细胞。 
* **脱靶效应**：CAR-T靶向肿瘤相关抗原，并非肿瘤细胞特异性的，正常细胞也可能受到攻击
* **稳定性差**：引入的CAR受体为外源性分子，具有一定的免疫原性，机体会产生针对CAR的抗抗体，会影响CAR-T细胞的存活。此外CAR分子使用的scFV不稳定，容易发生自身聚集，引发CRS。

![1](https://user-images.githubusercontent.com/111955215/187201339-b35a7ff0-6634-448d-85c5-319ed79544fa.png)

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/187209688-bfb04b5a-b8c8-4cea-ae3a-531712b06595.png" width="1500">
</div>

## TCR-T
### 关于T细胞
![image](https://user-images.githubusercontent.com/111955215/187206889-ab90a064-9beb-4b21-8674-b91f0b6d200d.png)

### TCR与CAR的异同
![image](https://user-images.githubusercontent.com/111955215/187206729-806e37c9-03a0-49dc-b863-0961077517de.png)

不同于CAR-T细胞只能识别细胞膜外的蛋白质，TCR-T细胞的主要优势是能够识别细胞外和细胞内的蛋白，而超过85%的细胞蛋白位于细胞内，所以对于实体瘤，TCR-T可以发挥更好的作用。

TCR的效力依赖于它与肽-主要组织相容性复合体（pMHC）的相互作用，pMHC即为肽结合于MHC形成的复合物。来自T细胞的TCR必须与患者的人类白细胞抗原（HLA）等位基因匹配，识别这些pMHC并杀伤癌细胞。因此rTCR需要MLA和抗原同时表达，但是CAR-T直接识别膜蛋白

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/187208815-1fc7ad11-0845-4a3b-8ea6-9a4c3d61273d.png" width="700">
</div>

总结如下：
<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/187209038-c76e0355-7b17-4260-8156-fa358a07ba53.png" width="700">
</div>

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/187209528-ade34db8-c836-4908-aa16-795f5cd5281f.jpg" width="1500">
</div>


# 基因编辑
## Cas 13
Cas13a 是一种VI-A型CRISPR-Cas RNA引导的 RNA 核糖核酸酶，降解CRISPR RNA(crRNA)靶向的侵袭性RNA

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/193724181-3090ceba-1439-4bbd-851c-922116690812.png" width="800">
</div>

其crRNA有一段repeat sequence，剩下的部分和target RNA形成RNA双链

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/193725159-473ca881-4e43-4f2a-89ab-f2d8be2d9921.png" width="400">
</div>


### 用于检测

这个位于靶激活的 Cas13复合物外表面的催化囊可以非特异性地切割任何周围的 RNA 分子，产生特征性的“**附带效应**”(collateral effect)。这种靶向触发的侧支活动，最初是一种旨在诱导宿主休眠和防止侵入噬菌体繁殖的免疫防御机制，已经被迅速开发用于体外检测核酸分子。例如，Cas13-crRNA复合物在靶标识别时被激活，并进行由单链RNA(ssRNA)连接的附近染料猝灭剂对的侧切以快速产生可测量的荧光或比色信号（如下图）

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/193726537-8241af81-80b2-478a-9f97-1c15aaacc906.png" width="1200">
</div>

#### 对比下Cas13a和Cas12

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/193726479-219e6502-74a7-4890-8e2e-88c690e3df7e.png" width="800">
</div>

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/193725974-5f45b122-9153-44ed-bd61-a510128f6fb0.png" width="800">
</div>

## 基于TALE的基因编辑

### 用TALE蛋白与脱氨酶DddA组成碱基编辑器
2018年，de Moraes发现DddA具有催化胞嘧啶脱氨转变为尿嘧啶的活性，而且有意思的是，与其他的脱氨酶不同，这种作用可以直接在DNA双螺旋上发生，不需要解旋。

Bacterial toxin DddA-derived cytosine base editors (DdCBEs)—composed of split DddAtox (a cytosine deaminase specifc to double-stranded DNA), custom-designed TALE (transcription activator-like efector) DNA-binding proteins, and a uracil glycosylase inhibitor。其可直接针对双链DNA将C-G碱基对编辑为T-A碱基对，而且编辑效率很高，也几乎没有脱靶效应

该技术可以用于解决线粒体DNA的编辑问题（Cas9解决不了）：要想解旋DNA，就得带上Cas9酶；可带上了Cas9酶，就进不去线粒体

要实现该方法还需要解决三个问题：
* 毒性：胞苷脱氨酶对哺乳动物细胞来说是有生物毒性的。为了避免这种毒性，研究者们想出的办法是把DddA一拆两半，两个没有活性的部分在编辑位点重组恢复脱氨活性
* 进线粒体的膜：加上线粒体靶向信号（MTS）蛋白序列，就能够利用线粒体的蛋白质吸收机制穿过线粒体的双层膜了
* 为了保住DddA的作用不被干扰，还要再加上尿嘧啶糖基化酶抑制剂（UGI），把U保住

![image](https://user-images.githubusercontent.com/111955215/196023581-2a80e559-4e82-4d56-aa38-8d6cf7d7a47b.png)

仍然存在的问题：该技术在不破坏DNA的情况下将一个核苷酸碱基转换为另一个核苷酸碱基。然而，这种技术也有其局限性。它不仅局限于C→T转换，而且大多局限于TC基序，使它实际上成为TC→TT转换器。这意味着它只能纠正90个确认的致病性线粒体点突变中的9个（10%）。

### 韩国人在DdCBE的基础上开发TALED
<a href="https://www.cn-healthcare.com/articlewm/20220429/content-1346554.html/">新型线粒体碱基编辑器</a>

## 基于*CRISPR*的基因编辑
基于CRISPR的基因编辑方式主要有四种，包括：**nucleases(核酸酶), base editors(碱基编辑器)**, transposases/recombinases(转座子/重组酶类) and prime editors(引物编辑器).

Homology-directed repair (HDR); cytosine base editor (CBE); adenine base editor (ABE); end-joining (EJ); prime editor (PE); uracil glycosylase inhibitor (UGI); **protospacer adjacent motif (PAM)**.

![1](https://user-images.githubusercontent.com/111955215/187057959-382192c9-397a-4806-9f42-76560272313f.png)

### 通过CRISPR–Cas核酸酶来实现基因编辑
家族Ⅰ用多种蛋白质进行核酸的切割，而家族Ⅱ用一种蛋白质进行切割（下图还应该补充下，classⅡ中还有typeⅣ，如Cas-13）

![image](https://user-images.githubusercontent.com/111955215/187058140-b2c8f4a8-70f9-4476-a906-cbe32609aa85.png)
#### Cas9家族
Cas9在protospacer序列上产生切割，大约在PAM前3bp的位置，且会用Cas9上两个不同的结构域（RuvC and HNH）进行切割产生非粘性末端。目前使用最广泛的 CRISPR-Cas 核酸酶 SpCas9含有1,368个氨基酸，识别相对常见的 NGG PAM，可以与 sgRNA 或 crRNA/tracrRNA 对一起使用，与20-nt 间隔物最佳地起作用，具有强大的 DNA 靶向和切割活性，并支持相对高水平的脱靶编辑

![image](https://user-images.githubusercontent.com/111955215/187072763-d23e58d2-bbbd-4ebd-9e5c-5eb508856bb0.png)

几种Cas9家族的结构域

![image](https://user-images.githubusercontent.com/111955215/187073720-dd142f67-b156-4ad3-b898-9a3874fad9c3.png)

#### Cas12家族
Cas12在远离PAM序列的位置产生切割，且只有RuvC进行切割，导向核酸也是crRNA而不是gRNA；Cas12核酸酶通常产生交错切割，这与Cas9的blunt切割不同。**Cas12a**通常使用富含T的PAM，这与大多数 Cas9的PAM不同。一般而言，Cas12a 变异体已被报道与许多 Cas9直系同源物相比产生少量脱靶编辑事件。

![image](https://user-images.githubusercontent.com/111955215/194810928-dcf231b9-e23a-4914-b844-51236b49da06.png)

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
<img src="https://user-images.githubusercontent.com/111955215/187063342-9f486748-b1b0-45c3-85d4-7b4384a25ed2.png" width="900">
</div>

* 在RNP上修饰一个NLS（细胞核定向序列），帮助定向到细胞核中

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/187063236-27eb9bbf-f091-4b78-a684-87cb053f21bb.png" width="900">
</div>

* 单链的HDR毒性更低，因此可以采用这个思路：两端是dsDNA从而带有CTS（Cas9 targeted sequence）
<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/187073916-7561faa5-642f-4217-be03-089a053ea6cb.png" width="500">
</div>

### 通过Cas相关的碱基编辑器来实现基因编辑
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

#### 常见的碱基编辑器的序列

![image](https://user-images.githubusercontent.com/111955215/187112477-2167805c-ee39-41fa-9d54-0ce374340e1c.png)

#### 碱基编辑器的选择
碱基编辑器可以根据几个标准来选择，包括所需的编辑(C•G-to-T•A或A•T-to-G•C)，目标序列中合适的 PAM 的可用性，围绕目标核苷酸的序列基序，目标核苷酸在原型间隔区内的位置，不希望的旁观者突变的可能性以及需要尽量减少脱靶DNA或RNA编辑。该流程图可以指导候选基本编辑器的识别。根据应用程序的不同，一些标准将优先于其他标准，可能需要在效率和特定性之间进行权衡。SpCas9 CBE 的标准编辑窗口通常是原型间隔区位置4-8，对于SaCas9 CBE 是位置3-12，对于 Cas12a CBE 是位置8-13。SpCas9 ABEs 的标准编辑窗口通常是原型间隔区位置4-7，对于 SaCas9 ABEs 是位置6-12，对于 Cas12a ABEs 是位置8-13。

![image](https://user-images.githubusercontent.com/111955215/187060579-48a2284c-6ca5-4a66-87a0-bb3583a00b04.png)

### Cas相关的转座酶
Tn7样转座子通常含有 tnsA、 tnsB、 tnsC、 tnsD 和 tnsE 基因，以及其他遗传货物。通常，TnsA 和 TnsB 形成特异性识别左端(LE)和右端(RE)基序的 TnsAB 复合物，其侧翼转座子并催化从供体基因座切除转座子。TnsB 是逆转录病毒整合酶超家族的成员，并催化磷酸二酯骨架的3’切割，而 FokI 样蛋白 TnsA 随后催化5’末端的切割。然后，TnsB 将转座子 DNA 的游离3’末端连接到由 TnsD 或 TnsE 底物分配结构域确定的靶 DNA 底物，在5’连接处留下小的间隙。这些缺口的修复导致特征性的5-bp 目标位点重复。TnsC 是一种与 TnsAB 复合物、双链 DNA 和 TnsD 或 TnsE 中的一种相互作用的 ATP 酶

Cas 转座酶包括 Cas 蛋白和转座酶相关组分。Cargo DNA 由其左端(LE)和右端(RE)序列鉴定，并与转座酶蛋白(Tns)结合。Cas 蛋白以 PAM 依赖的 RNA 定向方式定向到感兴趣的靶基因座。Cas 结合将转座酶蛋白定位到感兴趣的目标序列，并促进目标位点的Cargo DNA整合进入基因组。

![image](https://user-images.githubusercontent.com/111955215/187115301-543520ce-7ece-41d1-970d-21ebdd16aebd.png)
### Prime editting
以前的技术要么一次只改变一个碱基，要么是需要引入修复模版。通过将具有双重功能的融合蛋白（脱氨酶活性和内切酶活性）和经过修饰的RNA结合起来，Prime Editing允许引入所有突变类型，包括插入、缺失和12种碱基-碱基转换

![image](https://user-images.githubusercontent.com/111955215/187614760-9750f2d6-7a62-4413-ab4c-d0c835d26364.png)

![image](https://user-images.githubusercontent.com/111955215/187591916-f67a0f9e-bedc-4517-a7a2-41cdc40fc6c7.png)

在这个新方法中，sgRNA被prime editing guide RNA (pegRNA)取代，pegRNA不仅驱动内切酶，还包含引物结合位点(primer binding site, PBS)区域。PBS区域引入可以和逆转录酶(RT)结合序列，并以pegRNA的序列作为模板直接从pegRNA复制信息来引入到目标序列中。这种技术在人类细胞中可以引进12个点突变，实现范围是PAM上游3bp到下雨29 bp，插入达44 bp，缺失达80 bp。值得注意的是，Prime Editing的效率与碱基编辑器相似，但特异性比以往系统更高。特异性提高的原因是以往的CRISPR/Cas系统中，只有一种杂交即sgRNA与靶DNA的杂交。而在Prime Editing系统中，有三种杂交事件:靶DNA和pegRNA的间隔序列之间的杂交;目的DNA与PBS之间的杂交;靶DNA与RT产物之间的杂交。（但是效率更低）

![image](https://user-images.githubusercontent.com/111955215/187591887-eb8379b6-a3e4-4ad8-952a-de50ab7c5e0c.png)

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/193016887-8b69d823-7dc4-44a3-b634-86360e2dfdcc.png" width="1500">
</div>

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/187116466-90df7aa1-947d-4001-9d59-d6bab6d435bc.png" width="1500">
</div>

#### 关于提高prime editing的编辑效率
研究者利用indel的MMR(mismatch repair)效率高于base-base的效率，开发了一种能提高base-base的prime editing效率的方法，即引入更多的同义突变(same-sense mutaion,ssm)，从而使得细胞的MMR从base-base变成indel repair，从而提高效率；而SSM又不会改变最终的蛋白表达，其转录组情况也得到验证为安全。对于不同的ORF，应该选择不同的突变策略。

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/193042058-2e4c9c5e-b47b-4357-9731-070213cf32ad.png" width="1000">
</div>

<div align=center>
<img src="https://user-images.githubusercontent.com/111955215/193041244-659dd8a0-c644-42ed-987f-fa833b96a3d8.png" width="800">
</div>

## crispr工具的补充-迷你核酸酶IscB和TnpB
来自于IS200/605转座子家族的IscB和TnpB，它们在微生物中广泛分布，被认为是CRISPR/Cas9和Cas12系统的起源。它们的最大特点是非常短的CDS序列，在1.2kb左右，体积不到spCas9的1/3，留下了**巨大的改造空间**。
Zhang Feng将这个系统称为Ω系统。Ω系统与其他已知RNA引导的DNA靶向系统的比较（CRISPR系统通过捕获间隔序列并储存在CRISPR阵列基因座中，与CRISPR系统不同，Ω系统可以将它们的基因座转置到靶标序列中，将靶标转化为ωRNA guides）

![image](https://user-images.githubusercontent.com/111955215/187116932-8787573f-16eb-45bd-b258-4af059a1cc35.png)
### IscB
从蛋白结构预测分析中，我们能够看到IscB同样存在RuvC和HNH两个酶活性位点

![image](https://user-images.githubusercontent.com/111955215/187115991-0b0afac8-aa91-45a2-a963-198956b0399a.png)

借助RNA测序和RNA-pulldown等技术手段，研究者也找到了IscB对应的sgRNA，其结构比spCas9的sgRNA还要更加复杂，被作者称为ωRNA

![image](https://user-images.githubusercontent.com/111955215/187116044-606d96dc-9b4c-458f-a841-d0f3cbf10c83.png)

通过体外DNA切割实验，研究者发现IscB具备由ωRNA引导识别(下图)并切割特定DNA双链序列的能力，其PAM序列也被作者称为TAM(target-adjacent motif)。不同于spCas9的是，IscB的切口是粘性末端(下图)。

![image](https://user-images.githubusercontent.com/111955215/187117727-5e5e0dcb-de0c-4f8d-b36c-c30a5922ac74.png)

![image](https://user-images.githubusercontent.com/111955215/187117793-13a82a7d-7b79-4cf5-a156-6f24385789b8.png)

从目前的结果来看，部分IscB蛋白能够编辑人细胞的基因组序列，但编辑效率还明显低于spCas9，最高也只有2%左右。

SUM UP: IscB已经具备了很多spCas9的优点，比如有两个酶活性位点，分别负责一条DNA单链的切割；又比如ωRNA的结构较为复杂，便于进行改造。而IscB最大的优势还是其非常小的体积，为递送提供了极大的便利，同时也就腾出了巨大的改造空间。

### TnpB
IS200/IS605家族的Deinococcus radiodurans ISDra2中包含tnpA和tnpB基因，以及位于两侧的LE（Left element）和RE（Right element）。crispr依赖的转座酶（上一part）也是这样的序列结构。

![image](https://user-images.githubusercontent.com/111955215/187117222-64c33d7c-be0c-455e-85b0-ad12f35923d5.png)

在纯化TnpB的过程中，作者发现有许多RNA也被一同纯化。对TnpB结合的RNA进行small RNA测序（sRNA-seq）分析，发现它们大多是长度约为150nt的长非编码RNA，来源于ISDra2中的RE序列，作者将这些RNA称为reRNAs（right element RNA）。reRNA 3’端的16nt来源于IS200/IS605转座子的侧翼DNA序列，其余序列与TnpB基因的3’端和RE序列匹配，说明TnpB可以与转座子3’端来源的reRNA形成RNP复合物。

PAM（protospacer adjacent motif）序列是Cas9或Cas12核酸酶启动DNA切割所必须的，那么TnpB发挥作用可能也需要类似的序列。通过PAM鉴定实验，作者观察到在目标基因5’端上游富集了大量的**TTGAT**序列，并称之为**Transposon Associated Motif (TAM)**。体外DNA切割实验证实**TnpB具备RNA引导的靶向dsDNA的核酸酶活性**。进一步分析发现，将TnpB序列中的RuvC-like活性位点突变后，TnpB失去了切割能力，说明RuvC模块与TnpB的活性相关。研究人员发现实现TnpB的DNA切割功能需要同时满足两个条件：（1）TAM序列；（2）与靶基因匹配的位于reRNA 3’端的序列。

TnpA 介导的 ISDra2的“剥离和粘贴”转座机制。TnpA 二聚体在 DNA 复制过程中催化从滞后链切除转座子，形成环形单链 DNA 中间体和供体关节。切除的转座子圆在受体连接处插入落后的 DNA 链3′至 TTGAT 序列，完成转座周期。转座子切除/插入位点用红色三角形标记。
![image](https://user-images.githubusercontent.com/111955215/187118202-db16d521-124d-42f6-8dee-543945e0a835.png)


随后，作者对切割产物进行了测序分析，结果显示，TnpB采取的是一种交错切割模式，在NTS（non-target strand）的多个位置和 TS (target strand) 的单个位置进行切割，最终产生5’-悬挂端（overhangs）

![image](https://user-images.githubusercontent.com/111955215/187118227-4f60f867-c9ea-45a2-8062-9772c22aad24.png)
