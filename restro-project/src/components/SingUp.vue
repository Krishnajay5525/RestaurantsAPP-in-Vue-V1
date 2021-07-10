<template>
   <img class="logo" src="../assets/krishna.png"/>
    <h3>Sing Up</h3>
    <div class="register">
     <form>
  
  <input type="text"  placeholder="Enter Name">
  
  <input type="text"  placeholder="Enter Email">
 
  <input type="password"  placeholder="Enter Password">

  <button v-on:click="signUp"> SignUp </button>
     </form>

    </div>
</template>

<script>
export default{
    name: 'SignUp',
    data()
    {
      return{
          name:'',
          email:'',
          password:''
      }
    },methods:{
        signUp()
        {
     console.warn("signUp")
        }
    }
}
</script>

<style>
.register input
{
  width:300px;
  display:block;
  height:38px;
  border:1px solid skyblue;
  margin-bottom: 1em;
  padding-left: 20px;
  font-size: 14px;
  margin-left: auto;
  margin-right: auto;
  border-radius: 2px;
  
}

.register button
{
  width:320px;
  display:block;
  height:38px;
  border:1px solid skyblue;
  margin-bottom: 1em;
  padding-left: 20px;
  font-size: 14px;
  margin-left: auto;
  margin-right: auto;
  border-radius: 2px;
  cursor: pointer;
  background: skyblue;
  color:#fff;
  font-weight: 600;;
  
}

</style>