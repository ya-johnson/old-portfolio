<script>

</script>

<div class="container">

  <h2>Resources</h2>

  <div class="resources-main">
    <div class="left">
      <p>
        I maintain a list of resources for web development. <br>
        The content vary from learning resources, projects building, 
        dev tools, UI/UX inspiration and more. <br>
        It's somewhat an effort to keep up to date with the ternds and advancements 
        of the ever chainging Tech industry. <br>
        The Resources added and updated frequently, in order to keep it manageable 
        and public i initialiezed a Repository in my github account.
      </p>
      <a href="https://github.com/ya-johnson/web-dev-resources" target="_blank" class="link">Check it out Here -></a>
    </div>

    <div class="right"></div>
  </div>

</div>

<style>

  .container {
    display: flex;
    justify-content: center;
    flex-direction: column;
    height: 100vh;
    border-bottom: 2px solid var(--black);
  }

  h2 {
    margin-bottom: 4vh;
  }

  .resources-main {
    display: flex;
  }

  .left {
    width: 50%;
    padding-right: 40px;
  }

  .right {
    height: 50vh;
    width: 50%;
    background-image: var(--street-light);
    background-position: center;
    background-size: contain;
    background-repeat: no-repeat;
  }

  p {
    margin-bottom: 4vh;
  }

  @media screen and (max-width: 991px) {

    h2 {
      margin-bottom: 1vh;
    }

    .resources-main {
      flex-direction: column;
    }

    .left {
      width: 100%;
      padding: 0;
      margin-bottom: 6vh;
    }

    .right {
      height: 40vw;
      width: 100%;
      background-position: top;
    }
  }

</style>