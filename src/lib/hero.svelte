<script>
  import Cube from './cube.svelte'
</script>

<div class="container">

  <div class="left">
    <h1>I'm a Web Developer.</h1>
    <p>I build websites that look and feel nice.</p>
  </div>

  <div class="right">
    <Cube />
  </div>

</div>


<style>

  .container {
    display: flex;
    align-items: center;
    height: 100vh;
    border-bottom: 2px solid var(--black);
  }

  .left {
    width: 40%;
  }

  .right {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 60%;
    padding-left: 8vw;
  }

  h1 {
    font-size: 90px;
    line-height: 90px;
    margin-bottom: 30px;
  }

  p {
    font-size: 44px;
    line-height: 48px;
    font-weight: 600;
  }

  @media screen and (max-width: 991px) {

    .container {
      flex-direction: column;
    }

    .container > div {
      height: 50%;
      width: 100%;
    }

    .left {
      padding-top: 160px;
    }

    .right {
      padding: 0;
    }

    h1 {
      font-size: 78px;
      line-height: 78px;
      margin-bottom: 16px;
    }

    p {
      font-size: 34px;
      line-height: 38px;
    }

  }

  @media screen and (max-width: 600px) {

    h1 {
      font-size: 54px;
      line-height: 54px;
      margin-bottom: 12px;
    }

    p {
      font-size: 28px;
      line-height:34px;
    }
  }

</style>