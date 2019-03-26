<template>
  <div class="hello">
    <input type="text" v-model.trim="msg" @keyup.enter="clif"></input>
    <h1>{{ msg }}</h1>
    <h1 :class="{active : isactive}">{{ da }}</h1>
    <h1>{{ aaa }}</h1>
  </div>
</template>

<script>
export default{
  name: 'Test',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      da: '88888888888888',
      isactive: false
    }
  },
  methods: {
    clif(){
      console.log(this.msg);
      this.isactive = true;
    }
  },
  watch:{
    msg(newval, oldval){
      console.log(newval, oldval);
    }
  },
  computed: {
    aaa(){
      return this.msg + this.da;
    }
  },
  mounted: function(){
    this.$nextTick(function () {
      console.log(this.$route.params.id);
    })
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

.active{
  color: red;
}
</style>
