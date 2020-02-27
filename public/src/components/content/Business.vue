<template>
  <div class="business">
    <div class="image-holder">
      <img class="parallax" src="@/assets/platform.png" alt="">
    </div>
    <div class="banner">
      <ul class="banner-content">
        <li>
          <h2>Business Strategy</h2>
          <h3>Experience Design</h3>
          <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. In non, earum eius tempora aliquam autem placeat numquam assumenda voluptatum quisquam quidem excepturi porro vitae accusamus, dolorem sit quis libero dicta.</p>
          <h3>Marketing Strategy</h3>
          <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. In non, earum eius tempora aliquam autem placeat numquam assumenda voluptatum quisquam quidem excepturi porro vitae accusamus, dolorem sit quis libero dicta.</p>
          <button class="primary">See more</button>
        </li>
        <li>
          <img src="@/assets/business.jpg" alt="">
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
.business {
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
    overflow: hidden;

    .banner-content {
      display: flex;
      align-items: center;
      width: 1360px;
      margin: 0 auto;
      padding: 0;
      list-style: none;

      li {
        position: relative;
        width: calc(100% / 2);

        .primary {
          background: #3A3C3B !important;
        }

        &:last-child {
          text-align: right;

          img {
            width: 100%;
            z-index: 2;
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