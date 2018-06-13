<template>
  <div>
    <!--获取值-->
      <h1 class="test">hello world</h1>
      <h2 class="test">{{des}}</h2>
      <h3 class="test">{{user.name}}</h3>
      <p class="test" v-text="user.email"></p>
    <!--v-if指令-->
    <h3 class="test" v-if="showName">1{{user.name}}</h3>
    <!--v-else指令-->
    <h3 class="test" v-else="showName">{{user.name}}</h3>
    <!--v-for指令-->
    <ul>
      <li v-for="user in users" class="li">姓名：{{user.name}} 邮箱：{{user.email}}</li>
    </ul>
    <!--v-on指令  事件-->
    <button v-on:click="cliOk">ok</button>
    <!--键盘事件-->
    <input type="input" placeholder="请输入" v-on:keyup="keyup" v-on:keyup.enter.alt="enterHit"/>
    <!--computed 属性-->
    <hr>
    <label>firstname</label>
    <input placeholder="first name" v-model="user1.firstname">
    <br>
    <label>lastname</label>
    <input placeholder="first name" v-model="user1.lastname">
    <h3 class="test">{{fullname}}</h3>
    <!--props属性-->
    <h3 class="test">{{msg}}</h3>
  </div>
</template>
<script type="text/ecmascript-6">
  export default {
    name:"test",
    props:{
      msg:{
          type:String,
          default:"默认就是这些文字啊！"
      }
    },
    data(){
      return {
      des:"描述",
      user:{name:"张三",email:"zhang@qq.com"},
      user1:{firstname:"张三",lastname:"zhang@qq.com"},
      showName:true,
      users:[{name:"张三",email:"zhang@qq.com"},{name:"李四",email:"li@qq.com"}]
      };
    },
    methods:{
       cliOk:function(){
         alert("helllo");
       },
       keyup:function(){
         console.log("empress!!");
       },
       enterHit:function(){
         console.log("empress enter alt!!");
       },
    },
    computed:{
      fullname:function(){
         return this.user1.firstname+""+this.user1.lastname;
      }
    }
  }
</script>
<style>
  .test{
    color: red;
  }
  .li {list-style-type:none;}
</style>
