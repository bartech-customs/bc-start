<template>
  <div class="container">
    <div class="hero">
      <div class="left">
        <span class="note">NOTE: Site is under construction</span>
        <h1>Bartech Customs</h1>
        <p>Modern Websites and Apps that delivers better performance.</p>
        <a href="mailto:bartechg@gmail.com">Contact Us</a>
        <img class="monitor" src="~/assets/monitor.png" alt="" />
      </div>
      <div class="right">
        <div class="box">
          <span class="material-icons icon"> bolt </span>
          <h2>Faster Performance</h2>
        </div>
        <div class="box">
          <span class="material-icons icon"> shield </span>
          <h2>Higher Security</h2>
        </div>
        <div class="box">
          <span class="material-icons icon"> credit_score </span>
          <h2>Less expensive</h2>
        </div>
        <div class="box">
          <span class="material-icons icon"> insights </span>
          <h2>Scalability</h2>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { gsap } from 'gsap'
export default {
  mounted() {
    const tl = gsap.timeline({
      defaults: { ease: 'power2.inOut', duration: 1 },
    })
    tl.from('.left h1', { y: '50px', opacity: 0 })
      .from('.left p', {
        y: '150px',
        opacity: 0,
      })
      .from(
        '.box',
        {
          y: '250px',
          opacity: 0,
          stagger: 0.5,
        },
        '-=.5'
      )
      .from(
        '.left a',
        {
          x: '-250px',
          opacity: 0,
        },
        '-=.5'
      )
      .from(
        '.left img',
        {
          x: '-250px',
          opacity: 0,
        },
        '-=.5'
      )
  },
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Comfortaa:wght@300;400&family=Krona+One&display=swap');
.container {
  margin: 0 auto;
  height: 100vh;
  width: 100%;
  text-align: left;
}
.hero {
  width: 100%;
  height: 100%;
  background: url('~assets/banner.png');
  background-position: center left;
  background-size: cover;
  background-repeat: no-repeat;
  display: grid;
  grid-template-columns: 1fr 1fr;
  color: white;
  font-family: 'Comfortaa', cursive;
}

.left {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: center;
  text-align: left;
  padding-left: 2rem;
  height: 100%;

  h1 {
    font-size: 5vw;
    font-family: 'Krona One', sans-serif;
    text-transform: uppercase;
    margin-bottom: 2rem;
  }
  p {
    font-size: 2vw;
    font-weight: 300;
  }
  a {
    text-decoration: none;
    color: rgb(17, 17, 17);
    margin: 2rem 2rem 2rem auto;
    background-color: rgb(243, 243, 243);
    padding: 1rem 2rem;
    font-weight: 400;
    text-transform: uppercase;
  }
  img {
    width: 90%;
    justify-self: flex-start;
    align-self: flex-start;
  }
}
.right {
  display: grid;
  grid-template-columns: 1fr 1fr;
  justify-items: center;
  align-items: center;
  margin: 5rem;

  .box {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    color: rgb(231, 231, 231);

    h2 {
      font-size: 2rem;
      font-weight: 300;
    }
    .icon {
      font-size: 5rem;
      padding: 2rem;
      border: 2px solid transparent;

      border-radius: 5px;
      margin-bottom: 2rem;
      background-color: rgba(255, 255, 255, 0.158);
      backdrop-filter: blur(10px);
      background-clip: padding-box;
    }
  }
}

@media screen and (max-width: 1000px) {
  .container {
    height: 100%;
    width: 100%;
  }
  .hero {
    grid-template-columns: 1fr;
  }
  .left {
    align-items: center;
    justify-content: center;
    padding: 1rem;
    width: 100%;
    h1 {
      margin-top: 4rem;
      font-size: 3rem;
      text-transform: uppercase;
    }
    p {
      font-size: 2rem;
      width: 100%;
      padding: 1rem 1rem 2rem 1rem;
    }
    a {
      margin: 1rem auto 2rem 1rem;
      margin-bottom: 2rem;
    }
    img {
      width: 100%;
      filter: drop-shadow(1px 1px 10px rgba(255, 255, 255, 0.5));
      -webkit-filter: drop-shadow(1px 1px 10px rgba(255, 255, 255, 0.5));
    }
  }
  .right {
    grid-template-columns: 1fr;
    margin: 1rem;
    text-align: center;
    .box {
      .icon {
        font-size: 4rem;
        margin-bottom: 1rem;
      }
    }
    h2 {
      margin-bottom: 2rem;
    }
  }
}
</style>
