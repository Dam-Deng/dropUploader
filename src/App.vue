<template>
  <div id="app">
    <div class="box">
      <div class="box-item" @mouseover="mouseOverBox" @mouseleave="mouseLeaveBox">
        <span class="tips-text">{{ msg }}</span>
      </div>
    </div>
    <router-view></router-view>
  </div>
</template>

<script>
  export default {
    name: 'app',
    data() {
      return {
        msg: 'Where Your Mouse Is ?',
        timeOutId: null,
      };
    },
    methods: {
      mouseOverBox() {
        clearTimeout(this.timeOutId);
        this.timeOutId = setTimeout(() => {
          this.msg = 'It Here!';
        }, 200);
      },
      mouseLeaveBox() {
        clearTimeout(this.timeOutId);
        this.timeOutId = setTimeout(() => {
          this.msg = 'Where Your Mouse Is ?';
        }, 400);
      },
    },
  };
</script>

<style>
  #app {
    display: flex;
    flex-flow: column wrap;
    justify-content: center;
    width: 100%;
    height: 100vh;
    background: url('./assets/WhereYourMouseIs.jpeg') center center no-repeat;
    background-size: cover;
    cursor: none;
  }

  .box {
    align-items: center;
    text-align: center;
  }

  .tips-text {
    display: inline-block;
    width: 380px;
    padding: 20px;
    font-size: 1.8rem;
    font-weight: bold;
    cursor: default;
    transition: .8s;
  }

  .box-item {
    display: inline-block;
  }

  .box-item:hover .tips-text {
    color: #fff;
    transform: rotateX(360deg) scale(1.1);
    background: rgba(0, 0, 0, 0.7);
  }

  body {
    margin: 0;
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }
</style>
