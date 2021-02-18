<template>
    <div>
      <section class="nav_bar flex items-center h-12 bg-black pl-8 ">
          <!-- med and large nav contents -->
          <div class="hidden md:flex items-center w-full">
              <div class="text-white text-4xl">
                  <h1>LOGO</h1>
              </div>
              <ul class="text-white w-full flex flex-grow justify-around">
              <li>One</li>
              <li>Two</li>
              <li>Three</li>
              <li>Four</li>
          </ul>
          </div>
          <div class="flex md:hidden">
              <img class="w-8" @click="tog" src="../static/menu.svg" alt="">
          </div>
      </section>
      <!-- mobile nav -->
      <section v-bind:class="{'closed' : isClosed}" class="bg-black text-white absolute h-full top-0 mob_nav pl-10 pt-4">
         <img @click="tog" class="w-4 pb-8" src="../static/cancel.svg" alt="">
          <ul>
              <li>One</li>
              <li>Two</li>
              <li>Three</li>
              <li>Four</li>
          </ul>
      </section>
    </div>
</template>

<script>
export default {
   data(){
       return {
           isClosed: true
       }
   },
   methods: {
       tog(){
           if(this.isClosed) {
               this.isClosed = false
           } else {
               this.isClosed = true;
           }
       }
   }
}
</script>

<style scoped>
    .mob_nav {
        width: 200px;
        transition: all .3s cubic-bezier(0, .52, 0, 1);
    }
    .closed {
        margin-left: -200px;
        transition: all .3s cubic-bezier(0, .52, 0, 1);
    }

</style>