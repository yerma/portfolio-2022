<script>
  import Header from '../lib/header.svelte'
  import Toggle from '../lib/toggle.svelte'

  let darkTheme = false

  function toggleTheme () {
    document.body.classList.toggle('dark-theme')
  }
</script>

<Header />
<Toggle
  labelActive="🌞"
  initialValue={darkTheme}
  on:toggle={toggleTheme}
>🌜</Toggle>

<div class="shape-to-wrap"></div>
<main>
  <slot></slot>
</main>

<style type="scss">
  :global {

    :root {
      --background: white;
      --text-color: #303030;
      --accent: rgb(50, 173, 161);
    }

    html {
      box-sizing: border-box;
      font-size: 150%; /* 24px */
    }

    *, *:before, *:after {
      box-sizing: inherit;
    }

    body {
      min-height: 100vh;
      margin: 0;
      padding: 0 1.2rem;
      font-family: azote, serif;
      font-weight: 300;
      font-style: normal;
      color: var(--text-color);
      background-color: var(--background);
      transition: background-color 800ms ease-in-out, color 800ms ease-in-out;

      &.dark-theme {
        --background: #111d29;
        --text-color: white;
        --accent: turquoise;
      }
    }

    h1, h2, h3, h4, h5 {
      font-family: contralto-big, sans-serif;
      font-weight: 400;
      font-style: normal;
    }

    h1 {
      margin-top: 0;
      font-size: 1.802rem;
    }

    h2 { font-size: 1.602rem; }

    h3 { font-size: 1.424rem; }

    h4 { font-size: 1.266rem; }

    h5 { font-size: 1.125rem; }

    small, .text_small { font-size: 0.889rem; }

    a {
      color: var(--accent);
      font-weight: 400;
      cursor: pointer;
    }
  }

  .shape-to-wrap {
    float: left;
    width: 0;
    height: 100vh;
    margin-left: 16rem;
    shape-outside: polygon(0 0, 100% 0, 62% 100%);
  }

  main {
    padding: 2rem 2rem 2rem 0.8rem;
  }
</style>