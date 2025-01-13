<script lang="ts">
  import { writable } from "svelte/store";

  let name = "";
  let email = "";
  let message = "";
  const expandedIndex = writable<number | null>(null);

  const faqs = [
    {
      question: "What is BookBloom Library?",
      answer:
        "BookBloom Library is a free platform dedicated to providing a wide variety of books for everyone. From educational resources to engaging stories, our goal is to make reading accessible to all.",
    },
    {
      question: "Do I need to pay for the books?",
      answer:
        "No, all books on our platform are completely free. Our mission is to create an inclusive reading space without any financial barriers.",
    },
    {
      question: "How often are books updated?",
      answer:
        "We update our book collection weekly. Stay tuned for new titles and genres added regularly to keep your reading experience fresh and exciting.",
    },
    {
      question: "How can I get started?",
      answer:
        "Simply browse our library, select the books you want, and start reading or downloading for free. No account is needed, but signing up allows you to save your favorites and receive personalized recommendations.",
    },
  ];

  function toggleFAQ(index: number) {
    expandedIndex.update((current) => (current === index ? null : index));
  }

  function submitForm() {
    alert(`Thank you, ${name}! Your message has been sent.`);
    name = "";
    email = "";
    message = "";
  }
</script>

<section class="contact-page">
  <div class="container">
    <div class="form-container">
      <h2>Contact Us</h2>
      <form on:submit|preventDefault={submitForm}>
        <div class="form-group">
          <label for="name">Name</label>
          <input
            type="text"
            id="name"
            bind:value={name}
            placeholder="Your Name"
            required
          />
        </div>
        <div class="form-group">
          <label for="email">Email</label>
          <input
            type="email"
            id="email"
            bind:value={email}
            placeholder="Your Email"
            required
          />
        </div>
        <div class="form-group">
          <label for="message">Message</label>
          <textarea
            id="message"
            bind:value={message}
            placeholder="Your Message"
            required
          ></textarea>
        </div>
        <button type="submit" class="btn-submit">Send Message</button>
      </form>
    </div>

    <div class="faq-container">
      <h2>FAQs</h2>
      {#each faqs as { question, answer }, index}
        <div
          class="faq-item"
          role="button"
          tabindex="0"
          on:click={() => toggleFAQ(index)}
          on:keydown={(e) =>
            (e.key === "Enter" || e.key === " ") && toggleFAQ(index)}
        >
          <h3>{question}</h3>
          {#if $expandedIndex === index}
            <p>{answer}</p>
          {/if}
        </div>
      {/each}
    </div>
  </div>
</section>

<style>
  .contact-page {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 2rem;
    background: #ffe3f1;
    min-height: calc(100vh - 50px);
  }

  .container {
    display: flex;
    gap: 2rem;
    max-width: 1400px; /* Increased max width */
    width: 100%;
  }

  .form-container,
  .faq-container {
    flex: 1;
    background: #fff;
    padding: 2rem;
    border-radius: 1rem;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    max-width: 600px; /* Increased container width */
  }

  .form-container h2,
  .faq-container h2 {
    font-size: 1.8rem;
    margin-bottom: 1rem;
    color: #e91e63;
  }

  .form-group {
    margin-bottom: 1rem;
  }

  label {
    display: block;
    margin-bottom: 0.3rem;
    font-size: 0.9rem;
    color: #555;
  }

  input,
  textarea {
    width: 100%;
    padding: 0.75rem;
    border: 1px solid #ccc;
    border-radius: 0.5rem;
    font-size: 0.9rem;
  }

  textarea {
    height: 80px;
  }

  .btn-submit {
    width: 100%;
    padding: 0.75rem;
    border: none;
    border-radius: 0.5rem;
    background: #e91e63;
    color: #fff;
    font-weight: bold;
    cursor: pointer;
    transition: background 0.3s;
  }

  .btn-submit:hover {
    background: #d81b60;
  }

  .faq-item {
    margin-bottom: 0.8rem;
    padding: 0.4rem;
    border-bottom: 1px solid #ddd;
    cursor: pointer;
    transition: background 0.3s;
  }

  .faq-item:hover {
    background: #f9f9f9;
  }

  .faq-item h3 {
    font-size: 1rem;
    margin-bottom: 0.3rem;
    color: #333;
  }

  .faq-item p {
    font-size: 0.9rem;
    line-height: 1.4;
    color: #555;
  }

  @media (max-width: 768px) {
    .container {
      flex-direction: column;
    }

    .form-container,
    .faq-container {
      width: 100%;
    }
  }
</style>
