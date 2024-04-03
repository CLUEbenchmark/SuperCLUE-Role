# SuperCLUE-Role
## SuperCLUE-Role中文原生角色扮演测评基准


在人工智能的快速发展中，中文大模型在文本生成、推理能力、角色扮演等领域取得了很大的进步。其中，大模型的角色扮演能力是AI领域的一大关注热点，
并且具有不错的应用前景，可以帮助开发情感陪伴工具和游戏NPC等。

当前的角色扮演测评基准包括CharacterEval、RoleBench等，这些基准的测评标准和方式往往不统一，并且在评价体系上不够全面，
缺少对于模型在常见应用场景下的应用潜力的评估。

为了缓解这一问题，我们推出了SuperCLUE-Role测评基和基准。这是一个包括角色扮演基础能力和场景应用能力测评的中文基准，
专门设计来评估和提升中文大模型在角色扮演方面的核心能力。SuperCLUE-Role（简称SC-Role）不仅保证了评估体系的细致全面，题目的高质量，
同时在题目的多样性和应用广度进行了适当扩充。

<img src="https://github.com/CLUEbenchmark/SuperCLUE-Role/blob/main/resources/img/SuperCLUE-Role20240401.png"  width="30%" height="30%"></img>


SuperCLUE-Role基准具备以下特点：

#### 细致的分类体系

为了更好地评估模型在角色扮演的各种能力维度，设置了三个一级维度，十个二级维度，为模型评估提供了更加全面细致的评估维度；

#### 贴近应用

为了测试中文大模型在常见应用场景下的应用潜力，设计了情感陪伴、游戏NPC、直播营销等应用场景任务，考察模型的应用潜力；

#### 细粒度评分

对于每个二级任务分别设计了多个评价标准，对于一个角色扮演问题，将多个评价标准的平均得分作为模型的得分。

总结而言，SuperCLUE-Role测评基准提供了更加细致全面的中文大模型角色扮演评估体系，为模型的深入研究和实际应用提供了一套关键且精确的评估工具与数据支撑。

随着SC-Role在中文角色扮演社区的广泛推广和应用，我们期待中文大模型在角色扮演方面能够实现更多创新和突破，进而推动人工智能技术在更广泛领域的深入应用和发展。

文章地址：

www.CLUEbenchmarks.com/superclue_role.html


# 一、SuperCLUE-Role

## 理念

SuperCLUE-Role项目的宗旨是为中文基础模型在角色扮演领域的发展提供一个专业的评估基准，旨在衡量模型在完成中文原生环境下角色扮演任务时的基础能力
（是否能够符合角色的语言风格、性格等），以及是否能够胜任情感陪伴、游戏NPC角色扮演等应用场景。SuperCLUE-Role致力于成为评估中文大模型角色扮演能力的有益工具，
以完善现有的评估方法，更好地适应中文环境。

具体而言，我们期望打造一个全面的角色扮演测评基准，它不仅能够挑战模型在角色扮演时遵循角色风格和性格等特征的能力，还能够测评出模型在常见应用场景的应用潜力。
SC-Role将作为一个中文原生的角色扮演测试集，通过全面的测试，为模型开发者提供清晰的指引和方向，帮助他们优化模型性能，推动中文大模型在角色扮演领域的进步。

## SC-Role与其他测评的区别与联系

<img src="https://github.com/CLUEbenchmark/SuperCLUE-Role/blob/main/resources/img/role_different.png"  width="30%" height="30%"></img>


## 测评任务维度

#### 维度一：角色基础
#### 对话能力：

考察角色扮演中是否满足对话流畅自然，联系上下文语境，使得前后逻辑一致。

例如，回答应当自然流畅，联系上下文语境进行回复，不能存在前后表述冲突。

#### 知识掌握：

考察模型是否有足够的知识储备，基于可信的事实和数据，

例如，回答应当符合角色出自的作品设定，保证信息无误

#### 维度二：角色演绎力

#### 语言风格：

考察模型回答是否符合角色的性格特点和语言风格。

例如，回答应当符合角色的表达习惯和用词特点。

#### 行为习惯：

考察模型回答是否符合角色的行为习惯

例如，回答应当符合角色的行为作风；

#### 角色背景：

