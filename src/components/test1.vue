<template>
    <div class="test">
        {{txt}}
    </div>
</template>
<script>
export default {
  name: "test1",
  data () {
    return {
        txt: "hello world"
    };
  },
  mounted() {
      setTimeout(() => {
        this.$data.txt = 'bye';
      },2000)
  },
}
</script>
<style lang="sass" scoped>
</style>