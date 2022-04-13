<template>
<!--REsponsive Nav-->
<nav class="navbar navbar-expand-lg navbar-dark " style="height:70px; position:sticky; top:0;">
    <div class="container">
        <a href="#" class="navbar-brand">
            <span class="fw-bold text-light"><p style=" margin-left:2px; font-size:20px;">RESTO</p></span>
        </a>
       <!-- Nav button toggler-->
        <button @click="toggleNav"   class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon rotate" ></span>
        </button>
        <!--Navigation Content--> 
              <div v-show="showNav" class="collapse navbar-collapse" id="navbarNav">
            <div class="navbar-nav ms-auto" >  
                     <router-link class="nav-link text-light" to="/" >Home</router-link>
                     <router-link class="nav-link text-light" to="Add" >Add Resturant</router-link>
                     <router-link class="nav-link text-light"  to="SignUp" @click="Register">Register</router-link>
                     <router-link class="nav-link text-light"  to="Login" @click="logout">Logout</router-link>
               </div> 
        </div>
    </div>
</nav> 
</template>
           

<script>
export default {
    name:'Header',
   data() {
        return {
            showNav:'true'
        }
    },
    methods: {
        /*login routing*/
        logout()
        {
            localStorage.clear();
            this.$router.push({name:'Login'})
        },
        /*signup view routing*/
        Register()
        {
            localStorage.clear();
           this.$router.push({name:'SignUp'})
        },
        /*responsive menu toggling*/
     /* toggleNav(){
          this.showNav=!this.showNav
      }*/
    },
}
</script>

<style>
header{
   /* background: rgb(2, 2, 22);*/
    height: 50px;
    margin-top: 0;
    width: 100%;
    overflow: hidden;
    background: #fff;
    height: auto;
    box-shadow: rgba(50, 50, 93, 0.25) 0px 13px 27px -5px, rgba(0, 0, 0, 0.3) 0px 8px 16px -8px;
    }
    .nav1{
        display: flex;
        justify-content: space-between;
    }
    /*router styling*/
    .navbar a{
        color: #fff;
        padding: 14px 16px;
        text-align: center;
        font-size: 17px;
    }
    .navbar{
        background: rgb(2, 2, 22);
        color: #fff;
    }
    .navbar-toggler,.navbar-toggler-icon{
        border: none;
    }
    button:focus,button:active {
   box-shadow: none !important;
   color: goldenrod !important;
    }
   .rotate {
  animation: rotation 1s  linear;
  animation-delay: 0s;
}
@keyframes rotation {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(359deg);
  }
}
    
span:active{
    opacity: 0;
}
    /* responsive screen sizes*/
 @media only screen and (max-width: 900px) {
   .navbar{
       height: 100%; 
   }
   nav{
       height: auto !important;
   }
}
</style>



