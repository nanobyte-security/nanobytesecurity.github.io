---
layout: base
title: Contact | Nanobyte Security
description: Get in touch with Nanobyte Security about penetration testing and red team operations.
---
{%- comment -%}
  Contact page for nanobytesecurity.com
  Save as: contact.html (replaces contact.md; delete the old file so they don't conflict)
  Layout "base" keeps the shared header (_includes/nav.html) and footer
  but skips the theme's centered title banner. Styles are scoped to #nb-contact.
{%- endcomment -%}

<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=IBM+Plex+Sans:wght@400;500;600&amp;family=JetBrains+Mono:wght@400;500;700&amp;display=swap">

<style>
  #nb-contact,
  #nb-contact * {
    box-sizing: border-box;
  }

  #nb-contact {
    --c-bg: #0A0D0B;
    --c-surface: #0F1411;
    --c-border: #1F2A22;
    --c-border-2: #2A3A30;
    --c-text: #E6EDE8;
    --c-text-2: #A7B8AC;
    --c-muted: #7F9687;
    --c-accent: #4ADE80;
    --c-accent-hi: #86EFAC;
    --c-on-accent: #06140B;
    --c-sans: 'IBM Plex Sans', system-ui, sans-serif;
    --c-mono: 'JetBrains Mono', ui-monospace, monospace;

    max-width: 1120px;
    margin: 0 auto;
    padding: 96px 24px 80px;
    display: grid;
    grid-template-columns: minmax(0, 1fr) minmax(0, 1.1fr);
    gap: 64px;
    align-items: start;
    color: var(--c-text);
    font-family: var(--c-sans);
    text-align: left;
  }

  #nb-contact p {
    text-align: left;
    color: var(--c-text-2);
    line-height: 1.65;
    margin: 0;
  }

  #nb-contact a {
    color: var(--c-accent);
    text-decoration: none;
  }

  #nb-contact a:hover,
  #nb-contact a:focus {
    color: var(--c-accent-hi);
  }

  /* Left column */
  #nb-contact .c-eyebrow {
    font-family: var(--c-mono);
    font-size: 0.8rem;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--c-accent);
    margin-bottom: 12px;
  }

  #nb-contact h1 {
    font-size: 3rem;
    line-height: 1.08;
    font-weight: 600;
    letter-spacing: -0.02em;
    color: var(--c-text);
    margin: 0 0 20px;
  }

  #nb-contact .c-lead {
    font-size: 1.1rem;
    margin-bottom: 36px;
  }

  #nb-contact .c-options {
    display: flex;
    flex-direction: column;
    gap: 12px;
    margin-bottom: 36px;
  }

  #nb-contact .c-option {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 16px;
    padding: 16px 20px;
    border: 1px solid var(--c-border);
    border-radius: 8px;
    background: var(--c-surface);
    transition: border-color 0.15s;
  }

  #nb-contact .c-option:hover,
  #nb-contact .c-option:focus {
    border-color: var(--c-accent);
  }

  #nb-contact .c-option-label {
    display: block;
    font-family: var(--c-mono);
    font-size: 0.72rem;
    letter-spacing: 0.06em;
    text-transform: uppercase;
    color: var(--c-muted);
    margin-bottom: 2px;
  }

  #nb-contact .c-option-value {
    color: var(--c-text);
    font-size: 0.98rem;
    word-break: break-word;
  }

  #nb-contact .c-arrow {
    font-family: var(--c-mono);
    color: var(--c-accent);
  }

  #nb-contact .c-next {
    border-top: 1px solid var(--c-border);
    padding-top: 24px;
  }

  #nb-contact .c-next h2 {
    font-family: var(--c-mono);
    font-size: 0.8rem;
    font-weight: 500;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    color: var(--c-muted);
    margin: 0 0 14px;
  }

  #nb-contact .c-next ol {
    list-style: none;
    counter-reset: step;
    padding: 0;
    margin: 0;
    display: flex;
    flex-direction: column;
    gap: 10px;
  }

  #nb-contact .c-next li {
    counter-increment: step;
    color: var(--c-text-2);
    font-size: 0.95rem;
    line-height: 1.5;
    display: flex;
    gap: 12px;
  }

  #nb-contact .c-next li::before {
    content: counter(step, decimal-leading-zero);
    font-family: var(--c-mono);
    font-size: 0.8rem;
    color: var(--c-accent);
    padding-top: 2px;
  }

  /* Form card */
  #nb-contact .c-card {
    background: var(--c-surface);
    border: 1px solid var(--c-border);
    border-radius: 12px;
    overflow: hidden;
  }

  #nb-contact .c-card-bar {
    display: flex;
    gap: 8px;
    align-items: center;
    padding: 12px 16px;
    border-bottom: 1px solid var(--c-border);
    font-family: var(--c-mono);
    font-size: 0.8rem;
    color: #6F8577;
  }

  #nb-contact .c-card-bar span {
    width: 10px;
    height: 10px;
    border-radius: 50%;
    background: var(--c-border-2);
  }

  #nb-contact .c-card-bar em {
    font-style: normal;
    margin-left: 10px;
  }

  #nb-contact form {
    padding: 28px;
    display: flex;
    flex-direction: column;
    gap: 20px;
    margin: 0;
  }

  #nb-contact .c-field {
    display: flex;
    flex-direction: column;
    gap: 8px;
  }

  #nb-contact label {
    font-family: var(--c-mono);
    font-size: 0.8rem;
    color: var(--c-text-2);
    margin: 0;
  }

  #nb-contact label .c-req {
    color: var(--c-accent);
  }

  #nb-contact input[type="text"],
  #nb-contact input[type="email"],
  #nb-contact textarea {
    width: 100%;
    background: var(--c-bg);
    color: var(--c-text);
    border: 1px solid var(--c-border-2);
    border-radius: 6px;
    padding: 12px 14px;
    font-family: var(--c-sans);
    font-size: 1rem;
    line-height: 1.5;
    transition: border-color 0.15s, box-shadow 0.15s;
  }

  #nb-contact textarea {
    min-height: 160px;
    resize: vertical;
  }

  #nb-contact input::placeholder,
  #nb-contact textarea::placeholder {
    color: #5F7A69;
  }

  #nb-contact input:focus,
  #nb-contact textarea:focus {
    outline: none;
    border-color: var(--c-accent);
    box-shadow: 0 0 0 3px rgba(74, 222, 128, 0.18);
  }

  #nb-contact .c-submit-row {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 16px;
    flex-wrap: wrap;
    margin-top: 4px;
  }

  #nb-contact .c-note {
    font-family: var(--c-mono);
    font-size: 0.75rem;
    color: var(--c-muted);
  }

  #nb-contact button[type="submit"] {
    background: var(--c-accent);
    color: var(--c-on-accent);
    border: 0;
    border-radius: 6px;
    padding: 14px 26px;
    font-family: var(--c-sans);
    font-size: 1rem;
    font-weight: 600;
    cursor: pointer;
    transition: background 0.15s;
  }

  #nb-contact button[type="submit"]:hover,
  #nb-contact button[type="submit"]:focus {
    background: var(--c-accent-hi);
  }

  #nb-contact button[type="submit"]:focus-visible {
    outline: 2px solid var(--c-accent-hi);
    outline-offset: 3px;
  }

  #nb-contact .c-hidden {
    display: none !important;
  }

  @media (max-width: 900px) {
    #nb-contact {
      grid-template-columns: minmax(0, 1fr);
      gap: 48px;
      padding-top: 64px;
    }

    #nb-contact h1 {
      font-size: 2.4rem;
    }
  }

  @media (max-width: 480px) {
    #nb-contact form {
      padding: 20px;
    }

    #nb-contact button[type="submit"] {
      width: 100%;
    }
  }
