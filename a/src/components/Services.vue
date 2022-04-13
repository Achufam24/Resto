<template> 
<transition name="des" appear>
     <div >
    <div style="margin-top:100px;" class="rotate">
  <h1>Resto Services</h1>
<div class="container">
<div class="card">
  <img src="@/assets/data.svg" alt="advert">
  <p>Manage Restaurant data</p>
</div>
<div class="card">
  <img src="@/assets/chef.svg" alt="advert">
  <p>List Restaurant</p>
</div>
<div class="card">
  <img src="@/assets/advert.svg" alt="advert">
  <p>Adverts and Reconmendations</p>
</div>
</div>
</div>
</div>
</transition>
</template>

<script>
export default {
    name:'Services'
}
</script>

<style scoped>
.container{
  width: 100%;
  height: auto;
  margin-top: 20px;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
}

.card{
  width: 25%;
  height: auto;
  box-shadow: rgba(0, 0, 0, 0.19) 0px 10px 20px, rgba(0, 0, 0, 0.23) 0px 6px 6px;
}
.card img{
  width: 200px;
  height: 200px;
}
.des-enter-from{
  opacity: 0;
  transform: translateY(-300px)
}
.des-enter-to{
  opacity: 1;
  transform: translateY(0px)
}
.des-enter-active{
  transition: all 9s ease;
}
.des-leave-from{
 opacity: 1;
  transform: translateY(0)
}
.des-leave-to{
opacity: 0;
transform: translateY(-300px)
}
.des-leave-active{
  transition: all 9s ease;
}
@keyframes wobble {
  0% {transform: translateY(-300px); opacity: 0}
  50% {transform: translateY(0px); opacity: 1;}
}
 @media only screen and (max-width: 600px) {
    .container{
      display: block;
    }
    .card{
      width: 90%;
      align-items: center;
      margin-top: 10px;
      margin-left: 20px;
    }
 }
</style>

