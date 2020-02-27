<template>
  <div class="work">
    <div class="image-holder">
      <img class="parallax" src="@/assets/work.png" alt="">
    </div>
    <div class="banner">
      <ul class="banner-content">
        <li>
          <h2>Brand & Comms</h2>
          <h3>Brand and Communications Strategy</h3>
          <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. In non, earum eius tempora aliquam autem placeat numquam assumenda voluptatum quisquam quidem excepturi porro vitae accusamus, dolorem sit quis libero dicta.</p>
          <h3>Campaign & Media Strategy</h3>
          <p>Lorem ipsum dolor, sit amet consectetur adipisicing elit. In non, earum eius tempora aliquam autem placeat numquam assumenda voluptatum quisquam quidem excepturi porro vitae accusamus, dolorem sit quis libero dicta.</p>
        </li>
        <li>
          <img src="@/assets/iphone.png" alt="">
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'quote',
  data () {
    return {
      list: [
        {
          id: 'discover',
          subs: 'People First',
          title: 'We discover',
          desc: "We bring back the spark on people's eyes."
        },
        {
          id: 'design',
          subs: 'Intuitive Thinking',
          title: 'We design',
          desc: "We provide a strategic approach to every single challenge."
        },
        {
          id: 'deliver',
          subs: 'Solution Driven',
          title: 'We deliver',
          desc: "When life gives you lemons, we make the lemonade for you."
        }
      ]
    }
  }
}
</script>

<style lang="scss">
.work {
  position: relative;
  height: 100vh;
  overflow: hidden;
  // background-image: url('~@/assets/work.png');
  // background-attachment: fixed;
  // background-size: cover;
  // background-position: center center;

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

  > img {
    position: absolute;
    width: 100%;
    bottom: 0;
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
      align-items: center;
      width: 1360px;
      margin: 0 auto;
      padding: 0;
      list-style: none;

      li {
        position: relative;
        width: calc(100% / 2);

        &:last-child {
          text-align: right;

          img {
            width: 70%;
            margin-bottom: -170px;
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
}
</style>