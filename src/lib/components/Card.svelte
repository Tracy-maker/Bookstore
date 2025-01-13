<script lang="ts">
  export let name: string;
  export let description: string;
  export let onClick: () => void;
</script>

<div class="card">
  <div class="icon-container">
    <slot name="icon"></slot>
  </div>
  <div class="card-content">
    <h3>{name}</h3>
    <p>{description}</p>
  </div>
  <button class="btn" on:click={onClick}>View Book Demo</button>
</div>

<style>
  .card {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    padding: 0.8rem;
    border: 1px solid #ddd;
    border-radius: 0.6rem;
    box-shadow: 0 3px 6px rgba(0, 0, 0, 0.1);
    text-align: center;
    max-width: 200px;
    width: 100%;
    background: none;
    transition:
      box-shadow 0.2s ease-in-out,
      transform 0.2s ease-in-out;
  }

  .card:hover {
    box-shadow: 0 6px 12px rgba(0, 0, 0, 0.2);
    transform: translateY(-3px);
  }

  .icon-container {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 50px;
    height: 50px;
    border-radius: 50%;
    background: none;
    margin-bottom: 0.5rem;
  }

  .card-content h3 {
    font-size: 0.9rem;
    font-weight: bold;
    margin-bottom: 0.3rem;
  }

  .card-content p {
    font-size: 0.75rem;
    color: #555;
    margin-bottom: 0.8rem;
  }

  .btn {
    padding: 0.5rem 0.7rem;
    border: 1px solid #333;
    border-radius: 0.3rem;
    background: none;
    color: #333;
    font-size: 0.8rem;
    font-weight: bold;
    cursor: pointer;
    transition:
      background 0.3s ease-in-out,
      color 0.3s ease-in-out;
  }

  .btn:hover {
    background: #333;
    color: #fff;
  }
</style>
