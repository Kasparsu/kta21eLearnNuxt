<template>
  <div>
    <input class="input" type="text" v-model="message">
    <button class="button is-primary" @click="speak()">speak</button>
    <div class="select">
        <select v-model="selectedVoice">
            <option v-for="(voice,index) in voices" :key="index" :value="index">{{voice.name}}</option>
        </select>
    </div>
  </div>
</template>

<script>
export default {
    mounted(){
        if(process.client){
            let interval = setInterval( () => {
                
                this.voices = speechSynthesis.getVoices();
                if(this.voices.length > 0){
                    clearInterval(interval);
                }
            }, 100);
        }
    },
    data(){
        return {
            message: '',
            voices: [],
            selectedVoice: 0
        }
    },
    methods: {
        speak(){
            let utterance = new SpeechSynthesisUtterance(this.message);
            utterance.voice = this.voices[this.selectedVoice];
            speechSynthesis.speak(utterance);
        }
    }
}
</script>

<style>

</style>