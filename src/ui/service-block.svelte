<script>
  export let title = 'Graphic Design';
</script>

<div class="service">
  <div class="wrapper">
    <h2 class="title">{title}</h2>
    <p class="description">
      <slot />
    </p>
  </div>
</div>

<style>
  .service {
    text-align: center;
    color: var(--text-color);
    background-color: #9ae6d4;
    background-image: var(--bg-url);
    background-size: cover;
    background-repeat: no-repeat;
    background-position: top center;
    height: 600px; /* temp */
  }

  .service .title {
    font-family: 'Fraunces 9pt Soft';
    font-weight: 900;
    font-size: 28px;
    letter-spacing: -0.2px;
    padding-top: 398px;
  }

  .service .description {
    font-family: 'Barlow';
    font-weight: 600;
    font-size: 1rem;
    line-height: 27px;
    letter-spacing: -0.11px;
    margin-top: 27px;
  }
</style>
