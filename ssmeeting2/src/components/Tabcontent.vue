<template>
  <div class="container" style="width:270px; height:180px; ">
    <div class="header" style="width:100%; display: table;">
      <button
        class="title"
        :class="index === active? 'active' : ''"
        v-for="(item, index) in tabList"
        :key="index"
        @click="open(item.id)"
        style="display: table-cell;text-align: center;"
      >
        {{item.name}}
      
    
       
      </button>
       
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
            name: "公告",
           
          },
          {
            id: 1,
            name: "赛事",
           
          },
          {
            id: 2,
            name: "攻略",
           
          },
          {
            id: 3,
            name: "社区",
          
           
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
.container{
 background-color: rgb(75, 68, 68);
}
button{
  width: 58px;
  text-decoration: none;
  background-color: none;
  color: #FFFFFF;
  /* border-right: 3px solid rgb(13, 45, 190); */
   background-color: rgb(43, 41, 41);
  border-right: 1px solid rgb(13, 45, 190);
  border-left-style: none;
  border-bottom-style: none;
  border-top-style: none;
  
}

</style>  