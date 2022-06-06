<template>
  <master-layout pageTitle="AJOUTER UN TABLEAU DE BORD">
        <ion-row>
 <!--   <ion-fab-button style="margin-left: auto; "> -->
    <ion-icon  @click="shown = !shown" name="add" size="large" color="primary" style="margin-left: auto;"   
               ></ion-icon ><!-- </ion-fab-button> --></ion-row>
    <ion-card class="crd-add" v-if="shown" >
    <ion-item>
       <fa   icon="hashtag"  slot="start"/>
      <ion-label>Compteur</ion-label>
    </ion-item>
     <ion-item>
      <fa   icon="file"  slot="start" />
       <ion-label>Nouveau document</ion-label>
    </ion-item>
     <ion-item>
        <fa   icon="bars-progress"  slot="start" />
       <ion-label>Liste de tâches</ion-label>
    </ion-item>
     <ion-item>
       <fa   icon="link"  slot="start" />
       <ion-label>Page web</ion-label>
    </ion-item>
    </ion-card>
  </master-layout>
</template>
<script>
import axios from 'axios';
export default {
   data() {
    return {
      shown: false,}},
      methods: {
loadUsers(){axios.get("https://elise6-pfe.elisedemo.com/GED/elise/api/connection/user").then(
    response => {
      this.users = response.data // assigns the data from api call to the users variable 
    }) 
    }
  },
};
</script>
<style>
.crd-add{

  width: 50%;
  margin-left: auto;
  margin-top: -14px;

}
</style>