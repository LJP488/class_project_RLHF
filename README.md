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
