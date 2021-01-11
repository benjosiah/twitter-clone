<template>
  <div id="app" class="container">
   <div class="bar">
     <button class="icon">
       <i class="fab fa-twitter"></i>
     </button>
   <div>
     <div class="nav">
       <button @click="id=tab.id" :class="`menue ${id==tab.id? 'blue':''}`" v-for="tab in tabs" v-bind:key="tab"> 
          <i :class="`${tab.icon}`" ></i>
          <p>
            {{tab.title}}
          </p>
       </button>
     </div>
     <button class="tweet1">
       Tweet
     </button>
   </div>
   <div style="margin:150px 0px; position:relative">
     <button class="pro">
       <img src="699698.jpg" alt="">
       <div>
       <p> <b>me me me </b> </p>
       <p>@josiahben_</p>
       </div>
       <i class="fas fa-angle-down drop-down"></i>
     </button>
     <div class="drop">
      <button class="pro">
       <img src="699698.jpg" alt="">
       <div>
       <p> <b>me me me </b> </p>
       <p>@josiahben_</p>
       </div>
       <i class="fas fa-check blue drop-down"></i>
      </button>
      <button class="create">
        Add existing account
      </button>
      <button class="logout">
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
      id :'home'
    }
  
  }
}
</script>

<style>
body{
  padding: 0%;
  margin: 0%;
}
.container{
  display: flex;
  margin: 0px;
  width: 100%;
  height: auto;
  padding: 0%;
}
.bar{
  flex-basis:10%;
  padding: 20px 80px;
  border-right: 1px solid rgb(211, 211, 211);
  height:auto;
}
button{
  border: none;
   background: none;
  border-radius: 30px;
}
.icon{
  width: 50px;
  height: 50px;
  font-size: 30px;
  background: none;
  border: none;
  border-radius: 50%;
  color: rgb(70, 121, 233);
}
.icon:hover{
  background: rgb(191, 209, 241);
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
  margin-right: auto;
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
.tweet1{
  padding: 10px 70px;
  background: blue;
  color: #fff;
  border-radius:30px ;
  font:bold;
  margin: 10px 0px;
  font-size: 20px;


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
</style>
