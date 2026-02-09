---
permalink: /contact/
title: "Get in Touch"
author_profile: true
---

I’m happy to connect for collaborations, discussions, or just a chat.
Please fill out the form below.

<div class="contact-box">
  
  <div id="success-message" style="display: none; text-align: center; padding: 20px;">
    <h3 style="margin-top: 0;">Thanks for your message!
    I'll get back to you soon.</h3>
  </div>

  <form id="contact-form" action="https://formspree.io/f/mwvnpljw" method="POST" class="smart-form">
    
    <div class="form-group">
      <label for="name">Your Name</label>
      <input type="text" id="name" name="name" placeholder="Your Name" pattern="^[a-zA-Z][a-zA-Z\s\.]*$" title="Name must start with a letter and cannot contain numbers" required>
    </div>
    
    <div class="form-group">
      <label for="email">Your Email</label>
      <input type="email" id="email" name="email"  placeholder="Your Email address" required>
    </div>
    
    <div class="form-group">
      <label for="message">Message</label>
      <textarea id="message" name="message" placeholder="Your Message" rows="5" required></textarea>
    </div>
    
    <button type="submit" class="btn btn--primary btn--large" style="width: 100%;">Send Message</button>
    <p id="error-message" style="color: red; display: none;">Oops! There was a problem submitting your form.</p>
  </form>
</div>

<script>
  var form = document.getElementById("contact-form");
  
  async function handleSubmit(event) {
    event.preventDefault(); // STOP the redirect
    var data = new FormData(event.target);
    
    fetch(event.target.action, {
      method: form.method,
      body: data,
      headers: {
          'Accept': 'application/json'
      }
    }).then(response => {
      if (response.ok) {
        form.style.display = "none";
        document.getElementById("success-message").style.display = "block";
        form.reset();
      } else {
        response.json().then(data => {
          if (Object.hasOwn(data, 'errors')) {
            document.getElementById("error-message").innerText = data["errors"].map(error => error["message"]).join(", ")
          } else {
            document.getElementById("error-message").style.display = "block";
          }
        })
      }
    }).catch(error => {
      document.getElementById("error-message").style.display = "block";
    });
  }
  form.addEventListener("submit", handleSubmit)
</script>

<style>
  .contact-box {
    padding: 30px;
    border-radius: 8px;
    margin-top: 20px;
    background: rgba(128, 128, 128, 0.1); 
    border: 1px solid rgba(128, 128, 128, 0.2);
  }
  .smart-form label {
    display: block;
    margin-bottom: 8px;
    font-weight: bold;
    color: inherit !important; 
  }
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
  .smart-form input:focus,
  .smart-form textarea:focus {
    opacity: 1;
    outline: none;
    box-shadow: 0 0 5px rgba(128, 128, 128, 0.5);
  }
  #success-message h3, #success-message p {
    color: inherit !important;
  }
</style>