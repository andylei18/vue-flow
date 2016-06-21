<template>
  <div class="box" v-for="item in box.newmodel"
      <span>{{item.text}}</span>
  </div>
</template>

<script>
  export default {
    props: ['box'],
    created (){
      var self = this,
          rootID = getRootID(),
          node = self.$els.flow,
          myObjectList = self.createObjectList(rootID,0)

      //构建工作流程图的撒打算的撒打算的
      self.drawDiv(myObjectList,node,0,0,1000)

      function getRootID() {
        for(var i in self.model){
          if(self.model[i].begin){
            rootID = self.model[i].id
          }
        }
        return rootID;
      }
    }
  }
</script>
