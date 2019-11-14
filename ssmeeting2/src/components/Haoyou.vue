<template>
  <div class="ly" style="float:left;">
    <!-- 搜索框加按钮 -->
    <input
      style="float:left;margin:0px -0px -0px 29px;"
      placeholder="搜索好友"
      prefix-icon="el-icon-search"
      v-model="keyword"
    />
    <button class="searchbtn" @click="search">搜索</button>
    <!-- 数据 -->
    <ul>
      <li v-for="(item,index) in agentlisttwo" :key="item.id">
        <img v-bind:src="item.image" />
        <p>
          {{item.username}}
          <!--<p>{{item.userID}}</p>
          <p>{{item.agentnum}}</p>
          </p>-->
        </p>
        <p>{{item.phone}}</p>
      </li>
    </ul>
  </div>
</template>
 
 <script>
export default {
  data() {
    return {
      keyword: "", //搜索关键词
      agentlisttwo: "", //搜索重定义数组
      agentlist: [
        {
          image: require("../assets/Timg/pic3.png"),
          userID: "1240",
          agentnum: "22",
          username: "小张",
          phone: "1311278"
        },
        {
          image: require("../assets/Timg/pic3.png"),
          userID: "1240",
          agentnum: "22",
          username: "小张",
          phone: "1311278"
        },
        {
          image: require("../assets/Timg/pic3.png"),
          userID: "1240",
          agentnum: "22",
          username: "小张",
          phone: "1311278"
        },
        {
          image: require("../assets/Timg/pic3.png"),
          userID: "1241",
          agentnum: "23",
          username: "老王",
          phone: "1315236"
        }
      ]
    };
  },

  // 创建完成时
  created() {
    //重定义数组
    this.agentlisttwo = this.agentlist;
  },

  methods: {
    search() {
      //搜索
      var keyword = this.keyword;
      if (keyword) {
        this.agentlisttwo = this.agentlist.filter(function(agentlist) {
          return Object.keys(agentlist).some(function(key) {
            return (
              String(agentlist[key])
                .toLowerCase()
                .indexOf(keyword) > -1
            );
          });
        });
      } else {
        this.agentlisttwo = this.agentlist;
      }
    }
  }
};
</script>
 
<style scoped>
input {
  text-decoration: none;
  background-color: none;
  color: #ffffff;
  /* border-right: 3px solid rgb(13, 45, 190); */
  background-color: rgb(59, 40, 128);
  border-right: 1px solid #FFFFFF(13, 45, 190);
  border-left-style: none;
  border-bottom-style: none;
  border-top-style: none;
}
button {
  text-decoration: none;
  background-color: none;
  color: #ffffff;
  /* border-right: 3px solid rgb(13, 45, 190); */
  background-color: rgb(59, 40, 128);
  border-right: 1px solid rgb(13, 45, 190);
  border-left-style: none;
  border-bottom-style: none;
  border-top-style: none;
}
li {
  clear: left;
  list-style-type: none;
}
li img {
  float: left;
  /* width: 100%;
  height: 100%; */
  width: 35px;
  height: 35px;
}
p {
  float: left;
  width: 50px;
  height: 30px;
  line-height: 30px;

  text-align: center;
}
.p1 {
  color: red;
}
</style>