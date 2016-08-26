<!DOCTYPE HTML>
<!--自动生成10个格子-->
<!--<html>
<head>
	<meta charset="utf-8" />
	<title></title>
	<style type="text/css">
		.div1{
			width: 30px;
			height: 30px;
			float: left;
			margin-right: 10px;
			border: 1px solid black;
			font: normal bold 18px "微软雅黑";
			text-align: center;
			line-height: 30px;
		}
		input{display: block;margin-bottom: 20px;}
	</style>
	<script type="text/javascript">
		window.onload=function () {
			var oBtn=document.getElementById("btn1");
			var aDiv=document.getElementsByTagName("div");
			var arr=['red','gold','blue','green','pink'];
			oBtn.onclick=function () {
				for(var i=0;i<10;i++){
					document.body.innerHTML+='<div class="div1">'+i+'</div>';					
					aDiv[i].style.backgroundColor=arr[i%arr.length];
				}
				
			}
		}
	</script>
</head>
<body>
	<input id="btn1" type="button" value="自动生成10个格子" />
</body>
</html>-->
	
<!--自动生成100个格子-->	
<!--<html>
<head>
	<meta charset="utf-8" />
	<title></title>
	<style type="text/css">
		.div1{
			width: 30px;
			height: 30px;
			float: left;
/*			margin: 5px;*/
			border: 1px solid black;
			font: normal bold 18px "微软雅黑";
			text-align: center;
			line-height: 30px;
			position: absolute;		/*给格子定位*/
		}
		input{display: block;margin-bottom: 20px;}
	</style>
	<script type="text/javascript">
		window.onload=function () {
			var oBtn=document.getElementById("btn1");
			var aDiv=document.getElementsByTagName("div");
			var arr=['red','gold','blue','green','pink','greenyellow','blueviolet'];
			var str='';
			oBtn.onclick=function () {
				for(var i=0;i<100;i++){	
					//此处不能用str代替document.body.innerHTML，会出现style未定义的情况
					document.body.innerHTML+='<div class="div1">'+i+'</div>';
					aDiv[i].style.backgroundColor=arr[i%arr.length];				
					aDiv[i].style.top=50+(Math.floor(i/10))*40+'px';
					aDiv[i].style.left=50+(i%10)*40+'px';
				}
//				document.body.innerHTML=str;

			/*	方法二（先结构，再样式）
				for(var i=0;i<100;i++){	
					str+='<div class="div1">'+i+'</div>';					
				}
				document.body.innerHTML+=str;
				for(var i=0;i<100;i++){
					aDiv[i].style.backgroundColor=arr[i%arr.length];				
					aDiv[i].style.top=60+(Math.floor(i/10))*40+'px';
					aDiv[i].style.left=60+(i%10)*40+'px';
				} 
			*/
			}
		}
	</script>
</head>
<body>
	<input id="btn1" type="button" value="自动生成100个格子" />
</body>
</html>-->

<!--自动生成一个V字形格子阵-->
<!--<html>
<head>
	<meta charset="utf-8" />
	<title></title>
	<style type="text/css">
		#btn{
			width: 130px;
			height: 30px;
			border: 1px solid grey;
			border-radius: 5px;
			margin-bottom: 20px;
		}
		.div1{
			width: 50px;
			height: 50px;
			background: red;
			text-align: center;
			line-height: 50px;
			color: white;
			position: absolute;
		}
	</style>
	<script type="text/javascript">
		window.onload=function () {
			var oBtn=document.getElementById("btn");
			var aDiv=document.getElementsByTagName("div");
			oBtn.onclick=function () {
				for (var i=0;i<5;i++) {
					document.body.innerHTML+='<div class="div1">'+i+'</div>';				
				}
				for (var i=0;i<3;i++) {
					aDiv[i].style.top=50+50*i+'px';
					aDiv[i].style.left=10+50*i+'px';
				}
				for (var i=3;i<5;i++) {
					aDiv[i].style.top=(parseInt(aDiv[2].style.top)-50*(i-2))+'px';
					aDiv[i].style.left=(parseInt(aDiv[2].style.left)+50*(i-2))+'px';
				}
			}
		}
	</script>
