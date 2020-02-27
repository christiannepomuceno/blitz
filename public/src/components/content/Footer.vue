<template>
  <div class="footer">
    <div class="banner">
      <div class="banner-content">
        <hr>
        <p>
          We generate results that matteer, collaborating side-by-side with
          <br>
          our more than 300 clients.
        </p>
        <h2>
          “We bring back the spark on people’s eyes,
          <br>
          with two lines”.
        </h2>
      </div>
    </div>
    <div class="image-holder">
      <div class="image-content">
        <div class="text-center">
          <h2>Keep moving forward</h2>
          <button class="primary">SUBSCRIBE TO OUR NEWSLETTER</button>
        </div>
        <div class="address">
          <br>
          <br>
          <br>
          <br>
          <br>
          <br>
          <br>
          <br>
          <br>
          <br>
          <br>
          <br>
          <br>
          <br>
          <p>90 Crawford Street,</p>
          <p>Dunedin, 9016</p>
          <p>+64 03 474 0869</p>
          <br>
          <p><a href="mailto:hello@thehustle.nz">hello@thehustle.nz</a></p>
        </div>
      </div>
      <img src="@/assets/map.jpg" alt="">
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
.footer {
  display: flex;
  flex-flow: column;
  align-items: center;
  background-color: #F2F3F6;
  padding: 0 1em;

  .text-center {
    text-align: center;
  }

  h1 {
    margin-top: 1.5em;
    font-weight: normal;
    font-size: 3.125em;

    b {
      font-weight: bolder;
    }
  }

  .banner {
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    text-align: center;
    background-color: #fff;
    width: 100vw;
    padding-top: 5em;
    min-height: 400px;

    .banner-content {
      width: 1360px;
      margin: 0 auto;

      hr {
        background-color: #3A3C3B;
        height: 1px;
        border: 0;
      }
    }

    h2 {
      font-size: 3.75em;
      font-family: 'Playfair Display', serif;
    }
  }

  .image-holder {
    position: relative;

    .image-content {
      position: absolute;
      z-index: 2;
      left: 50%;
      transform: translateX(-50%);
      width: 1360px;
      padding: 5em 0;
      margin: 0 auto;
      color: #fff;
      
      h2 {
        text-align: center;
        font-weight: bold;
        font-size: 2em;
      }

      .primary {
        width: auto;
        padding: 0 1em;
      }

      .address {
        line-height: 1em;
        font-style: normal;

        p {
          font-size: 1em;

          a {
            color: #fff;
            text-decoration: none;
          }
        }
      }
    }

    &:after {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background: linear-gradient(to right, rgba(0,0,0,0.85) 20%,rgba(0,0,0,.5) 100%);
    }
  }
}
</style>