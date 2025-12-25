<template>
  <section id="catalog" class="section">
    <div class="container">
      <div class="section-head">
        <h2>Каталог</h2>
        <p>Підбірка зимового спорядження: куртки, термобілизна, рукавички та аксесуари.</p>
      </div>

      <div class="grid">
        <article v-for="p in products" :key="p.id" class="card">
          <div class="thumb" :style="{ '--h': p.hue + 'deg' }">
            <div class="badge">{{ p.tag }}</div>
          </div>

          <div class="card-body">
            <h3>{{ p.title }}</h3>
            <p class="desc">{{ p.desc }}</p>

            <div class="row">
              <div class="price">{{ p.price }} ₴</div>
              <button class="btn btn-primary" @click="addToCart(p)">Додати</button>
            </div>
          </div>
        </article>
      </div>

      <div class="note">
        <span>Демо-кошик:</span>
        <b>{{ cartCount }}</b> товар(и) додано
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";

const products = [
  { id: 1, title: "ArcticShell Jacket", desc: "Тепла мембранна куртка для активного відпочинку.", price: 3899, tag: "Top", hue: 210 },
  { id: 2, title: "FrostGrip Gloves", desc: "Рукавички з захистом від вітру та вологості.", price: 899, tag: "New", hue: 190 },
  { id: 3, title: "ThermoBase Set", desc: "Термобілизна для спорту та тривалих прогулянок.", price: 1299, tag: "Warm", hue: 220 },
  { id: 4, title: "SnowTrail Boots", desc: "Зимові черевики зі стійкою підошвою.", price: 2599, tag: "Pro", hue: 200 },
  { id: 5, title: "IceWind Balaclava", desc: "Балаклава для морозу та вітру.", price: 349, tag: "Hot", hue: 230 },
  { id: 6, title: "Blizzard Goggles", desc: "Окуляри для снігу з антифог покриттям.", price: 1599, tag: "Sport", hue: 205 },
];

const cartCount = ref(0);
function addToCart() {
  cartCount.value++;
}
</script>

<style scoped>
.section {
  padding: 70px 0;
}
.container {
  width: min(1100px, 92%);
  margin: 0 auto;
}
.section-head h2 {
  margin: 0 0 8px;
  font-size: 34px;
}
.section-head p {
  margin: 0 0 22px;
  opacity: 0.85;
}

.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 18px;
}

.card {
  background: rgba(15, 25, 35, 0.7);
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: 18px;
  overflow: hidden;
  backdrop-filter: blur(10px);
  box-shadow: 0 10px 26px rgba(0,0,0,0.25);
  transition: transform .25s ease, border-color .25s ease;
}
.card:hover {
  transform: translateY(-6px);
  border-color: rgba(60,140,255,0.35);
}

.thumb {
  height: 140px;
  background:
    radial-gradient(1200px 240px at 0% 0%, rgba(70,140,255,0.35), transparent 60%),
    radial-gradient(900px 240px at 100% 0%, rgba(0,255,255,0.12), transparent 60%),
    linear-gradient(135deg, rgba(20,30,40,0.9), rgba(12,18,25,0.9));
  position: relative;
}
.thumb::after{
  content:"";
  position:absolute; inset:-50%;
  background: radial-gradient(circle at 30% 30%, hsla(var(--h), 95%, 60%, .35), transparent 50%);
  transform: rotate(12deg);
}
.badge{
  position:absolute; top:12px; left:12px;
  z-index:1;
  padding: 6px 10px;
  border-radius: 999px;
  background: rgba(60,140,255,0.18);
  border: 1px solid rgba(60,140,255,0.35);
  font-size: 12px;
  letter-spacing: .5px;
}

.card-body { padding: 14px 14px 16px; }
.card-body h3 { margin: 0 0 8px; font-size: 18px; }
.desc { margin: 0 0 14px; opacity: .85; font-size: 14px; line-height: 1.35; }

.row{
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap: 10px;
}
.price{
  font-size: 18px;
  font-weight: 700;
}
.btn{
  border: 0;
  cursor: pointer;
  padding: 10px 14px;
  border-radius: 12px;
  transition: transform .15s ease, filter .2s ease;
}
.btn:active{ transform: translateY(1px) scale(.99); }

.btn-primary{
  background: linear-gradient(90deg, rgba(60,140,255,1), rgba(20,210,255,1));
  color: #071018;
  font-weight: 700;
}

.note{
  margin-top: 18px;
  padding: 14px 16px;
  border-radius: 14px;
  background: rgba(15,25,35,0.55);
  border: 1px solid rgba(255,255,255,0.08);
}
.note span{ opacity: .85; margin-right: 8px; }

@media (max-width: 980px){
  .grid{ grid-template-columns: repeat(2,1fr); }
}
@media (max-width: 640px){
  .grid{ grid-template-columns: 1fr; }
}
</style>
