<template>
    <ion-page>
        <ion-header>
            <ion-toolbar>
                <ion-title>
                    <h1>Library</h1>
                </ion-title>
            </ion-toolbar>
        </ion-header>
        <ion-content>
            <h1>Library</h1>
            <ion-menu content-id="main-content">
                <ion-header>
                    <ion-toolbar>
                        <ion-title>Menu Content</ion-title>
                    </ion-toolbar>
                </ion-header>
                <ion-content class="ion-padding">
                    <ion-list>
                        <ion-item>
                            <ion-label>Pokémon Yellow</ion-label>
                        </ion-item>
                        <ion-item>
                            <ion-label>Mega Man X</ion-label>
                        </ion-item>
                        <ion-item>
                            <ion-label>The Legend of Zelda</ion-label>
                        </ion-item>
                        <ion-item>
                            <ion-label>Pac-Man</ion-label>
                        </ion-item>
                        <ion-item>
                            <ion-label>Super Mario World</ion-label>
                        </ion-item>
                    </ion-list>
                </ion-content>
            </ion-menu>
            <ion-router-outlet id="main-content">
            </ion-router-outlet>
            <ion-page id="main-content">
                <ion-header>
                    <ion-toolbar>
                        <ion-buttons slot="start">
                            <ion-menu-button></ion-menu-button>
                        </ion-buttons>
                        <ion-title>Menu</ion-title>
                    </ion-toolbar>
                </ion-header>
                <ion-content class="ion-padding"> Tap the button in the toolbar to open the menu. </ion-content>
            </ion-page>
        </ion-content>
    </ion-page>
</template>

<script setup lang="ts">
import { IonPage, IonHeader, IonContent, IonToolbar, IonTitle, IonMenu, IonRouterOutlet, IonList, IonItem, IonButtons, IonMenuButton, IonLabel } from '@ionic/vue';
</script>

<style scoped></style>