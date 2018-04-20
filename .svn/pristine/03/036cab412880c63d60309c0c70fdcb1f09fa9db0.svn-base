/* 清除按钮function  */
function clearinfo(elem){
    elem.previousElementSibling.value="";
    elem.style.display="none";
}
    
function showclear(elem){
    if(elem.value!="")
    {
        elem.nextElementSibling.style.display="inline-block";
    }
    else
    {
        elem.nextElementSibling.style.display="none";
    }
}
/* 密码可见按钮function  */
function changeDisplay(){
	var elem=document.getElementById("display");
	var pselem=document.getElementById("password");
	if(elem.className=="display icon hide")
	{
		elem.src="../icon/visible.png";
		elem.className="display icon show";
		pselem.type="text";
	}
	else if(elem.className=="display icon show")
	{
		elem.src="../icon/invisible.png";
		elem.className="display icon hide";
		pselem.type="password";
	}
}
/* 进度条文字位置  */
function genStatus(id,grade){
	var statusList=document.getElementById(id).getElementsByClassName("name");
	var circleList=document.getElementById(id).getElementsByClassName("status");
	var barlength=document.getElementById(id).getElementsByClassName("status")[1].offsetWidth;
	var halfcirlen=document.getElementById(id).getElementsByClassName("circle")[0].offsetWidth/2;
	for(i=0;i<grade;i++)
	{
		statusList[i].className+=" active";
		console.log(statusList[i]);
		circleList[i].className+=" active";
	}
	for(i=0;i<statusList.length;i++)
	{
		statusList[i].style.left= (i*barlength+halfcirlen-statusList[i].offsetWidth/2)+"px";
		console.log(statusList[i].offsetWidth);
		console.log(statusList[i].style.left);
	}	
}