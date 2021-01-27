<template>
  <div class="h-full">
    <div class="hidden sm:block" style="width: 4rem"></div>
    <div class="fixed z-20" :class="!isExpanded ? ['hidden', 'sm:block'] : ''">
      <div class="color h-screen text-white overflow-x-hidden"
           :class="[isExpanded ? 'w-64' : 'w-16', transitionRunning]"
           @mouseenter="onEnter"
           @mouseleave="onLeave">
        <div class="p-4 py-1 flex items-center color h-12 cursor-pointer">
          <img @click="$router.push({ name: 'home' })" src="../assets/Grass.png" alt="logo" class="h-8 w-8">
        </div>
        <ul class="mt-2 text-gray-500">
          <li class="py-3 cursor-pointer strong-color hover:text-white flex row-style" @click="$router.push({ name: 'work' })">
            <span v-show="isExpanded" class="relative ml-8 whitespace-no-wrap">Equipos</span>
          </li>
          <li class="py-3 cursor-pointer strong-color hover:text-white flex row-style" @click="$router.push({ name: 'about'  })">
            <span v-show="isExpanded" class="relative ml-8 whitespace-no-wrap ">
              Trabajos
            </span>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    props: ['active'],
    data () {
      return {
        isExpanded: false,
        transitionRunning: null,
        disableMouseEvents: false
      }
    },
    methods: {
      onEnter () {
        if (this.disableMouseEvents) return
        this.disableMouseEventsMeanwhile(200)
        this.isExpanded = true
        this.transitionRunning = 'expand'
      },
      onLeave () {
        if (this.disableMouseEvents) return
        this.disableMouseEventsMeanwhile(200)
        this.isExpanded = false
        this.transitionRunning = 'contract'
      },
      close () {
        this.disableMouseEventsMeanwhile(200)
        this.isExpanded = false
        this.$emit('update:active')
        this.transitionRunning = 'contract'

      },
      disableMouseEventsMeanwhile(milliseconds) {
        this.disableMouseEvents = true
        setTimeout(() => this.disableMouseEvents = false, milliseconds)
      }
    },
    watch: {
      active (isActive) {
        this.transitionRunning = 'expand'
        this.isExpanded = isActive
        if (isActive) this.disableMouseEvents = true
      }
    }
  }
</script>

<style scoped>
  @tailwind base;
  @tailwind components;
  @tailwind utilities;
  .expand {
    animation-name: expand;
    animation-duration: 200ms;
  }

  @keyframes expand {
    from {
      width: 4rem;
    }
    to {
      width: 16rem;
    }
  }

  .contract {
    animation-name: contract;
    animation-duration: 200ms;
  }

  @keyframes contract {
    from {
      width: 16rem;
    }
    to {
      width: 4rem;
    }
  }

  .row-style:hover{
    border-bottom: solid 1px slategray;
    border-top: solid 1px slategray;
  }
  .color{
    background: #5EAAA8;
  }
  .strong-color:hover{
    background: #529b99;
  }
  .paddingIcon{

  }
</style>
