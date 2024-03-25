<script setup lang="ts">
import { IonPage, IonHeader, IonContent, IonToolbar, IonTitle, IonMenu, IonButton, IonRouterOutlet, IonList, IonItem, IonButtons, IonMenuButton, IonLabel } from '@ionic/vue';
import { Camera, CameraResultType } from '@capacitor/camera';
import { ref } from 'vue';


const srcImg = ref<string | undefined>(undefined);
const takePicture = async () => {
    const image = await Camera.getPhoto({
        quality: 90,
        allowEditing: true,
        resultType: CameraResultType.Uri
    });

    // image.webPath will contain a path that can be set as an image src.
    // You can access the original file using image.path, which can be
    // passed to the Filesystem API to read the raw data of the image,
    // if desired (or pass resultType: CameraResultType.Base64 to getPhoto)

    srcImg.value = image.webPath;
};


</script>
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
                <ion-content class="ion-padding">
                    <ion-button @click="takePicture">Tomar foto</ion-button>
                    <p>Tap the button in the toolbar to open the menu.</p>
                    <img :src="srcImg" alt="New image" />
                </ion-content>
            </ion-page>
        </ion-content>
    </ion-page>
</template>



<style scoped>
img {
    width: 500px;
    height: 500px;
}
</style>