<template>
  <div class="header">
    <div class="fadeText">
      <vue-typer :text="qoute" :repeat='0'></vue-typer>
      <!-- <h1 class="banner-text">{{ text }}<span></span></h1> -->
      <span class="res">- yes, we’re always thinking</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'banner',
  data () {
    return {
      scrolled: null,
    }
  }
}
</script>

<style lang="scss">
.header {
  position: relative;
  height: 100vh;
  background-image: url('~@/assets/header.jpg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  // font-family: 'Montserrat', sans-serif;
  font-family: 'Playfair Display', serif;
  
  &:after {
    content: '';
    position: absolute;
    z-index: 1;
    width: 100%;
    height: 100vh;
    background: linear-gradient(145deg, #ff5891 0%, 50%,#863ea3 100%);
    opacity: .75;
  }

  .vue-typer {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 810px;
    height: 300px;
    margin-left: 150px;
    z-index: 2;
    font-size: 3.5em;

    &:before {
      content: '';
      position: absolute;
      top: -20px;
      height: 4px;
      width: 150px;
      background-color: #fff;
    }
    
    span {
      color: #fff !important;
    }

    .caret {
      width: 3px;
      background-color: #fff;
    }

    + span {
      position: absolute;
      top: 50%;
      left: 50%;
      z-index: 2;
      transform: translate(-50%, -50%);
      width: 810px;
      margin-top: 200px;
      margin-left: 150px;
      font-size: 1.5em;
      color: #fff;
      opacity: 0;
      animation: show 1s linear forwards; 
      animation-delay: 6s;
    }
  }
}

@keyframes show {
  from { opacity: 0 }
  to { opacity: 1; }
}

@keyframes typing{
	from{ width: 100%;}
	to{ width: 0;}
}

@keyframes cursor{
	50% { border-color: white;}
}

.fadeText {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 100vh;
  z-index: 2;
}
</style>

<script>
export default {
  name: 'mainHeader',
  data () {
    return {
      qoute: `"We're purpose driven humans, focused on innovation, design & creativity"`
    }
  }
}
</script>