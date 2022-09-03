<template>
    <div>
        <!-- using v-model to update temp storage of what's entered -->
        <input v-model="user.user_email" placeholder="email" ref="entered_email">
        <input v-model="user.user_pw" placeholder="Password">
        <button @click="try_login()" ref="button_page">LOGIN</button>
    </div>
</template>

<script>
import axios from "axios"
import Cookies from "vue-cookies"

    export default {
        
        data() {
            return {
                user: {
                    user_email: "",
                    user_pw: ""
                },
                token: ""
            }
        },
        methods: {
            try_login() {
               

                axios.request({
                
                url: `https://reqres.in/api/login`,
                method: `POST`,
                data: {
                    email: this.user[`user_email`],
                    password: this.user[`user_pw`]
                }
            }).then((success)=>{
                success
                this.$refs.button_page.insertAdjacentHTML(`afterend`,  `<p><br>${success[`data`][`token`]} signed in<p>`)
                this.token = success[`data`][`token`]
                Cookies.set(`token`, this.token);
                // this below line is to do refreshing of page
                window.location.reload()
            }).catch((error)=>{
                error
                this.$refs.entered_email.insertAdjacentHTML(`beforebegin`, `<p>error</p>`)
            })
        },
        name: 'login-form'
    }
    }
</script>

<style scoped>

</style>