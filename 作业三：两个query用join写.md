## 作业三：这两个query,能不能用join写
### query一：
**query1 指令：**
```sql
    select*from t_employee WHERE 
    sal>(select sal from t_employee WHERE ename='SMITH');
 ```
 **指令运行结果**
 
 ![](https://github.com/BiubiuOoo1/My-Homework/blob/master/pictures/31.1.png)
 **join 指令：**
 ```sql
    select t1.deptno,t1.empno,t1.ename,t1.job,t1.MGR,t1.Hiredate,t1.sal,t1.comm
    from t_employee t1 inner join t_employee t2
    on t1.sal>t2.sal and (t2.ename='SMITH');
    select * from t_employee;
 ```
 **指令运行结果**
 
 ![](https://github.com/BiubiuOoo1/My-Homework/blob/master/pictures/31.2.png)
 
 ### query 二：
 **query1 指令：**
```sql
    select*from t_employee WHERE 
    (sal, job)=(select sal,job from t_employee where ename='smith');
 ```
 **指令运行结果**
 
 ![](https://github.com/BiubiuOoo1/My-Homework/blob/master/pictures/32.1.png)
 **join 指令：**
```sql
    select t1.deptno,t1.empno,t1.ename,t1.job,t1.MGR,
    t1.Hiredate,t1.sal,t1.comm from t_employee t1 inner 
    join t_employee t2 on (t1.sal = t2.sal and (t2.ename='SMITH')) 
    AND (t1.job=t2.job and (t2.ename='SMITH'));
 ```
 **指令运行结果**
 
 ![](https://github.com/BiubiuOoo1/My-Homework/blob/master/pictures/32.2.png)
 
