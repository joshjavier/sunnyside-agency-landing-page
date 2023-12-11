<script>
  import '../ui/css/main.css';
  import IconArrowDown from '../ui/icons/icon-arrow-down.svelte';
  import IconHamburger from '../ui/icons/icon-hamburger.svelte';
  import Logo from '../ui/logo.svelte';
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
