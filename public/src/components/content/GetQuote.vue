<template>
  <div class="getQuote">
    <h1><b>Kia Ora</b>, we're humans who care.</h1>
    <p>
      Our work is to produce digital solutions to business complexities, focused 
      <br>
      on empathy and understanding people, their values and experiences.
    </p>
    <button class="primary">Get a quote</button>
    <ul class="we-list">
      <li v-for="n in list" :key="n.subs">
        <div class="block">
          <img :src="require('@/assets/svg/' + n.id + '.svg')" :alt="n.subs">
          <span>{{ n.subs }}</span>
          <h2>{{ n.title }}</h2>
          <p>{{ n.desc }}</p>
        </div>
      </li>
    </ul>
    <div class="banner">
      <div class="banner-content">
        <h2>We see, we think, we do</h2>
        <p>
          Our work is to produce digital solutions to business complexities, focused
          <br />
          on empathy and understanding people, their values and experiences.
        </p>
      </div>
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
.getQuote {
  display: flex;
  flex-flow: column;
  align-items: center;
  background-color: #F2F3F6;
  padding: 0 1em;

  h1 {
    margin-top: 1.5em;
    font-weight: normal;
    font-size: 3.125em;

    b {
      font-weight: bolder;
    }
  }

  p {
    font-size: 1.5em;
    line-height: 1.8em;
  }

  .we-list {
    display: flex;
    margin:  6.5em 0 0;
    padding: 0;
    list-style: none;

    li {
      display: inline-flex;
      margin: 0 1.5em;
      width: 380px;
      height: 400px;
      background-color: #F2F3F6;
      box-shadow: 0 0 40px #D8D8D8;

      .block {
        margin: 2em
      }

      img {
        width: 150px;
        margin-bottom: 1em;
        display: block;
      }

      span {
        font-size: 0.875em;
      }

      p {
        font-size: 1em
      }
    }
  }

  .banner {
    display: flex;
    flex-flow: column;
    justify-content: center;
    align-items: center;
    color: #fff;
    margin-top: 10em;
    background: linear-gradient(145deg, #ff5891 0%, 50%,#863ea3 100%);
    width: 100vw;
    height: 400px;

    .banner-content {
      width: 1360px;
      margin: 0 auto;
    }

    h2 {
      font-size: 3.75em;
    }
    
    p {
      line-height: 2em;
      margin-left: 12em;
    }
  }
}
</style>