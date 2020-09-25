<template>
<div >
   <b-navbar style="background-color: rgba(207, 31, 119, 0.863);">
    <b-navbar-brand>Google Music</b-navbar-brand>
    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav class="ml-auto">
        <b-nav-form>
          <b-form-input size="sm" class="mr-sm-2" placeholder="login..."></b-form-input>
          <b-button size="sm" class="my-2 my-sm-0" type="submit">login</b-button>
        </b-nav-form>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
   <div id="app">
    <br />
    <img
      src="https://www.aoos.com/media/catalog/product/cache/d3537c321a700cb9c1fb7a409c881eeb/m/i/microphone_live_music_neon_sign_l187.jpg"
      width="30%"
    >
    <HelloWorld id="text" msg="Google Music" />
    <Music />
    <footer class="my-0 pt-0 text-muted text-center text-small">
      <br><br><br><br><br><br><br><br><br><br><br><br><br><br><hr>
        <p class="mb-0">&copy; Ying Nutwara &copy; 6104101346</p>
    </footer>
  </div></div>
</template>
<script>
import HelloWorld from "./components/HelloWorld.vue";
import Music from "./components/Music";

export default {
  name: "App",
  components: {
    HelloWorld,
    Music,
  },
};
</script>
<style>
#app {
  width: 100%;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #000000;
  background-size: cover;
  background-image: url();
  background-color: rgb(0, 0, 0);
}
#text {
  color: rgb(221, 71, 176);
}


</style>
