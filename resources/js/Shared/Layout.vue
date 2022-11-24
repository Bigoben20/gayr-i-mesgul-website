<template>
    <header class="flex flex-row justify-between items-center">
        <!-- <h1 class="text-3xl">Gayr-i Meşgul</h1> -->
        
        <Navbar v-if="!mobileView"/>
        <NavbarMobile v-if="mobileView"/>

    </header>
    <section class="p-3 w-full" @click="handleClose">
        <div class="max-w-3xl mx-auto">
            <slot />
        </div>
    </section>
</template>
  
  <script>
  import Navbar from "../Shared/Navbar.vue";
  import NavbarMobile from "../Shared/NavbarMobile.vue";

  
  export default {
      components:{Navbar, NavbarMobile},
      data(){
        return{
            mobileView:false,
        }
      },
      methods:{
        handleClose(){
            this.showNav = false
        },
        toggleMobile(){
          this.mobileView = window.innerWidth < 920
        }
      },
      created(){
        this.toggleMobile()
        window.addEventListener('resize', this.toggleMobile)
      }
  }
  </script>
  
  <style scoped>

    header{
    background-color: rgb(245, 245, 245,0.2);
    padding: 16px 24px ;
    color: var(--color-two);
    border-radius: 20px;
    }
    section{
    border-radius: 10px;
    min-height: 100%;
    height: 100%;
    padding: 24px 0;

    }
    
  </style>