<template>
  <div>
    <header class="top-nav">
      <nav class="nav-tabs">
         <NuxtLink to="/" class="tab">Home</NuxtLink>
        <NuxtLink to="/about" class="tab">About Me</NuxtLink>
        <NuxtLink to="/contact" class="tab">Contact</NuxtLink>
        <NuxtLink to="/projects" class="tab">Projects</NuxtLink>
        <NuxtLink to="/api" class="tab">API</NuxtLink>

      </nav>
    </header>

     <!-- Page content -->
    <NuxtPage />
  </div>
</template>

<style>
.top-nav{
  position: fixed;
  top: 20px;
  left: 0;
  right: 0;
  display: flex;
  justify-content: center;
  z-index: 10;
}

.nav-tabs{
  display: flex;
  gap: 25px;
  padding: 10px 20px;
  border-radius: 12px;
  background:#071828;
  backdrop-filter: blur(6px);
}

.tab{
  color: white;
  text-decoration: none;
  position: relative;
  font-size: 16px;
}

/* underline hover effect */
.tab::after{
  content: "";
  position: absolute;
  left: 0;
  bottom: -3px;
  width: 100%;
  height: 2px;
  background: white;
  transform: scaleX(0);
  transition: transform 0.2s ease;
}

.tab:hover::after{
  transform: scaleX(1);
}
</style>