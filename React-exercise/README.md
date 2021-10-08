难点1：柯里化
11-1 柯里化的操作比较麻烦，注意一下。 文件路径：https://github.com/Ming233/FrontEnd/blob/1365d31cef4885bc6633911d6ef3d5b3f900f780/React-exercise/react_basic/11_%E9%AB%98%E9%98%B6%E5%87%BD%E6%95%B0_%E5%87%BD%E6%95%B0%E6%9F%AF%E9%87%8C%E5%8C%96/1_%E9%AB%98%E9%98%B6%E5%87%BD%E6%95%B0_%E5%87%BD%E6%95%B0%E6%9F%AF%E9%87%8C%E5%8C%96.html
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

难点2：去除柯里化并使用回调形式
文件路径：https://github.com/Ming233/FrontEnd/blob/1365d31cef4885bc6633911d6ef3d5b3f900f780/React-exercise/react_basic/11_%E9%AB%98%E9%98%B6%E5%87%BD%E6%95%B0_%E5%87%BD%E6%95%B0%E6%9F%AF%E9%87%8C%E5%8C%96/2_%E4%B8%8D%E7%94%A8%E5%87%BD%E6%95%B0%E6%9F%AF%E9%87%8C%E5%8C%96%E7%9A%84%E5%AE%9E%E7%8E%B0.html
