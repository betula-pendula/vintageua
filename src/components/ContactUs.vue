<template>
  <div>
    <div v-for="(item, index) in items" :key="index">{{ item }}</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      items: [
        'aaa', 'sss', 'ssss', 'dddd'
      ]
    }
  },
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>