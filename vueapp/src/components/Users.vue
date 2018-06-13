<template>
  <div>
    <!--获取值-->
    <h1 class="test">users demo</h1>
    <!--computed 属性-->
    <hr>
    <label>添加用户数据</label><br>
    <form v-on:submit="addUser">
      <input type="text" placeholder="enter name" v-model="newUser.name"/>
      <input type="text" placeholder="enter email" v-model="newUser.email"/>
      <input type="submit" value="submit"/>
    </form>
    <hr>
    <label>展示用户数据</label><br>
    <ul>
      <li class="li" v-for="user in users">
        <input type="checkbox" class="toggle" v-model="user.isDel"/>
        <span :class="{isDel:user.isDel}">
          name:{{user.name}}&nbsp;&nbsp;&nbsp;&nbsp;email:{{user.email}}&nbsp;&nbsp;&nbsp;&nbsp;<button class="test" v-on:click="delUser(user)">X</button>
        </span>

      </li>

    </ul>
  </div>
</template>
<script type="text/ecmascript-6">
  export default {
    name:"users",
    data(){
      return {
      newUser:{},
      users:[{name:"张三",email:"zhang@qq.com",isDel:false},{name:"李四",email:"li@qq.com",isDel:false}]
      };
    },
    methods:{
       addUser:function(e){
        this.users.push({name:this.newUser.name,email:this.newUser.email,isDel:false});
        e.preventDefault();
       },
       delUser:function(user){
            if(user.isDel){
              this.users.splice(this.users.indexOf(user),1);
            }else{
              alert("请先勾选你要删除的用户信息！");
            }

       }
    }
  }
</script>
<style>
  .test{
    color: red;
  }
  .li {list-style-type:none;}
  .isDel{
    text-decoration: line-through;
  }
</style>
