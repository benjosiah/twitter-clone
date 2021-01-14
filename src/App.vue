<template>
  <div id="app" class="container bg-blue">
      <side/>
    <!-- tweets -->
    <div class="tweets">


    </div>
    <!-- explore  -->
    <div class="explore">
      <input type="text" placeholder="search twitter">
      <i class="fas fa-search" ></i>
    </div>
  </div>
</template>

<script>
import Sidebar from "./components/HelloWorld"
export default {
  name: 'App',
  components: {
  "Side":Sidebar
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
      trending: [
        {top: 'Trending in TX', title: 'Gigi', bottom: 'Trending with: Rip Gigi'},
        {top: 'Music', title: 'We Won', bottom: '135K Tweets'},
        {top: 'Pop', title: 'Blue Ivy', bottom: '40k tweets'},
        {top: 'Trending in US', title: 'Denim Day', bottom: '40k tweets'},
        {top: 'Trending', title: 'When Beyonce', bottom: '25.4k tweets'},
      ],
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
   .explore{
    flex:2;
    border-right:1px solid rgb(211, 211, 208);
    height:100vh;
    padding: 10px 20px;overflow-y: scroll;
    position: relative;
  
  }
  
  .explore input{
     border:1px solid rgb(211, 211, 208);
     background: rgb(225, 226, 228);
     width: 70%;
     border-radius: 30px;
     padding:10px 30px;
  }
  .explore input:focus{
    outline: none;
    
    border:1px solid rgb(151, 173, 214);
  }
  .fa-search{
    position: absolute;
    left: 0px;
    top: 0px;
    margin-left: 30px;
    margin-top: 20.5px;
   color: rgb(161, 162, 165);
  }
  .tweets{
    flex:3;
    border-right:1px solid rgb(211, 211, 208);
    height:100vh;
  }
</style>
