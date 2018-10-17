时间：2018年10月17日  
题目：喝酸奶问题

#### Java版本
```
    public static int Yogurt(int[] nums, int k){
        Arrays.sort(nums);
        int drink = 0,day=0,tmp=0;
        for(int i=0;i<nums.length;i++){
            if(tmp>=k){
                day ++;
                tmp = 0;
            }
            if(tmp<k && nums[i]>day){   // 酸奶没过期，可以喝
                tmp ++;
                drink ++;
            }
        }
        return drink;
    }
```

#### Python版本
```
def yogurt(nums,k):
    nums.sort()
    drink = 0
    day = 0
    tmp = 0
    for i in range(len(nums)):
        if(tmp>=k):
            day += 1
            tmp = 0
        if(tmp<k and nums[i]>day):
            tmp +=1
            drink += 1
    return drink

import sys
in_f = sys.argv[1]
out_f = sys.argv[2]
import pdb
with open(in_f,'r') as fr,open(out_f,'w') as fw:
    sample_num = int(fr.readline().strip())
    for i in range(sample_num):
        N, K = tuple(map(int,fr.readline().strip().split()))
        yogurts = list(map(int,fr.readline().strip().split()))
        res = "Case #{}: {}".format(i+1,yogurt(yogurts,K))
        fw.write(res+'\n')

```
