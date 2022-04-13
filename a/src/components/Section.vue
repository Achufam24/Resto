<template>
    <div class="row2">
        <div class="rotate" >
            <h1>Restaurant in one tap!</h1>
            <h3>Make your Restaurant visible to Millions</h3>
            <p>Register and add your Restaurant</p>
            <router-link to="SignUp" @click="Register">Register</router-link>

        </div>
        <div class="rotate">
            <img src="@/assets/resto.svg" class="img-fluid"  alt="">
        </div>
    </div>
</template>


<script>
export default {
    name:'Section',
  
}
</script>

<style scoped>
.row2{
    display: flex;
    justify-content: space-around;
    margin: 100px;
}
img{
    width: 400px;
    height: auto;
}
a{
    background: rgb(2, 2, 68);
    color: antiquewhite;
    padding: 5px;
    text-decoration: none;
    border-radius: 5px;
}
@media only screen and (max-width: 600px) {
  .row2 {
    display: flex;
    flex-direction: column-reverse;
  }
}
</style>

