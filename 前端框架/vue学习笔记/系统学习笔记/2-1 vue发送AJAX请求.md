# VUE中发送AJAX请求
### 1、VUE请求简介
    VUE本身是不支持发送AJAX请求,需要使用第三方插件(axios、vue-resource)等插件实现
    axios是一个基于Promise的HTTP的请求客户端
    axios中文文档 地址 https://www.kancloud.cn/yunye/axios/234845
    axios的官方文档 地址 https://github.com/axios/axios
### 2、关于安装以及文档使用
    可以参考官方文档介绍
    
    axios的官方文档 地址 https://github.com/axios/axios
    
    使用终端安装命令 npm install axios --save

#### 2.1、axios的使用
    使用axios({option})形式来进行请求
    一个vue的点击事件，和一个vue实例请求方法
html
```html
<button @click="send">发送axios请求</button>
```
js
```js
methods: {
				send() {
					axios({
						method: 'get',
						url: 'data.json'
					}).then(resp=>{
						console.log(resp)
					}).catch(resp=>{
						console.log('请求失败')
					})
				}
			}
```
json数据
```json
{
	"MSG":"success",
	"state":0,
	"strMSG":"数据返回成功"
}
```

#### 2.2、axios的POST请求使用

	关于axios的POST请求有个天生缺陷，根据官方网站介绍POST请求可以按照以下方式请求
```js
axios.post('/user', {
    firstName: 'Fred',
    lastName: 'Flintstone'
  })
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  });

  axios({
  method: 'post',
  url: '/postresponse.php',
  data: {
    name: 'Fred'
  }
}).then(resp=>{
	console.log(resp)
})
```
