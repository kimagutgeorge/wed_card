<template>
  <div class="wrapper">
    <div class="image-holder">
      <img src="../../public/images/1.png" alt="">
    </div>
    <div class="image-holder w-100">
      <img src="../../public/images/2.png" alt="">
    </div>
    <div class="image-holder w-100">
      <img src="../../public/images/3.png" alt="">
    </div>
    <div class="image-holder w-100">
      <img src="../../public/images/4.png" alt="">
    </div>
  </div>
    
  
</template>

<script>
export default {
  name: 'HomePage'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
*{
  margin:0px !important;
  padding:0px !important;
}
.wrapper{
  width:100%;
}
.image-holder img{
  width:100% !important;}
.image-holder{
  width:100%;
  border-bottom: 4px solid #333;
}
.image-holder:last-child{
  border-bottom: 0px;
}

</style>
