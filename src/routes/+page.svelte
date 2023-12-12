<script>
  import '../ui/css/main.css';
  import BurgerMenu from '../ui/burger-menu.svelte';
  import IconArrowDown from '../ui/icons/icon-arrow-down.svelte';
  import IconFacebook from '../ui/icons/icon-facebook.svelte';
  import IconInstagram from '../ui/icons/icon-instagram.svelte';
  import IconPinterest from '../ui/icons/icon-pinterest.svelte';
  import IconTwitter from '../ui/icons/icon-twitter.svelte';
  import Logo from '../ui/logo.svelte';
  import ServiceBlock from '../ui/service-block.svelte';
  import Testimonial from '../ui/testimonial.svelte';
  import UspBlock from '../ui/usp-block.svelte';

  let testimonials = [
    {
      name: 'Emily R.',
      jobTitle: 'Marketing Director',
      avatar: '/images/image-emily.jpg',
      body: 'We put our trust in Sunnyside and they delivered, making sure our needs were met and deadlines were always hit.',
    },
    {
      name: 'Thomas S.',
      jobTitle: 'Chief Operating Officer',
      avatar: '/images/image-thomas.jpg',
      body: 'Sunnyside’s enthusiasm coupled with their keen interest in our brand’s success made it a satisfying and enjoyable experience.',
    },
    {
      name: 'Jennie F.',
      jobTitle: 'Business Owner',
      avatar: '/images/image-jennie.jpg',
      body: 'Incredible end result! Our sales increased over 400% when we worked with Sunnyside. Highly recommended!',
    },
  ];
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
  <BurgerMenu />
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
    reverse={true}
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

<section class="services" aria-labelledby="services-label">
  <h2 class="visually-hidden" id="services-label">Services</h2>
  <ServiceBlock
    title="Graphic Design"
    --text-color="#24554a"
    --bg-url="url('/images/desktop/image-graphic-design.jpg')"
  >
    Great design makes you memorable. We deliver artwork that underscores your brand message and
    captures potential clients’ attention.
  </ServiceBlock>
  <ServiceBlock
    title="Photography"
    --text-color="#19536C"
    --bg-url="url('/images/desktop/image-photography.jpg')"
  >
    Increase your credibility by getting the most stunning, high-quality photos that improve your
    business image.
  </ServiceBlock>
</section>

