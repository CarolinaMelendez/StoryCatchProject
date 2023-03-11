<template>
    <ion-page>
      <ion-header :translucent="true">
        <ion-toolbar>
          <ion-title>Popular Cards ;)</ion-title>
        </ion-toolbar>
      </ion-header>
      
  
      <ion-content :fullscreen="true">
        <ion-card>
            <ion-card-header>
                <ion-card-title>Card Title</ion-card-title>
                <ion-card-subtitle>Chapter #</ion-card-subtitle>
            </ion-card-header>
        </ion-card>

      </ion-content>
    </ion-page>
    
  </template>
  
  <script setup lang="ts">
  import {
    IonContent,
    IonHeader,
    IonList,
    IonPage,
    IonRefresher,
    IonRefresherContent,
    IonTitle,
    IonToolbar,
  } from '@ionic/vue';
  import MessageListItem from '@/components/MessageListItem.vue';
  import { getMessages, Message } from '@/data/messages';
  import { ref } from 'vue';
  
  const messages = ref<Message[]>(getMessages());
  
  const refresh = (ev: CustomEvent) => {
    setTimeout(() => {
      ev.detail.complete();
    }, 3000);
  };
  </script>