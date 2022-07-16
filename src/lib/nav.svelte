<script>

  let y
  let style
  let hamburger
  let mobileMenu

  const navTheme = () => {
    if (y > 100) {
      style = 'active'
    }
    else {
      style = 'light'
    }
  }

  const toggleMenu = () => {
    
    if (hamburger == null && mobileMenu == null) {
      hamburger = 'hamburger-open'
      mobileMenu = 'menu-open'
    } 
    else {
      hamburger = null
      mobileMenu = null
    }
  }

</script>

<svelte:window on:scroll={navTheme} bind:scrollY={y}/>

<nav class={style}>
  <div class="container">

    <a href="/" class="logo-link">
      <div class="logo">
        <div class="pinecone"></div>
        <div class="logo-name">
          yonathan <br> abramov
        </div>
      </div>
    </a>

    <div class="hamburger {hamburger}" on:click={toggleMenu}>
      <span></span>
      <span></span>
    </div>

    <ul class={mobileMenu}>
      <li><a href="https://github.com/ya-johnson/web-dev-resources" target="_blank" class="nav-link">resources</a></li>
      <li><a href="https://github.com/ya-johnson" target="_blank" class="nav-link">github</a></li>
    </ul>

  </div>
</nav>

<style>

  nav {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    color: var(--fg);
    padding: 25px 0;
    border-bottom: 2px solid var(--br);
    background-color: var(--bg);
    z-index: 10;
    transition: all ease-out .15s;
  }

  nav .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .logo-link {
    color: var(--fg);
  }

  .logo {
    display: flex;
    align-items: center;
  }

  .pinecone {
    position: relative;
    height: 60px;
    width: 60px;
    background-image: var(--pinecone);
    background-position: center;
    background-size: contain;
    background-repeat: no-repeat;
    visibility: visible;
  }

  .pinecone::after {
    position: absolute;
    content: "";
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
    background-image: var(--pinecone-light);
    background-position: center;
    background-size: contain;
    background-repeat: no-repeat;
    visibility: hidden;
  }

  .pinecone-footer {
    visibility: hidden;
  }

  .pinecone-footer::after {
    visibility: visible;
  }

  .logo-name {
    font-size: 22px;
    font-weight: 600;
    line-height: 22px;
    margin: 0 8px;
    transition: all ease-out .3s;
  }

  .hamburger {
    cursor: pointer;
    display: none;
    height: 30px;
    width: 30px;
    flex-direction: column;
    justify-content: center;
    align-items: center;
  }

  .hamburger > span {
    height: 4px;
    width: 100%;
    margin: 4px 0;
    background-color: var(--fg);
  }

  ul {
    list-style: none;
    display: flex;
    align-items: center;
  }

  .nav-link {
    color: var(--dark);
    font-size: 16px;
    font-weight: 500;
    text-transform: uppercase;
    padding: 10px;
    margin-left: 60px;
    transition: all ease-out .3s;
  }

  .nav-link:hover {
    color: var(--orange);
  }

  @media screen and (max-width: 991px) {

    .nav-link {
      margin-left: 30px;
    }

  }

  @media screen and (max-width: 600px) {

    .pinecone {
      height: 50px;
      width: 50px;
    }

    .logo-name {
      font-size: 20px;
      line-height: 20px;
      margin: 0 4px;
    }

    .hamburger {
      display: flex;
    }

    .hamburger-open > span:first-of-type {
      height: 14px;
      width: 14px;
      border-radius: 50%;
      transition: all ease-out .2s;
    }

    .hamburger-open > span:last-of-type {
      display: none;
    }

    ul {
      opacity: 0;
      position: absolute;
      top: 102px;
      left: 0;
      height: calc(100vh - 102px);
      width: 100%;
      flex-direction: column;
      justify-content: center;
      background-color: var(--fg);
      transform: translateX(100%);
      transition: all ease-out .25s;
    }

    .nav-link {
      opacity: 0;
      color: var(--bg);
      font-size: 28px;
      line-height: 100px;
      margin: 0;
      transition: all ease-in-out 1.2s;
    }

    .menu-open {
      opacity: 1;
      transform: translateX(0);
    }

    .menu-open li .nav-link {
      opacity: 1;
    }
  }

</style>