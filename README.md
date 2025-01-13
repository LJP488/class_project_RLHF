# class_project_RLHF
RLHF训练分为三步，首先是训练actor model，由actor.ipynb文件实现；其次为训练reward model，由reward.ipynb文件实现；最后使用ppo进行actor model微调。
训练数据可从hugging face上下载得到，地址为 https://huggingface.co/datasets/shibing624/medical#finetune，
数据包含如下  
tree medical  
|-- finetune  # 监督微调数据集，可用于SFT和RLHF  
|   |-- test_en_1.json  
|   |-- test_zh_0.json  
|   |-- train_en_1.json  
|   |-- train_zh_0.json  
|   |-- valid_en_1.json  
|   -- valid_zh_0.json    
|-- medical.py # hf dataset 数据展示用  
|-- pretrain # 二次预训练数据集  
|   |-- medical_book_zh.json  
|   |-- test_encyclopedia.json  
|   |-- train_encyclopedia.json  
|   -- valid_encyclopedia.json  
|-- README.md  
-- reward # 奖励模型数据集  
    |-- test.json  
    |-- train.json  
    -- valid.json  

代码借鉴部分说明  
在reward文件中，in[33],in[34],in[36]代码借鉴自 https://github.com/lansinuote/Simple_RLHF/blob/main/2.critic.ipynb  
在PPO文件中，in 4~13部分代码借鉴自https://github.com/liucongg/ChatGPTBook/blob/main/RLHFProj/PPO/train.py
其中由于操作失误，原先PPO训练结果没能保存下来，故看到PPO中仅有跑90代的结果，实际上模型结果为PPO跑3000+代的结果。  
