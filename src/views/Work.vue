<template>
  <div class="about">
    <div class="flex ">
      <div class="flex ">
        <button type="button" class="button3">Primary</button>
        <input type="text" class="">
      </div>
      <div class="flex">
        <div class="w-2/3 "></div>
        <div class="1/3"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Work',
};
</script>

<style scoped>
  .button3{
    display:inline-block;
    padding:0.3em 1.2em;
    margin:0 0.3em 0.3em 0;
     border-radius:2em;
    box-sizing: border-box;
    text-decoration:none;
    font-family:'Roboto',sans-serif;
    font-weight:300;
    color:#FFFFFF;
    background-color:#228CDA;
    text-align:center;
    transition: all 0.2s;
  }
  .button3:hover{
    background-color:#4095c6;
  }
  @media all and (max-width:30em){
    .button3{
      display:block;
      margin:0.2em auto;
    }
  }
</style>
