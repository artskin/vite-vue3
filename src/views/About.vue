<template>
  <div class="about">
    <h1>This is an about page</h1>
    <TrackView />
  </div>
</template>
<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import TrackView from '../components/TrackView.vue'; // @ is an alias to /src

@Options({
  components: {
    TrackView
  },
})
export default class About extends Vue {

}
</script>