<script>
import NavBar from './components/Navbar.vue'
import SideBar from "./components/Sidebar.vue"
import TodoList from "./components/Todolist.vue"

export default {
    components:{
        NavBar,
        SideBar,
        TodoList,
    },
    data(){
      return{
        sideBarState: true,
      }
    },
    methods:{
      sideBarToggler : function(){
        this.sideBarState = ! this.sideBarState;
      }
    }
}

</script>

<template>
  <NavBar @sideBarToggler="sideBarToggler"/>

  <div class="w-screen bg-slate-200 hidden md:flex">
      <SideBar :sideBarState="sideBarState"/>
      <TodoList />
  </div>

</template>

<style>
@import './assets/base.css';

</style>
