<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-buttons slot="start">
          <ion-back-button></ion-back-button>
        </ion-buttons>
        <ion-title class="bg-warning"> Local Storage </ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content>
      <div class="p-3">
        <div class="mb-3">
          <label class="form-label">Key name </label>
          <input v-model="form.key" type="text" class="form-control" />
        </div>
        <div class="mb-3">
          <label class="form-label">Value</label>
          <input v-model="form.value" type="text" class="form-control" />
        </div>
        <button class="btn btn-primary w-100" @click="save()">
          Save Storage
        </button>
        <button class="btn btn-primary w-100 mt-3" @click="getData()">
          Get Data
        </button>
      </div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { menu, home, person } from 'ionicons/icons';
import { Preferences } from '@capacitor/preferences';

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
  name: 'localstorageScreen',
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
  },
  data() {
    return {
      form: {
        key: '',
        value: '',
      },
    };
  },
  methods: {
    async save() {
      await Preferences.set({
        key: this.form.key,
        value: this.form.value,
      });
    },
    async getData() {
      const data = await Preferences.get({
        key: this.form.key,
      });
      if (data.value) {
        this.form.value = data.value;
      }
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
