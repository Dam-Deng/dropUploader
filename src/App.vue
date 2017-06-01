<template>
  <div id="app" style="background-image: url('/static/img/WhereYourMouseIs.f934b8d.jpeg')">
    <div class="box">
      <div class="box-item">
        <span class="tips-text">Where Your Mouse Is ?</span>
      </div>
    </div>
    <router-view></router-view>
  </div>
</template>

<script>
  export default {
    name: 'app',
  };
</script>

<style>
  #app {
    width: 100%;
    height: 100vh;
    background-position: center center;
    background-repeat: no-repeat;
    background-size: cover;
    cursor: none;
    display: flex;
    flex-flow: column wrap;
    justify-content: center;
  }

  .box{
    align-items: center;
    text-align: center;
  }
  .tips-text {
    display: inline-block;
    padding: 20px;
    font-size: 1.8rem;
    font-weight: bold;
    transition: .5s;
    cursor: default;
  }
  .box-item{
    display: inline-block;
  }

  .box-item:hover .tips-text {
    transform: rotateX(360deg);
    background: rgba(255, 255, 255, 0.7);
  }

  body {
    margin: 0;
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }
</style>
