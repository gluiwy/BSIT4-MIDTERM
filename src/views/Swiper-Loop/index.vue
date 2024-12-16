<template>
  <ion-page>
    <ion-header>
      <ion-toolbar color="warning">
        <ion-buttons slot="start">
          <ion-back-button></ion-back-button>
        </ion-buttons>
        <ion-title> Loop </ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content>
      <swiper :slides-per-view="1" :space-between="50" @swiper="onSwiper">
        <swiper-slide v-for="(banner, i) in banners" :key="i">
          <img class="banner" :src="banner" />
        </swiper-slide>
      </swiper>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { menu, home, person } from 'ionicons/icons';
import { Swiper, SwiperSlide } from 'swiper/vue';
import 'swiper/css';

import {
  IonBackButton,
  IonButtons,
  IonToolbar,
  IonTitle,
  IonHeader,
  IonPage,
  IonContent,
  IonIcon,
  IonRouterOutlet,
} from '@ionic/vue';

export default defineComponent({
  name: 'swiperloopScreen',
  components: {
    IonBackButton,
    IonButtons,
    IonToolbar,
    IonTitle,
    IonHeader,
    IonPage,
    IonContent,
    IonIcon,
    IonRouterOutlet,
    Swiper,
    SwiperSlide,
  },
  data() {
    return {
      swiper: {} as any,
      banners: [
        'https://i.pinimg.com/736x/b3/94/2e/b3942eec07dd4c4bab3bf4b6841f0523.jpg',
        'https://cdn.kwork.com/pics/t3/26/31846904-65db133e3bd44.jpg',
        'https://cdn.prod.website-files.com/5b5729421aca332c60585f78/6181a854fe9af42fcf3acd8d_maje-flash-sale-banner-example.png',
        'https://cdn.kwork.com/files/portfolio/t3/90/45dbbf8bd3955a17ecfc6c7927719ae5200ed098-1708857109.jpg',
        'https://cdn.kwork.com/files/portfolio/t0/53/606e22e8d0b13b6bf35822dc24b65ad9461fe568-1708848370.jpg',
        'https://cdn.kwork.com/files/portfolio/t3/55/aaea459dc279378fccaedbed6a72ec8cbbc80190-1708857222.jpg',
      ],
    };
  },
  methods: {
    async onSwiper(event: any) {
      this.swiper = event;
    },
  },
  setup() {
    return {
      menu,
      home,
      person,
    };
  },
});
</script>

<style scoped>
.banner {
  width: 100vw;
  height: 260px;
  object-fit: cover;
  object-position: center;
}
</style>
