<template>
  <div class="container">
    <span class="mb-0 h1">
      <p class="centered">KILAVUZ TIMES</p>
    </span>
    <nav class="navbar navbar-expand-lg navbar-dark">
      <div class="navbar-inner">
        <ul class="navbar-nav mr-auto">
          <li v-for="(page,index) in pages" :key="index" class="nav-item">
            <nuxt-link class="nav-link" :to="page.href" exact>{{page.id}}</nuxt-link>
          </li>
          <li>
            <a href="javascript:void(0);" class="icon" onclick="myFunction()">
              <i class="fa fa-bars"></i>
            </a>
          </li>
        </ul>
      </div>
    </nav>
  </div>
</template>

<script>
export default {
  name: 'NavBar',
  data: () => {
    return {
      pages: [
        {
          id: 'news',
          href: '/',
          selected: true
        },
        {
          id: 'technology',
          href: '/tech',
          selected: false
        },
        {
          id: 'science',
          href: '/science',
          selected: false
        },
        {
          id: 'business',
          href: '/business',
          selected: false
        },
        {
          id: 'turkish',
          href: '/turkish',
          selected: false
        }
      ]
    }
  }

  /*methods: {
    resetPages() {
      console.log(this.pages)
      this.pages.forEach(page => (page.selected = false))
    },
    activated: function(page) {
      this.resetPages()
      page.selected = true
      console.log(this.pages)
    }
  }*/
}
</script>

<style  scoped>
@import url('https://fonts.googleapis.com/css?family=Gelasio&display=swap');

.navbar {
  background-color: transparent;
  margin-bottom: 10px;
}

.centered {
  text-align: center;
  font-family: 'Gelasio', serif;
  margin-top: 30px;
}

.nav-link {
  color: black !important;
  font-weight: bold;
  font-family: 'Gelasio', serif;
}

li {
  display: inline-block;
}

.navbar-nav {
  padding-left: 365px;
  padding-right: 30px;
}

a:hover {
  background-color: #aaa;
  color: white;
}

.nuxt-link-active {
  text-decoration: underline;
}

@media only screen and (max-width: 1200px) {
  .navbar {
    margin-left: -90px;
  }
}

@media only screen and (max-width: 991px) {
  .navbar {
    margin-left: -70px;
  }
}

@media only screen and (max-width: 414px) {
  .navbar {
    margin-left: -220px;
    text-align: center;
  }
}
@media only screen and (max-width: 375px) {
  .navbar {
    margin-left: -245px;
  }
}
</style>