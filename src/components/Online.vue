<template>
  <div class="online">
    <p class="noMr">Name <span></span></p>
  </div>
</template>

<script>
// @ is an alias to /src


export default {
  name: 'online',
  
}
</script>
<style scoped>
  .online{
    display:flex;
    justify-content: center;
    padding-top: 20px;
    max-width: 100%;
    height: calc(100vh - 64px);
    background:  rgb(249, 247, 247);
     -webkit-box-shadow: 0 2px 2px 0 rgba(0,0,0,0.14), 0 3px 1px -2px rgba(0,0,0,0.12), 0 1px 5px 0 rgba(0,0,0,0.2); 
    box-shadow: 0 2px 2px 0 rgba(0,0,0,0.14), 0 3px 1px -2px rgba(0,0,0,0.12), 0 1px 5px 0 rgba(0,0,0,0.2);
    
}
  
  
  span{
    display: inline-block;
    background: rgb(23, 218, 23);
    width: 15px;
    height: 15px;
    border-radius: 50%;
    
  }
  .noMr{
    margin-top: 0;
  }
</style>