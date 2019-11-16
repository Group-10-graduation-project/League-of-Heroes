
<template>
  <div class="index">
    <HelloWorld class="HelloWorld" :list="elList" :fnoptions="optionsFn" style="float:left;	margin:0px 0px 0px -15px; width:780px;">
      <div slot="0" class="HE">
        <the-all-game :list="gameAllList">
          <!-- <HelloWorldss></HelloWorldss> -->
              <Homepage></Homepage>
        </the-all-game>
      </div>
      <div class slot="-1">
        <the-collect :list="gameCollectList">
          <PLAyss></PLAyss>
        </the-collect>
      </div>
      <div class="" slot="1">
        <the-collect :list="gameCollectList">
          <shengyas class=""></shengyas>
        </the-collect>
      </div>
      <div class slot="2">
        <the-collect :list="gameCollectList">
          <index></index>
        </the-collect>
      </div>
    </HelloWorld>

    <HY style="   float: right;"></HY>
  </div>
</template>

<script>
//import MatchReportList from '../components/MatchReportList'

$(function() {
  $("div").each(function() {
    $(this).attr("the-all-game", "");
  });
});
</script>
<style scoped>
.index{

  background-color:#ffffff;
  border:1px solid black;
  opacity:0.9;
  filter:alpha(opacity=60); /* IE8 及更早版本 */
  
}
</style>