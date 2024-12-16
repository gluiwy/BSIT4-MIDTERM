<template>
  <ion-page>
    <ion-header>
      <ion-toolbar>
        <ion-title>Sign In</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <section class="vh-100 px-4 py-5">
        <div class="container-fluid h-custom">
          <div
            class="row d-flex justify-content-center align-items-center h-100"
          >
            <div class="col-md-8 col-lg-6 col-xl-4 offset-xl-1">
              <!-- Wattpad Logo -->
              <div class="text-center mb-4">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  enable-background="new 0 0 100 100"
                  viewBox="0 0 100 100"
                  class="wattpad-logo"
                >
                  <path
                    id="Layer_2"
                    fill="#f70"
                    d="M96.454,21.887c-0.326-1.901-1.942-3.377-3.735-3.933c-8.423-3.022-22.049,12.647-27.215,19.882
                    c3.649-21.719-8.753-26.885-19.497-18.889c-6.885,5.298-14.343,15.972-18.641,23.446c0.641-6.504,1.855-16.442-2.307-21.282
                    c-4.057-4.716-13.576-4.665-17.683,3.282C1.308,36.01,0.047,78.234,18.339,84.241c16.519,3.282,18.935-16.184,28.7-32.151
                    c-1.954,24.722,14.479,28.713,22.589,19.653c4.131-4.061,6.99-14.141,16.302-29.334C93.548,29.986,97.64,26.844,96.454,21.887z"
                  ></path>
                </svg>
              </div>

              <form>
                <!-- Email or Username Input -->
                <div class="form-outline mb-3">
                  <input
                    type="email"
                    id="emailInput"
                    class="form-control form-control-lg"
                    placeholder="Username or Email"
                  />
                </div>

                <!-- Password Input -->
                <div class="form-outline mb-4">
                  <input
                    type="password"
                    id="passwordInput"
                    class="form-control form-control-lg"
                    placeholder="Password"
                  />
                </div>

                <!-- Sign In Button -->
                <div class="d-flex justify-content-center">
                  <button
                    type="button"
                    class="btn btn-primary w-100"
                    @click="nextScreen"
                  >
                    Sign In
                  </button>
                </div>

                <!-- Links -->
                <div class="text-center mt-3">
                  <a href="#" class="text-muted small">Forgot Password?</a>
                </div>
                <div class="text-center mt-1">
                  <a href="#" class="text-muted small">Sign Up</a>
                </div>
              </form>
            </div>
          </div>
        </div>
      </section>
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
} from '@ionic/vue';

export default defineComponent({
  name: 'SignInScreen',
  components: {
    IonToolbar,
    IonTitle,
    IonHeader,
    IonPage,
    IonContent,
  },
  methods: {
    nextScreen() {
      this.$router.push('./index');
    },
  },
});
</script>

<style>
/* Logo styling */
.wattpad-logo {
  width: 120px;
  height: auto;
  margin-bottom: 1rem;
}

/* Container height adjustment */
.h-custom {
  height: calc(100% - 56px);
}

/* Button and link styling */
.btn-primary {
  background-color: #ff6f00;
  border-color: #ff6f00;
}

.btn-primary:hover {
  background-color: #ff6f00;
}

/* Active and focus states */
.btn-primary:active,
.btn-primary:focus {
  background-color: #ff6f00;
  outline: none;
  box-shadow: none;
}

/* Responsive adjustments */
@media (max-width: 450px) {
  .h-custom {
    height: 100%;
  }
}
</style>
