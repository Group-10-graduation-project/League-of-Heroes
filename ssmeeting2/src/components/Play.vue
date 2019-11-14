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
        style
      >
        <img v-bind:src="item.image" style />
        <p>{{item.names}}</p>
        <h1>{{item.name}}</h1>
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
          
            image: require("../assets/play/pic.png"),
            names: "5V5",

            name: "召唤师峡谷"
          },
          {
            id: 1,
             image: require("../assets/play/pic1.png"),
            names: "5V5",

            name: "扭曲丛林"
          },
          {
            id: 2,
             image: require("../assets/play/pic2.png"),
            names: "5V5",

            name: "极地大乱斗"
          },
          {
            id: 3,
            image: require("../assets/play/pic3.png"),
            names: "5V5",
            name: "云顶"
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
.header a img {
  width: 135px;
  height: 135px;
  display: block;
  margin: 0 auto;
}
.header a {
  float: left;
  width: 135px;
  height: 90px;
  margin: 70px 1px 0px 40px;
  text-align: center;
  text-decoration:none;
  color: #FFFFFF;
}

.header a h1 {
  font-size: 22px;
}
</style>  