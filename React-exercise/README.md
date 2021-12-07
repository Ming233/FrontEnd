# react难点总结

## 

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


## 难点3： [react的生命周期](./react_basic/12_组件的生命周期/2_react生命周期(旧).png)

## 难点4： [router的基石](./react_staging/08_src_路由的基本使用/前端路由的基石_history.html)
REACT-ROUTER-DOM就是基于这个原理，开发出来给SPA使用

## 难点5：[渲染props] (./React-exercise/react_extension/src/components/7_renderProps/index.jsx)
通过在组件中传入render这，可以给组件A传入B组件
				<A render={()=><B/>}/>
这样写，可以B组件传入PROPS
				<A render={(name)=><B name={name}/>}/>
                优势在于，A组件，可以提前预留一个RENDER，但是不知道这个预留的RENDER将来会是什么。（例如C,D,E,F都行）

## 组件通信方式总结

#### 方式：

		props：
			(1).children props
			(2).render props
		消息订阅-发布：
			pubs-sub、event等等
		集中式管理：
			redux、dva等等
		conText:
			生产者-消费者模式

#### 组件间的关系

		父子组件：props
		兄弟组件(非嵌套组件)：消息订阅-发布、集中式管理
		祖孙组件(跨级组件)：消息订阅-发布、集中式管理、conText(用的少)


[代码模板](./react_staging/02_src_hello_react/components/TestReact/Test.jsx)
RCC
RFC

    "start": "react-app-rewired start",
    "build": "react-app-rewired build",
    "test": "react-app-rewired test",
    "eject": "react-scripts eject"