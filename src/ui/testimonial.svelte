<script>
  export let avatar = '/images/image-emily.jpg';
  export let name = 'Emily R.';
  export let jobTitle = 'Marketing Director';
</script>

<article>
  <img src={avatar} alt="" width="144" height="144" />
  <p class="testimonial-body"><slot /></p>
  <div class="byline">
    <p class="name">{name}</p>
    <p class="job-title">{jobTitle}</p>
  </div>
</article>

<style>
  article {
    text-align: center;
    font-family: 'Barlow', sans-serif;
    font-weight: 600;
    max-width: 48ch;
    margin-inline: auto;
  }

  article > * + * {
    margin-top: 32px;
  }

  article img {
    width: 72px;
    border-radius: 50%;
    margin-inline: auto;
  }

  article .testimonial-body {
    font-size: 18px;
    line-height: 32px;
    letter-spacing: -0.13px;
    color: #5b636d;
    margin-top: clamp(2rem, -0.0313rem + 4.0625vw, 3.625rem);
  }

  article .byline {
    margin-top: clamp(2rem, -0.8906rem + 5.7813vw, 4.3125rem);
  }

  article .byline .name {
    font-family: 'Fraunces 9pt Soft', serif;
    font-weight: 900;
    font-size: 18px;
    letter-spacing: -0.13px;
    color: #24303e;
  }

  article .byline .job-title {
    font-size: 14px;
    line-height: 25px;
    letter-spacing: -0.1px;
    color: #a7aaad;
  }
</style>
