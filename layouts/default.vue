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
            {path: '/about', name: 'About'},
            {path: '/network', name: 'NetworkAPI'},
            {path: '/speech', name: 'SpeechAPI'},
        ]
    }
  }

}
</script>

<style>

</style>