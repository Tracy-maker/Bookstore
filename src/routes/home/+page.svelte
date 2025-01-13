<script lang="ts">
</script>

<section class="home">
  <header>
    <h1>Expand your mind, <br /> reading a book</h1>
    <p>
      Reading books is a wonderful way to spend your time. Here at we believe
      reading will help you make connections with others.
    </p>
    <div class="buttons">
      <a href="/about" class="btn-primary">About Us</a>
      <a href="/books" class="btn-secondary">Visit Book Store</a>
    </div>
  </header>

  <div class="illustration">
    <img src="src/assets/book.png" alt="Open Book" />
  </div>
</section>

<style>
  .home {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    text-align: center;
    padding: 1rem 1rem;
    background: #4a3aff;
    color: #fff;
    height: 100vh;
    animation: fadeInUp 1.5s ease-in-out;
  }

  header {
    margin-top: -50px;
    animation: slideInFromTop 1.2s ease-out;
  }

  h1 {
    font-size: 2.5rem;
    font-weight: bold;
    line-height: 1.3;
    margin-bottom: 1rem;
  }

  p {
    font-size: 1.1rem;
    line-height: 1.6;
    max-width: 600px;
    margin: 0 auto 2rem auto;
  }

  .buttons {
    display: flex;
    gap: 1rem;
    justify-content: center;
    margin-top: 1rem;
  }

  .btn-primary,
  .btn-secondary {
    display: inline-block;
    padding: 0.75rem 1.5rem;
    border-radius: 0.5rem;
    font-size: 1rem;
    font-weight: bold;
    text-decoration: none;
    text-align: center;
  }

  .btn-primary {
    background: #fff;
    color: #4a3aff;
  }

  .btn-primary:hover {
    background: #f3f3f3;
  }

  .btn-secondary {
    background: transparent;
    color: #fff;
    border: 2px solid #fff;
  }

  .btn-secondary:hover {
    background: rgba(255, 255, 255, 0.2);
  }

  .illustration {
    margin-top: 0.5rem;
    display: flex;
    justify-content: center;
    animation: fadeInScale 1.5s ease-in-out;
  }

  .illustration img {
    width: 300px;
    max-width: 100%;
    transform: scale(1);
    transition: transform 0.3s ease-in-out;
  }

  .illustration img:hover {
    transform: scale(1.1);
  }

  @keyframes fadeInUp {
    0% {
      opacity: 0;
      transform: translateY(20px);
    }
    100% {
      opacity: 1;
      transform: translateY(0);
    }
  }

  @keyframes slideInFromTop {
    0% {
      opacity: 0;
      transform: translateY(-30px);
    }
    100% {
      opacity: 1;
      transform: translateY(0);
    }
  }

  @keyframes fadeInScale {
    0% {
      opacity: 0;
      transform: scale(0.8);
    }
    100% {
      opacity: 1;
      transform: scale(1);
    }
  }

  @media (min-width: 768px) {
    .home {
      flex-direction: row;
      text-align: left;
      padding: 1rem 2rem;
    }

    header {
      flex: 1;
      margin-top: -50px;
    }

    .illustration {
      flex: 1;
      text-align: right;
    }

    h1 {
      font-size: 3.5rem;
    }

    p {
      font-size: 1.2rem;
    }
  }
</style>
