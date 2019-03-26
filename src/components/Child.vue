<template>
  <div id="child">
    {{age}}
    <button type="button" name="button" @click="$emit('pamethod', 100)">发送到父类</button>
  </div>
</template>

<script>
export default{
  name: 'Child',
  props:['age'],
  data () {
    return {

    }
  },
  methods: {

  }
}

</script>

<style scoped>

</style>
