<template>

  <div id="app" >

    <b-container>
      <b-row>
        <b-col xl="6"><router-view/></b-col>

      </b-row>
    </b-container>
    <div id="navFooter">
      <router-link to="/">Home</router-link>
      <router-link to="/about">About</router-link>
      <router-link to="/about">News</router-link>
      <router-link to="/about">Contact</router-link>
    </div>
  </div>

</template>


<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #3D1132;

}

#nav{
  padding-bottom: 30px;
  display: flex;
  justify-content: center;
  flex-direction: column;
}

#navFooter{
  background-color: #FF99E6;
  padding-bottom: 30px;
  display: flex;
  justify-content: center;
  flex-direction: column;
}

#navFooter a{
  font-weight: bold;
  color: white;
  font-size: 18px;
  padding: 5px;
}
#nav a {
  font-weight: bold;
  color: #ABFF99;
  font-size: 28px;
  padding: 5px;

}

#nav a.router-link-exact-active {
  color: #FF99E6;
}


@media (min-width: 768px) {
  #nav{
    padding-bottom: 30px;
    display: flex;
    justify-content: none;
    flex-direction: row;

  }
  #navFooter{
    padding-bottom: 30px;
    display: flex;
    justify-content: none;
    flex-direction: row;
    margin-top: 15px;

  }
  #navFooter a {
    font-size: 20px;
    padding-right: 15px;
    padding-bottom: 30px;

  }

  #nav a {
    font-size: 40px;
    padding-right: 15px;
  }
}
</style>

