<script setup lang="ts">
  import {
    IonContent,
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar,
  } from "@ionic/vue";

  // Import share plugin
  import { Share } from "@capacitor/share";
  import { Browser } from "@capacitor/browser";

  // Create share function

  const share = async () => {
    await Share.share({
      title: "Subscribe",
      text: "Subscribe to my youtube channel",
      url: "https://youtube.com",
      dialogTitle: "Subscribe",
    });
  };

  // Create  browser function
  const openBrowser = async () => {
    await Browser.open({
      url: "https://michael-njuguna-developer.netlify.app/",
    });
  };
</script>
<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Blank</ion-title>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Blank</ion-title>
        </ion-toolbar>
      </ion-header>

      <div id="container">
        <!-- Create a button for sharing -->
        <ion-button expand="block" color="danger" @click="share"
          >Subscribe</ion-button
        >
        <ion-button expand="block" color="primary" @click="openBrowser">
          Open
        </ion-button>
      </div>
    </ion-content>
  </ion-page>
</template>

<style scoped></style>
