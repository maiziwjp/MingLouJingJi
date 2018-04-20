    function addClipboardListener(elem){
	    elem.addEventListener('touchstart', function(ev) {
	        timeout = setTimeout(function(){clipboardshow(ev.target,ev.touches[0]);addCopyPasteListener(ev.target)}, 800);
	        }, false);
	    elem.addEventListener('touchend', function(ev) {
	        clearTimeout(timeout);
	        }, false);
	   if(document.addEventListener)
		    document.addEventListener("click",cbhide,false);
		//兼容IE
		if(document.attachEvent)
		    document.attachEvent("onclick",cbhide);
	}
	
	function addCopyPasteListener(elem){
		var cb=document.getElementById("clipboard");
	    var copybtn=cb.getElementsByTagName("button")[0];
	    if(copybtn.addEventListener)
		    copybtn.addEventListener("click",function(){copy(elem)},false);
		//兼容IE
		if(copybtn.attachEvent)
		    copybtn.attachEvent("onclick",function(){copy(elem)});
		if(cb.getElementsByTagName("button").length>1)
		{
			var pastebtn=cb.getElementsByTagName("button")[1];
			if(pastebtn.addEventListener)
			    pastebtn.addEventListener("click",function(){paste(elem)},false);
			//兼容IE
			if(pastebtn.attachEvent)
			    pastebtn.attachEvent("onclick",function(){paste(elem)});
		}
	}
	
	function cbhide(){
	    var cb=document.getElementById("clipboard");
	    cb.style.display="none";
	}
	
	function clipboardshow(elem,touch){
	   var cb=document.getElementById("clipboard");
	   cb.style.display="inline-block";
	   var ch=cb.scrollHeight;
	   var cw=cb.scrollWidth;
	   var ew=elem.scrollWidth;
	   var offset=elem.getBoundingClientRect();
	   cb.style.left=parseInt(offset.left+(ew-cw)/2)+"px";
	   cb.style.top=parseInt(touch.pageY-ch)+"px"; 
	}
	
	function copy(elem){
	    var val;
	    if(elem.tagName=="INPUT")
	        val=elem.value;
	    else
	        val=elem.innerHTML;
		clipBoard.set({
		    value: val 
		}, function(ret, err) {
		    if (ret) {
		        api.toast({
	                msg:'复制成功',
	                location:'top'
                });
		    } else {
		       api.toast({
	                msg:JSON.stringify(err),
	                location:'top'
                });
		    }
		});
	}
	
	function paste(elem){
	    clipBoard.get(function(ret, err) {
		    if (ret) {
		         if(elem.tagName=="INPUT")
			        elem.value=ret.value;
			     else
			        elem.innerHTML=ret.value;
			     
		    } else {
		          api.toast({
	                msg:JSON.stringify(err),
	                location:'top'
                  });
		    }
		});
	}