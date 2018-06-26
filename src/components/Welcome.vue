<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <table align="center">
      <tr>
        <td style="width:100px"><span>用户名:</span></td>
        <td style="width:200px"> <input style="width:200px;height:40px" v-model="username"></td>
      </tr>
      <tr>
        <td style="width:100px"><span>密码:</span></td>
        <td style="width:200px"><input style="width:200px;height:40px" v-model="pwd"></td>
      </tr>
      <br/>
      <tr>
        <td colspan="2">{{this.$route.params.username1}}
          <button v-on:click="back" style="width:300px;height:50px">返回</button>
        </td>
      </tr>
      <br/>
       <tr>
        <td>{{username}}</td>
        <td>{{pwd}}</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  name: 'Welcome',
  data () {
    return {
      msg: '恭喜你 登录成功',
      username: "",
      pwd: ""
    }
  },
  methods:{
    back:function (){
      this.$router.go(-1);
    }
  },

  created(){
      this.username =  this.$route.params.username;
      this.pwd = this.$route.params.pwd;
      this.msg = '恭喜你 '+this.username+'登录成功';
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
