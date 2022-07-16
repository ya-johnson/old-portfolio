<script>
  import projectsData from '../data/projects'

  const projects = projectsData.reverse()
  let screen
  let carousel
  let cardWidth
  let gap = 30

  const shift = (e) => {
    const target = e.target.classList

    if (target.contains('right') || target.contains('arrow-right')) {
      carousel.scrollLeft += cardWidth + gap
    } 
    else if (target.contains('left') || target.contains('arrow-left')) {
      carousel.scrollLeft -= cardWidth + gap
    }
  }

</script>

<svelte:window bind:innerWidth={screen}></svelte:window>

<div class="container">

  <h2>Projects</h2>
  <p>This website built with <a class="link" href="https://svelte.dev/" target="_blank">Svelte</a>.
     source code availble <a class="link" href="https://github.com/ya-johnson/portfolio" target="_blank">Here -></a> <br>
     Here are some projects that i built using: React, Javascript, HTML and CSS.
  </p>

  <div class="wrraper">

    <div class="projects" bind:this={carousel}>
      {#each projects as project }
  
        <div class="card" bind:offsetWidth={cardWidth}>
          <img src={project.image} alt="">
          <div class="info">
            <h4>{project.title}</h4>
            <span>{project.stack}</span>
            <div class="features">
              <p>Features: {project.features}</p>
            </div>
            <div class="links">
              <a href={project.demo} class="proj-link" target="_blank">Demo</a>
              <a href={project.repo} class="proj-link" target="_blank">Code</a>
            </div>
          </div>
        </div>
      {/each}
    </div>

    <div class="controls">
      <div class="shift left" on:click={shift}>
        <div class="arrow arrow-left"></div>
      </div>
      <div class="shift right" on:click={shift}>
        <div class="arrow arrow-right"></div>
      </div>
    </div>

  </div>

</div>

<style>

  .container {
    display: flex;
    justify-content: center;
    flex-direction: column;
    min-height: 100vh;
    padding-bottom: 2vh;
  }

  .wrraper {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
  }

  .projects {
    overflow: hidden;
    width: 100%;
    display: flex;
    justify-content: left;
    gap: 30px;
    padding: 4vh 0;
    margin-bottom: 0;
  }

  .card {
    position: relative;
    min-width: calc(100% / 3 - 30px);
    border: 2px solid var(--black);
  }

  img {
    width: 100%;
    border-bottom: 2px solid var(--black);
  }

  .info {
    padding: 20px;
  }

  h4 {
    font-size: 22px;
    font-weight: 500;
  }

  span {
    font-weight: 600;
  }

  .features {
    margin: 12px 0 40px 0;
  }

  .features p {
    font-size: 16px;
    line-height: 20px;
    padding-bottom: 20px;
  }

  .links {
    position: absolute;
    bottom: 0;
    left: 0;
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    padding: 20px;
  }

  .proj-link {
    color: var(--black);
    font-size: 14px;
    font-weight: 500;
    padding: 4px 12px;
    border: 2px solid var(--black);
    transition: all ease-out .3s;
  }

  .proj-link:hover {
    background-color: var(--orange);
  }

  .controls {
    width: 40%;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 100px;
  }

  .shift {
    cursor: pointer;
    position: relative;
    height: 50px;
    width: 50px;
    background-color: var(--black);
  }

  .shift:hover > .arrow {
    border-top: 2px solid var(--orange);
    border-right: 2px solid var(--orange);
  }

  .arrow {
    position: absolute;
    top: 50%;
    height: 14px;
    width: 14px;
    border-top: 2px solid var(--offwhite);
    border-right: 2px solid var(--offwhite);
    transform: translateY(-50%);
    background-color: transparent;
    transition: all ease-out .3s;
  }

  .arrow-left {
    left: 40%;
    transform: translate3d(0,-50%,0) rotate(-135deg);
  }

  .arrow-right {
    right: 40%;
    transform: translate3d(0,-50%,0) rotate(45deg);
  }

  @media screen and (max-width: 991px) {
    .card {
      min-width: calc(100% / 2 - 15.5px);
    }
  }

  @media screen and (max-width: 600px) {

    .container {
      padding-bottom: 1vh;
    }

    .projects {
      padding: 2vh 0;
    }

    .card {
      min-width: calc(100%);
    }

    .controls {
      gap: 40px;
    }
  }
  
</style>