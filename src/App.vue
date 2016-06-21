<style src="./assets/flow.css"></style>

<template>
  <div id="mmp">
    <div id="flow" v-el:flow>
      <box-module :box="box"></box-module>
      <line-module :line="box"></line-module>
    </div>
  </div>
</template>

<script>

  import BoxModule from './components/box'
  import LineModule from './components/line'

  export default {
    components: {
      BoxModule,
      LineModule
    },
    data (){
      return {
        box:{
          model:[
            {"id":"1","text":"时间","next":["2"],"begin":true,"left":"0"},
            {"id":"2","text":"筛选1","next":["3"],"begin":false,"left":"150"}
              // {"id":"1","text":"时间","next":["2","3","11"],"begin":true},
              // {"id":"2","text":"筛选1","next":["4"],"begin":false},
              // {"id":"3","text":"筛选2","next":["5"],"begin":false},
              // {"id":"4","text":"筛选3","next":["6"],"begin":false},
              // {"id":"5","text":"筛选4","next":["7","8"],"begin":false},
              // {"id":"6","text":"筛选5","next":["9"],"begin":false},
              // {"id":"7","text":"筛选6","next":["10","11"],"begin":false},
              // {"id":"8","text":"筛选7","next":["12"],"begin":false},
              // {"id":"9","text":"筛选8","next":["12"],"begin":false},
              // {"id":"10","text":"筛选9","next":["-1"],"begin":false},
          ],
          newmodel:[],
          type:'draw',
          width:"100"
        }
      }
    }
  }
</script>
