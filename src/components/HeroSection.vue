<template>
  <section class="hero">
    <div class="content">
      <div class="badge">Winter Collection</div>

      <h1>Інтернет-магазин SnowWear</h1>
      <p>Одяг та аксесуари для активного зимового відпочинку</p>

      <div class="actions">
        <button class="btn primary">Primary button</button>
        <button class="btn ghost">Детальніше</button>
      </div>
    </div>
  </section>
</template>

<style scoped>
.hero {
  height: calc(100vh - 80px);
  padding: 0 60px;
  display: flex;
  align-items: center;

  background:
    radial-gradient(900px 500px at 10% 30%, rgba(59, 130, 246, 0.22), transparent 60%),
    radial-gradient(700px 400px at 80% 50%, rgba(100, 210, 255, 0.14), transparent 60%),
    linear-gradient(120deg, #0b1d2a, #142b3c);
}

.content { max-width: 720px; }

.badge {
  display: inline-block;
  padding: 8px 12px;
  border-radius: 999px;
  font-size: 12px;
  letter-spacing: 0.8px;
  text-transform: uppercase;
  color: #d9f0ff;
  background: rgba(255, 255, 255, 0.08);
  border: 1px solid rgba(255, 255, 255, 0.10);
  margin-bottom: 18px;
}

h1 {
  font-size: 46px;
  line-height: 1.1;
  color: #ffffff;
  text-shadow: 0 0 22px rgba(120, 200, 255, 0.12);
}

p {
  margin: 18px 0 28px;
  font-size: 18px;
  color: #cddfeb;
  max-width: 560px;
}

.actions { display: flex; gap: 14px; }

.btn {
  padding: 14px 16px;
  border-radius: 12px;
  font-size: 16px;
  cursor: pointer;
  transition: transform 0.18s, box-shadow 0.18s, background 0.18s;
}
.btn:hover { transform: translateY(-2px); }

.primary {
  width: 240px;
  border: none;
  background: #3b82f6;
  color: white;
}
.primary:hover { box-shadow: 0 12px 26px rgba(59, 130, 246, 0.35); }

.ghost {
  border: 1px solid rgba(255, 255, 255, 0.12);
  background: rgba(255, 255, 255, 0.06);
  color: #e6f4ff;
}
.ghost:hover { background: rgba(255, 255, 255, 0.10); }
</style>
// lab6 marker 
