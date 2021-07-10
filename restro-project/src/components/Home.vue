<template>
<Header />
<br>
<br>
<h1>Hello Dear {{name}}, Welcome to Home Page</h1>
<br>
<br>
<br>
<table  class="table-class">
    <thead>
        <tr>
            <th>ID</th>
            <th>Name</th>
            <th>Address</th>
            <th>Contact</th>
            <th>Actions</th>
        </tr>
    </thead>

    <tbody>
        <tr v-for="item in restaurants" :key="item.id">
            <td>{{item.id}}</td>
            <td>{{item.name}}</td>
            <td>{{item.address}}</td>
            <td>{{item.contact}}</td>
            <td>
                <router-link :to="'/update/'+item.id">Update</router-link>
            </td>
        </tr>
    </tbody>

</table>
</template>

<script>
import axios from 'axios';
import Header from './Header.vue'
export default {
    name: 'Home',

    data() {
        return {
            name: "",
            restaurants: [],
        }
    },

    components: {
        Header
    },
    async mounted() {

        let user = localStorage.getItem('user-info');
        this.name = JSON.parse(user).name;
        if (!user) {

            this.$router.push({
                name: 'SignUp'
            })

        }
        let result = await axios.get("http://localhost:3000/restaurant");
        console.warn(result);
        this.restaurants = result.data;
    }
};
</script>

<style>


</style>