<section class="testimonials wrapper" aria-labelledby="testimonials-label">
  <h2 id="testimonials-label">Client testimonials</h2>
  <ul class="switcher" role="list">
    {#each testimonials as item}
      <li>
        <Testimonial avatar={item.avatar} name={item.name} jobTitle={item.jobTitle}>
          {item.body}
        </Testimonial>
      </li>
    {/each}
  </ul>
</section>

<section class="gallery" aria-labelledby="gallery-label">
  <h2 class="visually-hidden" id="gallery-label">Gallery</h2>
  <img srcset="/images/mobile/image-gallery-milkbottles.jpg 376w, /images/desktop/image-gallery-milkbottles.jpg 720w" src="/images/desktop/image-gallery-milkbottles.jpg" alt="" width="720" height="894" />
  <img srcset="/images/mobile/image-gallery-orange.jpg 376w, /images/desktop/image-gallery-orange.jpg 720w" src="/images/desktop/image-gallery-orange.jpg" alt="" width="720" height="894" />
  <img srcset="/images/mobile/image-gallery-cone.jpg 376w, /images/desktop/image-gallery-cone.jpg 720w" src="/images/desktop/image-gallery-cone.jpg" alt="" width="720" height="894" />
  <img srcset="/images/mobile/image-gallery-sugarcubes.jpg 376w, /images/desktop/image-gallery-sugarcubes.jpg 720w" src="/images/desktop/image-gallery-sugarcubes.jpg" alt="" width="720" height="894" />
</section>

<footer>
  <Logo width={170} />
  <nav aria-label="Site">
    <ul role="list" class="nav-links">
      <li><a href="#">About</a></li>
      <li><a href="#">Services</a></li>
      <li><a href="#">Projects</a></li>
    </ul>
  </nav>
  <ul role="list" class="social-links">
    <li>
      <a href="#">
        <IconFacebook />
        <span class="visually-hidden">Facebook</span>
      </a>
    </li>
    <li>
      <a href="#">
        <IconInstagram />
        <span class="visually-hidden">Instagram</span>
      </a>
    </li>
    <li>
      <a href="#">
        <IconTwitter />
        <span class="visually-hidden">Twitter</span>
      </a>
    </li>
    <li>
      <a href="#">
        <IconPinterest />
        <span class="visually-hidden">Pinterest</span>
      </a>
    </li>
  </ul>
</footer>

<style>
  header {
    display: flex;
    flex-wrap: wrap;
    gap: 1rem;
    align-items: center;
    justify-content: space-between;
    position: absolute;
    width: calc(100% - (24px * 2));
    top: 0;
    left: 50%;
    translate: -50%;
    margin-top: 32px;
    color: white;
    max-width: 1352px;
  }

  header > :global(:first-child) {
    width: clamp(7.75rem, 6.7377rem + 4.3192vw, 10.625rem);
    flex-shrink: 0;
  }

  .hero {
    height: 100vh;
    background-color: #4abdf2;
    background-image: url('/images/mobile/image-header.jpg');
    background-size: cover;
    background-repeat: no-repeat;
    background-position: bottom center;
    color: white;
  }

  @media (min-width: 751px) {
    header {
      margin-top: 34px;
    }

    .hero {
      background-image: url('/images/desktop/image-header.jpg');
    }
  }

  .headline {
    font-family: 'Fraunces 9pt Soft', serif;
    font-weight: 900;
    text-transform: uppercase;
    font-size: 40px;
    font-size: clamp(
      2.1875rem,
      -2.1603rem + 21.7391vw,
      2.5rem
    ); /* 40px that compresses to 35px on smaller screens */
    letter-spacing: 6.25px;
    text-align: center;
    padding-top: 144px;
    padding-top: 26.765vh;
  }

  @media (min-width: 420px) {
    .headline {
      font-size: clamp(2.5rem, 2.0882rem + 1.5686vw, 3.5rem);
    }
  }

  .scroll-down {
    display: flex;
    justify-content: center;
    margin-top: 52px;
  }

  @media (min-width: 700px) {
    .services {
      display: grid;
      grid-template-columns: 1fr 1fr;
    }
  }

  .testimonials {
    padding-top: clamp(4rem, 1.8873rem + 9.0141vw, 10rem); /* 64 -> 160 */
    padding-bottom: clamp(5.375rem, 3.7465rem + 6.9484vw, 10rem); /* 86 -> 160 */
    --wrapper-max-width: 1110px;
    --threshold: 800px;
    --v-gutter: 30px;
    --h-gutter: 64px;
  }

  .testimonials ul {
    margin-top: 64px;
  }

  #testimonials-label {
    text-transform: uppercase;
    text-align: center;
    font-family: 'Fraunces 9pt Soft', serif;
    font-weight: 900;
    font-size: clamp(1rem, 0.912rem + 0.3756vw, 1.25rem); /* 16 -> 20 */
    letter-spacing: 4px;
    color: #a7aaad;
  }

  .gallery {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }

  .gallery img {
    aspect-ratio: 1;
    object-fit: cover;
  }

  @media (min-width: 500px) {
    .gallery {
      grid-template-columns: 1fr 1fr 1fr 1fr
    }

    .gallery img {
      aspect-ratio: 720 / 894;
    }
  }

  footer {
    background-color: #90d4c6;
    color: #2c7566;
    padding: 64px 39px 80px;
  }

  footer > :global(*) {
    margin-inline: auto;
    display: block;
  }

  ul {
    padding-left: 0;
    margin-block: 0;
  }

  footer a {
    text-decoration: none;
  }

  footer a:hover {
    color: white;
  }

  .nav-links {
    font-family: 'Barlow', sans-serif;
    font-weight: 600;
    font-size: 18px;
    line-height: 25px;
    letter-spacing: -0.13px;
    display: flex;
    justify-content: center;
    gap: clamp(
      1.5rem,
      -10.5rem + 60vw,
      3.5625rem
    ); /* 57px that compresses to 24px on smaller screens */
    color: #458d7e;
    margin-top: 40px;
  }

  .social-links {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 28px;
    margin-top: 88px;
  }

  .nav-links a,
  .social-links a {
    display: flex;
  }
</style>
