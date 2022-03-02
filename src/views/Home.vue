<template>
  <div
    class="home"
    oncontextmenu="return false"
    onselectstart="return false"
    ondragstart="return false"
  >
    <header class="header">
      <img src="/imgs/logo.png" alt="logo" @click.stop="scrollTop" />
    </header>
    <main class="main__container">
      <div class="people__wrapper">
        <img
          :src="person.src"
          :alt="person.alt"
          v-for="(person, index) in people"
          :key="person.alt"
          @click.stop="onClick(index)"
        />
        <div class="people__skeleton" v-if="loading">
          <div
            class="skeleton"
            v-for="person in people"
            :key="person.alt"
          ></div>
        </div>
      </div>
      <div class="icons__wrapper">
        <div class="icon" v-for="(icon, index) in icons" :key="index">
          <a class="icon-img" :href="icon.to" target="_blank">
            <img :src="icon.imgPath" :alt="icon.name" :style="icon.style" />
          </a>
          <span class="icon-name">{{ icon.name }}</span>
        </div>
      </div>
    </main>
    <footer class="footer">
      <div class="sns__wrapper">
        <a
          href="https://www.youtube.com/channel/UCl6o-kqwVCKlSZVhQPWpsEg"
          target="_blank"
        >
          <img src="/imgs/sns/youtube-brands.svg" alt="ch-youtube" />
        </a>
        <a href="https://twitter.com/Earth__Sandwich" target="_blank">
          <img src="/imgs/sns/twitter-brands.svg" alt="ch-twitter" />
        </a>
        <!-- <a href="https://facebook.com" target="_blank">
          <img src="/imgs/sns/facebook-brands.svg" alt="ch-facebook" />
        </a> -->
        <a href="https://www.instagram.com/earthsandwich2020" target="_blank">
          <img src="/imgs/sns/instagram-brands.svg" alt="ch-instagram" />
        </a>
      </div>
      <span>Copyright&copy; 2022. Earth Sandwitch. All rights reserved.</span>
    </footer>
  </div>
</template>

