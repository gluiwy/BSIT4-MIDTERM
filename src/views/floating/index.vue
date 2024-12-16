<template>
  <ion-page>
    <ion-header>
      <ion-toolbar color="warning">
        <ion-buttons slot="start">
          <ion-back-button></ion-back-button>
        </ion-buttons>
        <ion-title> Floating Action Button </ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <ion-fab slot="fixed" vertical="top" horizontal="start">
        <ion-fab-button>
          <ion-icon :icon="chevronForwardCircle"></ion-icon>
        </ion-fab-button>
        <ion-fab-list side="end">
          <ion-fab-button>
            <ion-icon :icon="document"></ion-icon>
          </ion-fab-button>
          <ion-fab-button>
            <ion-icon :icon="colorPalette"></ion-icon>
          </ion-fab-button>
          <ion-fab-button>
            <ion-icon :icon="globe"></ion-icon>
          </ion-fab-button>
        </ion-fab-list>
      </ion-fab>

      <ion-fab slot="fixed" vertical="top" horizontal="end" :edge="true">
        <ion-fab-button>
          <ion-icon :icon="chevronDownCircle"></ion-icon>
        </ion-fab-button>
        <ion-fab-list side="bottom">
          <ion-fab-button>
            <ion-icon :icon="document"></ion-icon>
          </ion-fab-button>
          <ion-fab-button>
            <ion-icon :icon="colorPalette"></ion-icon>
          </ion-fab-button>
          <ion-fab-button>
            <ion-icon :icon="globe"></ion-icon>
          </ion-fab-button>
        </ion-fab-list>
      </ion-fab>

      <ion-fab slot="fixed" vertical="bottom" horizontal="end">
        <ion-fab-button>
          <ion-icon :icon="chevronUpCircle"></ion-icon>
        </ion-fab-button>
        <ion-fab-list side="top">
          <ion-fab-button>
            <ion-icon :icon="document"></ion-icon>
          </ion-fab-button>
          <ion-fab-button>
            <ion-icon :icon="colorPalette"></ion-icon>
          </ion-fab-button>
          <ion-fab-button>
            <ion-icon :icon="globe"></ion-icon>
          </ion-fab-button>
        </ion-fab-list>
      </ion-fab>
    </ion-content>

    <ion-footer>
      <ion-toolbar class="p-1">
        <ion-tabs>
          <ion-router-outlet></ion-router-outlet>
          <ion-tab-bar slot="bottom">
            <ion-tab-button tab="tab1" href="/tabs/home">
              <ion-icon aria-hidden="true" :icon="home" />
              <ion-label>Home</ion-label>
            </ion-tab-button>

            <ion-tab-button tab="tab2" href="/tabs/profile">
              <ion-icon aria-hidden="true" :icon="person" />
              <ion-label>Profile</ion-label>
            </ion-tab-button>

            <ion-tab-button tab="tab3" href="/tabs/menu">
              <ion-icon aria-hidden="true" :icon="menu" />
              <ion-label>Menu</ion-label>
            </ion-tab-button>
          </ion-tab-bar>
        </ion-tabs>
      </ion-toolbar>
    </ion-footer>
  </ion-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import { menu, home, person } from 'ionicons/icons';

import {
  IonBackButton,
  IonButtons,
  IonToolbar,
  IonTitle,
  IonHeader,
  IonItem,
  IonLabel,
  IonList,
  IonPage,
  IonContent,
  IonTabs,
  IonTabBar,
  IonTabButton,
  IonIcon,
  IonRouterOutlet,
  IonFab,
  IonFabButton,
  IonFabList,
} from '@ionic/vue';

import {
  chevronDownCircle,
  chevronForwardCircle,
  chevronUpCircle,
  colorPalette,
  document,
  globe,
} from 'ionicons/icons';

export default defineComponent({
  name: 'card',
  components: {
    IonBackButton,
    IonButtons,
    IonToolbar,
    IonTitle,
    IonHeader,
    IonItem,
    IonLabel,
    IonList,
    IonPage,
    IonContent,
    IonTabs,
    IonTabBar,
    IonTabButton,
    IonIcon,
    IonRouterOutlet,
    IonFab,
    IonFabButton,
    IonFabList,
  },
  setup() {
    return {
      chevronDownCircle,
      chevronForwardCircle,
      chevronUpCircle,
      colorPalette,
      document,
      globe,
      menu,
      home,
      person,
    };
  },
});
</script>
