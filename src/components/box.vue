<template>
  <div class="box" v-for="item in box.model" :id="item.id" :style="{left: item.left,top: item.top}">
      <span>{{item.text}}</span>
  </div>
</template>

<script>
  export default {
    props: ['box'],
    created (){
      // const rootid=()=>{
      //   for(var i in this.box.model){
      //     if(this.box.model[i].begin){
      //       console.log(this.box.model[i].id)
      //       sid = this.box.model[i].id
      //     }
      //   }
      // }
      //
      // const node = this.$els.flow
      // const myObjectList = this.createModel(rootid,0)

      //构建工作流程图
      this.drawDiv()
    },
    methods :{
      //创建新的数组
      createModel (id,level){
        console.log(id)
      },
      //构建工作流程图
      drawDiv (){
        const self = this
        const flowNode = this.$els.flow
        const boxModel = self.box.model
        let firstModel = {
          id:"1",
          text:"时间",
          next:[],
          begin:true,
          top:0,
          left:0
        }

        if(boxModel.length==0){
          boxModel.push(firstModel)
        }else{

          // DOM 还没有更新
          this.$nextTick(function () {
            // DOM 现在更新了
            // `this` 绑定到当前实例
            let boxs = document.getElementsByClassName('box')
            
          })
        }
      }
    }
  }
</script>
