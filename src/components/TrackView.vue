<template>
  <div class="track-body" ref="maps">
    <div class="svg-layer">
      <svg ref="svglayer" :width="svgWidth" height="100%" :viewBox="'0 0 '+svgWidth+' 400'" preserveAspectRatio="xMidYMid meet">
        <defs>
          <filter id="f1" x="0" y="0" width="200%" height="200%">
            <feOffset result="offOut" in="SourceGraphic" dx="1" dy="1" />
            <feColorMatrix result="matrixOut" in="offOut" type="matrix"
            values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 .5 0" />
            <feGaussianBlur result="blurOut" in="matrixOut" stdDeviation="1" />
            <feBlend in="SourceGraphic" in2="blurOut" mode="normal" />
          </filter>
        </defs>
        <g ref="svgGroup" v-if="isPathShow" class="svg-path" fill="none" stroke="#e24533">
          <polyline v-for="item in mapList" :points="item.deviceCoords" :key="item.id"/>
          <polyline class="cross-path" v-for="(item,index) in mapList" :points="item.crossMapCoords" fill="none" stroke="#707070" :key="index" stroke-dasharray="5,5"/>
        </g>
        <circle class="runer" ref="runer" r="10"></circle>
      </svg>
    </div>
  </div>
  <div class="track-footer">
    抓拍图 | 
    缩略图
  </div>
  <div class="track-footer">
    抓拍图 | 
    缩略图
  </div>

</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';

@Options({
  props: {
    msg: String
  }
})
export default class TrackView extends Vue {
  msg!: string
  svgWidth = 400
  isPathShow = false
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<!-- <style scoped lang="scss">

</style> -->
