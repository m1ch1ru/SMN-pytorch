# SMN-pytorch
0.Reproduce the result of paper Sequential Matching Network based on Pytorch. \n

For details about data preprocessing and model, refer to paper 
"Sequential Matching Network: A New Architecture for Multi-turn
Response Selection in Retrieval-Based Chatbots"

Author:
Yu Wu† Wei Wu‡ Chen Xing♦, Zhoujun Li†∗ Ming Zhou‡ \n
†State Key Lab of Software Development Environment, Beihang University, Beijing, China\n
♦College of Computer and Control Engineering, Nankai University, Tianjin, China\n
‡ Microsoft Research, Beijing, China\n
{wuyu,lizj}@buaa.edu.cn {wuwei,v-chxing,mingzhou}@microsoft.com\n
\n
For Tensorflow version implemented by the author, see repo:\n
https://github.com/MarkWuNLP/MultiTurnResponseSelection \n


1.Requirements \n
1.1 Dataset
Data file+vocab file+pretrained word2vec
All these can be downloaded in https://1drv.ms/u/s!AtcxwlQuQjw1jGn5kPzsH03lnG6U shared by author.
Perhaps VPN is needed if you are in China. Also I would like to upload the files to BaiduCloudDisk.

1.2 Environment
Tested on Ubuntu 16.04LTS with CUDA 10.1 + Pytorch 1.7
some third-party packages(easy to install with pip)

1.3 Device
Maybe 1 GPU or 2 is best. If you want more GPUs to be used, you should be able to deal with some trivial bug caused by cuda setup function.
Note that when model is trained in parallel on multiple GPUs,the speed depends on the slowest one, which is called bottleneck. 

2.Run
2.1 How to run
Change directory to the path where you clone these code and enter command:sh run.sh
It takes about 60-80 minutes to finish all the 3 experiments listed in run.sh

2.2 Model type
3 fusion modes are implemented for easy comparation, switch mode by giving command argument:
--fusion_type last -> SMN-last
--fusion_type static -> SMN-static
--fusion_type dynamic -> SMN-dynamic

2.3 Experiment settings
check all the arguments you can give:python run_train.py -help

2.4 File path
Don't forget to set :
--data_dir <the path where all the data files are saved> 
--output_dir <the path where cached file and trained model parameters should be saved>
 in run.sh,
 or you will never get rid of "No such file or directory".
  
All that you are expected to see when program is run successfully is writen as comments in run.sh

3.Douban Conversation Corpus
Not finished yet.
