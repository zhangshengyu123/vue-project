<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <table align="center">
      <tr>
        <td style="width:100px"><span>用户名:</span></td>
        <td style="width:200px"> <input style="width:200px;height:30px" v-model="username" placeholder="root"></td>
      </tr>
      <tr>
        <td style="width:100px"><span>密码:</span></td>
        <td style="width:200px"><input style="width:200px;height:30px" v-model="pwd" placeholder="inspur_123"></td>
      </tr>
      <br/>
      <tr>
        <td colspan="2">
          <button v-on:click="login" style="width:330px;height:50px">登录</button>
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
  name: 'HelloWorld',
  data () {
    return {
      msg: '浪潮系统-VUE登录',
      username: "",
      pwd: ""
    }
  },
  methods:{
    login:function (){
      if(this.username != 'root' || this.pwd != 'inspur_123'){
        alert("您的用户名或者密码填写错误");
      }else{
        this.$router.push({name:'welcome',params:{username:this.username,pwd:this.pwd}});
      }
      
    }
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
