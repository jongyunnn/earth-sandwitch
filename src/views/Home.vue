<template>
  <div class="home">
    <header class="header">
      <img src="/imgs/logo.png" alt="logo" />
    </header>
    <div class="img-top">
      <img src="/imgs/people-white.png" alt="album" />
    </div>
    <div class="icons__wrapper">
      <div class="icon" v-for="(icon, index) in icons" :key="index">
        <div class="icon-img">
          <img :src="icon.imgPath" :alt="icon.name" :style="icon.style" />
        </div>
        <span class="icon-name">{{ icon.name }}</span>
      </div>
    </div>
    <footer class="footer">
      <span>Copyright&copy; 2022. Earth Sandwitch. All rights reserved.</span>
    </footer>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "Home",
  data() {
    return {
      icons: [
        {
          name: "Apple Music",
          imgPath: "/imgs/apple.png",
          to: "",
          style: "transform: scale3d(0.9, 0.9, 0.9)",
        },
        {
          name: "Spotify",
          imgPath: "/imgs/spotify.png",
          to: "",
          style: "transform: scale3d(0.9, 0.9, 0.9)",
        },
        {
          name: "YouTube",
          imgPath: "/imgs/youtube.png",
          to: "",
          style: "transform: scale3d(0.9, 0.9, 0.9)",
        },
        {
          name: "YT Music",
          imgPath: "/imgs/ytmusic.png",
          to: "",
          style: "",
        },
        {
          name: "Melon",
          imgPath: "/imgs/melon.png",
          to: "",
          style: "",
        },
        {
          name: "Genie",
          imgPath: "/imgs/genie.png",
          to: "",
          style: "",
        },
        {
          name: "Bugs",
          imgPath: "/imgs/bugs.png",
          to: "",
          style: "transform: scale3d(0.9, 0.9, 0.9)",
        },
        {
          name: "Vibe",
          imgPath: "/imgs/vibe.png",
          to: "",
          style: "transform: scale3d(0.9, 0.9, 0.9)",
        },
        {
          name: "Flo",
          imgPath: "/imgs/flo.png",
          to: "",
          style: "transform: scale3d(0.9, 0.9, 0.9)",
        },
        {
          name: "SoundCloud",
          imgPath: "/imgs/soundcloud.png",
          to: "",
          style: "transform: scale3d(0.9, 0.9, 0.9)",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
* {
  box-sizing: border-box;
}
.home {
  width: 100%;
  max-width: 480px;
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  background-color: #fff;
  box-shadow: 4px 12px 20px 6px rgba(0, 0, 0, 0.18);
}
.header {
  width: 100%;
  max-width: 480px;
  color: #ffffff;
  background-color: #ffffff;
  z-index: 2;
  box-shadow: rgba(0, 0, 0, 0.12) 0 2px 16px 0;
  padding: 8px 0;
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  height: 60px;
  img {
    width: 65%;
  }
}
.img-top {
  padding-top: 60px;
  width: 100%;
  img {
    width: 100%;
  }
}
.icons__wrapper {
  padding: 32px 20px 40px;
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  gap: 24px;
  .icon {
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    align-items: center;
    width: 100%;
    height: 22vw;
    max-height: 120px;
    .icon-img {
      box-shadow: 4px 12px 30px 6px rgba(0, 0, 0, 0.09);
      border-radius: 16px;
      display: flex;
      justify-content: center;
      align-items: center;
      width: 100%;
      height: 20vw;
      max-height: 92px;
      img {
        width: 100%;
      }
    }
    .icon-name {
      margin-top: 8px;
      font-size: 10px;
      color: #121212;
    }
  }
}
.footer {
  display: flex;
  min-height: 120px;
  justify-content: center;
  align-items: center;
  background-color: #e2e2e2;
  color: #121212;
  font-size: 12px;
}
</style>
