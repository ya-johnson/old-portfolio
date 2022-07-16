<script>

  
</script>

<div class="cube-container">

  <div class="cube consumed">
    <div class="side front"></div>
    <div class="side back"></div>
    <div class="side right"></div>
    <div class="side left"></div>
    <div class="side top"></div>
    <div class="side bottom"></div>
  </div>

  <div class="cube consumer">
    <div class="side front"></div>
    <div class="side back"></div>
    <div class="side right"></div>
    <div class="side left"></div>
    <div class="side top"></div>
    <div class="side bottom"></div>
  </div>

</div>

<style>

  .cube-container {
    font-size: 8vw;
    transform-style: preserve-3d;
    transform: rotateX(-10deg) rotateY(10deg);
    animation: spin 4s steps(1) infinite;
  }

  .cube {
    position: absolute;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    height: 1em;
    width: 1em;
    transform-style: preserve-3d;
  }

  .side {
    position: absolute;
    top: 0;
    left: 0; 
    width: 100%;
    height: 100%;
    border: solid 6px var(--black);
    background: var(--offwhite);
    transform-style: preserve-3d;
  }

  .front {    transform: rotateY(0deg) translateZ(0.5em); }
  .back {     transform: rotateY(180deg) translateZ(0.5em); }
  .right {    transform: rotateY(90deg) translateZ(0.5em); }
  .left {     transform: rotateY(-90deg) translateZ(0.5em); }
  .top {      transform: rotateX(90deg) translateZ(0.5em); }
  .bottom {   transform: rotateX(-90deg) translateZ(0.5em); }

  .consumed {
    animation: scale-down 2s ease-out infinite;
  }

  .consumer {
    position: relative;
    z-index: 2;
    animation: consume-in 2s ease-out infinite;
  }

  .consumer .front {
    transform-origin: top center;
    transform: rotateY(0deg) translateZ(0.5em) rotateX(0deg);
    animation: consume-flap 2s ease-out infinite;
  }

  @keyframes spin {
    0%, 100% {
      transform: rotateX(-15deg) rotateY(45deg);
    }
    50% { 
      transform: rotateX(-15deg) rotateY(-45deg);
    }
  }

  @keyframes scale-down {
    50%,100% { transform: scale3d(0.5, 0.5, 0.5); } 
  }

  @keyframes consume-in {
    0% { transform: translateZ(-2.5em); } 
    90% { transform: translateZ(0em); }
  }

  @keyframes consume-flap {
    0%, 10% { 
      transform: rotateY(0deg) translateZ(0.5em) rotateX(280deg);
    }
      
    90% { transform: rotateY(0deg) translateZ(0.5em) rotateX(0deg); }
  }

  @media screen and (max-width: 991px) {
    .cube-container {
      font-size: 16vw;
    }
  }

</style>