# validator 1.0.0

HTML表单验证，简单易用




| 选项                  | 描述                                                                                                                                                                                                                                                                                                                         |
|----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| message        | {Object} 公用提示信息 |
| className      | {String} 提示信息css class |
| focus          | {Boolean} 错误表单元素是否获取焦点 |
| callback       | {Function} 自定义错误信息，返回两参，1错误信息，2错误element |

## 示例

#### 使用 
```javascript
   validator.init();
```
### 例子

```javascript
  <form action="">
    <p>*姓名：<input type="text" name="name" required pattern=".{1,4}" data-required="请填写姓名" data-pattern="你的姓能超过4个字！！！" /></p>
    <p>*年龄：<input type="text" name="age" required pattern="\d+" data-pattern="要填数字啊！！！" /></p>
    <p><input type="submit" value="提交" /></p>
  </form>
  <script>
    /*************** 初始化，init()必须，use()可选 ************/
     validator.use(/*{
		message:{
		  "required":"不能空着吧",	
		  "selectRequired":"选上有奖",
		  "pattern":"信息填写错误",
		  "type":"信息填写有误"
		},
		className:"err-msg",
		focus:true,
		callback:function(err,el){
			if(err){
				alert(err);
			};
		}
	}*/).init();
  </script>
```

### 其它
      三个常规验证: require，pattern,type，以及自定义验证customError；

	  customError错误，用input.setCustomValidity("错误信息")触发，用input.setCustomValidity("")取消;

	  即时显示错误信息 input.setMessage("错误信息");
      即时隐藏错误信息 input.setMessage("");
	
	  若要兼容IE9--，就不要用type为email、tel、number、url。。。等HTML5自身的验证，要用pattern验证。
