<template>
  <div id="app">
    <div id="menu">
      <div id="brand">
        <router-link to="/">
          <img src="/images/logo.png">
        </router-link>
      </div>
      <div id="side">
        <router-link to="/browse">
          <div class="menu-item browse">
            <img src="/images/globe.png">
            <p>Browse</p>
          </div> 
        </router-link>
        <router-link to="/cart">
          <div class="menu-item">
            <img src="/images/love.png">
            <p> {{numItems}} items</p>
          </div>
        </router-link>
      </div>
    </div>
    <router-view/>
    <div class="footer-container">
      <div class="footer">
        ALL CONTENT COPYRIGHT 2020 MOTHER_EARTH
        <a href="https://github.com/BYUCS260/grocery-store-weberadam12.git"><img src="/images/github.png"></a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
    }
  },
  computed: {
    numItems() {
      return this.$root.$data.cart.length;
    }
  },
}
</script>

<style>
* {
  box-sizing: border-box;
}
body {
  margin: 50px 100px;
}
#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px; 
  grid-template-areas: "none brand side"; 
  margin-bottom: 50px;
}
#menu a {
  color: #B84901; 
}

#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}
#brand img {
  height: 200px;
}
#side {
  grid-area: side;
  display: flex;
  justify-content: flex-end;
}
#side img {
  width: 50px;
}
.menu-item {
  display: flex;
  flex-direction: column;
}
.menu-item p {
  margin: 0px;
}
.browse {
  margin-right: 50px;
}
.footer-container {
  background-color: white;
  width: 100%;
  height: 50px;
  position: fixed;
  bottom: 0;
  padding-left: 550px;
}
.footer img {
  width: 30px;
  height: 30px;
}
</style>
