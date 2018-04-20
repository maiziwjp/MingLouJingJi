 window.onload=function()
    {
      var oPicList=document.getElementById("picList");
      var aBtns=document.getElementById("picBtns").children;
      var iScroll=0;
      var iStartX=0;
      var iStartPageX=0;
      var iNow=0;
      var oTimer=0;
      oPicList.innerHTML+=oPicList.innerHTML;
      oPicList.style.width=oPicList.clientWidth*2+"px";
      function autoPlay()
      {
          oTimer=setInterval(function(){
              iNow++;
              next();
          },2000);
      }
      function next()
      {
          iScroll=-iNow*window.screen.width;
          //alert(iScroll);
          for(var i=0;i<aBtns.length;i++)
          {
              aBtns[i].className="";
          }
          aBtns[iNow%aBtns.length].className="active";
          if(iNow>=aBtns.length)
          {
              tweenMove(oPicList,{translateX:iScroll},300,"easeOut",function(){
                  iNow=iNow%aBtns.length;
                  iScroll=-iNow*window.screen.width;
                  css(oPicList, "translateX", iScroll);
              });
          }
          else
          {
              tweenMove(oPicList,{translateX:iScroll},500,"easeOut");
          }
      }
      autoPlay();
  };