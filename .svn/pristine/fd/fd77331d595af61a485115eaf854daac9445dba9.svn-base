   /* 搜索  */
   function search(elem){
    	showclear(elem);
        if(userid)
        {
	        if(!locked)
	        {
	            locked=true;
	            setTimeout("sortlist()",200);
	            locked=false;
		    }	    
	    }
	     else
	    {
	        alert("请先登录！");
	    }
    }
    
    function sortlist(){
   		var key=document.getElementById("search").value;
        var temp = document.getElementById('sort');
        pageNum=1;
    	oWrapper.innerHTML="";
        getlist(false);
    }
    
    /* 渲染 */
    function xuanran(idname,arrlist){
        var temp=document.getElementById(idname);
	    var resultData ={dataList: arrlist};
	    juicer.register('tocomment',tocomment);
        juicer.register('totime',totime);
        juicer.register('ctocusType',ctocusType);
        juicer.register('tostring',tostring);
	    var result = juicer(temp.innerHTML, resultData);
	    oWrapper.innerHTML += result;
    }
    
    
    /* juicer 绑定函数  */
    function tocomment(data){
    	return data||"";
    }
    
    
 	function tostring(data){
    	var s=data+'';
    	if(s.length==1)
    		s="000"+s;
    	else if(s.length==2)
    		s="00"+s;
    	else if(s.length==3)
    		s="0"+s;
    	return s;
    }
    
    function totime(data){
        var time=new Date(data);
        return time.getFullYear()+"-"+parseInt(time.getMonth()+1)+"-"+time.getDate();
    }
    
    //客户类型
    //0无效客户1一般客户2优质客3水客4黑客
    var cusTypelist=["无效客户","一般客户","优质客","水客","黑客"];
    function ctocusType(data){
    	return cusTypelist[data];
    }
    
