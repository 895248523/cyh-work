###DOM             
#####一 .DOM中获取元素常用的方法：        

	1.document.getElementById();  //利用id的属性值获取   
	2.document.getElementsByTagName();  //利用标签名来获取元素
	3.document.getElementsByClassName(); //用类名获取元素
	4.document.getEelmentsByName();//用name属性获取元素
	5.document.querySelector();//用css选择器获取元素
	6.document.querySelectorAll();//用css选择器获取元素
	两种用css选择器获取元素的方法不同点:       
		第一种:只能找到元素列表中的第一个元素,  
		第二种:可以找到元素列表中全部的元素.  
#####二.DOM中获取和设置元素里面的其他信息          

	1.获取元素名:元素.TagName();  注意:此方法只能获取,不能设置  
	2.获取元素节点的内容:元素.innerHTML;     
	3.获取元素节点的文本:元素.innerText; 此方法可以获取 也可以设置文本内容.     
	4.获取元素的类名:元素.className;  注意:返回的是一个字符串,如果更换一个类的话,需要考虑该类名中的其他类名一起设置.     
	5.获取元素样式：元素style.样式属性名=“属性值”   
		注意：以js形式增加的样式的优先级大于css优先级 因为js拿到的是内联样式中的属性。   
	6.	获取元素属性：getAttribute(“属性“);
	  
	设置元素属性：setAttribute(“属性”,”属性值”);		
	删除元素属性：removeAttribute(“需要删除的属性”)；
 
#####三：查找元素        

	插入元素：元素.appenChild(创建好的文本或者元素);   
	  
	1.	创建元素节点：document.createElement(“元素名“);       
	注意：需要将创建好的元素插入到需要的元素中去.     
	2.	创建文本节点：document.createTextNode(“一段文字”)；   
	注意：需要将创建好的文本插入到需要的元素中去.     
	3.	Css样式赋予：元素.style.cssText;    
	例如：div.style.cssText=”width:100px;height:100px;”;   
	可以直接多条样式赋予       
	4.	在某个元素前，插入创建的新元素：insertBefore(“参数1”,“参数2”)；   
	参数1：需要插入的元素   参数2：是将元素插入到指定元素的前面  
	与appenChild用法基本一样，但是insertBefore可以选择将元素插入到指定元素的前面   


#####四：删除和替换元素              

	1.	元素的替换：元素.replaceChild();  该方法有两个参数;         
	参数1：将要替换的新元素 参数2：被替换的旧元素 逗号分割      
	2：元素的删除：父元素.removeChild(“需要删除的元素”):        
 
#####五：元素查找(node)        

	1：node节点的属性：nodeName，nodeType，nodeValue;        
	2：获取所有的子节点：childNodes;  所有的子节点不止包含元素.        
	3：获取第一个和最后一个子节点：                   
		获取第一个子节点：firstChild;  注意：不止包含元素             
		获取最后一个子节点：lastChild; 注意：不止包含元素            
	4：获取父元素：parentNode 注意：父节点只有一个        
	5.：获取兄弟节点：      
	
	获取第一个兄弟节点：proviousSibling    
	获取最后一个兄弟节点:nextSibling      
	注意：只能获取一个       
	
#####六：元素的宽高属性             
	1：获取元素的宽：             
	
			元素.style：只能获取内联样式。           
			元素.offsetWidth ：获取元素的宽，也包含了内边距和边框     
			元素.clientWidth：获取元素的宽，不包含边框        
			
2.	获取元素的高:           

	元素.offsetHeight ：获取元素的高，也包含了内边距和边框        
	元素.clientHeight：获取元素的高，不包含边框         
	
3.	子元素与父元素的距离        
             
	元素.offsetLeft：获取当前元素距离body左边界的距离                   
	元素.offsetTop：获取当前元素距离body上边界的距离                  
	注意：如果该元素使用了定位属性，这时就是距离它最近的父元素的距离         
	     
DOM事件            
一：鼠标键盘事件            

		1）	鼠标事件      
		a)	点击事件：元素.onclick         
		b)	双击事件：元素.ondblclick               
		c)	鼠标按下事件：元素.onmousedown;            
		d)	鼠标抬起事件：元素.onmouseup           
		e)	1.鼠标移入事件：元素.onmouseover           
		f)	鼠标移出事件：元素.onmouseout           
		g)	2.鼠标移入事件：元素.onmouseenter                    
		h)	鼠标移出事件：元素onmouseleava           
		第一套鼠标移入事件与第二套鼠标移入事件的区别             
		第一套会多次触发       第二套只能触发一次        

2）	键盘事件         
使用键盘事件时 触发事件时需要传入一个e参数代表哪个事件触发的

	a)	按下事件：元素.onkeydown
	b)	抬起事件：元素.onkeyup

二：Event事件对象            
1）	通过事件触发的函数,以参数的形式传入该函数内部.Event对象是事件触发时,调用函数时的第一个参数
2）	event对象的常见属性

	a)	鼠标的坐标值：clientX和clientY
	b)	键盘的值：keyCode
	
3）	Event的兼容性       

	a)	非IE：event 
	b)	IE：window.event

三：对象事件

	1）	Window.onload页面加载完毕之后才执行函数的内容
	2）	Window.onresize监听页面窗口大小 ,只要页面变化就触发该事件
	
四：表单事件

	1）	元素.onfocus 获取焦点
	2）	元素.onblur  失去焦点
	3）	元素.onchange 用户输入时触发
	4）	元素.oninput  内容改变时触发

五：事件绑定 / 事件监听          
1）	事件绑定          

	元素.onclick=function(){}
	a)	事件解绑:元素.onclick=null;
	
2）	事件监听         
监听事件有兼容性问题          

	a)	监听器：addEventListener(监听事件,方法,冒泡),
	i.	监听事件不需要加on 
	ii.	冒泡默认false
	b）IE监听器：attachEvent(监听事件,方法);
	i.   监听事件需要加on
			
