<template>
 <div>
    <div class="bar">
        <button class="icon text-blue hover:bg-blue-lighter">
        <i class="fab fa-twitter text-blue"></i>
        </button>
        <div>
            <div class="nav mb-2">
                <button @click="id=tab.id" :class="`hover:text-blue bg-transparent hover:bg-blue-lighter rounded-full flex items-center lg:py-0 lg:mb-0 py-2 mb-3 px-4 mr-auto ${id==tab.id? 'text-blue':''}`" v-for="tab in tabs" v-bind:key="tab"> 
                   <i :class="`${tab.icon} text-2xl mr-4 text-left`" ></i> 
                    <p class=" hidden lg:block text-left font-semibold text-lg"> 
                        {{tab.title}}
                    </p>
                </button>
            </div>
            <button class="p-3 bg-blue rounded-full w-12 h-12 lg:h-auto lg:w-full text-white font-semibold hover:bg-blue-dark">
              <p class="hidden lg:block"> Tweet</p>
              <i class="fas fa-plus lg:hidden block"></i>
            </button>
        </div>
    <div style="margin:50px 0px 0px 0px; position:relative">
            <button class="pro bg-transparent" @click="dropdown=true"> 
                <img src="699698.jpg" alt="">
                <div class="hidden lg:block">
                <p> <b>me me me </b> </p>
                <p>@josiahben_</p>
                </div>
                <i class="fas fa-angle-down drop-down hidden lg:block"></i>
            </button>
            <div class="drop" v-if="dropdown==true"> 
                <button class="pro bg-transparent" @click="dropdown=false">
                    <img src="699698.jpg" alt="">
                    <div>
                        <p> <b>me me me </b> </p>
                        <p>@josiahben_</p>
                    </div>
                    <i class="fas fa-check blue drop-down"></i>
                </button>
                <button class="create bg-transparent" @click="dropdown=false" >
                    Add existing account
                </button>
                <button class="logout bg-transparent" @click="dropdown=false">
                    logout @josiahben_
                </button>
            </div>
        </div>
    </div>
</div>
</template>

<script>
export default {
   name: 'App',
  components: {
  
  },
  data(){
    return{
       tabs: [
        {icon: 'fas fa-home', title: 'Home', id:'home'},
        {icon: 'fas fa-hashtag', title: 'Explore', id: 'explore'},
        {icon: 'far fa-bell', title: 'Notifications', id: 'notifications'},
        {icon: 'far fa-envelope', title: 'Messages', id: 'messages'},
        {icon: 'far fa-bookmark', title: 'Bookmarks', id: 'bookmarks'},
        {icon: 'fas fa-clipboard-list', title: 'Lists', id: 'lists'},
        {icon: 'far fa-user', title: 'Profile', id: 'profile'},
        {icon: 'fas fa-ellipsis-h', title: 'More', id: 'more'}
      ],
      id :'home',
      dropdown:false,
    }
  
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.bar{

  }
  button{
    border: none;
     /* background: none; */
    border-radius: 30px;
  }
  .icon{
    width: 50px;
    height: 50px;
    font-size: 30px;
    background: none;
    border: none;
    border-radius: 50%;
    /* color: rgb(70, 121, 233); */
  }
 
  .menue{
    margin: 0px;
    height: auto;
    padding:0px;
    background: none;
    border: none;
    border-radius: 30px;
    display: flex;
    align-items: center;
    /* margin-right: auto; */
  }
  
  .menue:hover{
    background: lightblue;
      color: rgb(70, 121, 233);
  }
  button:focus{
    border: none;
    outline: none;
  }
  .blue{
    color: blue;
  }
  
  .menue i{
    padding-left: 10px;
    margin-right:10px;
    text-align: left;
    font-size: 16px;
  
  }
  
  .menue p{
    margin-right: 20px;
    text-align: left;
    font-size: 15px;
  
  }
  
  .pro{
    padding: 10px;
    display: flex;
    align-items: center;
  }
  .pro:hover{
    background: rgb(241, 236, 236);
  }
  .pro div{
    margin-left: 10px;
  }
  
  .pro div p{
    margin: 0px;
  }
  .pro div p b{
    font-size: 14px;
  }
  .pro img{
    width: 50px;
    height: 50px;
    font-size: 30px;
    background: none;
    border: none;
    border-radius: 50%;
    color: rgb(70, 121, 233);
  }
  
  .drop-down{
    margin-left: 20px;
    font-size: 20px;
  }
  .drop{
    position: absolute;
    border: 1px solid rgb(211, 211, 211);
    border-radius: 10px;
    left:0px;
    bottom: 50px;
    width: 200px;
    margin-bottom: 26px;
    background: white;
  
  }
  
  .drop button{
    border-radius: none;
    padding: 3px;
  }
  
  .create, .logout{
    border-top:1px gray solid;
    width: 100%;
    text-align: left;
    border-radius: 0%;
  }
  
  .create p, .logout p{ 
  padding: 30px;
  
  }
  
  

  
 
</style>
