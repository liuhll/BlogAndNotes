# jQuery多库共存处理

- `无冲突处理`

- `$` 出现冲突的原因
   1. `$`太火热，`jQuery`采用`$`作为命名空间，不免会与别的库框架或者插件相冲突。

   2. jQuery版本更新太快，插件跟不上，导致不同版本对插件的支持度不一样。


- 解决冲突的方案
    - `noConflict函数`   
    > **Notes**  
    > -  引入jQuery运行这个`noConflict`函数将变量`$`的控制权让给第一个实现它的那个库，确保jQuery不会与其他库的`$`对象发生冲突。
在运行这个函数后，就只能使用`jQuery变量`访问`jQuery对象`

    ```javascript
    jQuery.noConflict();
    // 使用 jQuery
    jQuery("aaron").show();
    // 使用其他库的 $()
    $("aaron").style.display = ‘block’;
    ```
> **Notes**
> - 这个函数必须在你导入jQuery文件之后，并且在导入另一个导致冲突的库之前使用


## 源码分析

```javascript
Var _jQuery = window.jQuery,
    _$ = window.$;

jQuery.noConflict = function( deep ) {
    if ( window.$ === jQuery ) {
        window.$ = _$;
    }
if ( deep && window.jQuery === jQuery ) {
        window.jQuery = _jQuery;
    }
    return jQuery;
};
```

> **Notes**
> - 如果我们需要同时使用jQuery和其他JavaScript库，我们可以使用 `$.noConflict()`把`$`的控制权交给其他库。旧引用的`$` 被保存在jQuery的初始化; `
> - `noConflict()` 简单的恢复它们。
> -  通过类似`swap`交换的概念，先把之前的存在的命名空间给缓存起来，通过对比当前的命名空间达到交换的目的，
>     - 首先，我们先判断下当前的的`$`空间是不是被jQuery接管了，如果是则让出控制权给之前的`_$`引用的库，
>     - 如果传入`deep`为`true`的话等于是把`jQuery`的控制权也让出去了。


## 例子
```javascript
<script type="text/javascript">

    $("#aaron").click(function() {

        $.noConflict(); //让出控制权

		if (!$) {
			show("使用noConflict后，$不存在")
		}

		if (jQuery) {
			show("使用noConflict后，jQuery存在")
		}

		//通过闭包隔离出$
		;(function($) {
			if ($) {
				show("通过闭包隔离后，转为局部变量$存在")
			}
		})(jQuery);

    })

    function show(data) {
    	jQuery("body").append('<li>' + data + '</li>')
    }

</script>
```