<template>
      <div class="foot">
        <!--footer Content-->
        <transition name="fade1" appear>
                <footer>
            <div >
            <a style="font-size:30px" href="#">Resto..</a>   
        </div>
             <div class="col1 rotate">
            <a href="#">About</a>
            <a href="#">Contact</a>
            <a href="#">Resto Quality control</a>
        </div>
        <div class="col2 rotate">
            <a href="#">Marketing Solutions</a>
            <a href="#">Advertisng</a>
            <a href="#">Terms and Conditions</a>
        </div>
        </footer>
        </transition>      
        <h4>Resto Corpoartion &copy; 2022</h4>
    </div> 
</template>

<script>
export default {
    name:'Footer'
}
</script>

<style scoped>
/*footer bbackground styling*/
.foot{ 
    margin-top: 100px;
    background:rgb(2, 2, 22);
    color: #fff; 
    padding-top: 20px;
    padding-bottom: 50px;
    position: relative;
}
/*footer bottom tag styling*/
.foot h4{
    position: absolute;
    bottom: 0;
    width: 100%;
   height: auto;
}
/*footer content display*/
footer{
    display: flex;
    justify-content: space-around;
}
.col1,.col2{
    display: flex;
    flex-direction: column;
    justify-content: space-around;
}
a{
    text-decoration: none;
    color: #fff
}
.col1 a:hover{
  text-decoration: underline;
}
.col2 a:hover{
  text-decoration: underline;
}
.fade1-enter-from{
  opacity: 0;
  transform: translateX(-300px)
}
.fade1-enter-to{
  opacity: 1;
  transform: translateX(0px)
}
.fade1-enter-active{
  transition: all 17s ease;
}
.fade1-leave-from{
 opacity: 1;
  transform: translateX(0)
}
.fade1-leave-to{
opacity: 0;
transform: translateX(-300px)
}
.fade1-leave-active{
  transition: all 17s ease;
}
@keyframes wobble {
  0% {transform: translateY(-300px); opacity: 0}
  50% {transform: translateY(0px); opacity: 1;}
}
/*responsive Footer*/
@media only screen and (max-width: 600px) {
  footer {
    display: flex;
    flex-direction: column;
  }
}
</style>


