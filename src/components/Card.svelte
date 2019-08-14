<script>
  export let title;
  export let description = "Description coming soon!";
  export let imageUrl = "https://picsum.photos/64";
</script>

<style>
  h1 {
    color: coral;
  }
  section {
    border-radius: 8px;
    box-shadow: 0 0 4px rgba(255, 0, 0, 0.1);
    max-width: 600px;
    margin: 1rem auto;
    padding: 1rem 2rem;
  }
  img {
    width: 32px;
    height: 32px;
    margin-right: 12px;
    vertical-align: middle;
  }
</style>

<section>
  <h1>
    <img src={imageUrl} alt="Avatar for {title}" />
     {title}
  </h1>

  <p>{description}</p>
</section>
