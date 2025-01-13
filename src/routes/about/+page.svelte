<script lang="ts">
</script>

<section class="about-page">
  <div class="library-info">
    <div class="image-container">
      <img src="src/assets/about.png" alt="Books in Hand" />
    </div>
    <div class="details">
      <h2>Welcome to The BookBloom Library</h2>
      <p>
        At BookBloom, we aim to bring books closer to everyone. From timeless
        classics to the latest releases, we’re here to spark your imagination
        and fuel your love for stories.
      </p>
      <ul>
        <li><strong>Author:</strong> BookBloom Library</li>
        <li><strong>Total Books:</strong> 368 Books</li>
      </ul>
    </div>
  </div>
</section>

<style>
  /* Page Layout */
  .about-page {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    padding: 0;
    background: #ffc04d;
    color: #333;
    overflow: hidden;
  }

  /* Library Info Section */
  .library-info {
    display: flex;
    flex-direction: row;
    align-items: center;
    gap: 2rem;
    max-width: 1200px;
    width: 100%;
    background: #fff;
    border-radius: 1rem;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    padding: 2rem;
    animation: fadeIn 1.5s ease-in-out;
  }

  /* Image Section */
  .image-container {
    flex: 1;
    display: flex;
    justify-content: center;
    align-items: center;
    animation: slideInFromLeft 1.2s ease-out;
  }

  .image-container img {
    max-width: 100%;
    border-radius: 1rem;
  }

  /* Details Section */
  .details {
    flex: 1;
    text-align: left;
    animation: slideInFromRight 1.2s ease-out;
  }

  .details h2 {
    font-size: 2rem;
    margin-bottom: 1rem;
    font-weight: bold;
    color: #e67e22;
  }

  .details p {
    font-size: 1rem;
    line-height: 1.6;
    margin-bottom: 1.5rem;
    color: #555;
  }

  .details ul {
    list-style: none;
    padding: 0;
    margin: 0;
  }

  .details li {
    font-size: 1rem;
    margin-bottom: 0.5rem;
    color: #333;
  }

  /* Keyframes for Animations */
  @keyframes fadeIn {
    0% {
      opacity: 0;
    }
    100% {
      opacity: 1;
    }
  }

  @keyframes slideInFromLeft {
    0% {
      transform: translateX(-50px);
      opacity: 0;
    }
    100% {
      transform: translateX(0);
      opacity: 1;
    }
  }

  @keyframes slideInFromRight {
    0% {
      transform: translateX(50px);
      opacity: 0;
    }
    100% {
      transform: translateX(0);
      opacity: 1;
    }
  }

  @media (max-width: 768px) {
    .library-info {
      flex-direction: column;
      text-align: center;
      padding: 1.5rem;
    }

    .details {
      text-align: center;
    }
  }
</style>
