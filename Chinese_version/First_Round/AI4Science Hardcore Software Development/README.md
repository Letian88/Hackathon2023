# 赛题背景

AI4Science硬核软件开发赛道由DeepModeling开源社区、北京大学超算队、北京大学Linux俱乐部联合主办。本赛道鼓励选手积极参与到AI4Science本身的工具开发中。对高性能感兴趣的同学可以对指定软件进行高性能优化；对AI感兴趣的同学可以针对某些网络进行重构。又或者你发现软件中还有一些别的问题你想要改进——总之只要是和AI4Science有关的一切软件开发在这里都被鼓励！



**本赛道赛题分为自由命题和固定命题两个部分。我们特别鼓励大家做自由命题，只要和AI4Science硬核软件开发相关的任何创意都非常欢迎；当然如果大家对自由命题不知所措，也可以参与固定命题赛道，在指定的命题下发挥自己的创意与才华。**



## 自由命题

本赛道的选手拥有充分的创意自由，可以选择任意和AI4Science硬核软件开发相关的想法来完成。包括但不限于：


- DeepModeling开源社区软件高性能优化：选手可以自由浏览DeepModeling开源社区相关软件，并对自己感兴趣的部分进行高性能优化

- DeepModeling开源社区软件开发：选手可以自由浏览DeepModeling开源社区相关软件，并对自己感兴趣的事情进行开发。如果不确定如何下手，优先鼓励大家查看社区项目里面的相关issue，解决issue里面的问题


选择这个赛道的选手，需要在初赛阶段提交自己的proposal来描述自己的想法并初步证实该想法可行性（评审组也会给出一些建设性的指导建议，方便更好的实现）。



## 指定赛题

**赛题一：高性能跨平台的邻近表算法实现**


- 邻近表（Neighborlist）在计算化学中具有重要意义，在第一性原理计算、分子动力学模拟等领域都有重要的应用。邻近表是一种用于表示对象之间的局部关系或邻近关系的数据结构，记录了在一定截断半径范围内相邻粒子的索引，并在模拟过程中随原子的运动而动态更新。因此，无论是近程相互作用的计算，还是局域的结构性质的统计都直接依赖于邻近表。因此，临近表建立的算法优劣将显著影响计算效率。我们逐渐意识到，在不同的科学计算项目中都有共同的邻近表需求，并且可以抽象为具有明确输入与输出的算法。此外，由于科学软件的复杂性和特殊性，程序不仅仅像深度学习框架一样强烈地依赖于GPU，而且需要运行在各种架构且异构的加速平台上。我们是否可以将邻近表抽象出来并进行高度优化，形成从python、c++到cuda，从x86、arm到各种异构加速平台全覆盖的高度优化的库，从而减少重复地开发。


- 受计算机硬件架构特性的影响，邻近表算法在不同硬件平台上的实现和性能表现存在显著差异。因此，在设计和优化邻近表算法时，必须针对各种计算机硬件架构进行特定的实现和优化。此外，模拟体系的性质也存在很大差异，如体系规模（从小型到大型体系）、密度分布（从稀疏到均匀密集）以及空间分布（从均匀到局部稠密）。基于这些不同的模拟体系特点，设计邻近表算法和优化策略时需要综合考虑各种因素，以确保算法在各种场景下的高效性能表现。

**赛题二：ABACUS**


- ABACUS是一款广泛应用于材料科学计算的高性能密度泛函理论（DFT）软件。为了充分发挥其在实际生产应用中的性能潜力，本赛题旨在挖掘并优化软件中的性能瓶颈，从而提高计算效率、节省计算资源并加速科研进程。


- ABACUS支持平面波（PW）和数值原子轨道（LCAO）两种不同的基组，选手们需要在对给定的两个算例（1. LCAO基组算例，2. PW基组算例）进行性能热点分析，并自由进行性能优化。


**赛题三：可自动微分的点电荷长程静电作用算法**

- 在周期性边界条件下的系统中，由于最小镜像约定的限制，邻近表方法不能有效处理长程静电相互作用。为了解决这个问题，研究人员发展了诸如Ewald、PME、PPPM等长程相互作用算法。随着系统规模的扩大，优化现有算法和开发新算法变得非常重要。在基于物理的分子力场DMFF中，我们将各种物理力场和模拟计算流视为人工智能模型的自然延伸，以第一性原理或实验数据为输入，采用先进机器学习算法反向矫正和优化物理模型参数。实现这一目标的关键是代码的自动微分功能。因此，在保证自动微分功能的前提下，如何实现高效且先进的长程静电作用算法成为一个亟待解决的问题。


**赛题四：DeepFlame—热力学函数和输运参数的神经网络训练**


- 在燃烧模拟中，计算更新热力学状态和输运参数是关键的一步。在工程应用中，工质入射、混合和燃烧等过程至少部分发生在跨临界或超临界状态下，可能导致燃烧模拟中常用的理想气体模型不再适用。尽管可以通过引入形式上更复杂的真实流体模型以提高燃烧模拟的准确性，但将导致模拟复杂度的增加和计算量的显著增加，定量来看，使用真实气体模型更新热力学函数和输运参数将会占用大涡模拟总计算时长的50%到75%。


**赛题五：DeepFlame—DeepFGM框架**


- Flamelet Generated Model（FGM）是一种使用预先计算的火焰来表示湍流反应流中火焰结构的燃烧模型。它为模拟复杂燃烧过程提供了一种高效的计算方式，并且被广泛应用在燃烧系统的CFD模拟。使用FGM模型需要基于查表计算而来的火焰面数据。然而，当又众多的反应组分，且随着变量的维度提升，用于计算的表所占用的内存将会十分巨大。DeepFGM，一种在DeepFlame里包含的湍流燃烧积分（TCI）模型，将会根据表中计算用到的每一个物理量生成量身定制的神经网络，最终减少整体的内存占用。





**[点击此处即可查看详细赛题内容](https://dptechnology.feishu.cn/docx/QGfHdUHrEowMi4xYkJuchN9Rnbh?from=from_copylink)**


