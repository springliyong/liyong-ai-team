# 公交车站间的距离  

### 要求：  
环形公交路线上有n个站，按次序从0到n-1进行编号。我们已知每一对相邻公交站之间的距离，distance[i] 表示编号为i的车站和编号为(i+1)%n的车站之间的距离。  
环线上的公交车都可以按顺时针和逆时针的方向行驶。返回乘客从出发点 start 到目的地 destination 之间的最短距离。  
  
### 说明：  
![_config.yml]({{ site.baseurl }}/images/bus1.png)

(http://img1.imgtn.bdimg.com/it/u=760114423,719454564&fm=15&gp=0.jpg)
    
**代码**：  
```java
public int distanceBetweenBusStops(int[] distance, int start, int destination) {
        if(distance==null||distance.length==0){
            return 0;
        }
        int sum=0;
        int dis=0;
        for(int i = 0; i < distance.length; i++){
            sum += distance[i];
            if(i >= Math.min(start,destination) && i < Math.max(start,destination)){
                dis+=distance[i];
            }
        }
        return Math.min(dis,sum-dis);
}
```  
  
**方法**：  
遍历一次求出环形总距离，两站之间的一个半环距离，总站距离减去半环距离为另一个半环距离，返回两个半环距离较小的即可。  

[题目地址](https://leetcode-cn.com/problems/distance-between-bus-stops/)
