---
permalink: /contact/
title: "Contact Me"
author_profile: true
---

Feel free to reach out for collaborations, discussions on AI safety, or just a chat!

<div class="contact-box">
  
  <form action="https://formspree.io/f/YOUR_FORM_ID" method="POST" class="smart-form">
    
    <div class="form-group">
      <label for="name">Your Name</label>
      <input type="text" id="name" name="name" required>
    </div>
    
    <div class="form-group">
      <label for="email">Your Email</label>
      <input type="email" id="email" name="email" required>
    </div>
    
    <div class="form-group">
      <label for="message">Message</label>
      <textarea id="message" name="message" rows="5" required></textarea>
    </div>
    
    <button type="submit" class="btn btn--primary btn--large" style="width: 100%;">Send Message</button>
  </form>
</div>

<style>
  /* 1. THE BOX CONTAINER */
  .contact-box {
    padding: 30px;
    border-radius: 8px;
    margin-top: 20px;
    /* Adapts to the theme's background automatically or falls back to a neutral grey */
    background: rgba(128, 128, 128, 0.1); 
    border: 1px solid rgba(128, 128, 128, 0.2);
  }

  /* 2. LABELS */
  .smart-form label {
    display: block;
    margin-bottom: 8px;
    font-weight: bold;
    color: inherit !important; 
  }

  /* 3. INPUT FIELDS */
  .smart-form input,
  .smart-form textarea {
    width: 100%;
    padding: 12px;
    margin-bottom: 20px;
    border-radius: 5px;
    font-family: inherit;
    font-size: 1rem;
    background-color: transparent !important;
    color: inherit !important;
    border: 1px solid currentColor !important;
    opacity: 0.7; 
  }

  /* Focus Effect */
  .smart-form input:focus,
  .smart-form textarea:focus {
    opacity: 1;
    outline: none;
    box-shadow: 0 0 5px rgba(128, 128, 128, 0.5);
  }
</style>