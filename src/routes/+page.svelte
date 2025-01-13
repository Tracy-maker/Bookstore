<script lang="ts">
  import { onMount } from "svelte";

  let storyIndex = 0;
  let storyText = [
    "In a world filled with endless stories,",
    "...where imagination knows no bounds,",
    "...and knowledge waits to be discovered,",
    "there exists a place where every book finds a reader.",
    "Welcome to the Bookstore, your gateway to adventures untold.",
  ];

  let showButton = false;

  function goToHomePage() {
    showButton = false;
    setTimeout(() => {
      window.location.href = "http://localhost:5173/home";
    }, 1000);
  }

  onMount(() => {
    const interval = setInterval(() => {
      if (storyIndex < storyText.length - 1) {
        storyIndex++;
      } else {
        clearInterval(interval);
        showButton = true;
      }
    }, 2000);
  });
</script>

<section class="nav-page">
  <div class="animated-container">
    <img
      src="../src/assets/3.png"
      alt="Bookstore illustration"
      class="image left"
    />
    <div class="story">
      {#each storyText.slice(0, storyIndex + 1) as line}
        <p class="story-line">{line}</p>
      {/each}
      {#if showButton}
        <button class="navigate-btn" on:click={goToHomePage}>
          Go to Home Page
        </button>
      {/if}
    </div>
    <img src="../src/assets/4.png" alt="Open book" class="image right" />
  </div>
</section>

<style>
  .nav-page {
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100vh;
    background: #d2a6e3;
    overflow: hidden;
    font-family: "Arial", sans-serif;
  }

  .animated-container {
    display: flex;
    align-items: center;
    gap: 2rem;
    animation: fadeIn 1s ease-in-out;
  }

  .story {
    text-align: center;
    max-width: 600px;
    color: #ffffff;
  }

  .story-line {
    font-size: 1.2rem;
    font-weight: 500;
    margin: 0.5rem 0;
    opacity: 0;
    animation: fadeInLine 1s ease-in-out forwards;
  }

  @keyframes fadeInLine {
    from {
      opacity: 0;
      transform: translateY(10px);
    }
    to {
      opacity: 1;
      transform: translateY(0);
    }
  }

  .image {
    width: 200px;
    height: auto;
    animation: float 2s ease-in-out infinite;
  }

  .image.left {
    transform: translateX(-50px);
  }

  .image.right {
    transform: translateX(50px);
  }

  @keyframes float {
    0% {
      transform: translateY(0);
    }
    50% {
      transform: translateY(-20px);
    }
    100% {
      transform: translateY(0);
    }
  }

  .navigate-btn {
    padding: 1rem 2rem;
    font-size: 1.2rem;
    font-weight: bold;
    color: #9b59b6;
    background: #ffffff;
    border: none;
    border-radius: 0.5rem;
    cursor: pointer;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    margin-top: 1.5rem;
    transition:
      transform 0.3s ease-in-out,
      background 0.3s ease-in-out;
  }

  .navigate-btn:hover {
    transform: scale(1.1);
    background: #f8f8f8;
  }

  .navigate-btn:active {
    transform: scale(0.95);
    background: #d8bfd8;
  }

  @keyframes fadeIn {
    0% {
      opacity: 0;
      transform: translateY(-20px);
    }
    100% {
      opacity: 1;
      transform: translateY(0);
    }
  }
</style>
