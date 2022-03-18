<div class="diagonal-box">
  <header>
    <h1>Yermaín<span>Araya</span></h1>
    <nav>
      <a>About</a>
      <a>Works</a>
      <a>Blog</a>
      <a>Contact</a>
    </nav>
  </header>
</div>


<style type="scss">
  .diagonal-box {
    position: fixed;
    background-color: transparent;
    width: 240px;
    height: 100vh;
    transform: skew(-12deg);
    border-right: 1px solid var(--text-color);
    transition: border-right 900ms ease-in-out;
  }
  header {
    height: 100%;
    padding: .8rem 0 1rem;
    transform: skew(12deg);
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }
  h1 {
    margin-bottom: .2rem;
    font-size: 1.8rem;

    span {
      color: var(--accent);
      vertical-align: -34px;
      margin-left: -77px;
    }
  }

  nav {
    display: flex;
    flex-direction: column;
    gap: .4rem;
    a {
      font-weight: 300;
      font-style: italic;

      &:hover {
        font-weight: 400;
      }
    }
  }
</style>