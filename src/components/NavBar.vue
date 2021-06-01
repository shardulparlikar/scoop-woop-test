<template>
  <div class="header-container">
    <nav id="navbar" :class="{ shown: scrolled }">
      <div class="container">
        <div class="left-nav">
          <div class="navbar-logo">
            <img src="../assets/logo.png" alt="" />
          </div>
          <ul class="links">
            <li>
              <a href="#">TRENDING</a>
            </li>
            <li>
              <a href="#">Video</a>
            </li>
            <li>
              <a href="#">Stories</a>
            </li>
            <li>
              <a href="#">Quizzes</a>
            </li>
            <li>
              <a href="">Memes</a>
            </li>
            <li>
              <a href="#">spotlight</a>
            </li>
          </ul>
        </div>
        <div class="right-nav">
          <ul>
            <li>
              <a href="#"><i class="far fa-bookmark"></i></a>
            </li>
            <li>
              <a href="#"><i class="far fa-user"></i></a>
            </li>
            <li>
              <a href="#"><i class="fas fa-search"></i></a>
            </li>
            <li>
              <a href="#"><i class="fas fa-bars"></i></a>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </div>
  <nav class="navbar-mobile">
    <div class="mobile">
      <i class="fas fa-search"></i>
      <img src="../assets/mobilelogo.png" alt="" />
      <i class="fas fa-bars"></i>
    </div>
  </nav>
  <div class="container banner-image">
    <a class="image-link" href="#">
      <img
        src="https://s4.scoopwhoop.com/anj2/60547185c8d1115b02424f3a/77808a56-3907-44bd-a6f2-e270996c225c.jpg"
        alt=""
      />
    </a>
    <div class="text-image">
      <div class="text-container">
        <a class="subtitle">Entertainment</a>
        <h1 class="title">
          16 Fan Favourite Cult Movies That You Didn't Know Were Copied
        </h1>
        <a class="read-more" href="#"
          >Read Article <i class="fas fa-arrow-right"></i
        ></a>
      </div>
    </div>
  </div>
  <div class="mobile-menu">
    <nav class="mobile-menu-nav">
      <ul>
        <li class="mobile-menu-icons">
          <p>Trending</p>
          <i class="fas fa-bolt"></i>
        </li>
        <li class="mobile-menu-icons">
          <p>Videos</p>
          <i class="fas fa-play"></i>
        </li>
        <li class="mobile-menu-icons">
          <p>Storys</p>
          <i class="fas fa-bars"></i>
        </li>
        <li class="mobile-menu-icons">
          <p>Quizzes</p>
          <i class="fas fa-trophy"></i>
        </li>
        <li class="mobile-menu-icons">
          <p>Memes</p>
          <i class="far fa-grin-squint-tears"></i>
        </li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  data() {
    return {
      scrolled: false,
    };
  },
  methods: {
    handleScroll() {
      this.scrolled = window.scrollY > 300;
    },
  },
  created() {
    window.addEventListener("scroll", this.handleScroll);
  },
};
</script> 

<style scoped>
body {
  padding: 0;
  margin: 0;
}
.navbar-mobile {
  display: none;
}
.mobile-menu {
  display: none;
}

.header-container {
  position: absolute;
  width: 100%;
}
.container {
  position: relative;
}
.container img {
  display: block;
  width: 100%;
}

#navbar {
  position: sticky;
  z-index: 10;
  left: 0;
  right: 0;
  top: auto;
  height: 100px;
  background-color: transparent;
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
#navbar .container {
  width: 100%;
  max-width: 1364px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
}
#navbar.shown {
  background-color: #fff;
  transition: background-color ease-in 0.3s;
  position: fixed;
}
ul,
li {
  padding: 0;
  list-style: none;
}
#navbar li a {
  color: #1b91ff;
}
#navbar.shown .left-nav li a {
  color: #747070;
}

#navbar li:hover {
  transition: transform 0.3s, -webkit-transform 0.3s, -o-transform 0.3s;
  cursor: pointer;
  transform: scale(1.25);
}

a {
  text-decoration: none;
}
.left-nav,
.right-nav,
.right-nav ul,
.links {
  display: flex;
  align-items: center;
  text-transform: uppercase;
}
.left-nav ul {
  width: 700px;
  justify-content: space-between;
}
.navbar-logo {
  padding-right: 38px;
}
.right-nav ul {
  width: 240px;
  justify-content: space-between;
  margin: auto;
}

.banner-image {
  position: relative;
}
.banner-image .image-link::before {
  background: linear-gradient(
    180deg,
    rgba(0, 0, 0, 0.9) 0,
    rgba(30, 30, 30, 0) 58.02%
  );
}

.banner-image .image-link::after {
  background: linear-gradient(
    0deg,
    rgba(0, 0, 0, 0.8) -2.88%,
    rgba(30, 30, 30, 0) 41.98%
  );
}
.text-image {
  position: absolute;
  bottom: 40px;
  /* left: 40px; */

  width: 100%;
}
.text-container {
  max-width: 1364px;
  margin: 0 auto;
}
.subtitle {
  padding: 1px 15px;
  background: linear-gradient(136.04deg, #1b91ff -0.78%, #9f49e3 92.66%)
    no-repeat;
  color: #fff;
  margin-bottom: 20px;
  display: block;
  width: fit-content;
  margin-bottom: 20px;
}
.title {
  font-size: 30px;
  font-weight: 900;
  line-height: 142.97%;
  margin: 0 0 20px;
  max-width: 800px;
  color: #fff;
}
.read-more {
  background: linear-gradient(136.04deg, #1b91ff -0.78%, #9f49e3 92.66%)
    no-repeat;
  display: inline-block;
  color: #1b91ff;
  -webkit-background-clip: text !important;
  background-clip: text;
  -webkit-text-fill-color: transparent;
}

@media only screen and (max-width: 600px) {
  .banner-image {
    display: none;
  }
  #navbar {
    display: none;
  }
  .navbar-mobile {
    display: block;
  }
  .navbar-mobile .mobile {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 15px;
  }
  .mobile .fas {
    color: #1b91ff;
    font-size: 20px;
  }
  .mobile-menu {
    display: block;
    background: linear-gradient(156.31deg, #9f49e3 3.34%, #1e82de 128.25%);
    position:fixed;
    width: 100%;
    bottom: 0;
    z-index: 5 ;
  }
  .mobile-menu-nav ul {
    display: flex;
    justify-content: space-around;
    
    
  }
  .mobile-menu-icons {
    display: flex;
    flex-direction: column-reverse;
    align-items: center;
    color: #cccde8;
    margin:  15px 0 15px 0 ;
    font-family : 'Roboto';

    font-weight: 300;
  }
  .mobile-menu-icons p {
    margin: 0px;
  }
  .card{
    flex:1 0 100%;
    margin: 0 20px;
  }
}
</style>