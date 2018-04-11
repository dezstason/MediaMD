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

    <md-card class="card" md-with-hover>
      <md-card-media>
        <img src="logo.jpg" >
      </md-card-media>

      <md-card-header>
        <div class="md-title">Title goes here</div>
        <div class="md-subhead">Subtitle here</div>
      </md-card-header>

      <md-card-actions>
        <md-button>Buy</md-button>
        <md-button>View More</md-button>
      </md-card-actions>
    </md-card>

    <md-card class="card" md-with-hover>
      <md-card-media>
        <img src="logo.jpg" >
      </md-card-media>

      <md-card-header>
        <div class="md-title">Title goes here</div>
        <div class="md-subhead">Subtitle here</div>
      </md-card-header>

      <md-card-actions>
        <md-button>Buy</md-button>
        <md-button>View More</md-button>
      </md-card-actions>
    </md-card>

    <md-card class="card" md-with-hover>
      <md-card-media>
        <img src="logo.jpg" >
      </md-card-media>

      <md-card-header>
        <div class="md-title">Title goes here</div>
        <div class="md-subhead">Subtitle here</div>
      </md-card-header>

      <md-card-actions>
        <md-button>Buy</md-button>
        <md-button>View More</md-button>
      </md-card-actions>
    </md-card>

    <md-card class="card" md-with-hover>
      <md-card-media>
        <img src="logo.jpg" >
      </md-card-media>

      <md-card-header>
        <div class="md-title">Title goes here</div>
        <div class="md-subhead">Subtitle here</div>
      </md-card-header>

      <md-card-actions>
        <md-button>Buy</md-button>
        <md-button>View More</md-button>
      </md-card-actions>
    </md-card>

    <md-card class="card" md-with-hover>
      <md-card-media>
        <img src="logo.jpg" >
      </md-card-media>

      <md-card-header>
        <div class="md-title">Title goes here</div>
        <div class="md-subhead">Subtitle here</div>
      </md-card-header>

      <md-card-actions>
        <md-button>Buy</md-button>
        <md-button>View More</md-button>
      </md-card-actions>
    </md-card>

    <md-card class="card" md-with-hover>
      <md-card-media>
        <img src="logo.jpg" >
      </md-card-media>

      <md-card-header>
        <div class="md-title">Title goes here</div>
        <div class="md-subhead">Subtitle here</div>
      </md-card-header>

      <md-card-actions>
        <md-button>Buy</md-button>
        <md-button>View More</md-button>
      </md-card-actions>
    </md-card>

    <md-card class="card">
      <md-card-media>
        <img src="logo.jpg" alt="People">
      </md-card-media>

      <md-card-header >
        <div class="md-title" v-for="card in cards">{{card.title}}</div>
        <div class="md-subhead">Subtitle here</div>
      </md-card-header>

      <md-card-actions>
        <md-button v-on:click = "fillCard()">Action</md-button>
        <md-button>Action</md-button>
      </md-card-actions>
    </md-card>

    <md-card class="card">
      <md-card-area>
        <md-card-media>
          <img src="/assets/examples/card-image-1.jpg" alt="People">
        </md-card-media>

        <md-card-header>
          <div class="md-title">Actions left aligned</div>
          <div class="md-subhead">Subtitle here</div>
        </md-card-header>

        <md-card-content>
          Lorem ipsum dolor sit amet, consectetur adipisicing elit. Optio itaque ea, nostrum odio. Dolores, sed accusantium quasi non, voluptas eius illo quas, saepe voluptate pariatur in deleniti minus sint. Excepturi.
        </md-card-content>
      </md-card-area>

      <md-card-actions md-alignment="left">
        <md-button>Action</md-button>
        <md-button>Action</md-button>
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
  name: 'ProgressBarQuery',
  data: function(){
    return {
      cards: []
    }
  },
  methods: {
    fillCard: function(){
      this.cards.push({title: 'Stanislav title'})
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
    position: absolute;
    bottom: 24px;
    right: 36px;
  }
  .md-button{
    margin-left: 0px;
  }
</style>
