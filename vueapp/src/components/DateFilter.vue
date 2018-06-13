<template>
    <div id="app">
        <h2 >{{date|formateDate}}</h2>
      <ul>
        <li v-for="(nn,index) in 10">hi{{index}}</li>
      </ul>
    </div>
</template>

<script type="es6">
var padDate=function(value){
 return value<10 ? '0'+value:value;
}
export default {
  name: 'DateFilter',
  data(){
    return {
        date : new Date()
    };

  },
  filters:{
    formateDate:function(value){
        var tdate=new Date(value);
        var year = tdate.getFullYear();
        var month = padDate(tdate.getMonth()+1);
        var day = padDate(tdate.getDate());
        var hours = padDate(tdate.getHours());
        var minutes = padDate(tdate.getMinutes());
        var seconds = padDate(tdate.getSeconds());
        return year+'-'+month+'-'+day+' '+hours+':'+minutes+':'+seconds;
    }
  },
  mounted:function(){
      var _this=this;

      this.timer= setInterval(function(){
        _this.date=new Date();
      },1000);
  },
  beforeDestory:function(){
    if(this.timer){
        clearInterval(this.timer);
    }
  }


}

</script>

<style >
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>
