<template>
<Header />
<br />
<br />
<br />
<div class="container">
    <form class="contact">
        <h3>User Adding Restaurant</h3>
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
            <button type="button" v-on:click="addRestaurant">Add New Restaurant</button>
        </div>

    </form>
</div>
</template>

<script>
import Header from './Header.vue'
export default {
    name: 'Add',
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

    methods: {

        addRestaurant() {
            console.warn(this.restaurant)
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
