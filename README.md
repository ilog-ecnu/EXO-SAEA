# EXO-SAEA
"Accelerating surrogate assisted evolutionary algorithms for expensive multi-objective optimization via explainable machine learning"代码



## 论文

Li B, Yang Y, Liu D, et al. Accelerating surrogate assisted evolutionary algorithms for expensive multi-objective optimization via explainable machine learning[J]. Swarm and Evolutionary Computation, 2024, 88: 101610.

```tex
@article{li2024accelerating,
  title={Accelerating surrogate assisted evolutionary algorithms for expensive multi-objective optimization via explainable machine learning},
  author={Li, Bingdong and Yang, Yanting and Liu, Dacheng and Zhang, Yan and Zhou, Aimin and Yao, Xin},
  journal={Swarm and Evolutionary Computation},
  volume={88},
  pages={101610},
  year={2024},
  publisher={Elsevier}
}
```



## 算法框架

### A:流程图

#### A.1: 主流程

![fig-EXO-p1](https://github.com/user-attachments/assets/2ec98fd0-4aff-4353-88ac-51a61aef0cbc)


#### A.2: EXO operator 细节
![fig-EXO-p2](https://github.com/user-attachments/assets/78ed0481-c602-4cca-bb79-3d62ac26a7b6)



### B: 算法主流程伪代码
<img width="354" alt="fig-EXO-p3" src="https://github.com/user-attachments/assets/449cd610-0082-446f-b48d-fb96648801cc">


## 运行

**代码主函数**：REMOEXO.m

**脚本:**

```matlab
addpath('.');
LSMOP = {@LSMOP3,@LSMOP4,@LSMOP5,@LSMOP6,@LSMOP7,@LSMOP8,@LSMOP9,@LSMOP1,@LSMOP2};
Problem={LSMOP};
Alg = {@REMOEXO};
M=3;
D = [100];
N = [100];
len=length(D);
maxFE=300;
save=10;
run_count=5;
for alg_index=1:length(Alg)
    for pro_index=1:length(Problem)
        for pro_inner_index=1:length(Problem{pro_index})
            for r=1:run_count
                for i=1:len
                    platemo('algorithm',Alg{alg_index},'problem',Problem{pro_index}{pro_inner_index},'M',M,'D',D(i),'N',N(i),'maxFE',maxFE(i),'save',save);
                end
            end
        end
    end
end
```



## 版本

**PlatEMO version:** PlatEMO 4.2

**Matlab version:**  Matlab R2022b

