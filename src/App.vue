<template>
  <div class="flex h-screen w-full">
      <side class="w-1/5 h-full border-blue-lighter border-r border-solid"/>
    <!-- tweets -->
    <div class="w-1/2 h-full">


    </div>
    <!-- explore  -->
    <div class="lg:block hidden w-1/3 h-full border-l border-solid border-grey-light py-2 px-6 relative overflow-y-scroll" >
      <input type="text" placeholder="search twitter" class=" mb-4 rounded-full w-4/5 p-2 pl-10 bg-blue-lightest text-sm focus:outline-none">
      <i class="fas fa-search absolute pin-t pin-l mt-5  ml-12 text-sm text-blue-light" ></i>
      <div class=" w-full rounded-lg bg-blue-lightest">
        <div class="flex items-center justify-between p-3">
          <p class="font-bold text-lg ">
            Trends for You
          </p>
           <i class="fas fa-cog text-lg text-blue"></i>
          
        </div>
        <button v-for="trend in trending" v-bind:key="trend" class=" border-0 flex justify-between w-full hover:bg-blue-lighter border-t border-blue-lighter bg-transparent" >
          <div>
            <p class="text-sm text-left  leading-tight text-dark"> {{trend.top}}</p>
            <p class="text-sm text-left  leading-tight font-bold"> {{trend.title}}</p>
            <p class="text-sm text-left  leading-tight text-dark"> {{trend.top}}</p>
          </div>
          <i class="fas fa-angle-down text-lg text-dark mt-3"></i>
        </button>
        <button class="border-0 w-full p-3 hover:bg-blue-lighter text-left text-blue border-t bg-transparent border-blue-lighter">
          Show more
        </button>
      </div>
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
        friends: [
        {src: 'elon.jpg', name: 'Elon Musk', handle: '@teslaBoy'},
        {src: 'monk.jpg', name: 'Adrian Monk', handle: '@detective:)'},
        {src: 'kevin.jpg', name: 'Kevin Hart', handle: '@miniRock'}
      ],
      following: [
        {src: 'elon.jpg', name: 'Elon Musk', handle: '@teslaBoy', time: '20 min', tweet: 'Should I just quarantine on mars??', comments: '1,000', retweets: '550', like: '1,000,003'},
        {src: 'kevin.jpg', name: 'Kevin Hart', handle: '@miniRock', time: '55 min', tweet: 'Should me and the rock do another sub-par movie together????', comments: '2,030', retweets: '50', like: '20,003'},
        {src: 'elon.jpg', name: 'Elon Musk', handle: '@teslaBoy', time: '1.4 hr', tweet: 'Haha just made a flame thrower. Shld I sell them?', comments: '100,000', retweets: '1,000,002', like: '5,000,003'},
        {src: 'elon.jpg', name: 'Elon Musk', handle: '@teslaBoy', time: '1.4 hr', tweet: 'Just did something crazyyyyyyy', comments: '100,500', retweets: '1,000,032', like: '5,000,103'}
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
  
  .tweets{
    flex:3;
    border-right:1px solid rgb(211, 211, 208);
    height:100vh;
  }
</style>
