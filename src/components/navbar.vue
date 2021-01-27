<template>
  <div class="flex px-4 justify-between h-16 w-full font-serif text-gray-200 items-center color">
    <div>
      <img src="" class="w-1/12 h-6" alt="">
    </div>
    <div>
      <h1 class="navbar-title">PastiWork</h1>
    </div>
    <div>
      <div class="rounded-full h-14 w-14 flex items-center justify-center bg-gray-100">
        <img src="../assets/1200px-User_font_awesome.svg.png" class="h-10 w-10 justify-center flex" alt="user">
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'navbar',
};
</script>

<style scoped>
  @tailwind base;
  @tailwind components;
  @tailwind utilities;

  .color {
    background-image: linear-gradient(to right, #5eaaa8, #6fb7b0, #80c3b9, #92d0c2, #a3ddcb);
  }
  .navbar-title{
    font-size: x-large;
  }

  .circulo {

    -moz-border-radius: 50%;
    -webkit-border-radius: 50%;
    border-radius: 50%;
    background: #ffffff;
  }
</style>
