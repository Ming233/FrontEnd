11-1 柯里化的操作比较麻烦，注意一下。 文件路径：
function sum(a){
    return(b)=>{
        return (c)=>{
            return a+b+c
        }
    }
}
						
//简化 sum(y)
sum(y) = x => y => z =>x+y+z
柯里化解释：https://zhuanlan.zhihu.com/p/361398128

