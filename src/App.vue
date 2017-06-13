<template>
  <div>
    <v-header :seller="seller"></v-header>
    <div class="tab border-1px">
      <div class="tab-item">
        <a v-link="{path:'/goods'}">商品</a>
      </div>
      <div class="tab-item">
        <a v-link="{path:'/ratingMode'}">评论</a>
      </div>
      <div class="tab-item">
        <a v-link="{path:'/seller'}">商家</a>
      </div>
    </div>
    <router-view :seller="seller"></router-view>
  </div>
</template>

<script type="text/ecmascript-6">
  import header from 'components/header/header.vue';

  const ERR_OK = 0;

  export default {
    data() {
      return {
        seller: {}
      };
    },
    created() {
      this.$http.get('/api/seller').then((response) => {
        response = response.body;
        if(response.errno === ERR_OK ){
          this.seller = response.data;
//          console.log(this.seller);
        }
      });
    },
    components: {
      'v-header': header
    }
  };

</script>

<style type="text/css" rel="stylesheet">
/*#app {*/
  /*font-family: 'Avenir', Helvetica, Arial, sans-serif;*/
  /*-webkit-font-smoothing: antialiased;*/
  /*-moz-osx-font-smoothing: grayscale;*/
  /*text-align: center;*/
  /*color: #2c3e50;*/
  /*margin-top: 60px;*/
/*}*/

#app .tab{
	display: flex;
	width: 100%;
	height: 40px;
	line-height: 40px;
  border-bottom: 1px solid rgba(7,17,27,0.1);
}
#app .tab .tab-item{
	flex: 1;
	text-align: center;
}
#app .tab .tab-item > a{
  display: block;
  font-size: 14px;
  color: rgb(77, 85, 93);
}
#app .tab .tab-item > a.active{
  color: rgb(240, 20, 20);
}
</style>
