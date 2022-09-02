<template>
    <div>
        <h1 ref="display_here">testing</h1>
        <section v-for="(item, index) in storage" :key="index">
            <p>{{item.first_name}} {{item.last_name}}</p>
            <img :src="item.avatar">
            <p>{{item.email}}</p>
        </section>
    </div>
</template>

<script>
import axios from "axios";
    export default {
        data() {
            return {
                storage: []
            }
        },
        name: 'all-users',
        mounted() {
            axios.request({
                url: `https://reqres.in/api/users`
            }).then((success)=>{
                success
                this.$refs.display_here.innerHTML = "axios data stored"
                for(let i = 0; i<success[`data`][`data`].length; i++){
                this.storage.push(success[`data`][`data`][i])
                }
            }).catch((error)=>{
                error
                this.$refs.display_here.innerHTML = 'error'
            })
        }
    }
</script>

<style scoped>

</style>