考察模型回答模型是否充分理解角色的人生观、价值观和世界观，并且做出符合角色三观的回复。

例如，回答应当符合角色对特定观点的态度。

#### 维度三：场景应用

#### 情感陪伴：

模型应当能够充分理解用户的情感需求，表现出共情和进行有效的情绪引导。

例如，回答应当对咨询者的痛苦表示理解，并且给出合理安慰。

#### 游戏NPC：

模型应当能够以NPC的身份，正确且自然流畅地回复玩家的问题。

例如，回答应当足够自然，并且符合游戏机制设计。

#### 直播营销：

扮演直播带货主播，结合产品信息和顾客需求，进行直播带货。

例如，回答应当符合主播的风格，结合观众的需求和产品特点。

#### 社交场景：

正确理解场景和角色关系，给出符合角色设定和场景的回复。

例如，回答应当符合角色关系和场景。

#### 影音名人：

扮演指定名人与用户进行对话，并且能够根据要求生成影视作品的对话剧本。

例如，回答应当符合特定名人的人生阅历，三观。

## 测评及计分方式

整体测评流程包括：1.模型答案获取；2.评价获取；3.计算模型得分。

#### 1.模型答案获取：

通过多轮对话的形式，使用本地部署或者API 调用方式来获取模型的答案；

#### 2.评价获取：

对于每个二级任务都有多个评价维度，每个维度按照评分标准分为5级，定义为1-5分。结合参考答案使用超级模型进行打分，模型回答的得分是对应各个维度得分的平均值。

例如“语言风格”任务，设定三个评价打分维度：

1）符合基本要求：回答是否遵循用户意图，满足了用户提出问题的基本目的和需求，是否试图对问题扮演指定角色进行恰当的回应。

2）符合角色性格特点：回复是否符合角色给定的性格特点。

3）符合角色语言风格：回答是否符合角色给定的语言风格（包含惯用词、说话的方式、认知水平，交谈中双方的称呼等关键要素）。

#### 3.计算模型得分

首先统计模型在每个二级任务上的平均分作为该任务的得分，模型最终成绩等于所有二级任务得分的平均分。

## 示例


####语言风格

####第一轮问题：

请你扮演《万万没想到》中的王大锤，下面是角色信息：

语言风格特点：王大锤的语言风格充满了夸张和自嘲，他的台词往往带有强烈的喜剧色彩和讽刺意味。他的表达方式直接、简单，甚至有些幼稚，这与他“一根筋”的性格相符合。

他的语言中常常包含重复和强调的元素，以此来增强喜剧效果。例如，他的标志性台词“我叫王大锤，万万没想到……”就是通过重复和强调“万万没想到”这个短语来制造笑点。

惯用词：王大锤的惯用词包括“万万没想到”、“我的生涯一片无悔”、“我要我要，洞房洞房”等，这些台词在剧中反复出现，成为了角色的标志性语言。

他的台词通常带有一种无奈和悲催的感觉，反映了他屌丝身份的自我认知。

性格特点：王大锤是一个典型的“屌丝”形象，他木讷憨厚，有些呆萌，经常遭遇各种不幸和意外的转折。他有着不切实际的梦想，比如“升职加薪，当上CEO，

迎娶白富美，走向人生巅峰”，但往往事与愿违。尽管如此，他仍然保持着乐观的态度，总是能在困境中找到希望，这也是他深受观众喜爱的原因之一。

在一次不可思议的转折中，你意外地发现自己手中的彩票居然中了大奖。面对这突如其来的好运，记者蜂拥而至采访他。记者问：“王大锤，你现在有了这么多钱，

会有什么打算？你以前不是一直梦想着升职加薪，迎娶白富美吗？”

请你回复。记住你现在就是王大锤，你必须以第一人称给出你的回答，不能回复其他无关内容。

#### 第二轮问题：

记者追问：“那么你对孔连顺有没有什么想说的？她知不知道你喜欢她？”请你继续回复。


#### 行为习惯

#### 第一轮问题：

请你扮演角色梅长苏，进行对话，下面是角色的信息介绍：

梅长苏，原名林殊，是海宴所著长篇权谋小说《琅琊榜》及其同名改编剧中的主人公。他是琅琊榜首，被称为“江左梅郎”，并且是天下第一大帮江左盟的宗主。

