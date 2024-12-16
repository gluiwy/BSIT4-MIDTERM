<template>
  <ion-page>
    <ion-header>
      <ion-toolbar color="warning">
        <ion-buttons slot="start">
          <ion-back-button></ion-back-button>
        </ion-buttons>
        <ion-title> Swiper </ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content>
      <swiper :slides-per-view="1" :space-between="50" @swiper="onSwiper">
        <swiper-slide>
          <img
            class="banner"
            src="https://bobo.muzli.cloud/1722592917233-Selling%20templates%C2%A0.png?format=600:450"
            alt="image 1"
          />
        </swiper-slide>
        <swiper-slide>
          <img
            class="banner"
            src="https://i.pinimg.com/736x/45/07/f8/4507f899b2a8d0d3b3017a31401ed5d3.jpg"
            alt="image 2"
          />
        </swiper-slide>
        <swiper-slide>
          <img
            class="banner"
            src="https://cdn.kwork.com/files/portfolio/t3/55/aaea459dc279378fccaedbed6a72ec8cbbc80190-1708857222.jpg"
            alt="image 3"
          />
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
  name: 'swiperScreen',
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
