# forget-knowledge
容易忘记的一些小功能，小细节，小case



VPN:hanjinbao@huanqiu.com   PB456123

cmd 退出 alt+c。

1. 手风琴效果
	手风琴： 鼠标放在div上，左边的全部（包括鼠标悬停的这个），left值 重新赋予，每个都间隔相同距离x。右边的 	left值，全部 x + div的宽度。即可实现。

2. JSON.parse()和JSON.stringify()

	parse用于从一个字符串中解析出json对象,如

	var str = '{"name":"huangxiaojian","age":"23"}'
	注意：单引号写在{}外，每个属性名都必须用双引号，否则会抛出异常。

	结果：
	JSON.parse(str) 	// {age: "23",name: "huangxiaojian"}

	stringify()用于从一个对象解析出字符串，如
	var
	 a = {a:1,b:2}

	结果：

	JSON.stringify(a)		// ‘{“a”:1,”b”:2}’

3. javascript:void（0）;:        
	void是无返回值的操作，点击这个时候没有任何反应。
	而且如果在a标签中，如果href="#"，点击后会回到网页顶部，javascript:void(0)会没有任何反应.
	但是不影响对这个标签绑定一些动作事件。

4. async: false,（默认是true）;
	如上：false为同步，这个 testAsync()方法中的Ajax请求将整个浏览器锁死，
	只有tet.php执行结束后，才可以执行其它操作。

5. 获得页面url的某个url参数的方法
	function getUrlParam(name){ 
		var reg = new RegExp("(^|&)"+ name +"=([^&]*)(&|$)"); 
		var r = window.location.search.substr(1).match(reg); 
		if (r!=null) return unescape(r[2]); return null; 
	}
   window.location.search.substr(1)方法
	window的location对象
	search: 得到的是url中 包括?后所有部分
	substr()：返回一个从指定位置开始的指定长度的子字符串，这里设置为1，是为了把url中的？号去掉

6. 获得当前域名：console.log( window.location.href )

7. 火箭特效
	$(document).ready(function(e) {
    //页面滚动事件
    $(window).scroll(function(){
        //获取窗口已滚动的高度
        var windowScrollTop=$(window).scrollTop();
        var oTools=$("#tools");
            //如果大约100PX，就渐显出“回到顶部”，否则即隐藏
            if(windowScrollTop>100)
            {
                oTools.fadeIn();
                }else{
                        oTools.fadeOut();
                    }
        });
         
    $("#back_top").click(function(){
        //点击“回到顶部”，滚动到顶部，并带动画效果
            $("html,body").animate({scrollTop:0},1000);
        }); 
    });

8. <base target="_blank"> 加在head标签里将对所有未指定目标窗口的都用新窗口来打开..

9. 背景操作：
	background-clip：border|padding|content
	该属性指定了背景在哪些区域可以显示，但与背景开始绘制的位置无关，背景的绘制的位置可以出现在不显示背景的区域，这时就相当于背景图片被不显示背景的区域裁剪了一部分一样。
	background-origin：padding|border|content
	该属性指定了背景从哪个区域(边框、补白或内容)开始绘制,但也仅仅能控制背景开始绘制的位置，你可以用这个属性在边框上绘制背景，但边框上的背景显不显示出来那就要由background-clip来决定了


10. $(this).children('option:selected')
	
	直接选中当前选中的option。
	
11. jQuery.isEmptyObject()函数用于判断指定参数是否是一个空对象。

	所谓"空对象"，即不包括任何可枚举(自定义)的属性。简而言之，就是该对象没有属性可以通过for...in迭代。

12. $ ssh root@47.93.44.37          // root是用户名，@后面是服务器ip地址。回车然后输入密码即可连接。



13. 溢出文字省略...
	text-overflow:ellipsis;

14. 规定段落中的文本不进行换行：
	p
 	 {
 	     white-space: nowrap;
  	  }


