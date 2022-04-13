<template>
<div>
 <Header/>
 <transition name="fade" appear>
    <div>
      <div style="margin-top:30px;">
  <h1>Hello {{name}}, welcome to Resto!</h1>
    <p>Your Restaurant Management App</p>
 </div>
    <Section/>
    <h3>Restaurant List</h3>
    <table border="1" class="table table-striped" >
        <tr>
            <th>ID</th>
            <th>NAME</th> 
            <th>CONTACT</th>
            <th>ADDRESS</th>
            <th>ACTIONS</th>
        </tr>
        <tr v-for="item in resturant" :key="item" >
            <td>{{item.id}}</td>
            <td>{{item.name}}</td>
            <td>{{item.contact}}</td>
            <td>{{item.address}}</td>
            <td><router-link :to=" '/Update/'+item.id" id="update" >Update</router-link>
            <button @click="deleteResturant(item.id)" style="padding-top:3px; margin-top:4px;">Delete</button>
            </td>
        </tr>
    </table>
 </div>
 </transition>
 
 
    <!-- Button trigger modal -->

  <Services/>
    <Footer/>
</div>
</template>

<script>
import Header from '../components/Header.vue'
import Section from '../components/Section.vue'
import Services from '../components/Services.vue'
import Footer from '../components/Footer.vue'
import axios from 'axios'

export default {
    name: 'Home',
    data() {
        return {
            name:'',
            resturant:[]
        }
    },
    components:{
        Header,Section,Services,Footer
        },
        methods: {
         async deleteResturant(id)
         {
            let result = await axios.delete("http://localhost:3000/resturant/"+id);
            console.warn(result)
            if (result.status==200) 
            {
                this.loadData()
            }
            },
       async loadData()
       {
           let user = localStorage.getItem('user-info');
        this.name= JSON.parse(user).name;
        if(!user){
            this.$router.push({name:'SignUp'})
        }
        let result = await axios.get('http://localhost:3000/resturant');
        this.resturant= result.data;
       }      
        },
    async mounted() 
    {
       this.loadData();
    },
}
</script>
<style scoped>
table{
    margin-left: 10%;
width: 80%;
border-collapse: collapse;
overflow: scroll;
box-shadow: rgba(50, 50, 93, 0.25) 0px 13px 27px -5px, rgba(0, 0, 0, 0.3) 0px 8px 16px -8px;
}
th{
    height: 60px;
}
td{
    height: 70px;
}
tr:hover{
    background: #fff;
}
#update{
    margin-right: 6px;
    border-radius: 5px;
    background: green;
    color: #fff;
    padding: 2px;
    text-decoration: none;
    
}
td button{
    border: none;
    background: rgb(205, 12, 12);
    width: 3.4rem;
    height: 1.5rem;
    border-radius: 5px;
    color: #fff;
}
.fade-enter-from{
  opacity: 0;
  transform: translateX(-60px)
}
.fade-enter-to{
  opacity: 1;
  transform: translateX(0px)
}
.fade-enter-active{
  transition: all 5s ease;
}
.fade-leave-from{
 opacity: 1;
  transform: translateX(0)
}
.fade-leave-to{
opacity: 0;
transform: translateX(-60px)
}
.fade-leave-active{
  transition: all 5s ease;
}
@keyframes wobble {
  0% {transform: translateY(-300px); opacity: 0}
  90% {transform: translateY(0px); opacity: 1;}
}
</style> 


