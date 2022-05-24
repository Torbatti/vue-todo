<script>
export default {
    data(){
        return{
            smulSideBar: false,
            sideBarState: true
        }
    },
    methods:{
        smulSideBarHandler: function(){
            this.smulSideBar = ! this.smulSideBar;
        },
        sideBarHandler: function(){
            this.sideBarState = ! this.sideBarState;
            this.$emit('sideBarToggler');
            console.log(this.sideBarState);
        }
    },

}
</script>


<template>
    <div class="smulScreen md:hidden">
            <div class="pl-4 pt-4 bg-slate-700 h-16 w-16 fixed top-0 left-0 rounded-br-xl shadow-2xl">
                <button @click="smulSideBarHandler">
                    <span class="iconify-inline text-slate-300" data-icon="quill:hamburger" data-width="32" data-height="32"></span>
                </button>
            </div>

            <div class="pl-4 pt-4 bg-slate-700 h-screen w-48 fixed top-0 left-0" v-show="smulSideBar">
                <button @click="smulSideBarHandler" class="m-b-24" >
                    <span class="iconify-inline text-slate-300" data-icon="bi:x-lg" data-width="32" data-height="32"></span>
                </button>
            </div>
    </div>

    <div class="normalScreen w-screem h-12 bg-slate-700 hidden md:flex md:justify-between md:items-center">

            <div class="pl-4 md:flex md:justify-between md:items-center" v-show="!sideBarState">
                <button @click="sideBarHandler">
                    <span class="iconify-inline text-slate-300" data-icon="charm:screen-maximise" data-width="24" data-height="24"></span>
                </button>
            </div>

            <div class="pl-4 md:flex md:justify-between md:items-center" v-show="sideBarState">
                <button @click="sideBarHandler">
                    <span class="iconify-inline text-slate-300" data-icon="charm:screen-minimise" data-width="24" data-height="24"></span>
                </button>
            </div>
    </div>


</template>




<style>

</style>