15.文字超出具体处理

   1> p{
	display: -webkit-box;
	-webkit-box-orient: vertical;
	-webkit-line-clamp: 3;   // 限定3行，超出部分隐藏并且用省略号代替。
	overflow: hidden;
       }



   2> p{
	position: relative; 
	line-height: 20px; 
	max-height: 80px;    // 限定一个高度，超过这个高度，超出部分隐藏并且用省略号代替。
	overflow: hidden;
     }
    p::after{
	content: "..."; 
	position: absolute; 
	bottom: 0; right: 0; 
	padding-left: 40px;
        background: -webkit-linear-gradient(left, transparent, #fff 55%);
        background: -o-linear-gradient(right, transparent, #fff 55%);
        background: -moz-linear-gradient(right, transparent, #fff 55%);
        background: linear-gradient(to right, transparent, #fff 55%);
     }


		<p style="width: 300px;">
			因使用了WebKit的CSS扩展属性，该方法gggggg
			因使用了WebKit的CSS扩展属性，该方法gggggg
			因使用了WebKit的CSS扩展属性，该方法gggggg
			因使用了WebKit的CSS扩展属性，该方法gggggg
			因使用了WebKit的CSS扩展属性，该方法gggggg
		</p>



16. 如果 返回顶部图标 想实现首页那种效果（位置）

	.gotop {
    		width: 40px;
    		height: 190px;
   		position: fixed;
   		bottom: 5%;
    		left: 50%;
    		margin-left: 500px;
    		z-index: 100;
	}

内网IP地址：cmd命令工具：ipconfig;


17. 设置git 帐号。
	git config --global user.email "you@example.com"
	git config --global user.name "Your Name"
    查看git 账号/邮箱 git config user.name/git config user.email

加载更多距离底部：42px。
屏幕高度：$(window).height()=667； 
加载更多距离顶部：  $("#load_more").offset().top
 = 4342.78125
减去的高度： $(window).scrollTop();

if($("#load_more").offset().top - $(window).scrollTop()

整体越来越小。当 <= $(window).height()- 42px - 50px  + 20px


18. 自己封装的滑动加载更多，完美
	bindEvent : function(){
				var flag;

        		window.onscroll = function(){	
        			// $(window).scrollTop() += 0.18750;
        				if($("#load_more").offset().top - $(document).scrollTop() <= $(window).height()- 42 - 55){
        					
							flag = true;
	
        				}
						console.log(flag);
				}

                $('body').on('touchend',function(){
                    console.log('触碰结束');

                        if(flag){
                            console.log("keyile");

                            flag = false;

                            List.tmp.page++;
                            var data = { 
                                page : List.tmp.page,
                                callback : function(results){ 
                                    List.tmp.data = results.data.list;
                                    List.tmp.total = results.data.total;        
                                    var dom = List.createDom(); 
                                    $("#listItems #load_more").replaceWith(dom);
                                    List.bindEvent();
                                }
                            }  
                            Ajax_list(data);
    
                        }else{
                            console.log("bukeyile");
                
                        }
                })


        }


19. 自动获取焦点
	<input type="text" name="fname" autofocus="autofocus">

20. 右击新建消失
	直接 开始 运行：cmd /k reg add "HKEY_CLASSES_ROOT\Directory\Background\shellex\ContextMenuHandlers\New" /ve /t REG_SZ /d {D969A300-E7FF-11d0-A93B-00A0C90F2719} /f


21. 粒子漩涡 canvas 特效：http://www.jq22.com/js/a11.html

22. rem 用法 替换px (47有更好办法，切换屏幕不用刷新自适应)
   1. 主要的公式就是  1rem=规定值*（物理设备宽度/设计稿的物理设备实际宽度）

		<meta charset="UTF-8" />
		<title>Document</title>
		<!-- 将一个默认的html面 变为 移动端页面 首先需要添加 添加的位置 是最上方 -->
		<!-- 视口属性  -->
		<meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0" />
	<script>
         	//通过window.screen.width获取屏幕的宽度
         	var offWidth = 30 * window.screen.width / 设计的设备实际宽度; //这里表示1rem取得的px
         	document.getElementsByTagName("html")[0].style.fontSize = offWidth + 'px'; //把rem的值复制给顶级标签html的font-size	
         	console.log(document.getElementsByTagName("html")[0].style.fontSize);
    	</script>

23. 微信分享时的图片设置（下面55 会有最新方法）
	把缩略图放在第一个位置 图片尺寸也有要求 宽高最小400像素(具体的不清楚，你可以试一下200的是不行 太小 微信会跳过) 如果	不想让图片显示 ，用div包住，写上?style="width:0px; height:0px; overflow:hidden" 不能写display:none


24. 阻止事件冒泡：
	function showMsg(obj,e)
	{
    		alert(obj.id);
    		stopBubble(e)
	}

	//阻止事件冒泡函数
	function stopBubble(e){
    		if (e && e.stopPropagation){
        		e.stopPropagation()
    		else{
        		window.event.cancelBubble=true
		}
	}
</script>

25-1. form提交 打开2个页面解决：<form action="" onsubmit="return false">

25-2.  如何表单提交后不刷新页面？

	  <form action="" method="post" target="nm_iframe">    
      		<input type="text" id="id_input_text" name="nm_input_text" />    
      		<input type="submit" id="id_submit" name="nm_submit" value="提交" />    
  	  </form>    
  	  <iframe id="id_iframe" name="nm_iframe" style="display:none;"></iframe> 
	
	  在页面里定义一个iframe, name为hideIframe,这个iframe不让它显示，然后<form target="hideIframe">  就可以这么做了



26. HTML meta中添加X-UA-Compatible和IE=Edge,chrome=1有什么作用？

	<meta http-equiv="X-UA-Compatible" content="IE=7">  
	#以上代码告诉IE浏览器，无论是否用DTD声明文档标准，IE8/9都会以IE7引擎来渲染页面。  
	<meta http-equiv="X-UA-Compatible" content="IE=8">  
	#以上代码告诉IE浏览器，IE8/9都会以IE8引擎来渲染页面。  
	<meta http-equiv="X-UA-Compatible" content="IE=edge">  
	#以上代码告诉IE浏览器，IE8/9及以后的版本都会以最高版本IE来渲染页面。  
	<meta http-equiv="X-UA-Compatible" content="IE=7,IE=9">  
	<meta http-equiv="X-UA-Compatible" content="IE=7,9">  
	<meta http-equiv="X-UA-Compatible" content="IE=Edge,chrome=1">
	#以上代码IE=edge告诉IE使用最新的引擎渲染网页，chrome=1则可以激活Chrome Frame.

    注意事项：

	1，根据官网定义X-UA-compatible 标头不区分大小写；不过，它必须显示在网页中除 title 元素和其他 meta 元素以外
	   的所有其他元素之前。如果不是的话，它不起作用

	2，content的内容是IE=8，或者IE=edge等值，注意不是IE8或者直接写个edge的值，否则不起作用

27. 怎么让手机点击Web页面为数字就拨打电话 ？

	<a href="tel:电话号码">电话号码</a>


28. 关于jquery中on绑定click事件在苹果手机失效的问题？

     经过查找资料才知道，苹果有这么个设置： 
	对于点击的对象，拥有cursor:pointer这个样式的设置，也就是说，鼠标放上去，能够出现“手”型的图标才被认作可以使用点击事件，于是要给事件对象增加样式

	<style>
    		.demo{
        	    cursor:pointer;
    		}
	</style>

29. 手机打开网页，强制跳转到wap版。但是点击电脑版还会到pc版
      <script type="text/javascript">

        // 获取URL？方法：
        function getURL(name) {
            var reg = new RegExp("(^|&)" + name + "=([^&]*)(&|$)");
            var r = window.location.search.substr(1).match(reg);
            if (r != null) return decodeURI(r[2]);
            return null;
        }
        var cid = getURL("desktop")=== "true";

        var system ={
            win : false,
            mac : false,
            xll : false
        };
        //检测平台
        var p = navigator.platform;
        system.win = p.indexOf("Win") == 0;
        system.mac = p.indexOf("Mac") == 0;
        system.x11 = (p == "X11") || (p.indexOf("Linux") == 0);
        //跳转语句，如果是手机访问就自动跳转到http://3g.visitbeijing.com.cn/页面
        if(system.win||system.mac||system.xll){
            
        }else{
            // 首先是手机，然后根据URL判断，如果是http://www.visitbeijing.com.cn/ 自动转 3g。 在3g中
            // 强制进入电脑版 后面+desktop=true。
            if(!cid){
                window.location.href="http://wap.visitbeijing.com.cn/";/*如果是手机访问就跳转到这个网址*/
            }
            
        }
    </script>


30  如何跳转到另一个页面的指定位置，跳转页面指定位置
	
	设置<a>的锚点！ 例如：从index.html跳转到index1.html的指定位置，在index1.html指定的位置写入<a name="#tz"></a> 
	在index.html中写入<a href="index1.html#tz">跳转</a>
	然后点击跳转就会跳转到<a name="#tz"></a>所在的位置


31  jquery链式写法问题

	这样加个end()就可以了，表示回到$(this)元素，而你原来的表示这个里面找div元素
 
 
	$ (this).find ("div").css ("background", "red").end().siblings ().find ("div").css ("background", "green");


32.  // 封装的跟随滑动 功能。
	function moveBy1(h1, id){

		// h1 为当页面被卷去的高度（固定值），当到达这个值，开始执行某个事件。

		var timer;

		$(document).scroll(function(event) {
			// if($(document).scrollTop()>= 400){
				console.log(1)
				clearTimeout(timer);
				timer = setTimeout(function() {
					var h = $(id).offset().top;
					console.log(2)
					
					var j = $(document).scrollTop();

					if($(document).scrollTop()>= h1){    // 注意这个判断的位置。
							console.log(3)
							$(id).animate({top: j - h1}, 700);
					}else{
						$(id).animate({top: 0 }, 700);
					}
				}, 50);
			
		});
	}
	moveBy1(300, "#hid");

33.   html5中video标签中视频的长和宽如何调整?
      如题，主要就是视频比例和video标签的比例是不同的，然后就会有一些空的地方，我想拉伸视频

	答： 为video设置宽高，
		添加object-fit:fill属性，
 		搞定。

34. 跨域通信(锚点问题)
            1、js实现
		a.html中
            <script>
            window.addEventListener("message",?function?(e)?{

                console.log(1);  
                // console.log(e.data);  
                // console.log(e.origin);  
    
??              if(e.origin !== 'http://special.huanqiu.com') return;  
                if(e.data){
                     $("html, body").animate({
                    scrollTop: 3872 }, {duration: 500,easing: "swing"});
                }
                console.log(2);  
            },?false);
            </script>

	b.html中
	var?targetOrigin='*';
	var?eventObj?=?flag;
	window.parent.postMessage(eventObj,targetOrigin);  

   2、css实现
	html,body{
                height:100%;
                overflow: hidden;
            }
            iframe{
                min-width: 1038px;
            }
	<iframe id="myiframe" src="http://special.huanqiu.com/special/Enlyj/index.html" frameborder="0" frameborder="0" width="100%" height="100%" ></iframe>
	这种有小瑕疵，原理：父页面隐藏滚轮，显示子页面的。


35.  将字符串类数组转换为数组
     var strArr = '["a","b","c"]';
     var arr = json.parse(strArr);

36.  在本页面只要点击 回车都会执行键盘事件
     var input = document.getElementById("input");
     document.activeElement === input;当前获取焦点的元素是 input。 注意：这个input只能是原生获取，不能jq获取（$('#input'）)。
     document.hasFocus();  检测文档(或文档内的任一元素)是否获取焦点。

	// pc端键盘事件：回车 搜索，需要加一个限制条件 document.hasFocus() && document.activeElement === input，
	// 否则在本页面只要点击 回车都会执行键盘事件。

37. JSON.stringify()/JSON.parse()在 IE6、7、8下会有兼容问题.

38. 点击 <a href="18禁.pdf">下载</a> 的时候，Chrome 会自动调用内置的 pdf 阅读器打开，我只想让用户下载这个文件，有什么办法呢？
	最方便的是：
	<a href="18禁.pdf" download>下载</a>

39. git branch -r 分支不全：
	 git config -e   命令后
	将里面fetch = +refs/heads/master:refs/remotes/origin/master 改成 fetch = +refs/heads/*:refs/remotes/origin/*
  
	
40. 图片之间依然有空隙

	img标签本身是个行内元素，所以当多个img排在一起时，它们之间如果有回车换行或者空格就会形成空隙

41. CSS3 animation-name 属性
	/*  -o-transition  -moz-transition   -webkit-transition  transition */
	/* transform  -ms-transform  -moz-transform  -webkit-transform  -o-transform */
	/* -webkit-animation  animation */
	/* animation-direction:alternate; 是否反向播放 */
	/* keyframes @-webkit-keyframes*/

	为 @keyframes 动画规定一个名称：
	div
	{
		width:100px;
		height:100px;
		background:red;
		position:relative;
		animation-name:mymove;
		animation-duration:5s;
		/* Safari and Chrome */
		-webkit-animation-name:mymove;
		-webkit-animation-duration:5s;
	}
		@keyframes mymove
	{
		0% {left:0px;}
		100% {left:200px;}
	}
	@-webkit-keyframes mymove /* Safari and Chrome */
	{
		0% {left:0px;}
		100% {left:200px;}
	}
	请用百分比来规定变化发生的时间，或用关键词 "from" 和 "to"，等同于 0% 和 100%。
	0% 是动画的开始，100% 是动画的完成。
	为了得到最佳的浏览器支持，您应该始终定义 0% 和 100% 选择器。


42.  git branch -r 分支不全：
	 git config -e   命令后
	将里面fetch = +refs/heads/master:refs/remotes/origin/master 改成 fetch = +refs/heads/*:refs/remotes/origin/*

43.  时间插件 datatimepacker。http://topic.visitbeijing.com.cn/site/2018/EN/overseas_3g/join.html 实例

44.  最新jq版本线上地址：    <script src="https://code.jquery.com/jquery-3.2.1.min.js"></script>

45.  提交表单，文字信息和文件同时提交的 打包formData方法（原生有兼容，建议用jq）

46.  表单复选框 name="checkbox[]"  注意必须要有[],前面是任意名字

47.  手机自动适应，不需要刷新
	<script>
// 该代码来自http://www.ghugo.com/mobile-h5-fluid-layout-for-iphone6/
(function (doc, win) {
    // 分辨率Resolution适配
    var docEl = doc.documentElement,
        resizeEvt = 'orientationchange' in window ? 'orientationchange' : 'resize',
        recalc = function () {
            var clientWidth = docEl.clientWidth;
            if (!clientWidth) return;
            docEl.style.fontSize = 100 * (clientWidth / 320) + 'px';
        };

    // Abort if browser does not support addEventListener
    if (!doc.addEventListener) return;
    win.addEventListener(resizeEvt, recalc, false);
    doc.addEventListener('DOMContentLoaded', recalc, false);
    
    // 一物理像素在不同屏幕的显示效果不一样。要根据devicePixelRatio来修改meta标签的scale,要注释上面的meta标签
    (function(){
        return;
        var dpr = scale =1;
         var isIPhone = win.navigator.appVersion.match(/iphone/gi);
        var devicePixelRatio = win.devicePixelRatio;
        if (isIPhone) {
            // iOS下，对于2和3的屏，用2倍的方案，其余的用1倍方案
            if (devicePixelRatio >= 3 && (!dpr || dpr >= 3)) {                
                dpr = 3;
            } else if (devicePixelRatio >= 2 && (!dpr || dpr >= 2)){
                dpr = 2;
            } else {
                dpr = 1;
            }
        } else {
            // 其他设备下，仍旧使用1倍的方案
            dpr = 1;
        }
           scale = 1 / dpr;
           
           // 
           var metaEl = "";
           metaEl = doc.createElement('meta');
        metaEl.setAttribute('name', 'viewport');
        metaEl.setAttribute('content', 'initial-scale=' + scale + ', maximum-scale=' + scale + ', minimum-scale=' + scale + ', user-scalable=no');
        if (docEl.firstElementChild) {
            docEl.firstElementChild.appendChild(metaEl);
        } else {
            var wrap = doc.createElement('div');
            wrap.appendChild(metaEl);
            doc.write(wrap.innerHTML);
        }
    })();
        
})(document, window);    
</script>

48. border-radius兼容写法：
	 border-radius:3px; 
	-webkit-border-radius:3px; 
	-moz-border-radius:3px;
	-ms-border-radius:3px; 
	-o-border-radius:3px;

49. head 中   <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />

50. css3动画：
	/*  -o-transition  -moz-transition   -webkit-transition  transition */
	/* transform  -ms-transform  -moz-transform  -webkit-transform  -o-transform */
	/* -webkit-animation  animation */
	/* animation-direction:alternate; 是否方向播放 */
	/* @keyframes    @-webkit-keyframes*/

51. // 阻止手机浏览器屏幕 上下滑动
    $('body').on('touchstart', function (event) {
        event.preventDefault();
    });


52. video标签视频不成比例拉伸 添加：
	css: object-fit: fill;


53. 阿拉伯语文字顺序： css 给html{direction: rtl; unicode-bidi: bidi-override;}

54. Mac sublime 下载插件.在Sublime Text 3中选中packageControl：Install Package并回车 ，然后在输入框中输入你要下载的插件，然后按回车就可以安装插件了。

55. 微信分享文章缩略图问题：使用jssdk。公众号配置一下。前端页面 引入2个js. 1.http://res.wx.qq.com/open/js/jweixin-1.2.0.js
	2.一些配置。北京旅游网配置代码在 wx1.js文件。

56. $(selector).hover(inFunction,outFunction)
    等同于 $( selector ).mouseover( handlerIn ).mouseout( handlerOut );

57. 时间戳
    // 时间戳 --> 日期  yyyy-mm-dd hh:mm:ss
    function formatDate(ns){
        if(ns==0 || isNaN(ns)) { return '' }
        var date = new Date(parseInt(ns) * 1000);
            Y = date.getFullYear() + '-';
            M = (date.getMonth()+1 < 10 ? '0'+(date.getMonth()+1) : date.getMonth()+1) + '-';
            D = (date.getDate() < 10 ? '0'+ date.getDate() : date.getDate())+ ' ';
            h = (date.getHours() < 10 ? '0'+ date.getHours() : date.getHours()) + ':';
            m = (date.getMinutes() < 10 ? '0'+ date.getMinutes() : date.getMinutes()) + ':';
            s = (date.getSeconds() < 10 ? '0'+ date.getSeconds() : date.getSeconds());  
        return Y+M+D+h+m+s;
    }

58. 设置meta标签 清除页面缓存，详询： https://blog.csdn.net/m0_38073829/article/details/75453050
				http://www.jb51.net/web/160491.html
	<meta http-equiv="Cache-Control" content="no-cache, no-store, must-revalidate" />
	<meta http-equiv="Pragma" content="no-cache" />
	<meta http-equiv="Expires" content="0" />

59. ie8不兼容
	Background-size; box-sizing;

60. npm ls -g --depth=0
	是看npm全局安装了哪些模块
	安装gulp成功了，就能在列表里看到了

61. js方法图片预加载
    //存放图片路径的数组
    var imgSrcArr = [
        'http://r1.visitbeijing.com.cn/images/7200a4b511b4dd410a08cb56ea72f0fb.png',
        'http://r1.visitbeijing.com.cn/images/6f6ca4abe5652a08a96369df6f7c4f6d.png',
        'http://r1.visitbeijing.com.cn/images/5fb1af879ab57645c95ac04e2b287716.png',
        'http://r1.visitbeijing.com.cn/images/764d9c61b0d527ba61b91f1be97dd3ad.png'
    ];

    var imgWrap = [];

    function preloadImg(arr) {
        for(var i =0; i< arr.length ;i++) {
            imgWrap[i] = new Image();
            imgWrap[i].src = arr[i];
        }
    }

    preloadImg(imgSrcArr);

62. 	SSH:是安全外壳协议,专为远程登录会话和其他网络服务提供安全性的协议
	shell: 是一个用 C 语言编写的程序，既是一种命令语言，又是一种程序设计语言。
    	Xshell:Xshell是一个远程终端工具软件,支持ssh协议、SFTP、TELNET、RLOGIN和SERIAL，允许你远程访问,只是一个ssh连接工具

63. ceshi.html里面有一些内容，并且包含了一个iframe框架,在iframe框架里代码如下： 
	<script> window.top.close(); </script> 
	这段代码是关闭当前访问页面

64. letter-spacing 增加或减少字符间的空白（字符间距）。
	例：h1 {letter-spacing:2px}

65. $.isEmptyObject  jQuery的isEmptyObject方法判断对象/数组（也是对象）是否为空

66. $(function(){})和$(document).ready(function(){}) 的区别
	document.ready和onload的区别——JavaScript文档加载完成事件
	页面加载完成有两种事件
	一是ready，表示文档结构已经加载完成（不包含图片等非文字媒体文件）
	二是onload，指示页面包含图片等文件在内的所有元素都加载完成。

67. props如何传值给data
	在data里面设置的时候只能设置初始值，所以如果想要在[‘props’]值改变的时候跟着改变，可以watch一下，然后在watch里面做更新操作。
	[‘props’]值可以应用在data中、应用在模板中、可以应用在方法中。


























