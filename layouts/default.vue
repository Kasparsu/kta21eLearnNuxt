<template>
<div>
    <tabs :links="pages" :current="$route.path"></tabs>
    <section class="section">
        <div class="container">
            <div class="content">
                <nuxt/>
            </div>
        </div>
    </section>  
</div>
</template>

<script>
import Tabs from '../components/Tabs.vue';
export default {
  components: { Tabs },
  data(){
    return {
        pages: [
            {path: '/', name: 'Home'},
            {path: '/databases', name: 'Databases'},
            {path: '/network', name: 'NetworkAPI'},
            {path: '/speech', name: 'SpeechAPI'},
            {path: '/geolocation', name: 'GeolocationAPI'},
            {path: '/eyedropper', name: 'EyeDropperAPI'},
            {path: '/clipboard', name: 'ClipboardAPI'},
            {path: '/canvasapi', name: 'CanvasAPI'},
            {path: '/chat', name: 'Chat'},

        ]
    }
  }

}
</script>

<style>

</style>