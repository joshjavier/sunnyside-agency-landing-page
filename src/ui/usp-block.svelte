<script>
  export let image = '/images/mobile/image-transform.jpg';
  export let title = 'Transform your brand';
  export let ctaText = 'Learn more';
  export let ctaLink = '#';
  export let reverse = false;
</script>

<div class="usp" class:reverse>
  <div class="image">
    <img src={image} alt="" />
  </div>
  <div class="content wrapper">
    <h3 class="title">{title}</h3>
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
    --wrapper-max-width: 445px;
    --gutter: 24px;
  }

  .usp .title,
  .usp .cta {
    font-family: 'Fraunces 9pt Soft', serif;
    font-weight: 900;
    color: #24303e;
  }

  .usp .title {
    font-size: 32px;
    letter-spacing: -0.23px;
  }

  .usp .description {
    font-family: 'Barlow', sans-serif;
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

  @media (min-width: 700px) {
    .usp {
      display: grid;
      grid-template-columns: 1fr 1fr;
    }

    .usp.reverse .image {
      order: 1;
    }

    .usp .image img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      max-height: 624px;
    }

    .usp .content {
      margin-block: auto;
    }

    .usp .title {
      font-size: clamp(2rem, 1.527rem + 1.0811vw, 2.5rem);
    }

    .usp .description {
      margin-top: 32px;
    }

    .usp .cta {
      margin-top: 40px;
    }
  }

  @media (min-width: 1100px) {
    .usp .content {
      text-align: left;
    }
  }
</style>
