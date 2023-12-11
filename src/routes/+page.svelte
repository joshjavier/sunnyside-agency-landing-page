<script>
  import '../ui/css/main.css';
  import IconArrowDown from '../ui/icons/icon-arrow-down.svelte';
  import IconHamburger from '../ui/icons/icon-hamburger.svelte';
  import Logo from '../ui/logo.svelte';
  import ServiceBlock from '../ui/service-block.svelte';
  import UspBlock from '../ui/usp-block.svelte';
</script>

<svelte:head>
  <title>Frontend Mentor | Sunnyside agency landing page</title>
  <meta
    name="description"
    content="A landing page of a made-up creative agency built with SvelteKit by Josh Javier, a frontend developer from the Philippines."
  />
</svelte:head>

<header>
  <Logo />
  <IconHamburger />
</header>

<section class="hero">
  <div class="wrapper">
    <h2 class="headline">We are creatives</h2>
    <div class="scroll-down"><IconArrowDown width={30} /></div>
  </div>
</section>

<section aria-labelledby="whatwedo-label">
  <h2 class="visually-hidden" id="whatwedo-label">What We Do</h2>
  <UspBlock
    --accent-color="#FAD400"
    title="Transform your brand"
    image="/images/mobile/image-transform.jpg"
  >
    We are a full-service creative agency specializing in helping brands grow fast. Engage your
    clients through compelling visuals that do most of the marketing for you.
  </UspBlock>
  <UspBlock
    --accent-color="#FE7766"
    title="Stand out to the right audience"
    image="/images/mobile/image-stand-out.jpg"
  >
    Using a collaborative formula of designers, researchers, photographers, videographers, and
    copywriters, we’ll build and extend your brand in digital places.
  </UspBlock>
</section>

<section aria-labelledby="services-label">
  <h2 class="visually-hidden" id="services-label">Services</h2>
  <ServiceBlock
    title="Graphic Design"
    --text-color="#24554a"
    --bg-url="url('/images/mobile/image-graphic-design.jpg')"
  >
    Great design makes you memorable. We deliver artwork that underscores your brand message and
    captures potential clients’ attention.
  </ServiceBlock>
  <ServiceBlock
    title="Photography"
    --text-color="#19536C"
    --bg-url="url('/images/mobile/image-photography.jpg')"
  >
    Increase your credibility by getting the most stunning, high-quality photos that improve your
    business image.
  </ServiceBlock>
</section>

<style>
  header {
    display: flex;
    align-items: center;
    justify-content: space-between;
    position: absolute;
    width: calc(100% - (24px * 2));
    top: 0;
    left: 50%;
    translate: -50%;
    margin-top: 32px;
    color: white;
  }

  .hero {
    height: 538px; /* temp */
    background-color: #4abdf2;
    background-image: url('/images/mobile/image-header.jpg');
    background-size: cover;
    background-repeat: no-repeat;
    color: white;
  }

  .headline {
    font-family: 'Fraunces 9pt Soft';
    font-weight: 900;
    text-transform: uppercase;
    font-size: 40px;
    letter-spacing: 6.25px;
    text-align: center;
    padding-top: 144px;
  }

  .scroll-down {
    display: flex;
    justify-content: center;
    margin-top: 52px;
  }
</style>
