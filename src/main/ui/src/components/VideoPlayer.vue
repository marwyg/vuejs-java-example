<template>

  <div class="video-container">
    <!--<video ref="videoPlayer" class="video-js vjs-theme-sea"/>-->
    <video
        ref="videoPlayer"
        class="video-js vjs-theme-sea"
        controls
        preload="auto"
        data-setup='{
          "fluid": true,
          "playbackRates": [0.25, 0.5, 1, 1.5, 2, 4, 10]
        }'/>
  </div>

</template>

<style>
@import 'https://vjs.zencdn.net/7.8.4/video-js.css';
@import './../assets/styles/myskin.css';
@import './../assets/styles/marker.css';
</style>

<script>

import videojs from 'video.js'
import markers from 'videojs-markers-plugin' // eslint-disable-line no-unused-vars

export default {
  name: "VideoPlayer",
  props: {
    options: {
      type: Object,
      default() {
        return {};
      }
    }
  },
  data() {
    return {
      player: null
    }
  },
  mounted() {
    this.player = videojs(this.$refs.videoPlayer, this.options, function onPlayerReady() {
      console.log('onPlayerReady', this);
    });
    //console.log(markers);
    this.player.markers({
      markers: [
        {time: 9.5, text: "this"},
        {time: 16,  text: "is"},
      ]
    });
  },
  beforeDestroy() {
    if (this.player) {
      this.player.dispose()
    }
  }
}
</script>