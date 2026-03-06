Thekgo Mamogobo- u25499212

<template>
  <main class="page">
    <div class="container">
      <section class="card">
        <header class="header">
          <h1>Projects</h1>
        </header>

        <p class="subtitle">Some of the projects I have worked on.</p>

        <div class="projects">

          <!-- Project 1 -->
          <div class="project">
            <h2>Vacation Oasis Travel Website</h2>

            <p>
              A responsive travel website showcasing South African destinations,
              package pricing, and a booking enquiry form.
            </p>

            <ul>
              <li>HTML</li>
              <li>CSS</li>
              <li>Form handling</li>
              <li>Responsive layout</li>
            </ul>

          <a href="/projects/Vacation Oasis.pdf" target="_blank">View Project</a>
          </div>

          <!-- Project 2 -->
          <div class="project">
            <h2>Normal People Fan Site</h2>

            <p>
              A multi-page website about <em>Normal People</em> by Sally Rooney, featuring navigation,
              content pages, a gallery (images + video), and a fan club form with JavaScript validation.
            </p>

            <ul>
              <li>HTML &amp; CSS (multi-page layout)</li>
              <li>Navigation + content structure</li>
              <li>Gallery page with video</li>
              <li>Fan club form + JS validation</li>
            </ul>

            <a href="/projects/Normal People.pdf" target="_blank">View Project</a>
          </div>

          <!-- Project 3 -->
          <div class="project">
            <h2>SPARKED – Digital Comic</h2>

            <p>
              A digital comic illustrating the journey of creativity,
              perseverance, and innovation through visual storytelling.
              The project combines illustration, layout design,
              and narrative structure to communicate the idea that
              failure is part of the path to success.
            </p>

            <ul>
              <li>Illustration</li>
              <li>Visual storytelling</li>
              <li>Comic layout design</li>
              <li>Digital design</li>
            </ul>

            <a href="/projects/sparked.pdf" target="_blank">View Project</a>
          </div>

        </div> <!-- ✅ CLOSES .projects -->

      </section> <!-- ✅ CLOSES .card -->
    </div>
  </main>
</template>

<style scoped>
.page{
  min-height:100vh;
  padding:120px 20px;
  display:flex;
  justify-content:center;
  background:#9fd3d6; /* teal */
}

.container{
  width:min(1000px,100%);
}

.card{
  background:white;
  padding:30px;
  border-radius:20px;
  box-shadow:0 15px 40px rgba(0,0,0,0.2);
}

.header{
  display:flex;
  align-items:center;
  gap:10px;
}

.header h1{
  font-size:2rem;
  margin:0;
  color:#081a2a;
}

.star{
  background:#f4d13a;
  padding:6px 10px;
  border-radius:20px;
  font-weight:bold;
}

.subtitle{
  margin:10px 0 25px;
}

.projects{
  display:grid;
  gap:20px;
}

.project{
  border:1px solid rgba(0,0,0,0.1);
  padding:20px;
  border-radius:14px;
  background: rgba(244,209,58,.35); /* soft yellow */
}

.project h2{
  margin-top:0;
  color:#081a2a;
}

.project a{
  display:inline-block;
  margin-top:10px;
  text-decoration:none;
  font-weight:bold;
  color:#081a2a;
}

.project a:hover{
  text-decoration:underline;
}
</style>