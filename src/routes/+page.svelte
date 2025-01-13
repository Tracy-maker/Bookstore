<script lang="ts">
    let containerStyle = "";
  
    function goToHomePage() {
      containerStyle = "transform: translateX(200px); opacity: 0;";
      setTimeout(() => {
        window.location.href = "http://localhost:5173/";
      }, 1000); // Adding delay for the animation effect
    }
  </script>
  
  <section class="nav-page">
    <div class="animated-container" style={containerStyle}>
      <img
        src="../src/assets/3.png"
        alt="Bookstore illustration"
        class="image left"
      />
      <div class="center-container">
        <button class="navigate-btn" on:click={goToHomePage}>
          Go to Home Page
        </button>
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
      background: linear-gradient(135deg, #e6e6fa, #d8bfd8); /* Soft purple gradient */
      overflow: hidden;
      font-family: "Arial", sans-serif;
    }
  
    .animated-container {
      display: flex;
      align-items: center;
      gap: 2rem;
      animation: fadeIn 1s ease-in-out;
    }
  
    /* Image Styles */
    .image {
      width: 200px;
      height: auto;
      animation: float 2s ease-in-out infinite; /* Floating animation */
    }
  
    .image.left {
      transform: translateX(-50px);
    }
  
    .image.right {
      transform: translateX(50px);
    }
  
    /* Floating Animation */
    @keyframes float {
      0% {
        transform: translateY(0);
      }
      50% {
        transform: translateY(-20px); /* Move up */
      }
      100% {
        transform: translateY(0); /* Back to original position */
      }
    }
  
    /* Button Styles */
    .navigate-btn {
      padding: 1rem 2rem;
      font-size: 1.2rem;
      font-weight: bold;
      color: #fff;
      background: #9b59b6; /* Purple button */
      border: none;
      border-radius: 0.5rem;
      cursor: pointer;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2); /* Subtle shadow */
      transition: transform 0.3s ease-in-out, background 0.3s ease-in-out;
    }
  
    .navigate-btn:hover {
      transform: scale(1.1); /* Slightly larger on hover */
      background: #8e44ad; /* Darker purple for hover */
    }
  
    .navigate-btn:active {
      transform: scale(0.95); /* Slightly smaller on click */
      background: #76448a; /* Even darker purple for click */
    }
  
    /* Fade-in Animation */
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
  