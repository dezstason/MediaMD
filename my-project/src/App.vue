<template>
  <div id="app">

    <!-- NAVBAR OF THE SITE -->

    <div class="navbar">
      <md-menu class="topItem" style="float: left;">
        <p id="logo"> <i class="material-icons">&#xE8CB;</i>ONLINE SHOP</p>
      </md-menu>
      <md-menu class="topItem">
        <md-button md-menu-trigger>My Account</md-button>

        <md-menu-content class="item">
          <md-menu-item>Register</md-menu-item>
          <md-menu-item>Log In</md-menu-item>
        </md-menu-content>
      </md-menu>

      <md-menu class="topItem">
        <md-button md-menu-trigger>
          <i class="badge" :md-active.sync = "visib" v-if="newPosts">{{ newPosts }}</i>Cart</md-button>
        <md-menu-content class="item" >
          <md-menu-item>Your Cart</md-menu-item>
          <md-menu-item><hr style="width: 100%"></md-menu-item>
          <md-menu-item v-for="order in orders">{{ order.title }}  &#160 &#160 &#160 &#160 &#160{{ order.price}}$</md-menu-item>
        </md-menu-content>
      </md-menu>
    </div>

    <!-- TABS WITH CARDS AND OTHER INFORMATION -->

    <md-tabs md-sync-route class="tabs">
      <md-tab id="tab-home" md-label="Home" to="/components/tabs/home">

        <md-card class="card" md-with-hover v-for="card in cards">
          <md-card-media>
            <img v-bind:src="card.urlImg">
          </md-card-media>

          <md-card-header>
            <div class="md-title">{{ card.title }}</div>
            <div class="md-subhead">{{ card.price }} $</div>
          </md-card-header>

          <md-card-actions>
            <md-button class="md-accent" @click="first = true; newPosts += 1; visib = true; orderAdd(card.title, card.price)" md-ripple>Buy </md-button>
            <md-button class="md-accent" @click="second = true">View More</md-button>
          </md-card-actions>
        </md-card>

      </md-tab>

      <md-tab id="tab-pages" md-label="Pages" to="/components/tabs/pages">
        Pages tab
        <p>Unde provident nemo reiciendis officia, possimus repellendus. Facere dignissimos dicta quis rem. Aliquam aspernatur dolor atque nisi id deserunt laudantium quam repellat.</p>
      </md-tab>

    </md-tabs>

    <!-- LEFT BOTTOM CORNER BUTTONS -->

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

    <!-- DIALOG WINDOW -->

    <md-dialog-alert
      :md-active.sync="first"
      md-content="Your order was added to cart"
      md-confirm-text="Cool!"
      class="dialogWindow"
    />
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
          'urlImg': 'https://assets.pcmag.com/media/images/441875-iphone-6-inline-2.jpg?thumb=y&width=980&height=552',
          'price' : 700
        },
        {
          'title': 'iPhone 5',
          'urlImg': 'https://p1.akcdn.net/full/217009883.apple-iphone-5s-16gb.jpg',
          'price' : 700
        },
        {
          'title': 'Samsung S9',
          'urlImg': 'https://htstatic.imgsmail.ru/pic_image/126ac6cb7c7b167974345444bed93d37/410/329/1252342/',
          'price' : 850
        },
        {
          'title': 'Xiaomi Redmi 5',
          'urlImg': 'https://d2giyh01gjb6fi.cloudfront.net/default/0002/15/thumb_114133_default_big.jpeg',
          'price' : 550
        },
        {
          'title': 'iPhone X',
          'urlImg': 'https://www.vodafone.co.uk/cs/groups/public/documents/webcontent/vfcon084827.jpg',
          'price' : 1089
        },
        {
          'title': 'Samsung Note 8',
          'urlImg': 'https://3dnews.ru/assets/external/illustrations/2017/08/03/956423/sg1.jpg',
          'price' : 950
        },
        {
          'title': 'iPhone 8',
          'urlImg': 'https://images.kaina24.lt/43/61/apple-iphone-8-256gb-3.jpg',
          'price' : 900
        }
      ],
      first: false,
      visib: false,
      newPosts: 0,
      orders: []
    }
  },
  methods: {
    orderAdd: function (msg, prc) {
      this.orders.push({title: msg, price: prc})
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
  width: 1030px;
  margin: 0 auto;

}
#logo{
  position: relative;
  top: -20px;
  font-size: 20px;
}
body{
  padding-bottom: 10px;

  /*background: url("https://5dwallpaper.com/wp-content/uploads/2016/09/white-brick-wallpaper7.jpg") no-repeat fixed;*/
  background: linear-gradient( rgba(0, 0, 0, 0.01), rgba(0, 0, 0, 0.01) ), url("https://png.pngtree.com/element_origin_min_pic/16/06/17/195763de232dcd8.jpg") no-repeat fixed top rgba(0, 0, 0, 0.5);
  background-size: 100%;
}
.card{
    width: 300px;
    float: left;
    margin-left: 15px;
    margin-top: 20px;
    background-color: white;
  transition: all 200ms;
  transform: scale(1);

}

.card:hover{
  transition: transform 0.2s ease-in-out;
  transform: scale(1.05);
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
  .tabs{
    font-size: 45px;
  }

  .navbar{
    height: 80px;
    background-color: white;
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

  .tabs .md-tabs-navigation{
    padding-left: 400px;
    align-content: center;
    margin-top: 20px;
    background-color: white;
    box-shadow: 0 3px 1px -2px rgba(0,0,0,.2),0 2px 2px 0 rgba(0,0,0,.14),0 1px 5px 0 rgba(0,0,0,.12);

  }

  .tabs .md-tabs-navigation .md-button{
    font-family: 'Quicksand', sans-serif;
    font-size: 15px;
  }

  .md-button{
    font-size: 17px;
    margin-left: 0;
  }


.badge {
  width: 22px;
  height: 22px;
  display: flex;
  justify-content: center;
  align-items: center;
  position: absolute;
  top: -8px;
  right: -20px;
  background: red;
  border-radius: 100%;
  color: white;
  font-size: 15px;
  font-style: normal;
  font-weight: 600;
  letter-spacing: -.05em;
  font-family: 'Roboto Mono', monospace;
  z-index: 1000;
}
</style>
