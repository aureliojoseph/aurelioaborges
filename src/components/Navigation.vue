<template>
  <header>
    <img alt="Aurelio Borges logo" class="logo" src="@/assets/logo.png"/>

    <nav>
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/about">About</RouterLink>
      <RouterLink to="/skillset">Skill Set</RouterLink>
      <RouterLink to="/experience">Experience</RouterLink>
      <RouterLink to="/mywork">My Work</RouterLink>
      <RouterLink to="/contact">Contact</RouterLink>
    </nav>

    <div class="action_buttons">
      <button class="lang_btn">PT</button>

      <div class="switch" onclick="toggleMode()">
        <button></button>
        <span></span>
      </div>
    </div>
  </header>

  <RouterView />
</template>

<script setup lang="ts">
  import { RouterLink, RouterView } from 'vue-router'
</script>

<style scoped lang="scss">
  @import '../assets/base.css';

  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 3rem;
    padding: 0 1.2rem;
    background-color: rgba(255, 255, 255, 0.97);
    box-shadow: 0 1.2rem 3.2rem rgba(0, 0, 0, 0.07);

    .logo {
      width: 4.4rem;
      height: 2.2rem;
      border-radius: 2px;
      box-shadow: 0 0.3rem 2rem rgba(0, 0, 0, 0.35);
    }

    nav {
      display: flex;
      gap: 1.8rem;

      a {
        font-weight: 500;
        font-size: 18px;
      }
    }

    .action_buttons {
      display: flex;
      gap: 10px;

      .lang_btn {
        background-color: #666;
        color: #fff;
        border-radius: 9px;
        padding: 0 10px;
        transition: all 0.3s;
        display: inline-block;
        text-decoration: none;
        border: none;
        cursor: pointer;
        font-family: inherit;
        font-weight: 600;
        font-size: 10px;

        &:hover {
          background-color: #ccc;
          color: #373737;
        }
      }

      .switch {
        position: relative;
        width: 64px;
        margin: 4px auto;

        button {
          cursor: pointer;
          width: 32px;
          height: 32px;
          background: #c7c7c7 var(--switch-bg-url) no-repeat center;
          border: 0;
          border-radius: 50%;
          position: absolute;
          top: 50%;
          left: -1px;
          z-index: 1;
          transition: all 0.3s;
          transform: translateY(-50%);
          animation: slide-back 0.2s;

          &:hover {
            background-color: var(--highlight-color);
          }
        }

        span {
          display: block;
          width: 56px;
          height: 24px;
          background: var(--surface-color);
          border: 1px solid var(--stroke-color);
          backdrop-filter: blur(4px);
          -webkit-backdrop-filter: blur(4px);
          border-radius: 9999px;
        }
      }

      .light {
        .switch {
          button {
            animation: slide-in 0.2s forwards;
          }
        }
      }
    }

    @keyframes slide-in {
      from {
        left: 0;
      }
      to {
        left: 50%;
      }
    }

    @keyframes slide-back {
      from {
        left: 50%;
      }
      to {
        left: 0;
      }
    }
  }
</style>