难点1：柯里化
11-1 柯里化的操作比较麻烦，注意一下。 [柯里化例子](./react_basic/11_高阶函数_函数柯里化/1_高阶函数_函数柯里化.html)

function sum(a){
    return(b)=>{
        return (c)=>{
            return a+b+c
        }
    }
}

//简化 sum(y)
sum(y) = x => y => z =>x+y+z
[柯里化解释：](https://zhuanlan.zhihu.com/p/361398128)

难点2：去除柯里化并使用回调形式
[柯里化去除：](.\react_basic\11_高阶函数_函数柯里化\2_不用函数柯里化的实现.html)

难点3： [react的生命周期](https://github.com/Ming233/FrontEnd/blob/5ed6b0b47b0744aa62036f82283528da865cb7f8/React-exercise/react_basic/12_%E7%BB%84%E4%BB%B6%E7%9A%84%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F/2_react%E7%94%9F%E5%91%BD%E5%91%A8%E6%9C%9F(%E6%97%A7).png)


[this subtext](./react_basic/11_高阶函数_函数柯里化/1_高阶函数_函数柯里化.html)