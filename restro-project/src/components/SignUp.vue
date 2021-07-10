<template>
<Header />
<br />
<br />
<br />

<div class="register">
      <h3>Sing Up</h3>
    <input type="text" v-model="name" placeholder="Enter Name">

    <input type="text" v-model="email" placeholder="Enter Email">

    <input type="password" v-model="password" placeholder="Enter Password">

    <button v-on:click="signUp"> SignUp </button>

    <p>
        <router-link to="/login">Login</router-link>
    </p>

</div>
</template>

<script>
import axios from 'axios'
import Header from './Header.vue'
export default {
    name: 'SignUp',
    components: {
        Header
    },
    data() {
        return {
            name: '',
            email: '',
            password: ''
        }
    },
    methods: {
        async signUp() {
            console.warn("signUp", this.name, this.email, this.password)
            let result = await axios.post("http://localhost:3000/users", {
                name: this.name,
                email: this.email,
                password: this.password
            });

            console.warn("result");
            if (result.status == 201) {

                localStorage.setItem("user-info", JSON.stringify(result.data))
                this.$router.push({
                    name: 'Home'
                })
            }

        }
    },

    mounted() {
        //console.warn("mount")

        let user = localStorage.getItem('user-info');
        if (user) {

            this.$router.push({
                name: 'Home'
            })

        }
    }
}
</script>

<style>

</style>
