<template>
  <main>
    <div class="home__view">
      <div class="home__view--info">
        <span>Aurelio Borges</span>

        <h1>Frontend<br>Developer</h1>

        <div>
          <nav>
            <RouterLink to="/mywork" class="home__view--btn-prime">View My Work</RouterLink>
            <RouterLink to="/contact" class="home__view--btn-sec">Get in Touch &darr;</RouterLink>
          </nav>
        </div>
      </div>

      <div class="home__view--picture">
        <picture>
          <img
            src="../assets/selfie.JPG"
            alt="Profile photo of Aurelio Borges"
          />
        </picture>
      </div>
    </div>
  </main>

  <RouterView />
</template>

<script setup lang="ts">
  import { RouterLink, RouterView } from 'vue-router'
</script>

<style scoped lang="scss">
  @import '../assets/base.css';

  .home__view {
    max-width: 1300px;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    column-gap: 64px;
    align-items: center;
    justify-items: center;
    padding: 48px;

    .home__view--info {
      span {
        display: block;
        color: var(--color-text);
        font-weight: 600;
        font-size: 32px;
        letter-spacing: 0.75px;
        margin-bottom: 18px;
      }

      h1 {
        color: var(--color-text-header-1);
        font-size: 56px;
        line-height: 1.05;
        margin-bottom: 48px;
        font-weight: 700;
        letter-spacing: -0.5px;
      }

      .home__view--btn-prime,
      .home__view--btn-sec {
        font-size: 20px;
        text-decoration: none;
        padding: 16px 32px;
        border-radius: 2px;
        border: none;
        cursor: pointer;
        font-family: inherit;
        transition: all 0.3s;
        font-weight: 600;
      }

      .home__view--btn-prime {
        color: #373737;
        background-color: #f9f9f9;
        margin-right: 20px;

        &:hover {
          color: #fff;
          background-color: #000;
        }
      }

      .home__view--btn-sec {
        background-color: #000;
        color: #fff;

        &:hover {
          color: #222;
          background-color: #f9f9f9;
        }
      }
    }

    .home__view--picture {
      img {
        width: 75%;
      }
    }
  }
</style>