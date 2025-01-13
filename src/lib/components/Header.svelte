<script>
  import { page } from "$app/state";
</script>

<header>
  <div class="logo-container">
    <a href="/home">
      <span>BookBloom</span>
    </a>
  </div>

  <nav>
    <ul>
      <li aria-current={page.url.pathname === "/home" ? "page" : undefined}>
        <a href="/home">Home</a>
      </li>
      <li aria-current={page.url.pathname === "/about" ? "page" : undefined}>
        <a href="/about">About</a>
      </li>
      <li aria-current={page.url.pathname === "/books" ? "page" : undefined}>
        <a href="/books">Books</a>
      </li>
      <li aria-current={page.url.pathname === "/contact" ? "page" : undefined}>
        <a href="/contact">Contact</a>
      </li>
    </ul>
  </nav>
</header>

<style>
  header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 1rem 2rem;
    background: rgba(255, 255, 255, 0.5);
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
    backdrop-filter: blur(10px);
    z-index: 1000;
    transition: background 0.3s ease-in-out;
  }

  .logo-container {
    position: absolute;
    left: 2rem;
  }

  .logo-container a {
    font-size: 1.5rem;
    font-weight: bold;
    text-decoration: none;
    color: white;
    transition: color 0.2s ease-in-out;
  }

  .logo-container a:hover {
    color: var(--color-theme, #434649);
  }

  nav ul {
    list-style: none;
    display: flex;
    gap: 2rem;
    margin: 0;
    padding: 0;
  }

  nav li {
    position: relative;
  }

  nav a {
    text-decoration: none;
    font-size: 1rem;
    font-weight: 500;
    color: white;
    transition: color 0.2s ease-in-out;
  }

  nav a:hover,
  li[aria-current="page"] a {
    color: var(--color-theme, #434649);
  }

  li[aria-current="page"]::after {
    content: "";
    position: absolute;
    bottom: -4px;
    left: 0;
    width: 100%;
    height: 2px;
    background: var(--color-theme, #434649);
  }

  @media (max-width: 768px) {
    header {
      flex-direction: column;
      align-items: center;
      padding: 1rem;
    }

    .logo-container {
      position: static;
      margin-bottom: 1rem;
    }

    nav ul {
      flex-direction: column;
      gap: 1rem;
    }

    nav li {
      width: 100%;
    }

    nav a {
      text-align: center;
      width: 100%;
    }
  }
</style>
