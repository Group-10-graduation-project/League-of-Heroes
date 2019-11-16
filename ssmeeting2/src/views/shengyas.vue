<template>
  
     
      <shengya :list="elList" :fnoptions="optionsFn" style="float:left;	margin:0px 0px 0px -15px;">
    <div class slot="0"  >
      <the-all-game :list="gameAllList" >
        
      </the-all-game>
    </div>
    <div class slot="1">
      <the-collect :list="gameCollectList">
        
      </the-collect>
    </div>
  </shengya>
  

</template>

<script>
export default {

}
</script>

<style>

</style>