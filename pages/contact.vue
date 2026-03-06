Thekgo Mamogobo- u25499212

<template>
  <main class="page">
    <div class="container">
      <section class="card">
        <header class="head">
          <h1 class="h1">Contact</h1>
          <p class="small">Feel free to send me a message using the form below.</p>
        </header>

        <!-- Contact info -->
        <div class="info">
          <p><strong>Email:</strong> <a class="link" href="mailto:thekgomamogobo4@gmail.com">thekgomamogobo4@gmail.com</a></p>
          <p><strong>Phone:</strong> 076 826 1041</p>
        </div>

        <!-- NETLIFY FORM -->
        <form
          name="contact"
          method="POST"
          data-netlify="true"
          netlify-honeypot="bot-field"
          class="form"
        >
          <!-- Required hidden input for Netlify -->
          <input type="hidden" name="form-name" value="contact" />

          <!-- Honeypot field (spam protection) -->
          <p class="hidden">
            <label>Don’t fill this out: <input name="bot-field" /></label>
          </p>

          <div class="field">
            <label for="name">Name</label>
            <input id="name" name="name" type="text" required placeholder="Your name" />
          </div>

          <div class="field">
            <label for="email">Email</label>
            <input id="email" name="email" type="email" required placeholder="your@email.com" />
          </div>

          <div class="field">
            <label for="message">Message</label>
            <textarea id="message" name="message" rows="6" required placeholder="Type your message..."></textarea>
          </div>

          <div class="actions">
            <button class="btn" type="submit">Send</button>
          </div>
        </form>
      </section>
    </div>
  </main>
</template>

<style scoped>

.page{
  min-height: 100vh;
  padding: 120px 18px 40px;
  display:flex;
  justify-content:center;
  background: #9fd3d6; 
}

.container{
  width: min(900px, 100%);
}

.card{
  background: #fff;
  border-radius: 18px;
  box-shadow: 0 18px 60px rgba(0,0,0,.18);
  padding: 22px;
  border: 1px solid rgba(8,26,42,.10);
}

.head{
  margin-bottom: 12px;
}

.h1{
  margin: 0 0 8px;
  font-size: 2.2rem;
  font-weight: 900;
  letter-spacing: .2px;
  color: #081a2a; 
}

.small{
  opacity: .8;
  color: rgba(8,26,42,.75);
}

.info{
  margin: 14px 0 18px;
  padding: 12px 14px;
  border-radius: 14px;
  background: rgba(244,209,58,.35); 
  border: 1px solid rgba(8,26,42,.10);
}

.link{
  color: #081a2a;
  text-decoration: none;
  font-weight: 800;
}

.link:hover{
  text-decoration: underline;
}

.form{
  display:grid;
  gap: 12px;
}

.field label{
  display:block;
  font-weight: 800;
  margin: 0 0 6px;
  color: #081a2a;
}

input, textarea{
  width: 100%;
  padding: 12px 12px;
  border-radius: 14px;
  border: 1px solid rgba(8,26,42,.25);
  background: #fff;
  color: #081a2a;
  font: inherit;
  outline: none;
}

input:focus, textarea:focus{
  border-color: rgba(8,26,42,.65);
}

.actions{
  display:flex;
  gap: 12px;
  align-items:center;
  flex-wrap: wrap;
  margin-top: 6px;
}

.btn{
  border: 2px solid #081a2a;
  background: #081a2a;
  color: white;
  padding: 10px 16px;
  border-radius: 999px;
  font-weight: 900;
  cursor: pointer;
}

.btn:hover{
  transform: translateY(-1px);
}

.note{
  margin: 0;
}

.hidden{ display:none; }
</style>