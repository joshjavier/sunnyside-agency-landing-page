<script>
  import '../ui/css/main.css';
  import IconArrowDown from '../ui/icons/icon-arrow-down.svelte';
  import IconFacebook from '../ui/icons/icon-facebook.svelte';
  import IconHamburger from '../ui/icons/icon-hamburger.svelte';
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

<section class="testimonials wrapper" aria-labelledby="testimonials-label">
  <h2 id="testimonials-label">Client testimonials</h2>
  {#each testimonials as item}
    <Testimonial avatar={item.avatar} name={item.name} jobTitle={item.jobTitle}>
      {item.body}
    </Testimonial>
  {/each}
</section>

<section class="gallery" aria-labelledby="gallery-label">
  <h2 class="visually-hidden" id="gallery-label">Gallery</h2>
  <img src="/images/mobile/image-gallery-milkbottles.jpg" alt="" width="376" height="376" />
  <img src="/images/mobile/image-gallery-orange.jpg" alt="" width="376" height="376" />
  <img src="/images/mobile/image-gallery-cone.jpg" alt="" width="376" height="376" />
  <img src="/images/mobile/image-gallery-sugar-cubes.jpg" alt="" width="376" height="376" />
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
    font-family: 'Fraunces 9pt Soft', serif;
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

  .testimonials {
    padding-block: 64px 86px;
  }

  .testimonials > :global(*) + :global(*) {
    margin-top: 64px;
  }

  #testimonials-label {
    text-transform: uppercase;
    text-align: center;
    font-family: 'Fraunces 9pt Soft', serif;
    font-weight: 900;
    font-size: 1rem;
    letter-spacing: 4px;
    color: #a7aaad;
  }

  .gallery {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }

  footer {
    background-color: #90d4c6;
    color: #2c7566;
    padding: 64px 80px 39px;
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
    gap: 57px;
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

  .social-links a {
    display: flex;
  }
</style>
