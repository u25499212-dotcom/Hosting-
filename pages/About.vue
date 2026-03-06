Thekgo Mamogobo- u25499212
<template>
  <main class="page">
    <div class="container">

      <section class="card layout">

        <!-- LEFT SIDE -->
        <aside class="left">
          <div class="photo-box">
            <img src="/images/pic.jpg" alt="Profile photo">
          </div>

          <p class="bio">
            I am an Information Science student at the University of Pretoria
            specialising in multimedia. My interests include UI/UX design,
            software development, and building modern digital experiences.
          </p>


        </aside>

        <!-- RIGHT SIDE -->
        <section class="right">

          <header class="header">
            <h1>Future UI/UX Designer & Software Developer</h1>
          </header>

          <div class="section">
            <h2>Education</h2>
            <p>
              <strong>Eduplex</strong>
              <br>2020-2024<br>
              <strong>University of Pretoria</strong><br>
              Information Science (Multimedia)
              <br>2025-current
            </p>
          </div>

          <div class="section">
            <h2>Skills</h2>
            <ul>
              <li>UI / UX Design</li>
              <li>Web Development</li>
              <li>backend development</li>
              <li>Frontend development</li>
              <li>Branding & Visual Design</li>

            </ul>
          </div>

          <div class="section">
            <h2>Software & Tech</h2>
            <div class="chips">
              <span>Photoshop</span>
              <span>Illustrator</span>
              <span>VS Code</span>
              <span>JavaScript</span>
              <span>Java</span>
              <span>C++</span>
              <span>CSS</span>
            </div>
            </div>
        </section>

      </section>

    </div>
  </main>
</template>



<style scoped>

.page{
  min-height:100vh;
  padding:120px 20px 40px;
  display:flex;
  justify-content:center;
  background:#9fd3d6;
}

.container{
  width:min(1100px,100%);
}

.card{
  background:white;
  border-radius:20px;
  padding:30px;
  box-shadow:0 20px 60px rgba(0,0,0,0.2);
}

.layout{
  display:grid;
  grid-template-columns:320px 1fr;
  gap:30px;
}


/* LEFT COLUMN */

.photo-box{
  border-radius:14px;
  overflow:hidden;
  border:3px solid #081a2a;
}

.photo-box img{
  width:100%;
  display:block;
}

.bio{
  margin-top:14px;
  line-height:1.5;
}

.contact{
  margin-top:20px;
}

.contact h3{
  margin-bottom:6px;
}


/* RIGHT COLUMN */

.header{
  display:flex;
  align-items:center;
  gap:10px;
  margin-bottom:20px;
}

.header h1{
  margin:0;
  font-size:2rem;
  color:#081a2a;
}



.section{
  margin-bottom:22px;
}

.section h2{
  margin-bottom:8px;
  color:#081a2a;
}

ul{
  padding-left:18px;
}

.chips{
  display:flex;
  flex-wrap:wrap;
  gap:10px;
}

.chips span{
  border:1px solid #081a2a;
  padding:6px 10px;
  border-radius:20px;
  font-size:0.9rem;
}




</style>