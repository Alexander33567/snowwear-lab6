<template>
  <header class="header">
    <div class="logo">SnowWear</div>

    <nav class="nav">
<a href="#home">Home</a>
<a href="#catalog">Catalog</a>
<a href="#login">Login</a>
    </nav>
  </header>
</template>

<style scoped>
.header {
  height: 80px;
  padding: 0 60px;
  display: flex;
  justify-content: space-between;
  align-items: center;

  background: rgba(15, 25, 35, 0.85);
  border-bottom: 1px solid rgba(255, 255, 255, 0.08);
  backdrop-filter: blur(10px);
}

.logo {
  font-size: 26px;
  font-weight: 800;
  color: #e6f4ff;
  letter-spacing: 0.5px;
  text-shadow: 0 0 16px rgba(120, 200, 255, 0.15);
}

.nav a {
  margin-left: 30px;
  color: #c9dceb;
  text-decoration: none;
  font-size: 16px;
  transition: color 0.25s, text-shadow 0.25s;
}

.nav a:hover {
  color: #ffffff;
  text-shadow: 0 0 14px rgba(120, 200, 255, 0.25);
}
</style>
