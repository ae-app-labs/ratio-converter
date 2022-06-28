<script>
  import Converter from './lib/Converter.svelte'
</script>

<main>
  <h1>Ratio Converter</h1>
  
  <p class="subtitle">
    A handy utility for ratio conversion
  </p>

  <p>
    Enter the reference Width and Height resolution, and enter either width or height for the target resolution. <br/>
    Focus out of the text field and the other value is auto calculated.
  </p>

  <Converter />
</main>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
      Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }

  main {
    text-align: center;
    padding: 1em;
    margin: 0 auto;
  }

  h1 {
    color: #1fa591;
    text-transform: uppercase;
    font-size: 4rem;
    font-weight: 100;
    line-height: 1.1;
    margin: 2rem auto;
    max-width: 14rem;
  }

  p {
    max-width: 14rem;
    margin: 1rem auto;
    line-height: 1.35;
  }

  @media (min-width: 480px) {
    h1 {
      max-width: none;
    }

    p {
      max-width: none;
    }
  }
</style>
