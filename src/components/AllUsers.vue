<template>
    <div>
        <h1>testing</h1>
    </div>
</template>

<script>
import axios from "axios";
    export default {
        name: 'all-users',
        mounted () {
            axios.request({
                url: `https://reqres.in/api/users`,
            }).then((response22) => {
                for (let i = 0; i< response22.data.length;i++) {
                document.body.insertAdjacentHTML(`beforeend`, `<h1>${response22[`data`]}</h>`)
                }
            }).catch((error) => {
                console.log(error)
            });
        },
    }
</script>

<style scoped>

</style>