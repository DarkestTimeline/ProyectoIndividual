<template>
  <ion-page>
    <ion-header :translucent="true">
      <ion-toolbar>
        <ion-title>Acidosis Metabolica</ion-title>
        <ion-title slot="end">Sergio Vasquez</ion-title>
      </ion-toolbar>
    </ion-header>
    
    <ion-content :fullscreen="true">
      <ion-header collapse="condense">
        <ion-toolbar>
          <ion-title size="large">Hola</ion-title>
        </ion-toolbar>
      </ion-header>
    
      <div id="container">

        <ion-card>
          <img height="350" src="assets\img.jpg"/>
          <ion-card-header>
            <ion-card-title>¿ANION GAP?</ion-card-title>
            <ion-card-subtitle>AG = Na<sup>+</sup> - (Cl + HCO<sub>3</sub>)</ion-card-subtitle>
          </ion-card-header>
          <ion-card-content>
            La acidosis metabólica se desarrolla cuando se produce demasiado ácido en el cuerpo. 
            También puede ocurrir cuando los riñones no pueden eliminar suficiente ácido del cuerpo.
          </ion-card-content>
          <ion-item @click="isVisible1 = !isVisible1; isVisible3 = !isVisible3">
           <ion-icon :icon="checkmarkCircle" color="success" slot="start" v-if="isVisible1"></ion-icon>
            <ion-label>ANION GAP ELEVADO</ion-label>
          </ion-item>

          <ion-item @click="isVisible2 = !isVisible2; isVisible7 = !isVisible7">
            <ion-icon :icon="checkmarkCircle" color="success" slot="start" v-if="isVisible2"></ion-icon>
            <ion-label>ANION GAP NORMAL</ion-label>
          </ion-item>
        </ion-card>

        <ion-card v-if="isVisible3">
          <ion-card-header>
            <ion-card-title>Sintomas</ion-card-title>
            <ion-card-subtitle></ion-card-subtitle>
          </ion-card-header>
          <ion-card-content>
            
          </ion-card-content>
          <ion-item @click="isVisible4 = !isVisible4">
           <ion-icon :icon="checkmarkCircle" color="success" slot="start" v-if="isVisible4"></ion-icon>
            <ion-label @click="presentAlert1">¿Hipoxia tisular?</ion-label>
          </ion-item>

          <ion-item @click="isVisible5 = !isVisible5">
            <ion-icon :icon="checkmarkCircle" color="success" slot="start" v-if="isVisible5"></ion-icon>
            <ion-label @click="presentAlert2">¿Cuerpos cetonicos?</ion-label>
          </ion-item>

          <ion-item @click="isVisible12 = !isVisible12">
            <ion-icon :icon="checkmarkCircle" color="success" slot="start" v-if="isVisible12"></ion-icon>
            <ion-label @click="presentAlert3">¿Funcion renal?</ion-label>
          </ion-item>

          <ion-item @click="isVisible14 = !isVisible14; isVisible6 =! isVisible6">
            <ion-icon :icon="checkmarkCircle" color="success" slot="start" v-if="isVisible14"></ion-icon>
            <ion-label>Ninguna</ion-label>
          </ion-item>
        </ion-card>

        <ion-card v-if="isVisible6">
          <ion-card-header>
            <ion-card-title>¿Gap Osmolar?</ion-card-title>
            <ion-card-subtitle>G<sub>o</sub> = OSM medida - OSM calculada</ion-card-subtitle>
          </ion-card-header>

          <ion-card-content>
            This is content, without any paragraph or header tags,
            within an ion-card-content element.
          </ion-card-content>

          <ion-item @click="isVisible13 = !isVisible13">
           <ion-icon :icon="checkmarkCircle" color="success" slot="start" v-if="isVisible13"></ion-icon>
            <ion-label @click="presentAlert4">Elevado</ion-label>
          </ion-item>

          <ion-item @click="isVisible8 = !isVisible8">
            <ion-icon :icon="checkmarkCircle" color="success" slot="start" v-if="isVisible8"></ion-icon>
            <ion-label @click="presentAlert5">Normal</ion-label>
          </ion-item>
        </ion-card>

        <ion-card v-if="isVisible7">
          <ion-card-header>
            <ion-card-title>¿GAP URINARIO?</ion-card-title>
            <ion-card-subtitle>G<sub>u</sub> = (Na + K)<sub>o</sub> - Cl<sub>o</sub></ion-card-subtitle>
          </ion-card-header>
          <ion-card-content>
            This is content, without any paragraph or header tags,
            within an ion-card-content element.
          </ion-card-content>
          <ion-item @click="isVisible10 = !isVisible10">
           <ion-icon :icon="checkmarkCircle" color="success" slot="start" v-if="isVisible10"></ion-icon>
            <ion-label @click="presentAlert6">Negativo <br> (Na<sup>+</sup> + K<sup>+</sup>) &lt;Cl </ion-label>
          </ion-item>

          <ion-item @click="isVisible11 = !isVisible11">
            <ion-icon :icon="checkmarkCircle" color="success" slot="start" v-if="isVisible11"></ion-icon>
            <ion-label @click="presentAlert7">Positivo <br> (Na<sup>+</sup> + K<sup>+</sup>) &gt;Cl</ion-label>
          </ion-item>
        </ion-card>
      </div>
    </ion-content>
  </ion-page>
