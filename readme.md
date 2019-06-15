```	
  function fly(element,duration,eal) {
		
		if (typeof element == 'string') element = document.querySelector(element)
		if (element[0]) element = element[0]
		gizmo = document.body

		//zoom out
		window.scrollTo(0,0); 
		gizmo.style['transform'] = ''
	
		if (gizmo.style['transition-duration'] == ''){
			gizmo.style['transition-duration'] = duration+'s'
			gizmo.style['transition-timing-function'] = 'ease-in'
			zoomin()
		}else{
			
			setTimeout(zoomin,(duration*1000)+500)
			//budge fix is adding 500ms delay
		}
		
		function zoomin(){
			var destination = element.getBoundingClientRect()

			var s = window.innerWidth/destination.width;
			var x = -destination.x
			var y = -destination.y

			gizmo.style['transform-origin'] = 0+'px '+0+'px';
			gizmo.style.transform = ' scale('+s+') translateX('+x+'px)  translateY('+y+'px)';
			console.log(s,x,y)
		}
		
	}

 fly('.xpdopen',1)
 ```
 
 
