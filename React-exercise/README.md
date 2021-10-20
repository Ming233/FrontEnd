# react难点总结

## 难点一：柯里化
11-1 柯里化的操作比较麻烦，需注意一下。 [柯里化例子](./react_basic/11_高阶函数_函数柯里化/1_高阶函数_函数柯里化.html)

   ```js
    function sum(a){
        return(b)=>{
            return (c)=>{
                return a+b+c
            }
        }
    }
   ```

//简化后的柯里化 则是 sum(y)

   ```js
    sum(y) = x => y => z =>x+y+z
   ```
   
[柯里化解释：](https://zhuanlan.zhihu.com/p/361398128)


## 难点二：柯里化去除柯里化并使用回调形式
[柯里化去除：](./react_basic/11_高阶函数_函数柯里化/2_不用函数柯里化的实现.html)


   ```js
    saveFormData = (dataType,event)=>{
        this.setState({[dataType]:event.target.value})
    }

    //原来模样（柯里化）:
    用户名：<input onChange={this.saveFormData('username')} type="text" name="username"/>
    //react调用一下方法
    用户名：<input onChange={ ()=>{} } type="text" name="username"/>
    //加入event
    用户名：<input onChange={ (event)=>{this.saveFormData('username', event)} } type="text" name="username"/>
    //简化并精简后：
    用户名：<input onChange={event => this.saveFormData('username',event) } type="text" name="username"/>

   ```

   
[普通和高阶的调用实例：](./react_staging/03_src_TodoList案例/components/Item/index.jsx)
   ```js
    //勾选、取消勾选某一个todo的回调 ==> 高阶，柯里化
	handleUpdate = (id)=>{
		return (event)=>{
			this.props.updateTodo(id,event.target.checked)
		}
	}

	//删除一个todo的回调 ==> 非高阶，但是在文件里面需要写回调形式。例子：()=>this.handlexxx(id)
	handleDelete = (id)=>{
		if(window.confirm('Sure to Delete?')){
			this.props.deleteTodo(id)
		}
	}

   ```
    
   ```jsx
    <button onClick={this.handleCheck(id)}>Update</button>
    <button onClick={()=> this.handleDelete(id) }>Delete</button>
   ```

更多例子
    //原来模样（柯里化）:
    用户名：<input onChange={this.saveFormData('username')} type="text" name="username"/>
    //react调用一下方法
    用户名：<input onChange={ ()=>{} } type="text" name="username"/>
    //加入event
    用户名：<input onChange={ (event)=>{this.saveFormData('username', event)} } type="text" name="username"/>
    //简化并精简后：
    用户名：<input onChange={event => this.saveFormData('username',event) } type="text" name="username"/>

   ```


难点3： [react的生命周期](./react_basic/12_组件的生命周期/2_react生命周期(旧).png)

[代码模板](./react_staging/02_src_hello_react/components/TestReact/Test.jsx)
RCC
RFC

    "start": "react-app-rewired start",
    "build": "react-app-rewired build",
    "test": "react-app-rewired test",
    "eject": "react-scripts eject"