</style>

<main id="nb-contact">

  <section>
    <div class="c-eyebrow">// Contact</div>
    <h1>Let's talk about your environment.</h1>
    <p class="c-lead">
      Tell me what you're working toward, whether that's an insurance requirement, a compliance audit,
      a customer questionnaire, or just wanting to know where you stand. I'll get back to you personally.
    </p>

    <div class="c-options">
      <a class="c-option" href="https://calendly.com/alex-nanobytesecurity/30min">
        <div>
          <span class="c-option-label">Fastest</span>
          <span class="c-option-value">Book a free 30-minute scoping call</span>
        </div>
        <span class="c-arrow" aria-hidden="true">→</span>
      </a>
      <a class="c-option" href="mailto:alex@nanobytesecurity.com">
        <div>
          <span class="c-option-label">Email</span>
          <span class="c-option-value">alex@nanobytesecurity.com</span>
        </div>
        <span class="c-arrow" aria-hidden="true">→</span>
      </a>
      <a class="c-option" href="https://linkedin.com/in/alexander-dalzell">
        <div>
          <span class="c-option-label">LinkedIn</span>
          <span class="c-option-value">Alexander Dalzell</span>
        </div>
        <span class="c-arrow" aria-hidden="true">→</span>
      </a>
    </div>

    <div class="c-next">
      <h2>What happens next</h2>
      <ol>
        <li>I read your message and reply directly, no sales team.</li>
        <li>We set up a short scoping call if it makes sense.</li>
        <li>You get a clear, fixed-price proposal. No obligation.</li>
      </ol>
    </div>
  </section>

  <section class="c-card" aria-label="Contact form">
    <div class="c-card-bar" aria-hidden="true">
      <span></span>
      <span></span>
      <span></span>
      <em>new_message.txt</em>
    </div>

    <form id="form" action="https://api.web3forms.com/submit" method="POST">
      <!-- Web3Forms settings: unchanged -->
      <input type="hidden" name="access_key" value="d3bee2f3-1516-44e3-b80d-f3c3e75bbf34">
      <input type="hidden" name="subject" value="New Contact Form Submission from Web3Forms">
      <input type="hidden" name="from_name" value="My Website">
      <input type="hidden" name="redirect" value="https://nanobytesecurity.com/thanks">

      <!-- Web3Forms spam honeypot: humans never see or tick this -->
      <input type="checkbox" name="botcheck" class="c-hidden" tabindex="-1" autocomplete="off">

      <div class="c-field">
        <label for="name">Name <span class="c-req" aria-hidden="true">*</span></label>
        <input id="name" name="name" type="text" placeholder="Your name" autocomplete="name" required>
      </div>

      <div class="c-field">
        <label for="email">Email <span class="c-req" aria-hidden="true">*</span></label>
        <input id="email" name="email" type="email" placeholder="you@company.com" autocomplete="email" required>
      </div>

      <div class="c-field">
        <label for="message">Message <span class="c-req" aria-hidden="true">*</span></label>
        <textarea id="message" name="message" placeholder="What are you looking to test, and is there a deadline or requirement driving it?" required></textarea>
      </div>

      <div class="c-submit-row">
        <span class="c-note">Your details stay private.</span>
        <button type="submit">Send message</button>
      </div>
    </form>
  </section>

</main>

<script>
  // Clear the form when the page loads (e.g. after using the back button)
  window.addEventListener("load", function () {
    var form = document.getElementById("form");
    if (form) {
      form.reset();
    }
  });
</script>
