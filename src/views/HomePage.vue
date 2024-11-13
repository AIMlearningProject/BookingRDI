<<<<<<<<<<<<<<  ✨ Codeium Command 🌟  >>>>>>>>>>>>>>>>
<template>
  <ion-page>
<ion-header :translucent="true">
      <ion-toolbar>
        <div style="display: flex; align-items: center;">
          <img src="https://github.com/oumaimaAINIYANITS22K/RDI-Office-Booking-/blob/main/centria%20logo.png?raw=true" alt="Logo" style="height: 60px; width: 60px; margin-right: 10px;">
          <ion-title style="font-weight: bold; color: #e10e49; font-size: 24px;">RDI Office Booking </ion-title>
        </div>
      </ion-toolbar>
    </ion-header>

    <ion-content :fullscreen="true" class="ion-padding custom-background">
<div class="container1">
        <h2 class="container" style="font-size: 25px; font-weight: bold; text-align: center; color: #e10e49">Welcome to the RDI Desk Booking System</h2>
        <br>
        <p class="container" style="font-size: 17px; text-align: center">
          We are pleased to offer a convenient desk booking system for our remote workers when they arrive on campus.
          Our system allows you to reserve a desk in the RDI staff offices quickly and easily. Simply fill out the form below,
          choose the room, and specify your reservation dates to ensure you have a workspace ready when you need it.
        </p>
        <br>
        <br>
      </div>
      <div style="display: flex;">
        <div class="container2" style="flex: 1; margin-right: 5%; margin-left: 15%">
          <form @submit.prevent="bookDesk">
            <div style="flex: 1;">
              <div class="input-container">
                <ion-item>
                  <ion-label position="floating" class="input-label">Full name <span style="color: red">*</span></ion-label>
                  <br>
                  <ion-input v-model="form.fullName" class="input-field" required></ion-input>
                </ion-item>
              </div>

              <div class="input-container">
                <ion-item>
                  <ion-label position="floating" class="input-label">Team name <span style="color: red">*</span></ion-label>
                  <br>
                  <ion-input v-model="form.teamName" class="input-field" required></ion-input>
                </ion-item>
              </div>

              <div class="input-container">
                <ion-item>
                  <ion-label position="floating" class="input-label">Room number <span style="color: red">*</span></ion-label>
                  <br>
                  <ion-input v-model="form.roomNumber" class="input-field" required></ion-input>
                </ion-item>
              </div>

              <div class="input-container">
                <ion-item>
                  <ion-label position="floating" class="input-label">Desk number <span style="color: red">*</span></ion-label>
                  <br>
                  <ion-input v-model="form.deskNumber" class="input-field" required></ion-input>
                </ion-item>
              </div>

              <div class="input-container">
                <ion-item>
                  <ion-label position="floating" class="input-label">Date <span style="color: red">*</span></ion-label>
                  <br>
                  <ion-datetime display-format="MMMM DD, YYYY" :picker-options="{from: new Date().toISOString()}" v-model="form.date" class="input-field" required></ion-datetime>
                </ion-item>
              </div>

              <div class="input-container">
                <ion-item>
                  <ion-label position="floating" class="input-label">Starting time <span style="color: red">*</span></ion-label>
                  <br>
                  <ion-input v-model="form.startTime" class="input-field" required></ion-input>
                  <ion-datetime display-format="hh:mm A" :picker-options="{from: form.date, minuteValues: [0, 30]}" v-model="form.startTime" class="input-field" required></ion-datetime>
                </ion-item>
              </div>

              <div class="input-container">
                <ion-item>
                  <ion-label position="floating" class="input-label">Ending time <span style="color: red">*</span></ion-label>
                  <br>
                  <ion-datetime display-format="hh:mm A" :picker-options="{from: form.startTime, minuteValues: [0, 30]}" v-model="form.endTime" class="input-field" required></ion-datetime>
                </ion-item>
              </div>

              <div style="display: flex; justify-content: center;">
                <ion-button type="submit" shape="round" size="default" class="ion-margin-top login-button">Book Desk</ion-button>
              </div>
            </div>
          </form>
        </div>
        <div class="container3" style="flex: 1; margin-left: 5%;">
          <ion-item>
                     <img src="https://github.com/oumaimaAINIYANITS22K/RDI-Office-Booking-/blob/main/8785470_3991843.jpg?raw=true" alt="booking desk" justify-content="center" style="width: 100%; height: 100%;">
           </ion-item>
        </div>
      </div>

    </ion-content>
  </ion-page>
</template>

<script setup lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonDatetime } from '@ionic/vue';
import { ref } from 'vue';

interface Form {
  fullName: string;
  teamName: string;
  roomNumber: string;
  deskNumber: string;
  date: string;
  startTime: string;
  endTime: string;
}

const form = ref<Form>({
  fullName: '',
  teamName: '',
  roomNumber: '',
  deskNumber: '',
  date: '',
  startTime: '',
  endTime: '',
});

const bookDesk = () => {
  console.log(form.value);
};
</script>

<style scoped>
.container2 {
  max-width: 400px;
  margin: 0 auto;
}

.input-container {
  border: 1px solid #ccc;
  border-radius: 8px;
  padding: 16px;
  margin-bottom: 16px;
}

.input-label {
  font-weight: bold;
}

.login-button {
  --ion-button-background-color: #e10e49;
  --ion-button-color: white;
}
</style>


<<<<<<<  136a7400-d06d-423f-a66c-ab0b2e514f20  >>>>>>>