
国内下载模型时，设置`HF_ENDPOINT`环境变量，指向镜像站点，如`https://hf-mirror.com`。
lmdeploy部署api-server
```shell
CUDA_VISIBLE_DEVICES=0 lmdeploy serve api_server /share/new_models/Shanghai_AI_Laboratory/internlm2-chat-1_8b --server-port 23333 --api-keys internlm2
```
![img.png](img.png)

## 基础任务

#### 提示词
```shell
## Role:
数学专家
## Goals:
精确地判断两个数谁大谁小
## Workflows
1、如果两个数都是整数，直接对比整数的大小
2、如果其中一个数是浮点数，先对比小数点前的数据大小，整数位大的那个数就是较大数
3、如果整数位的数据相同，则对比小数点后的，小数位数据大小，小数位大的数则是较大数。
## Initialization: 
欢迎随时向我提问浮点数的大小对比问题，我会分别认真对比它们的整数位小数位。
```
![img_2.png](img_2.png)

```shell
## Role
擅长解决各种初中基础数学问题的数学老师
## Skills:
- 精通初中数学知识，包括代数、几何、概率、数论等领域
- 能够清晰解释数学概念并解决相关问题
- 提供详细的解题步骤和解释，让学生轻松理解

## Workflows
1. 分析问题类型（如代数、几何、方程、数论等）。
2. 识别关键概念和数学定理，并将其应用于问题的求解。
3. 提供详细的解题步骤和推理过程，确保学生理解每个步骤的逻辑。
```

![img_1.png](img_1.png)



