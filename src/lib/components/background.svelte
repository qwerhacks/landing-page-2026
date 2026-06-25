<script lang="ts">
  // Imports from 2023 landing page
  /*
  import BottomLeft from "$lib/media/bottom_left.svg";
  import BottomRight from "$lib/media/bottom_right.svg";
  import TopRight from "$lib/media/top_right.svg";
  import TopLeft from "$lib/media/top_left.svg";
  import Right from "$lib/media/right_side.svg";
  */
</script>

<div class="w-full h-full relative" style="background:#ffcbb3; background: linear-gradient(311deg, rgba(255, 203, 179, 1) 0%, rgba(138, 219, 192, 1) 43%, rgba(10, 55, 161, 1) 100%);">
  <div id="bg-overlay" class="fixed left-0 top-0 w-full h-full" style="z-index:100;background:transparent;opacity:0.5;mix-blend-mode:dodge"/>

  <!-- Subtle time ripples - more of them -->
  <div class="time-ripple ripple-1"></div>
  <div class="time-ripple ripple-2"></div>
  <div class="time-ripple ripple-3"></div>
  <div class="time-ripple ripple-4"></div>
  <div class="time-ripple ripple-5"></div>

  <!-- Timeline elements - vertical lines with dots -->
  <div class="timeline timeline-left">
    <div class="timeline-dot"></div>
    <div class="timeline-dot"></div>
    <div class="timeline-dot"></div>
    <div class="timeline-dot"></div>
  </div>

  <div class="timeline timeline-right">
    <div class="timeline-dot"></div>
    <div class="timeline-dot"></div>
    <div class="timeline-dot"></div>
    <div class="timeline-dot"></div>
  </div>

  <div class="timeline timeline-center">
    <div class="timeline-dot"></div>
    <div class="timeline-dot"></div>
    <div class="timeline-dot"></div>
  </div>

  <!-- Floating sparkle elements -->
  <div class="floating-sparkle sparkle-1">✨</div>
  <div class="floating-sparkle sparkle-2">✦</div>
  <div class="floating-sparkle sparkle-3">⭐</div>
  <div class="floating-sparkle sparkle-4">✧</div>
  <div class="floating-sparkle sparkle-5">⋆</div>
  <div class="floating-sparkle sparkle-6">·</div>
  <div class="floating-sparkle sparkle-7">✨</div>
  <div class="floating-sparkle sparkle-8">✦</div>

  <!--Elements from 2023 landing page-->
  <!--<img src={BottomLeft} alt="" class="fixed left-0 bottom-0 z-10 max-w-screen max-h-[70vh] md:max-w-[82vw]"/>
  <img src={TopRight} alt="" class="fixed right-0 top-0 max-w-[60vw] md:max-w-[40vw]"/>
  <img src={TopLeft} alt="" class="fixed top-0 left-0 max-w-[60vw] md:max-w-[55vw]"/>-->
</div>