</template>

<script lang="ts">
import { IonContent, IonHeader, IonPage, IonTitle, IonToolbar, IonCard, IonCardContent, IonCardHeader, IonCardSubtitle, IonCardTitle, IonIcon, IonItem, IonLabel, alertController  } from '@ionic/vue';
import { Icon } from 'ionicons/dist/types/components/icon/icon';
import { pinOutline, walk, warning, wifi, wine, checkmarkCircle, rocket, closeCircle } from 'ionicons/icons';
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'HomePage',
  components: {
    IonContent,
    IonHeader,
    IonPage,
    IonTitle,
    IonToolbar,
    IonCard,
    IonCardContent,
    IonCardHeader,
    IonCardSubtitle,
    IonCardTitle,
    IonIcon,
    IonItem,
    IonLabel 
  },
  setup(props) {
    return { warning, rocket, walk, wifi, wine, checkmarkCircle, pinOutline, closeCircle};
  }, data() {
    return {
      isVisible1: false,
      isVisible2: false,
      isVisible3: false,
      isVisible4: false,
      isVisible5: false,
      isVisible6: false,
      isVisible7: false,
      isVisible8: false,
      isVisible9: false,
      isVisible10: false,
      isVisible11: false,
      isVisible12: false,
      isVisible13: false,
      isVisible14: false
    }
  }, methods: {
    chkIcon(){
      console.log("A")
    }, async presentAlert1() {
        const alert = await alertController.create({
          header: 'Diagnostico',
          subHeader: 'El diagnostico es',
          message: 'Acidosis L-Lactica',
          buttons: ['OK'],
        });

        await alert.present();
      }, async presentAlert2() {
        const alert = await alertController.create({
          header: 'Diagnostico',
          subHeader: 'El diagnostico es',
          message: 'Cetoacidosis',
          buttons: ['OK'],
        });

        await alert.present();
      }, async presentAlert3() {
        const alert = await alertController.create({
          header: 'Diagnostico',
          subHeader: 'El diagnostico es',
          message: 'Insuficiencia Renal',
          buttons: ['OK'],
        });

        await alert.present();
      }, async presentAlert4() {
        const alert = await alertController.create({
          header: 'Diagnostico',
          subHeader: 'Intoxicaciones:',
          message: '- Etanol \n- Metanol \n- Etilenglicol',
          buttons: ['OK'],
          cssClass: 'foo'
        });

        await alert.present();
      }, async presentAlert5() {
        const alert = await alertController.create({
          header: 'Diagnostico',
          subHeader: 'Intoxicaciones:',
          message: '- Salicilatos \n- Paralddehido \n\nAcidosis D-Lactica',
          buttons: ['OK'],
          cssClass: 'foo'
        });

        await alert.present();
      }, async presentAlert6() {
        const alert = await alertController.create({
          header: 'Diagnostico',
          subHeader: 'Perdidas digestivas:',
          message: '- Diarreas \n- Ileo \n- Adenoma veloso \n- Fistuas intestinales \n\nATR Proximal (tipo II) \nAcetazolamida',
          buttons: ['OK'],
          cssClass: 'foo'
        });

        await alert.present();
      }, async presentAlert7() {
        const alert = await alertController.create({
          header: 'Diagnostico',
          subHeader: 'Perdidas digestivas:',
          message: 'ATR Distal (tipo I) \nATR tipo IV \nCiertas formas de insuficiencia renal',
          buttons: ['OK'],
          cssClass: 'foo'
        });

        await alert.present();
      }
  },
});
</script>

<style scoped>
#container {
  text-align: center;
  
  position: absolute;
  left: 0;
  right: 0;

}

#container strong {
  font-size: 20px;
  line-height: 26px;
}

#container p {
  font-size: 16px;
  line-height: 22px;
  
  color: #8c8c8c;
  
  margin: 0;
}

#container a {
  text-decoration: none;
}
</style>
