<template>
<div class="container-All">
    <div class="back-menu">
        <div class="back-menu-center">
            <div class="logo">
                <a class="logo-link" href="#"><img class="logo" src="../assets/krishna.png" /></a>
            </div>
            <div class="let-80">
                <div class="menu-items">
                    <ul>

                        <li class="menu-item-1">
                            <router-link to="/">Home</router-link>
                        </li>
                        <li class="menu-item-2">
                            <router-link to="/add">Add Restaurant</router-link>
                        </li>

                    </ul>
                </div>
                <div class="menu-register">
                    <router-link to="/sign-up" class="register-link">Register</router-link>
                    <span style="color: #748194;font-weight: 900;">|</span>
                    <router-link to="/login" class="register-link">Login</router-link>
                    <span style="color: #748194;font-weight: 900;">|</span>
                    <a class="register-link" v-on:click="logout" href="#">LogOut</a>
                </div>
            </div>
        </div>

    </div>
</div>
</template>

<script>
export default {
    name: 'Header',
    methods: {
        logout() {
            //console.log("Logout")
            localStorage.clear();
            this.$router.push({
                name: 'Login'
            })
        }
    }
}
</script>

<style>
.container-All {
    max-width: 1840px;
    width: 100%;
    margin-right: auto;
    margin-left: auto;
}

.let-80 {
    max-width: 100%;
    width: 100%;
    position: relative;
    display: flex;
    align-items: center;
    justify-content: space-between;
    height: 50px;
}

.back-menu {
    width: 100%;
    background-color: #fff;
    margin: 0;
    box-shadow: 0px 10px 13px -6px rgb(92 92 92 / 66%);
    color: #000;
    margin: 0;
    -webkit-box-shadow: 0px 10px 13px -6px rgba(92, 92, 92, 0.66);
    -moz-box-shadow: 0px 10px 13px -6px rgba(92, 92, 92, 0.66);
    box-shadow: 0px 10px 13px -6px rgba(92, 92, 92, 0.66);
}

.back-menu-center {
    width: 90%;
    height: 100%;
    margin: 0 auto;
    display: flex;
    flex-wrap: nowrap;
}

.logo {
    width: 22%;
    height: 100%;

}

.logo-link {
    color: #000;
    font-size: 17px;
    font-weight: 800px;
    text-decoration: none;
}

.logo-link img {
    width: 132px;
}

.logo-link:nth-child(2) {
    position: relative;
    top: 32%;
    left: 5%;
}

.menu-items {
    /* background-color: red; */

    max-width: 100%;
    width: 100%;

}

.menu-items ul {
    list-style: none;
    display: flex;
}

li[class^="menu-item-"] a {
    margin: 12px 22px;
    color: #000;
    text-decoration: none;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    -webkit-transition: all 0.9s ease-in-out;
    -moz-transition: all 0.9s ease-in-out;
    -ms-transition: all 0.9s ease-in-out;
    -o-transition: all 0.9s ease-in-out;
    transition: all 0.9s ease-in-out;
}

li[class^="menu-item-"] a:hover {
    color: #dc18ff !important;
}

.menu-item-1 a {
    color: rgb(97 159 255) !important;
}

.register-link {
    color: #748194;

    margin: 0px 5px;
    text-decoration: none;
    letter-spacing: 0.5px;
}

.register,
.Login,
.contact {

    text-decoration: none;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    font-size: 12px;
    width: 400px;
    padding-bottom: 40px;
    border-radius: 15px;
    margin: auto;
    background-color: white;
    color: #748194;

}

.register h3,
.Login h3,
.contact h3 {
    color: #748194;
    font-size: 21px;
    text-align: center;
    padding-top: 30px;
    padding-bottom: 50px;
}

.register input,
.Login input,
.contact input {
    font-weight: bold;
    width: 300px;
    margin: 0 35px 20px;
    height: 35px;
    padding: 6px 15px;
    border-radius: 5px;
    outline: none;
    border: none;
    background: #F6F7F9;
    color: #748194;
    font-size: 14px;
    letter-spacing: 0.3px;

}

.register button,
.Login button,
.contact button {
    font-weight: bold;
    width: 330px;
    margin: 0 35px 20px;
    height: 45px;
    padding: 6px 15px;
    border-radius: 5px;
    outline: none;
    border: none;
    background: #EE9BA3;
    color: white;
    font-size: 14px;
    cursor: pointer;
    letter-spacing: 0.3px;

}

.table-class {
    margin: auto;
    max-width: 650px;
    width: 100%;
    border-color: #e2e8f0;
    border: 1px solid #e2e8f0;
    border-radius: 15px;
    background: #fff;
}

.table-class thead {
    background-color: #f7fafc;
    border: none;
    color: #718096
}

.table-class td,
.table-class th {
    border: 1px solid #edf2f7;
    border-width: 0 0 1px;
    vertical-align: top;
}

.table-class tr th {
    letter-spacing: 0.5px;
    padding: 0.75em;
}

.table-class tr td {
    padding: 0.75em;
    text-transform: capitalize;
    color: #718096
}

.register:hover {
    color: #dc18ff !important;
}

.container {
    max-width: 400px;
    width: 100%;
    margin: 0 auto;
    position: relative;
}

.contact button:hover {
    background: #43A047;
    -webkit-transition: background 0.3s ease-in-out;
    -moz-transition: background 0.3s ease-in-out;
    transition: background-color 0.3s ease-in-out;
}

.contact button:active {
    box-shadow: inset 0 1px 3px rgba(0, 0, 0, 0.5);
}

::-webkit-input-placeholder {
    /* Chrome/Opera/Safari */
    color: #748194;
    font-family: 'Work Sans', sans-serif;
    font-weight: normal;
    letter-spacing: 0.3px;
}

::-moz-placeholder {
    /* Firefox 19+ */
    color: #748194;
    font-family: 'Work Sans', sans-serif;
    font-weight: normal;
    letter-spacing: 0.3px;
}

:-ms-input-placeholder {
    /* IE 10+ */
    color: #748194;
    font-family: 'Work Sans', sans-serif;
    font-weight: normal;
    letter-spacing: 0.3px;
}

:-moz-placeholder {
    /* Firefox 18- */
    color: #748194;
    font-family: 'Work Sans', sans-serif;
    font-weight: normal;
    letter-spacing: 0.3px;
}
</style>
