<template>
  <nav class="orange darken-1">
    <div class="nav-wrapper ">
      <a href="#" class="brand-logo">Logo</a>
      <ul id="nav-mobile" class="right hide-on-med-and-down">
        <li>
          <a href="sass.html">User</a>
        </li>
        <li>
          <a href="badges.html">Log out</a>
        </li>
       
      </ul>
    </div>
  </nav>
</template>

<script>
// @ is an alias to /src

export default {
  name: "navbar"
};
</script>
<style scoped>
  nav{
    padding-left: 10px;
    
  }
  nav a{
    color: rgb(36, 34, 34)
  }
</style>