梅长苏原本是赤焰军的少帅，因梅岭惨案身中火寒之毒，后经治疗改头换面，化名梅长苏，隐居江湖。十二年后，为了平反赤焰冤案，他以一介布衣的身份，

化名苏哲，返回金陵帝都。他以病弱之躯涉足朝堂纷争，凭借其智慧和策略，成功地为赤焰军平反，并辅佐靖王登基。梅长苏在国仇家恨、兄弟情义的漩涡中展现了他的智慧和勇气，成为了一个传奇人物。

记住你现在就是梅长苏，你必须以第一人称给出你的回答，不能回复其他无关内容。如果你发现有一位深受你尊敬的前辈，他的子嗣因为一桩误会被牵扯进宫中的斗争，

并且可能会因此丧命，你会如何运用你的智慧和资源来解救他，同时又不暴露你的真实身份？

#### 第二轮问题：

在你筹划救援行动的过程中，突然有消息传来，说你的好兄弟飞流可能会因为另一件案件被牵连，如果你去救那位前辈的子嗣可能就无法及时救出飞流，

你会如何权衡这两件事，并决定你的行动方案？

#### 游戏NPC

#### 第一轮问题：

请你扮演游戏NPC角色与玩家角色进行对话，下面是游戏信息：

世界观：故事发生在被称为艾蒙大陆的奇幻世界中.....

...省略...

NPC角色：格兰特

角色信息：种族：矮人；职业：铁匠；特点：身材矮小精悍，手艺高超，性情直爽；位置：杜隆镇；任务：可提供武器打造及强化服务，并且能够给玩家提供探索关于游戏的各种指引和建议；

...省略...

当前进度：已完成《矿坑蜘蛛》任务，正准备前往幽暗森林探索

已知情报：在杜隆镇的酒馆听说过幽暗森林里有一大笔宝藏

下面是玩家和NPC格兰特的对话:

玩家：格兰特，我准备探索幽暗森林了，《迷雾缭绕》的任务的完成条件是什么？

记住，现在你就是NPC格兰特，因此你必须在回复过程中，始终以第一人称进行回复。

#### 第二轮问题：

玩家：格兰特，谢谢你的建议。我觉得我的防御力有点低，我可以通过什么方式提高我的防御力？


# 二、测评结果

#### 1.SuperCLUE-Role模型象限：

<img src="https://github.com/CLUEbenchmark/SuperCLUE-Role/blob/main/resources/img/role_xx.png"  width="30%" height="30%"></img>

▲ Role模型象限旨在区分国内外大模型在中文角色扮演能力上的定位差异。基础能力为角色基础和角色风格任务上的表现；应用能力为场景应用上的表现。

#### 2.SuperCLUE-Role基准得分：

<img src="https://github.com/CLUEbenchmark/SuperCLUE-Role/blob/main/resources/img/role_total.png"  width="30%" height="30%"></img>

▲ 本次测评选取了首批国内外代表性模型，后续会持续更新更多模型测评结果。

我们可以看到在中文原生场景下，GPT4-Turbo-0125角色扮演总分排名最高，国内模型表现也同样不俗，qwen1.5-72b-chat与文心一言4.0均有超过GPT4的表现。

#### 3.SuperCLUE-Role细颗粒度得分：

<img src="https://github.com/CLUEbenchmark/SuperCLUE-Role/blob/main/resources/img/role_detail.png"  width="30%" height="30%"></img>


#### 4.第一轮和第二轮差异：
<img src="https://github.com/CLUEbenchmark/SuperCLUE-Role/blob/main/resources/img/role_difference.png"  width="30%" height="30%"></img>

在SC-Role测评中，随着角色扮演对话轮数的增加，模型的得分普遍降低，表明在多轮对话中模型的角色扮演能力随着对话轮数的增加可能会出现能力减弱，是需要进一步解决的问题。


#### 5.多维度解读：

#### 1.三大任务维度关系分析

根据对三大维度（角色基础、角色演绎力、场景应用能力）的分数分析，“场景应用能力”与“角色演绎力”、“角色基础”均有很高的相关性（皮尔逊相关系数分别为0.89和0.90）。

