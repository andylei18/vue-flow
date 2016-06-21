<template>
  <div class="line">

  </div>
</template>

<script>

  import '../assets/line.js'

  export default {
      props :['line'],
      ready (){
        const self = this
        const Boxmodel = this.line.model
        Boxmodel.forEach(model => {
          let boxID = model.id
          let nextID = model.next
          let boxDivStar = document.getElementById(boxID)
          nextID.forEach(nextChild => {
            let boxDivEnd = document.getElementById(nextChild)
            self.drawLine(boxDivStar,boxDivEnd)
          })
        })
      },
      methods :{
        drawLine (star,end){
          const flowNode = this.$parent.$els.flow
          const flowseLeft = flowNode.offsetLeft
          const flowseTop = flowNode.offsetTop

          const draw = new jsGraphics(this.line.type)

          console.log(draw)
        }
      }
  }
</script>
