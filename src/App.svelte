<script>
  import Counter from "./lib/Counter.svelte";
  import CardProduct from "./lib/CardProduct.svelte";
</script>

<main>
  <div class="banner">
    <h1>Summa Solutions FED Test</h1>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Suscipit corporis
      dignissimos ducimus sunt eligendi in sed hic, quae, eaque voluptate
      accusantium laboriosam at id atque unde nisi temporibus quis.
    </p>
  </div>

  <div class="container">
    <div class="product-list">
      <CardProduct />
    </div>
  </div>
</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
      Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  }

  main {
    background-color: #ebebeb;
    min-height: 100vh;
    padding-inline: 10px;
    padding-top: 10px;
  }

  .banner {
    max-width: 900px;
    text-align: center;
    margin: 0 auto;
    
  }
  .banner h1 {
    margin-top: 0;
  }

  .container {
    margin: 0 auto;
    max-width: 1200px;
  }

  .container .product-list {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: normal;
    align-items: normal;
    align-content: normal;
    gap: 10px;
  }

  @media (min-width: 723px) {
    main {
      padding-top: 50px;
      padding-bottom: 50px;
     }
     .container {
       margin-top: 50px;
     }
    .container .product-list {
      gap: 30px;
    }
   }

</style>
