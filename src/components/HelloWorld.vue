<template>
  <h1>{{ msg }}</h1>
  <button @click="count++">count is: {{ count }}</button>
  <p>Edit22 <code>components/HelloWorld.vue</code> to test hot module replacement.</p>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
@Options({
  props: {
    msg: String
  }
})

export default class HelloWorld extends Vue {
  msg!: string
  // data() {
  //   return {
  //     count: 0
  //   }
  // }
}
</script>
<style scoped lang="scss">
h1 {
  color:green;
}

</style>