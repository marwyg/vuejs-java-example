<template>
  <div style="height: 100%;">
    <Header/>

    <video-player :options="videoOptions"/>

  </div>
</template>

<script>
import Header from './Header.vue'
import VideoPlayer from "@/components/VideoPlayer";

export default {
  name: 'Dashboard',
  components: {
    Header,
    VideoPlayer
  },
  data() {
    return {
      videoOptions: {
        inactivityTimeout: 0,
        controlBar: {
          volumePanel: {inline: false}
        },
        autoplay: true,
        controls: true,
        sources: [
          {
            src:
                "/city.mp4",
            type: "video/mp4"
          }
        ]
      }
    }
  },
  methods: {
    /*getAllUsers() {
      getAllUsers().then(response => {
        console.log(response)
        this.users = response
        this.numberOfUsers = this.users.length
      })
    },
    userCreate(data) {
      console.log('data:::', data)
      data.id = this.numberOfUsers + 1
      createUser(data).then(response => {
        console.log(response);
        this.getAllUsers();
      });
    }*/
  },
  /*mounted () {
    this.getAllUsers();
  }*/
}
</script>