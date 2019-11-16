<template>
  <div class="container">
    <div class="header">
      <a
        href="#"
        class="title"
        :class="index === active? 'active' : ''"
        v-for="(item, index) in tabList"
        :key="index"
        @click="open(item.id)"
        style=" background-image: url(assets/pj.gif); "
      
      >
        <h1>{{item.name}}</h1>
        <p>{{item.names}}</p>
        <img v-bind:src="item.image" style />
      </a>
    </div>

    <div class="content">
      <div class="wrap">
        <slot :name="active"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "tab-content",
  data() {
    return {
      active: 0,
      tabList: this.list,
      runfn: this.fnoptions
    };
  },
  components: {
    // ScrollComponent
  },
  props: {
    list: {
      type: Array,
      default() {
        return [
          {
            id: 0,
            image: require("../assets/Timg/pic1.png"),
            names: "无",

            name: "单人/双人"
          },
          {
            id: 1,
            image: require("../assets/Timg/pic2.png"),
            names: "1级",

            name: "荣誉"
          },
          {
            id: 2,
            image: require("../assets/Timg/pic3.png"),
            names: "500",

            name: "成就积分"
          },
          {
            id: 3,
            image: require("../assets/Timg/pic4.png"),
            names: "无",
            name: "奖杯"
          },
          {
            id: 0,
            image: require("../assets/Timg/pic5.png"),

            names: "无",

            name: "旗帜"
          }
        ];
      }
    },
    fnoptions: {
      type: Array,
      default() {
        return [];
      }
    }
  },
  methods: {
    open(id) {
      this.active = id;
      if (this.runfn[id]) {
        this.runfn[id].runFn();
      }
    }
  }
};
</script>
<style scoped>
template {
  background: url(https://ol.3dmgame.com/uploads/images/raiders/20191016/1571192527_531866.png)
    repeat;
    
}
.header a img {
  
  width: 100%;
  height: 100%;
  display: block;
  margin: 0 auto;
}
.header a {
  
  float: left;
  width: 100px;
  height: 90px;
  margin: 290px 1px 0px 30px;
  text-align: center;
  text-decoration: none;
  color: #FFFFFF;
}
.header a h1 {
  font-size: 22px;
}
a:hover,a:active {font-size:150%;}
</style>  