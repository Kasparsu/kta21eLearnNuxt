<template>
  
</template>

<script>
import loki from 'lokijs';
import IndexedDbAdapter from 'lokijs/src/loki-indexed-adapter';
export default {
    mounted(){
        if(process.client){
       
            var db = new loki("quickstart.db", {
                adapter: new IndexedDbAdapter(),
                autoload: true,
                autoloadCallback : databaseInitialize,
                autosave: true, 
                autosaveInterval: 4000
            });

            function databaseInitialize() {
                if (!db.getCollection("users")) {
                    var users = db.addCollection("users");
                    users.insert({name:'odin', age: 50});
                }
            }
        }
    }
}
</script>

<style>

</style>