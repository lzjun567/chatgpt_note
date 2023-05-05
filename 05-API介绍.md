利用ChatGPT提供的API来构建我们自己的AI工具前，有必要先了解里面的概念


### 概念介绍

#### 什么是Prompt


在 ChatGPT 中，prompt 表示提示词，指用户与AI发起对话时输入的内容，提示词可以是一个问题、一个指令等信息，也可以是包含其他详细信息，例如一个完整的上下文、示例等信息，模型会基于这个提示词生成回复内容。


prompt 的设计对于生成高质量回答非常关键。好的 prompt 可以引导模型更准确、更有针对性地生成回复。



### 什么是model

模型是OpenAI的核心，OpenAI提供了多种模型，最新的模型是GPT-4，此外还有GPT-3.5、GPT3、以及Whisper等多种模型，他们功能以及价格各不相同。



### 什么是Token

Token 是模型处理文本的基本单位。Token 可以是一个单词、一个词语或者是单词中的字块。例如，单词“hello”这个单词就是一个token，而“hamburger”会被拆分为“ham”、“bur”和“ger”这三个token。

模型负责将输入的文本数据转换为 GPT 可以处理的数据格式（token）。

通常1000个Token约等于750个英文单词或者400～500个汉字。

每个 GPT 模型都有一个预设的最大 Tokens 数量。例如，GPT-3 每次调用允许处理的最大 Tokens 数量约为 4096。GPT4则允许处理3万多个Token， 这个数量包括用户输入和GPT输出的所有 Tokens。

另外，OpenAI官网提供了一个文本与token长度计算[工具](https://platform.openai.com/tokenizer)

![image-20230419221746818](../../images/image-20230419221746818.png)

比如“我是刘志军”5个字符占用了9个token。



#### API KEY



API Key 是开发者调用 OpenAI 提供的API 的凭证，另外某些第三方ChatGPT工具，都需要我们自己指定KEY。 



#### 如何获取key

登录网站：https://platform.openai.com/，点击右上角账号名字，弹出菜单后点击「View API keys」



![img](../../images/FtpGaKL4oSzyifHuHHnJ1CXAEjL0.png)

点击「Create new secret key」创建一个新key



![img](../../images/FsgwnWLmF7a1eWn88f_gGndI1zKP.png)



可以给这个key设置一个名字方便后面查阅，也可以不设



![img](../../images/FkdTXrGJU_V5o4-iJm1S97js0rnN.png)



点击「Create secret key」  



![img](../../images/FgiLh0IxHYH1okQ8KW8yskJES2hh.png)

创建成功后，一定要及时把key保存到本地，因为当前页面关闭后就无法完整的查询到该key的内容，否则你只能创建一个新key。



#### API如何计费

OpenAI根据不同的模型提供了不同的API收费价格

GPT3.5价格非常便宜，1000个token的价格是0.002美元，换算成人民币1000字的问答所消耗的费用2分钱左右。而GPT4的价格比GPT3最高贵了近6倍。

![image-20230419221042273](../../images/image-20230419221042273.png)



虽然在官网使用ChatGPT完全免费，不会有任何费用扣除，但是调用API是付费的，默认ChatGPT账号一定的余额，通常是5美元或者18美元，而且余额是有有效期的。


登录OpenAI账号[platform.openai.com](https://platform.openai.com/account/usage)可查看到账号的余额还剩多少。

![image-20230419103026890](../../images/image-20230419103026890.png)

点击左侧的Usage，能详细看到每天消耗的费用和总使用量，注意这个赠送额度是有期限的，例如我账号里面的余额6月1日到期，过期后会自动清零。如后续还需继续使用API服务，就需要另外购买。



#### 如何申请API额度

余额用完后，我们可以申请更多的额度，普通账号就可以操作，你只要绑以上一张国外信用卡，确保卡里面已经有余额（几美元就行）。



![image-20230419111332138](../../images/image-20230419111332138.png)

根据自己需求选择个人或者企业

![image-20230419111932747](../../images/image-20230419111932747.png)

地址可以根据IP所在地在网上找生成器弄一个

![image-20230419112408148](../../images/image-20230419112408148.png)



绑卡成功后，信用卡会预扣款5美元，同时在你的账号中会多出120美元的使用额度，注意这个不是赠送给你的余额，而是你当月可消费的最大限额，具体扣款会在月底根据你实际消费从信用卡中扣除。



![image-20230419104413858](../../images/image-20230419104413858.png)

如果你的使用量非常大，120美刀不够用，你还可以去申请更大限额，填表格就行，然后等待审核通过即可。

![image-20230419144605860](../../images/image-20230419144605860.png)



### API介绍







#### 参数