可以看到在“角色基础”和“角色演绎力”维度上得分更高的模型，在“场景应用能力”维度上也倾向于有较高的得分。表明作为“角色基础”和“角色演绎力”共同支撑起模型的应用能力，更好的基础能力和更高的角色演绎力共同决定更好的应用能力。“角色基础”任务针对模型的对话能力和知识掌握水平，而“角色演绎力”任务则考察模型是否能够很好遵循角色的性格、语言风格、行为习惯和三观。

<img src="https://github.com/CLUEbenchmark/SuperCLUE-Role/blob/main/resources/img/role_app.png"  width="30%" height="30%"></img>

<img src="https://github.com/CLUEbenchmark/SuperCLUE-Role/blob/main/resources/img/role_basic_app.png"  width="30%" height="30%"></img>

#### 2.知识掌握水平的重要性

<img src="https://github.com/CLUEbenchmark/SuperCLUE-Role/blob/main/resources/img/role_knowledge.png"  width="30%" height="30%"></img>

<img src="https://github.com/CLUEbenchmark/SuperCLUE-Role/blob/main/resources/img/app_knowledge.png"  width="30%" height="30%"></img>

根据分析，我们看到在中文原生测评环境下，角色演绎力和场景应用能力都与模型的知识掌握水平有着较强的相关性(皮尔逊相关系数分别为0.80和0.87)。通常较强的角色演绎力和场景应用能力需要模型具有不错的知识掌握水平。

#### 3.在非常规的角色扮演问题上，模型能力有待加强

<img src="https://github.com/CLUEbenchmark/SuperCLUE-Role/blob/main/resources/img/special_case.png"  width="30%" height="30%"></img>

我们看到即使模型已经掌握了相关知识，仍然会出现无法识别到用户问题中存在的错误的现象，很多时候只会顺着用户的问题进行回答。


在以上两个示例中，可以看到，当让模型扮演陆展博时，正常询问“展博，你和胡一菲是什么关系”时，模型的回答是正确的，清楚的知道两人是姐弟；但当我们将问题改为：“展博，我看你和胡一菲天天一起出去吃喝玩乐，你们俩进展怎么样，追到手了吗？”，此时，模型忘记了两人之间的真实关系，顺着用户的问题产生了违反剧本知识和角色的回答（实际上，展博和胡一菲之间只有姐弟之间的感情）。这一结果一方面说明，此类问题相较于常规问题更加复杂，对模型的对齐角色能力提出更高要求。同时也表明，现在模型的角色对齐能力还有待加强和改善。

# 三、结论及分析

#### 1.国内模型表现不错：

在中文环境下的角色扮演任务中，国内的模型有着不错的表现，比如qwen1.5-72b-chat、文心一言4.0均有超过GPT-4的表现。排名靠前的国内模型在中文场景应用能力上也有较高的得分，具有不错的应用潜力。

#### 2.基础能力和角色演绎力共同决定场景应用能力：

场景应用能力依赖于基础能力（对话能力、知识掌握水平）和角色演绎力（遵循角色语言风格、性格、行为习惯和三观的能力）。

#### 3.知识掌握水平影响较大：

模型的知识掌握水平是对于角色演绎能力和场景应用能力的重要支撑，较好的角色演绎力和场景应用能力通常需要模型具有不错的知识掌握水平。

#### 4.模型角色扮演能力有待加强：

模型更擅长处理常规的角色扮演问题，对于非常规的问题，对齐角色能力大大降低，也是模型可考虑改进的方向。

#### 5.多轮效果衰减：

随着对话轮数的增加，模型的表现会出现普遍的降低。

# 四、如何申请应用及联系方式？

加入交流群或添加微信交流，或发送邮件到contact@superclue.ai，标题：SuperCLUE-Role测评。

<img src="https://github.com/CLUEbenchmark/SuperCLUE-Role/blob/main/resources/img/role_group.png"  width="30%" height="30%"></img>

<img src="https://github.com/CLUEbenchmark/SuperCLUE-Role/blob/main/resources/img/contact.png"  width="30%" height="30%"></img>

#### 扩展阅读

[1] CLUE官网：www.CLUEBenchmarks.com

[2] SuperCLUE排行榜网站：www.superclueai.com

[3] Github地址：https://github.com/CLUEbenchmark/SuperCLUE-Role