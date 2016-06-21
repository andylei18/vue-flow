<template>
  <div class="line">

  </div>
</template>

<script>
  export default {
      props :['line'],
      compiled (){
        const Boxmodel = this.line.model
        Boxmodel.forEach(model => {
          let nextID = model.next
          console.log(nextID)
        })
      }
  }
</script>
