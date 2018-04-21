<template>
  <div id="app">
    <div class="navbar">
      <md-menu class="topItem">
        <md-button md-menu-trigger>Default</md-button>

        <md-menu-content class="item">
          <md-menu-item>My Item 1</md-menu-item>
          <md-menu-item>My Item 2</md-menu-item>
          <md-menu-item>My Item 3</md-menu-item>
        </md-menu-content>
      </md-menu>
      <md-menu class="topItem">
        <md-button md-menu-trigger>Default</md-button>

        <md-menu-content class="item">
          <md-menu-item>My Item 1</md-menu-item>
          <md-menu-item>My Item 2</md-menu-item>
          <md-menu-item>My Item 3</md-menu-item>

          <md-menu-item>My Item 4</md-menu-item>
        </md-menu-content>
      </md-menu>
    </div>


    <md-card class="card" md-with-hover v-for="card in cards">
      <md-card-media>
        <img v-bind:src="card.urlImg">
      </md-card-media>

      <md-card-header>
        <div class="md-title">{{ card.title }}</div>
        <div class="md-subhead">Subtitle here</div>
      </md-card-header>

      <md-card-actions>
        <md-button class="md-accent" @click="first = true">Buy </md-button>
        <md-button>View More</md-button>
      </md-card-actions>
    </md-card>





    <div class="actionButtons">
      <md-button class="md-fab"  style="background-color: cornflowerblue; color: white;">
        <md-icon>edit</md-icon>
      </md-button>

      <md-button class="md-fab md-primary" style="background-color: gold; color: white;">
        <md-icon>email</md-icon>
      </md-button>

      <md-button class="md-fab md-warn" style="background-color: lawngreen; color: white;"  md-with-hover>
        <md-icon>save</md-icon>
      </md-button>

      <md-button class="md-fab md-clean" style="background-color: lightcoral; color: white;">
        <md-icon>dialpad</md-icon>
      </md-button>

      <md-button class="md-fab" style="background-color: cornflowerblue; color: white;">
        <md-icon>message</md-icon>
      </md-button>
    </div>



  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'


export default {
  name: 'App',
  data: function(){
    return {
      cards: [
        {
          'title': 'iPhone 6',
          'urlImg': 'https://assets.pcmag.com/media/images/441875-iphone-6-inline-2.jpg?thumb=y&width=980&height=552'
        },
        {
          'title': 'iPhone 5',
          'urlImg': 'https://p1.akcdn.net/full/217009883.apple-iphone-5s-16gb.jpg'
        },
        {
          'title': 'Samsung S9',
          'urlImg': 'https://p1.akcdn.net/full/217009883.apple-iphone-5s-16gb.jpg'
        },
        {
          'title': 'Xiaomi Redmi 5',
          'urlImg': 'https://p1.akcdn.net/full/217009883.apple-iphone-5s-16gb.jpg'
        },
        {
          'title': 'iPhone 6',
          'urlImg': 'https://p1.akcdn.net/full/217009883.apple-iphone-5s-16gb.jpg'
        },
        {
          'title': 'iPhone 5',
          'urlImg': 'https://p1.akcdn.net/full/217009883.apple-iphone-5s-16gb.jpg'
        },
        {
          'title': 'Samsung S9',
          'urlImg': 'https://p1.akcdn.net/full/217009883.apple-iphone-5s-16gb.jpg'
        }
      ],
      first: false
    }
  }

}




</script>





<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding: 20px;
  width: 1000px;
  margin: 0 auto;
}

.card{
    width: 300px;
    float: left;
    margin-left: 15px;
    margin-top: 20px;
}

.card img {
  height: 260px;
}
.dialogWindow{
  background-color: white;
  width: 450px;
  height: 200px;
  font-size: 25px;
}
  .navbar{
    height: 80px;
    margin-top: 20px;
    margin-bottom: 10px;
    box-shadow: 0 3px 1px -2px rgba(0,0,0,.2),0 2px 2px 0 rgba(0,0,0,.14),0 1px 5px 0 rgba(0,0,0,.12);
    padding: 23px;
  }
  .topItem{
    float: right;

  }
  .item{
    z-index: 20;
    background-color: white;

  }
  .actionButtons{
    width: 40px;
    align-content: center;
    position: fixed;
    bottom: 24px;
    right: 36px;
  }
  .md-button{
    margin-left: 0px;
  }
</style>
