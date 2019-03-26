<template>
  <div class="hello">
    <input type="text" v-model.trim="msg" @keyup.enter="clif"></input>
    <h1>{{ msg }}</h1>
    <h1>{{ dd }}</h1>
    <h1 :class="{active : isactive}">{{ da }}</h1>
    <router-link to="/test/5555"><h1>{{ aaa }}</h1></router-link>
    <Child :age="age" @pamethod="showmsg"></Child>
  </div>
</template>

<script>

  import Child from './Child'

export default{
  name: 'HelloWorld',
  components:{Child},
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      da: '111111111',
      isactive: false,
      age: 122200
    }
  },
  methods: {
    clif(){
      console.log(this.msg);
      this.isactive = true;
    },
    showmsg(v){
      console.log(v);
      this.age = v;
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
    },
    dd(){
      return this.$store.state.count
    }
  },
  mounted: function(){
    this.$nextTick(function () {
      let i = 0
      setInterval(() => {
        //this.$store.commit('updateCount', i++)
      })
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