</head>
<body>
	<input id="btn" type="button" value="自动生成一个V字形" />
</body>
</html>-->

<!--自动生成一个V字形格子阵(升级版)-->
<html>
<head>
	<meta charset="utf-8" />
	<title></title>
	<style type="text/css">
		#btn{
			width: 130px;
			height: 30px;
			border: 1px solid grey;
			border-radius: 5px;
			margin-bottom: 10px;
		}
		#div_l{
			width: 250px;
			height: 250px;
			background: gainsboro;
			position: relative;
		}
		.div1{
			width: 50px;
			height: 50px;
			background: red;
			text-align: center;
			line-height: 50px;
			color: white;
			position: absolute;
		}
	</style>
	<script type="text/javascript">
		window.onload=function () {
			var oBtn=document.getElementById("btn");
			var oDivL=document.getElementById("div_l");	
			var aDiv=oDivL.getElementsByTagName("div");		//红格子处在大的DIV里面，所以要用oDivL
			var j=0;
			var str='';
			function fn1 () {				
				for (var i=0;i<3;i++) {
					aDiv[i].style.top=100-50*i+'px';
					aDiv[i].style.left=0+50*i+'px';
				}
				for (var i=3;i<5;i++) {
					aDiv[i].style.top=(parseInt(aDiv[2].style.top)+50*(i-2))+'px';
					aDiv[i].style.left=(parseInt(aDiv[2].style.left)+50*(i-2))+'px';
				}
			}
			function fn2 () {
				for (var i=0;i<3;i++) {
					aDiv[i].style.top=0+50*i+'px';
					aDiv[i].style.left=0+50*i+'px';
				}
				for (var i=3;i<5;i++) {
					aDiv[i].style.top=(parseInt(aDiv[2].style.top)+50*(i-2))+'px';
					aDiv[i].style.left=(parseInt(aDiv[2].style.left)-50*(i-2))+'px';
				}
			}
			function fn3 () {
				for (var i=0;i<3;i++) {
					aDiv[i].style.top=0+50*i+'px';
					aDiv[i].style.left=0+50*i+'px';
				}
				for (var i=3;i<5;i++) {
					aDiv[i].style.top=(parseInt(aDiv[2].style.top)-50*(i-2))+'px';
					aDiv[i].style.left=(parseInt(aDiv[2].style.left)+50*(i-2))+'px';
				}
			}
			function fn4 () {
				for (var i=0;i<3;i++) {
					aDiv[i].style.top=0+50*i+'px';
					aDiv[i].style.left=100-50*i+'px';
				}
				for (var i=3;i<5;i++) {
					aDiv[i].style.top=(parseInt(aDiv[2].style.top)+50*(i-2))+'px';
					aDiv[i].style.left=(parseInt(aDiv[2].style.left)+50*(i-2))+'px';
				}
			}	
			oBtn.onclick=function() {
				j++;
				oDivL.innerHTML='';		//再次点击的时候，要把oDivL.innerHTML先清空，并且str的值也清空，否则会出现div特别多的问题
				str='';
				for (var i=0;i<5;i++) {		//先输出格子，再调整布局
					str+='<div class="div1">'+i+'</div>';	
					oDivL.innerHTML=str;
				}
				/*	
					一次性直接写入页面，性能更优；
					不要直接往document.body上写，在页面上放一个div，往div里面添加元素,
					DOM已经生成了,事件绑定已经无效了;
				*/
				switch(j){			
					case 1:fn1();break;
					case 2:fn2();break;
					case 3:fn3();break;
					case 4:fn4();break;
				}
				if(j==4){j=0;}
			}			
		}		
	</script>
</head>
<body>
	<input id="btn" type="button" value="自动生成一个V字形" />
	<div id="div_l"></div>
</body>
</html>