<style>
  /* Subtle time ripples - concentric circles - MORE PROMINENT */
  .time-ripple {
    position: fixed;
    border-radius: 50%;
    border: 2px solid rgba(255, 255, 255, 0.15);
    pointer-events: none;
    z-index: 1;
    animation: ripple-pulse 12s ease-in-out infinite;
  }

  .ripple-1 {
    width: 500px;
    height: 500px;
    top: 10%;
    right: -150px;
    animation-delay: 0s;
  }

  .ripple-2 {
    width: 600px;
    height: 600px;
    bottom: -200px;
    left: -180px;
    animation-delay: 4s;
  }

  .ripple-3 {
    width: 400px;
    height: 400px;
    top: 60%;
    right: 15%;
    animation-delay: 8s;
  }

  .ripple-4 {
    width: 450px;
    height: 450px;
    top: 30%;
    left: 10%;
    animation-delay: 2s;
  }

  .ripple-5 {
    width: 350px;
    height: 350px;
    bottom: 15%;
    right: 25%;
    animation-delay: 6s;
  }

  /* Timeline vertical lines - MORE PROMINENT */
  .timeline {
    position: fixed;
    width: 2px;
    height: 85vh;
    top: 7.5vh;
    background: linear-gradient(
      to bottom,
      rgba(255, 255, 255, 0) 0%,
      rgba(255, 255, 255, 0.25) 20%,
      rgba(255, 255, 255, 0.25) 80%,
      rgba(255, 255, 255, 0) 100%
    );
    pointer-events: none;
    z-index: 1;
  }

  .timeline-left {
    left: 8%;
    animation: fade-in-out 10s ease-in-out infinite;
  }

  .timeline-right {
    right: 10%;
    animation: fade-in-out 10s ease-in-out infinite;
    animation-delay: 5s;
  }

  .timeline-center {
    left: 50%;
    transform: translateX(-50%);
    height: 70vh;
    top: 15vh;
    animation: fade-in-out 10s ease-in-out infinite;
    animation-delay: 2.5s;
  }

  /* Timeline dots - MORE PROMINENT */
  .timeline-dot {
    position: absolute;
    width: 10px;
    height: 10px;
    background: rgba(255, 255, 255, 0.3);
    border: 2px solid rgba(255, 255, 255, 0.4);
    border-radius: 50%;
    left: 50%;
    transform: translateX(-50%);
    animation: dot-glow 8s ease-in-out infinite;
  }

  .timeline-dot:nth-child(1) {
    top: 15%;
    animation-delay: 0s;
  }

  .timeline-dot:nth-child(2) {
    top: 40%;
    animation-delay: 2s;
  }

  .timeline-dot:nth-child(3) {
    top: 65%;
    animation-delay: 4s;
  }

  .timeline-dot:nth-child(4) {
    top: 85%;
    animation-delay: 6s;
  }

  /* Floating sparkle elements */
  .floating-sparkle {
    position: fixed;
    pointer-events: none;
    z-index: 2;
    color: white;
    font-size: 24px;
    opacity: 0.5;
    animation: sparkle-float 15s ease-in-out infinite;
    text-shadow: 0 0 10px rgba(255, 255, 255, 0.5);
  }

  .sparkle-1 {
    top: 15%;
    right: 18%;
    font-size: 32px;
    animation-delay: 0s;
  }

  .sparkle-2 {
    top: 25%;
    left: 15%;
    font-size: 20px;
    animation-delay: 2s;
  }

  .sparkle-3 {
    bottom: 30%;
    right: 12%;
    font-size: 28px;
    animation-delay: 4s;
  }

  .sparkle-4 {
    top: 45%;
    left: 20%;
    font-size: 16px;
    animation-delay: 1s;
  }

  .sparkle-5 {
    top: 60%;
    right: 25%;
    font-size: 22px;
    animation-delay: 5s;
  }

  .sparkle-6 {
    bottom: 20%;
    left: 18%;
    font-size: 18px;
    animation-delay: 3s;
  }

  .sparkle-7 {
    top: 35%;
    right: 8%;
    font-size: 26px;
    animation-delay: 6s;
  }

  .sparkle-8 {
    bottom: 45%;
    left: 10%;
    font-size: 20px;
    animation-delay: 7s;
  }

  /* Animations */
  @keyframes ripple-pulse {
    0%, 100% {
      transform: scale(1);
      opacity: 0.15;
    }
    50% {
      transform: scale(1.2);
      opacity: 0.3;
    }
  }

  @keyframes fade-in-out {
    0%, 100% {
      opacity: 0.5;
    }
    50% {
      opacity: 1;
    }
  }

  @keyframes dot-glow {
    0%, 100% {
      opacity: 0.4;
      transform: translateX(-50%) scale(1);
    }
    50% {
      opacity: 0.8;
      transform: translateX(-50%) scale(1.4);
    }
  }

  @keyframes float-gentle {
    0%, 100% {
      transform: translateY(0px) translateX(0px) rotate(0deg);
      opacity: 0.3;
    }
    25% {
      transform: translateY(-25px) translateX(15px) rotate(8deg);
      opacity: 0.6;
    }
    50% {
      transform: translateY(-15px) translateX(25px) rotate(-5deg);
      opacity: 0.8;
    }
    75% {
      transform: translateY(-30px) translateX(8px) rotate(6deg);
      opacity: 0.5;
    }
  }

  @keyframes sparkle-float {
    0%, 100% {
      transform: translateY(0px) translateX(0px) scale(1);
      opacity: 0.3;
    }
    25% {
      transform: translateY(-20px) translateX(10px) scale(1.2);
      opacity: 0.7;
    }
    50% {
      transform: translateY(-10px) translateX(20px) scale(0.9);
      opacity: 0.5;
    }
    75% {
      transform: translateY(-25px) translateX(5px) scale(1.1);
      opacity: 0.6;
    }
  }

  /* Responsive - hide some elements on smaller screens */
  @media (max-width: 768px) {
    .timeline-center,
    .timeline-right,
    .ripple-3,
    .ripple-4,
    .ripple-5,
    .sparkle-3,
    .sparkle-4,
    .sparkle-5,
    .sparkle-6,
    .sparkle-7,
    .sparkle-8 {
      display: none;
    }
    
    .timeline-left {
      left: 5%;
    }
  }
</style>