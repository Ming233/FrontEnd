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
[柯里化去除：](./react_basic/11_高阶函数_函数柯里化/2_不用函数柯里化的实现.html)

难点3： [react的生命周期](./react_basic/12_组件的生命周期/2_react生命周期(旧).png)