<script>
import bus from "../utils/bus.js";
export default {
  name: "Home",
  data() {
    return {
      loading: true,
      clicked: false,
      ogPeople: [
        {
          src: "/imgs/people/1.jpg",
          alt: "p1",
        },
        {
          src: "/imgs/people/2.jpg",
          alt: "p2",
        },
        {
          src: "/imgs/people/3.jpg",
          alt: "p3",
        },
        {
          src: "/imgs/people/4.jpg",
          alt: "p4",
        },
        {
          src: "/imgs/people/5.jpg",
          alt: "p5",
        },
        {
          src: "/imgs/people/6.jpg",
          alt: "p6",
        },
        {
          src: "/imgs/people/7.jpg",
          alt: "p7",
        },
        {
          src: "/imgs/people/8.jpg",
          alt: "p8",
        },
        {
          src: "/imgs/people/9.jpg",
          alt: "p9",
        },
        {
          src: "/imgs/people/10.jpg",
          alt: "p10",
        },
        {
          src: "/imgs/people/11.jpg",
          alt: "p11",
        },
        {
          src: "/imgs/people/12.jpg",
          alt: "p12",
        },
      ],
      people: [
        {
          src: "/imgs/people/1.jpg",
          alt: "p1",
        },
        {
          src: "/imgs/people/2.jpg",
          alt: "p2",
        },
        {
          src: "/imgs/people/3.jpg",
          alt: "p3",
        },
        {
          src: "/imgs/people/4.jpg",
          alt: "p4",
        },
        {
          src: "/imgs/people/5.jpg",
          alt: "p5",
        },
        {
          src: "/imgs/people/6.jpg",
          alt: "p6",
        },
        {
          src: "/imgs/people/7.jpg",
          alt: "p7",
        },
        {
          src: "/imgs/people/8.jpg",
          alt: "p8",
        },
        {
          src: "/imgs/people/9.jpg",
          alt: "p9",
        },
        {
          src: "/imgs/people/10.jpg",
          alt: "p10",
        },
        {
          src: "/imgs/people/11.jpg",
          alt: "p11",
        },
        {
          src: "/imgs/people/12.jpg",
          alt: "p12",
        },
      ],
      icons: [
        {
          name: "Apple Music",
          imgPath: "/imgs/apple.png",
          to: "https://music.apple.com",
          style: "transform: scale3d(0.9, 0.9, 0.9)",
        },
        {
          name: "Spotify",
          imgPath: "/imgs/spotify.png",
          to: "https://www.spotify.com",
          style: "transform: scale3d(0.9, 0.9, 0.9)",
        },
        {
          name: "YouTube",
          imgPath: "/imgs/youtube.png",
          to: "https://youtube.com",
          style: "transform: scale3d(0.9, 0.9, 0.9)",
        },
        {
          name: "YouTube Music",
          imgPath: "/imgs/ytmusic.png",
          to: "https://music.youtube.com",
          style: "",
        },
        {
          name: "Melon",
          imgPath: "/imgs/melon.png",
          to: "https://www.melon.com",
          style: "",
        },
        {
          name: "Genie",
          imgPath: "/imgs/genie.png",
          to: "https://www.genie.co.kr",
          style: "",
        },
        {
          name: "Bugs",
          imgPath: "/imgs/bugs.png",
          to: "https://music.bugs.co.kr",
          style: "transform: scale3d(0.9, 0.9, 0.9)",
        },
        {
          name: "Vibe",
          imgPath: "/imgs/vibe.png",
          to: "https://vibe.naver.com",
          style: "transform: scale3d(0.9, 0.9, 0.9)",
        },
        {
          name: "Flo",
          imgPath: "/imgs/flo.png",
          to: "https://www.music-flo.com",
          style: "transform: scale3d(0.9, 0.9, 0.9)",
        },
        {
          name: "SoundCloud",
          imgPath: "/imgs/soundcloud.png",
          to: "https://soundcloud.com",
          style: "transform: scale3d(0.9, 0.9, 0.9)",
        },
      ],
    };
  },
  methods: {
    scrollTop() {
      window.scroll(0, 0);
    },
    onClick(index) {
      if (this.clicked) {
        return;
      }
      this.clicked = true;
      const newPeople = [];
      for (let i = 0; i < 12; i++) {
        newPeople.push({
          src: `/imgs/people/${index + 1}.jpg`,
          alt: `p${i + 1}`,
        });
      }
      this.loading = true;
      this.people = newPeople;
      this.loading = false;
      setTimeout(() => {
        this.loading = true;
        this.people = this.ogPeople;
        this.loading = false;
        this.clicked = false;
      }, 2000);
    },
  },
  mounted() {
    window.addEventListener("load", () => {
      bus.$emit("end:spinner");
      this.loading = false;
    });
    document.oncontextmenu = function () {
      return false;
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
    width: 52%;
    cursor: pointer;
  }
}
.main__container {
  padding-top: 60px;
}
.people__wrapper {
  display: grid;
  position: relative;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 2.5px;
  width: 100%;
  aspect-ratio: 1.25;
  img {
    width: 100%;
    aspect-ratio: 1;
  }
}
.people__skeleton {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 2.5px;
  width: 100%;
  aspect-ratio: 1.25;
  position: absolute;
  z-index: 3;
  top: 0;
  left: 0;
  background-color: #ffffff;
  .skeleton {
    background-color: #e2e2e2;
    width: 100%;
    aspect-ratio: 1;
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
      aspect-ratio: 1;
      img {
        width: 100%;
      }
    }
    .icon-name {
      margin-top: 8px;
      font-size: 10px;
      color: #121212;
      white-space: nowrap;
    }
  }
}
.footer {
  display: flex;
  flex-direction: column;
  min-height: 120px;
  justify-content: space-between;
  align-items: center;
  background-color: #e2e2e2;
  color: #121212;
  font-size: 12px;
  padding: 32px 20px;
  .sns__wrapper {
    display: flex;
    width: 100%;
    justify-content: center;
    align-items: center;
    gap: 16px;
    img {
      width: 18px;
      height: 18px;
    }
  }
}
</style>
