<template>
  <div class="sm:flex block h-screen w-full overflow-hidden">
      <side class="lg:w-1/5 min-h-full border-grey-lighter border-r border-solid px-2 lg:px-8 py-2 overflow-y-scroll hidden sm:block"/>
    <!-- tweets -->
    <div class="lg:w-1/2 h-screen">
      <div class="top flex justify-between items-center border-0 border-solid border-b border-grey-lighter px-5 py-3 bg-white" >
       <div class="flex ">
         <img src="699698.jpg" class="sm:hidden block w-12 h-12 rounded-full mr-4">
        <h1 class="font-bold text-xl " >
          Home
        </h1>
       </div>
        <i class="far fa-star text-blue text-xl"></i>
      </div>
      <div class="overflow-y-scroll overflow-x-hidden tweet relative">
      <div class=" border-0 px-5 py-3 border-b-8 border-grey-lighter border-solid sm:flex hidden" >
        <div>
           <img src="699698.jpg" class="w-12 h-12 rounded-full">
        </div>
        <form class="w-full px-4 relative">
          <textarea placeholder="What's Happening?" class=" mt-3 pb-3 w-full focus:outline-none border-0"/>
          <div class="flex justify-between items-center">
          <div>
            <i class="text-xl text-blue mr-4 far fa-image"></i>
            <i class="text-xl text-blue mr-4 fas fa-film"></i>
            <i class="text-xl text-blue mr-4 far fa-chart-bar"></i>
            <i class="text-xl text-blue mr-4 far fa-smile"></i>
          </div>

          <button class="h-10 px-4 font-semibold text-white rounded-full bg-blue hover:bg-blue-dark border-0 focus:outline-none">
            tweet
          </button>
          </div>
        </form>
      </div>
      <div  v-for="follow in following" v-bind:key="follow" class="flex hover:bg-grey-lighter  w-full p-4 border-0 border-b border-solid border-grey-lighter">
        <div class="flex-none mt-4 mr-4">
          <img :src="`${ follow.src }`" class=" w-12 h-12 rounded-full flex-none">
        </div>
        <div class="w-full m-0">
          <div class="flex w-full justify-between">
            <div class="flex items-center m-0">
              <p class="font-semibold">{{follow.name}}</p>
              <p class="text-sm text-dark ml-2">{{follow.handle}}</p>
              <p class="text-sm text-dark ml-2">{{follow.time}}</p>
            </div>
            
            <i class="fas fa-ellipsis-h text-lg text-dark text-left  font-semibold"></i>
          </div>
          <p class="m-0">{{follow.tweet}}</p>
          <div class="flex justify-between items-center">
            <div class="flex text-sm items-center" > 
              <i class="mr-2 far fa-comment "></i>
              <p>{{follow.comments}}</p>
            </div>
             <div class="flex text-sm items-center"> 
              <i class="mr-2 fas fa-retweet"> </i>
              <p>{{follow.retweets}}</p>
            </div>
             <div class="flex text-sm items-center rounded-full hover:bg-red-lightest hover:po" > 
              <i class="mr-2 far fa-heart  "> </i>
              <p>{{follow.like}}</p>
            </div>  
            <div class="flex text-sm items-center"> 
              <i class="mr-5 fas fa-share-square"> </i>
            </div>
          </div>
        </div>
        </div>
      </div>
       <button class="h-16 w-16 text-white rounded-full absolute font-semibold bg-blue mr-4 pin-r pin-b-6 sm:hidden block">
        <i class="fas fa-plus" ></i> 
       </button>
      <div class="flex justify-between items-center px-3 sm:hidden .footer" >
        <div @click="id=tab.id"  v-for="tab in tabs" :key="tab" :class="`font-normal ${id==tab.id? 'text-blue':''}`">
          <i :class="`${tab.icon} text-2xl mr-4 text-left m-2`" ></i> 
        </div>
      </div>
    </div>
    <!-- explore  -->
    <div class="lg:block hidden w-1/3 h-full border-l border-solid border-grey-light py-2 px-6 relative overflow-y-scroll" >
      <input type="text" placeholder="search twitter" class=" mb-4 rounded-full w-4/5 p-2 pl-10 bg-grey-lightest text-sm focus:outline-none border-0" >
      <i class="fas fa-search absolute pin-t pin-l mt-5  ml-12 text-sm text-blue-light" ></i>
      <div class=" w-full rounded-lg bg-grey-lightest">
        <div class="flex items-center justify-between p-3">
          <p class="font-bold text-lg ">
            Trends for You
          </p>
           <i class="fas fa-cog text-xl text-blue"></i>
          
        </div>
        <button v-for="trend in trending" v-bind:key="trend" class=" border-0 flex justify-between w-full hover:bg-grey-lighter border-t border-grey-lighter bg-transparent" >
          <div>
            <p class="text-sm text-left  leading-tight text-dark"> {{trend.top}}</p>
            <p class="text-sm text-left  leading-tight font-bold"> {{trend.title}}</p>
            <p class="text-sm text-left  leading-tight text-dark"> {{trend.top}}</p>
          </div>
          <i class="fas fa-ellipsis-h text-lg text-dark mt-3 mr-2 font-semibold"></i>
        </button>
        <button class="border-0 w-full p-3 hover:bg-blue-lighter text-left text-blue border-t bg-transparent border-grey-lighter">
          Show more
        </button>
      </div>
      <div class=" w-full rounded-lg bg-grey-lightest mt-4" >
        <div class="flex items-center justify-between p-3">
          <p class="font-bold text-lg">
            Who to Follow
          </p>
        </div>
        <button v-for="friend in friends" v-bind:key="friend" class=" border-0 flex p-3 w-full hover:bg-blue-lighter border-t border-grey-lighter bg-transparent" >
          <img src="699698.jpg" class="w-12 h-12 rounded-full">
          <div class="ml-4 mt-1">
          <p class="text-sm font-bold leading-tight mt-0 p-0 mb-0" >{{friend.name}}</p>
          <p class="text-sm leading-tight p-0 mt-0">{{friend.handle}}</p>
          </div>
          <button class=" ml-auto text-sm py-1 px-4 rounded-full border-solid border-1 border-blue bg-white">
            follow
          </button>
        </button>
      </div>
      
    </div>
    <!-- footer  -->
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
        {icon: 'fas fa-search', title: 'Explore', id: 'explore'},
        {icon: 'far fa-bell', title: 'Notifications', id: 'notifications'},
        {icon: 'far fa-envelope', title: 'Messages', id: 'messages'},
      ],
      id :'home',
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
        {src: 'qnFYDGO9_400x400.jpg', name: 'Kevin Hart', handle: '@miniRock'}
      ],
      following: [
        {src: '6_Cnf8ED_400x400.jpg', name: "sophia's Expression", handle: '@sophia', time: '20 min', tweet: 'teach us to number our days ', comments: '1.6k', retweets: '550', like: '67k'},
        {src: '6gy2bvnB_400x400.jpg', name: 'mike Musk', handle: '@i_miky', time: '55 min', tweet: 'react is the present and future', comments: '2,030', retweets: '50', like: '20k'},
        {src: 'qnFYDGO9_400x400.jpg', name: 'The great tay', handle: '@taycode', time: '1.4 hr', tweet: 'God!!! i am broken ', comments: '106', retweets: '1k', like: '5.5k'},
        {src: '6_Cnf8ED_400x400.jpg', name: "sophia's Expression", handle: '@sophia', time: '1.4 hr', tweet: 'of your fulness have we all recieved', comments: '100k', retweets: '178', like: '600'}
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
</style>
