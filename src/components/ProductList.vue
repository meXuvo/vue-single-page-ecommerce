<template>
  <div>
    <div v-for="(name,index) in info" :key="index">
      <span @click="displayName(name.name)" style="user-select: none">{{name.name}}</span>
    </div>
  </div>

</template>

<script>
export default {
  name: "ProductList.vue",
  props:['info'],
  methods:{
    displayName(name){
      this.$emit('showName',name)
    }
  }

}
</script>

<style scoped>

</style>
