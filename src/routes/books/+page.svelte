<script lang="ts">
  import Card from "../../lib/components/Card.svelte";

  let categories = [
    "Fiction",
    "Non-Fiction",
    "Education",
    "Technology",
    "Science",
    "History",
    "Biography",
    "Self-Help",
    "Fantasy",
    "Children’s Books",
    "Philosophy",
    "Art",
    "Poetry",
  ];

  let currentIndex = 0;

  const books = [
    {
      name: "The Great Gatsby",
      description: "A classic novel by F. Scott Fitzgerald",
      category: "Fiction",
    },
    {
      name: "Atomic Habits",
      description: "Build good habits and break bad ones",
      category: "Self-Help",
    },
    {
      name: "A Brief History of Time",
      description: "Stephen Hawking explores the universe",
      category: "Science",
    },
    {
      name: "Clean Code",
      description: "A Handbook of Agile Software Craftsmanship",
      category: "Technology",
    },
    {
      name: "Harry Potter",
      description: "The magical fantasy world of Harry Potter",
      category: "Fantasy",
    },
  ];

  function scrollUp() {
    if (currentIndex > 0) {
      currentIndex--;
    }
  }

  function scrollDown() {
    if (currentIndex < categories.length - 1) {
      currentIndex++;
    }
  }

  function filterBooks() {
    return books.filter((book) => book.category === categories[currentIndex]);
  }
</script>

<section class="books-page">
  <aside class="sidebar">
    <h2 class="title">Categories</h2>
    <div class="scroll-buttons">
      <button
        on:click={scrollUp}
        aria-label="Scroll Up"
        class="scroll-btn"
        disabled={currentIndex === 0}
      >
        {#if currentIndex > 0}
          {categories[currentIndex - 1]}
        {:else}
          &uarr;
        {/if}
      </button>
      <div class="current-category">{categories[currentIndex]}</div>
      <button
        on:click={scrollDown}
        aria-label="Scroll Down"
        class="scroll-btn"
        disabled={currentIndex === categories.length - 1}
      >
        {#if currentIndex < categories.length - 1}
          {categories[currentIndex + 1]}
        {:else}
          &darr;
        {/if}
      </button>
    </div>
  </aside>

  <main class="content">
    <h2>{categories[currentIndex]} Books</h2>
    <div class="cards">
      {#each filterBooks() as { name, description }}
        <Card {name} {description} onClick={() => alert(`Viewing ${name}`)} />
      {/each}
    </div>
  </main>
</section>

<style>
  .books-page {
    display: flex;
    min-height: 100vh;
    background-color: #2e3b42;
    color: #d9f0ff;
    font-family: "Arial", sans-serif;
  }

  /* Sidebar Styling */
  .sidebar {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    width: 25%;
    padding: 2rem 1rem;
    background-color: #1a292e;
    border-right: 1px solid #34495e;
  }

  .title {
    font-size: 1.8rem;
    font-weight: bold;
    margin-bottom: 20%;
    color: #89c2d9;
    text-transform: uppercase;
  }

  /* Scroll Buttons and Current Category */
  .scroll-buttons {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 3rem;
  }

  .scroll-btn {
    background: #2f3e46;
    border: 1px solid #89c2d9;
    color: #89c2d9;
    border-radius: 0.5rem;
    width: 160px;
    height: 50px;
    font-size: 1rem;
    font-weight: bold;
    cursor: pointer;
    text-align: center;
    transition:
      background-color 0.3s,
      color 0.3s,
      transform 0.2s;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .scroll-btn:disabled {
    background: #3c5058;
    border: 1px solid #657d85;
    color: #657d85;
    cursor: not-allowed;
  }

  .scroll-btn:hover:not(:disabled) {
    background-color: #89c2d9;
    color: #1a292e;
    transform: scale(1.05);
  }

  .current-category {
    background: #34495e;
    color: #89c2d9;
    font-size: 1.4rem;
    font-weight: bold;
    padding: 0.8rem 1rem;
    border-radius: 0.5rem;
    text-align: center;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
  }

  /* Main Content Area */
  .content {
    flex: 1;
    padding: 2rem;
    background-color: #a4c3bb;
    color: #1a292e;
  }

  .cards {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 1rem;
  }

  @media (max-width: 768px) {
    .sidebar {
      width: 100%;
    }
  }
</style>
