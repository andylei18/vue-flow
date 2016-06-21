<template>
  <div class="line">

  </div>
</template>

<script>

  export default {
      props :['line'],
      ready (){
        const self = this
        const Boxmodel = this.line.model
        self.$nextTick(function () {
          Boxmodel.forEach(model => {
            let boxID = model.id
            let nextID = model.next
            let boxDivStar = document.getElementById(boxID)
            nextID.forEach(nextChild => {
              let boxDivEnd = document.getElementById(nextChild)
              self.drawLine(boxDivStar,boxDivEnd)
            })
          })
        })

      },
      methods :{
        drawLine (start,end){
          
          const drawNode = this.$parent.$els.draw
          const drawseLeft = drawNode.offsetLeft
          const drawseTop = drawNode.offsetTop

          const x1 = start.offsetLeft- drawseLeft + 5 + 100
  				const x2 = start.drawseTop - drawseTop + 5 + 50
  				const y1 = end.offsetLeft - drawseLeft
  				const y2 = end.drawseTop - drawseTop + 5 + 50

          const draw = new jsGraphics(drawNode)
          draw.setStroke(2)
          // draw.drawLine(x1,x2,y1,y2)
					// draw.drawImage('../assets/right_sword.png',y1-5,y2-7,10,15)
        }
      }
  }
</script>
