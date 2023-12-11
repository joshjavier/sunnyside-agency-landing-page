<script>
  export let image = '/images/mobile/image-transform.jpg';
  export let title = 'Transform your brand';
  export let ctaText = 'Learn more';
  export let ctaLink = '#';
</script>

<div class="usp">
  <img src={image} alt="" />
  <div class="content wrapper">
    <h2 class="title">{title}</h2>
    <p class="description">
      <slot />
    </p>
    <a class="cta" href={ctaLink}>{ctaText}</a>
  </div>
</div>

<style>
  .usp .content {
    padding-block: 64px;
    text-align: center;
  }

  .usp .title,
  .usp .cta {
    font-family: 'Fraunces 9pt Soft';
    font-weight: 900;
    color: #24303e;
  }

  .usp .title {
    font-size: 32px;
    letter-spacing: -0.23px;
  }

  .usp .description {
    font-family: 'Barlow';
    font-weight: 600;
    font-size: 18px;
    line-height: 30px;
    letter-spacing: -0.13px;
    color: #808397;
    margin-top: 24px;
  }

  .usp .cta {
    text-transform: uppercase;
    text-decoration: none;
    font-size: 15px;
    line-height: 25px;
    letter-spacing: 1px;
    margin-top: 32px;
    display: inline-block;
    position: relative;
  }

  .usp .cta::after {
    content: '';
    width: 115%;
    height: 10px;
    background-color: var(--accent-color);
    position: absolute;
    left: 50%;
    translate: -50%;
    border-radius: 28px;
    bottom: 0;
    z-index: -1;
    opacity: 0.25;
  }

  .usp .cta:hover::after {
    opacity: 1;
  }
</style>
