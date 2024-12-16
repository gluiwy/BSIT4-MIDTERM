<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title> Ionic Components </ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content color="light">
      <ion-toolbar>
        <ion-title> Midterm Activity </ion-title>
      </ion-toolbar>
      <ion-list>
        <ion-item :button="true" @click="cardScreen()">
          <ion-label>
            <h2 class="text-bold">Card</h2>
            <p>
              Cards are containers that display content such as text, images,
              buttons, and lists.
            </p>
          </ion-label>
        </ion-item>
        <ion-item :button="true" @click="modalScreen()">
          <ion-label>
            <h2 class="text-bold">Modal</h2>
            <p>A Modal is a dialog that appears on top of the app's content.</p>
          </ion-label>
        </ion-item>
        <ion-item :button="true" @click="reorderScreen()">
          <ion-label>
            <h2 class="text-bold">Reorder</h2>
            <p>
              Reorder is a component that allows an item to be dragged to change
              its order.
            </p>
          </ion-label>
        </ion-item>
        <ion-item :button="true" @click="floatScreen()">
          <ion-label>
            <h2 class="text-bold">Floating</h2>
            <p>
              Fabs are container elements that contain one or more fab buttons.
            </p>
          </ion-label>
        </ion-item>

        <ion-toolbar>
          <ion-title> Prefinal Activity </ion-title>
        </ion-toolbar>

        <ion-item :button="true" @click="swiper()">
          <ion-label>
            <h2 class="text-bold">Act 1: Swiper Slider</h2>
            <p>Learn how to implement slider</p>
          </ion-label>
        </ion-item>
        <ion-item :button="true" @click="swiperloop()">
          <ion-label>
            <h2 class="text-bold">Act 2 : For Loop with components</h2>
            <p>Learn how to implement loop around reusable components</p>
          </ion-label>
        </ion-item>
        <ion-item :button="true" @click="localstorage()">
          <ion-label>
            <h2 class="text-bold">Act 3 : Local Device Storage</h2>
            <p>Learn how to implement device storage</p>
          </ion-label>
        </ion-item>

        <ion-item :button="true" @click="mapScreen()">
          <ion-label>
            <h2 class="text-bold">Act 4: Map Implementation</h2>
            <p>Learn how to implement map in ionic</p>
          </ion-label>
        </ion-item>
        <ion-item :button="true" @click="GPSscreen()">
          <ion-label>
            <h2 class="text-bold">Act 5 : GPS | Geolocation</h2>
            <p>Get latitude and longitude</p>
          </ion-label>
        </ion-item>
        <ion-item :button="true" @click="cameraScreen()">
          <ion-label>
            <h2 class="text-bold">Act 6 : Camera Implementation</h2>
            <p>Learn how to implement camera in ionic</p>
          </ion-label>
        </ion-item>
      </ion-list>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import {
  IonToolbar,
  IonTitle,
  IonHeader,
  IonPage,
  IonContent,
  IonFooter,
  IonList,
  IonItem,
  IonLabel,
  IonCard,
  IonCardHeader,
  IonCardTitle,
} from '@ionic/vue';

export default defineComponent({
  name: 'home',
  components: {
    IonToolbar,
    IonTitle,
    IonHeader,
    IonPage,
    IonContent,
    IonFooter,
    IonList,
    IonItem,
    IonLabel,
    IonCard,
    IonCardHeader,
    IonCardTitle,
  },
  methods: {
    async cardScreen() {
      this.$router.push('/card');
    },
    async modalScreen() {
      this.$router.push('/modal');
    },
    async reorderScreen() {
      this.$router.push('/reorder');
    },
    async floatScreen() {
      this.$router.push('/float');
    },
    async swiper() {
      this.$router.push('/tabs/swiper');
    },
    async swiperloop() {
      this.$router.push('/tabs/swiperloop');
    },
    async localstorage() {
      this.$router.push('/tabs/localstorage');
    },
    async mapScreen() {
      this.$router.push('/map');
    },
    async GPSscreen() {
      this.$router.push('/gps');
    },
    async cameraScreen() {
      this.$router.push('/camera');
    },
  },
});
</script>
