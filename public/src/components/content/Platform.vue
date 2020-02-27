<template>
  <div class="platform">
    <div class="image-holder">
      <img class="parallax" src="@/assets/brand.png" alt="">
    </div>
    <div class="banner">
      <ul class="banner-content">
        <li>
          <h2>Digital Platforms</h2>
          <h3>Content Strategy</h3>
          <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. In non, earum eius tempora aliquam autem placeat numquam assumenda voluptatum quisquam quidem excepturi porro vitae accusamus, dolorem sit quis libero dicta.</p>
          <h3>Digital Strategy</h3>
          <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. In non, earum eius tempora aliquam autem placeat numquam assumenda voluptatum quisquam quidem excepturi porro vitae accusamus, dolorem sit quis libero dicta.</p>
        </li>
        <li>
          <img src="@/assets/laptop.png" alt="">
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'brand',
  data () {
    return {

    }
  }
}
</script>

<style lang="scss">
.platform {
  position: relative;
  height: 100vh;
  background-color: #F2F3F6;

  .image-holder {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    z-index: 2;
    height: 50vh;
    background-color: #F2F3F6;
    overflow: hidden;

    img {
      position: absolute;
      width: 100%;
      bottom: 0;
    }
  }

  .banner {
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    z-index: 2;
    height: 50vh;
    padding-bottom: 30px;
    background-color: #F2F3F6;

    .banner-content {
      display: flex;
      flex-flow: row-reverse;
      align-items: center;
      width: 1360px;
      margin: 0 auto;
      padding: 0;
      list-style: none;

      li {
        position: relative;
        width: calc(100% / 2);

        &:last-child {

          img {
            width: 100%;
            z-index: 2;
            margin-left: -6.25em;
          }
        }
      }
    }

    h2 {
      font-size: 3.75em;
      margin-bottom: 0;
      font-weight: bold;
    }
    
    p {
      line-height: 2em;
    }
  }

  > img {
    position: absolute;
    width: 100%;
    bottom: 0;
  }
}
</style>