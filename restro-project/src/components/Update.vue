<template>
<Header />
<br />
<br />
<br />
<div class="container">
    <form class="contact">
        <h3>User Update Restaurant</h3>
        <!-- <h4>Contact us for custom quote</h4> -->
        <div class="fl-set">
            <input v-model="restaurant.name" placeholder="Restaurant name" type="text" tabindex="" required autofocus>
        </div>
        <div class="fl-set">
            <input v-model="restaurant.address" placeholder="Restaurant Address" type="text" tabindex="" required>
        </div>
        <div class="fl-set">
            <input v-model="restaurant.contact" placeholder="Restaurant Phone Number (optional)" type="tel" tabindex="" required>
        </div>

        <div class="fl-set">
            <button type="button" v-on:click="addRestaurant">Update Restaurant</button>
        </div>

    </form>
</div>
</template>

<script>
import Header from './Header.vue'
export default {
    name: 'Update',
    components: {
        Header
    },

    data() {
        return {
            restaurant: {
                name: '',
                address: '',
                contact: ''
            }
        }
    },

    mounted() {
        //console.warn("mount")

        let user = localStorage.getItem('user-info');
        if (!user) {

            this.$router.push({
                name: 'SignUp'
            })

        }
    }
};
</script>

<style>

</style>
