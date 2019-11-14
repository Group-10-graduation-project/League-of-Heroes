<template>
  <div>
    <input type="radio" id="runoob" value="Runoob" v-model="picked" />
    <label for="runoob">自选模式</label>
    <br />
    <input type="radio" id="google" value="Google" v-model="picked" />
    <label for="google">排位赛 单排/双排</label>
    <br />
    <input type="radio" id="googles" value="Googles" v-model="picked" />
    <label for="googles">排位赛 灵活排位</label>
    <br />
    <nav>
      
      <button :to="'test'" class="butts" >
        <img src="..//assets/quxiao.png" />
        
      </button>
      <button class="butt">确认</button>
    </nav>
  </div>
</template>

<script>
export default {
  data() {
    return {
      picked: "Runoob"
    };
  }
};
</script>

<style>
nav{

  
  float: left;
  margin: 50px 0px 0px -0px;
}
.butt {
  width: 150px;
  height: 30px;
}
.butts {
  width: 40px;
  height: 30px;
}
.butts img {
  width: 100%;
  height: 100%;
}
button{
 /* width: 58px;
  text-decoration: none;
  background-color: none; */
  color: #FFFFFF;
  /* border-right: 3px solid rgb(13, 45, 190); */
   background-color: rgb(43, 41, 41);
  border-right: 1px solid rgb(13, 45, 190);
  border-left-style: none;
  border-bottom-style: none;
  border-top-style: none;}
</style>