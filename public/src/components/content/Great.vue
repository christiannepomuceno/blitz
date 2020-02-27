<template>
  <div class="div-great">
    <ul id="great" class="we-list">
      <li v-for="n in list" :key="n.subs">
        <div class="block">
          <h2>{{ n.title }}</h2>
          <p>{{ n.desc }}</p>
        </div>
      </li>
    </ul>
    <img class="great" src="@/assets/great.jpg" alt="">
  </div>
</template>

<script>
export default {
  name: 'brand',
  data () {
    return {
      list: [
        {
          title: 'Tailored solutions',
          desc: "Small, interdisciplinary teams work in true collaboration with clients, helping to ﬁnd new opportunities and solve existing business problems."
        },
        {
          title: 'Collaboration',
          desc: "Our collaborative approach fosters a more enjoyable working relationship, better communication and transparency, a more efﬁcient use of project resource and ultimately allows us to add maximum value to your business."
        },
        {
          title: 'A true partner',
          desc: "We take the time to understand your business from the top down so we can drive real value. We becomea true partner to our client's business, working across brand, marketing and technology initiatives tohelp them win."
        }
      ]
    }
  }
}
</script>

<style lang="scss">
.div-great {
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
  height: 100vh;
  background-color: #000;
  overflow: hidden;

  > img {
    position: absolute;
    width: 100%;
    bottom: -250px;
  }

  .we-list {
    position: relative;
    z-index: 1;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 0;
    transform: translateY(100px);
    transition: .5s linear transform;
    list-style: none;

    &.show {
      transform: translateY(-300px)
    }

    li {
      display: inline-flex;
      margin: 0 1.5em;
      width: 330px;
      height: 330px;
      background-color: #000;
      color: #fff;

      .block {
        margin: 2em
      }

      span {
        font-size: 0.875em;
      }

      p {
        font-size: 1em
      }
    }
  }
}
</style>