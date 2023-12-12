<script>
  import { onMount } from 'svelte';
  import IconHamburger from './icons/icon-hamburger.svelte';

  /** @type {HTMLElement} */
  let root;

  let status = 'closed';
  let enabled = false;

  /** @param {string} [forcedStatus] */
  function toggle(forcedStatus) {
    if (forcedStatus) {
      if (status === forcedStatus) return;
      status = forcedStatus;
    } else {
      status = status === 'closed' ? 'open' : 'closed';
    }
  }

  onMount(() => {
    const ro = new ResizeObserver((entries) => {
      const { contentRect } = entries[0];

      // Dynamically switch to burger menu UI on smaller screens
      if (contentRect.width < 672) {
        enabled = true;
      } else {
        enabled = false;
      }
    });

    // @ts-ignore
    ro.observe(root.parentNode);
  });
</script>

<div class="burger-menu-root" bind:this={root}>
  {#if enabled}
    <button
      class="burger-menu-trigger"
      aria-expanded={status === 'open'}
      aria-label={status === 'open' ? 'Close menu' : 'Open menu'}
      on:click={() => toggle()}
    >
      <IconHamburger />
    </button>
  {/if}
  <div class="burger-menu-panel">
    <nav aria-label="Site">
      <ul role="list" class="nav-links">
        <li><a href="#">About</a></li>
        <li><a href="#">Services</a></li>
        <li><a href="#">Projects</a></li>
      </ul>
    </nav>
    <a href="#" class="btn">Contact</a>
  </div>
</div>

<style>
  .burger-menu-root {
    position: relative;
  }

  .burger-menu-trigger {
    background-color: transparent;
    border: none;
    display: grid;
    place-items: center;
    width: 40px;
    height: 40px;
    cursor: pointer;
  }

  .burger-menu-trigger[aria-expanded='true'] {
    opacity: 50%;
  }

  .burger-menu-panel,
  .nav-links {
    display: flex;
    flex-wrap: wrap;
    column-gap: 47px;
    row-gap: 1rem;
  }

  .burger-menu-panel {
    align-items: center;
  }

  .nav-links a {
    text-decoration: none;
    display: flex;
  }

  .nav-links {
    padding-left: 0;
    margin-block: 0;
    font-family: 'Barlow', sans-serif;
    font-weight: 600;
    font-size: 18px;
    line-height: 25px;
    letter-spacing: -0.13px;
  }

  /* Mobile navigation */
  .burger-menu-trigger + .burger-menu-panel {
    background-color: white;
    color: #808397;
    padding-block: 39px;
    padding-inline: clamp(3.75rem, -6.553rem + 51.5152vw, 5.875rem);
    position: absolute;
    right: 8px;
    bottom: -30px;
    translate: 0 100%;
  }

  .burger-menu-trigger[aria-expanded='false'] + .burger-menu-panel {
    display: none;
  }

  .burger-menu-trigger + .burger-menu-panel::before {
    content: '';
    width: 24px;
    height: 24px;
    position: absolute;
    top: 0;
    right: 0;
    translate: 0 -100%;
    border-bottom: 12px solid white;
    border-right: 12px solid white;
    border-left: 12px solid transparent;
    border-top: 12px solid transparent;
  }

  .burger-menu-trigger + .burger-menu-panel,
  .burger-menu-trigger + .burger-menu-panel .nav-links {
    flex-direction: column;
    align-items: center;
    gap: 32px;
  }

  .burger-menu-trigger + .burger-menu-panel .btn {
    --bg-color: 51 100% 49%;
    --hover-text-color: #24303e;
  }
</style>
