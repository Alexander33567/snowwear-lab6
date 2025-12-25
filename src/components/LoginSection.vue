<template>
  <section id="login" class="section">
    <div class="container">
      <div class="wrap">
        <div class="left">
          <h2>Вхід</h2>
          <p>Демо-форма для лабораторної. Перевіряє заповненість та мінімальну довжину пароля.</p>

          <ul class="tips">
            <li>✅ Простий UI</li>
            <li>✅ Валідація</li>
            <li>✅ Повідомлення про успіх</li>
          </ul>
        </div>

        <form class="card" @submit.prevent="onSubmit">
          <label>
            Email
            <input v-model.trim="email" type="email" placeholder="name@mail.com" />
          </label>

          <label>
            Пароль
            <input v-model.trim="password" type="password" placeholder="мін. 6 символів" />
          </label>

          <button class="btn" type="submit">Увійти</button>

          <p v-if="error" class="msg error">{{ error }}</p>
          <p v-else-if="ok" class="msg ok">✅ Успішний вхід (демо)</p>
        </form>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from "vue";

const email = ref("");
const password = ref("");
const error = ref("");
const ok = ref(false);

function onSubmit() {
  ok.value = false;
  error.value = "";

  if (!email.value || !password.value) {
    error.value = "Заповни email і пароль.";
    return;
  }
  if (password.value.length < 6) {
    error.value = "Пароль має бути мінімум 6 символів.";
    return;
  }

  ok.value = true;
}
</script>

<style scoped>
.section{ padding: 70px 0 90px; }
.container{ width: min(1100px, 92%); margin: 0 auto; }

.wrap{
  display:grid;
  grid-template-columns: 1.1fr .9fr;
  gap: 20px;
  align-items: start;
}

.left h2{ margin: 0 0 8px; font-size: 34px; }
.left p{ margin: 0 0 16px; opacity: .85; max-width: 520px; }

.tips{
  margin: 0; padding-left: 18px;
  opacity: .9;
}
.tips li{ margin: 8px 0; }

.card{
  background: rgba(15, 25, 35, 0.75);
  border: 1px solid rgba(255,255,255,0.08);
  border-radius: 18px;
  padding: 16px;
  backdrop-filter: blur(10px);
  box-shadow: 0 10px 26px rgba(0,0,0,0.25);
}

label{
  display:block;
  margin-bottom: 12px;
  font-size: 14px;
  opacity: .95;
}
input{
  width:100%;
  margin-top: 6px;
  padding: 12px 12px;
  border-radius: 12px;
  border: 1px solid rgba(255,255,255,0.12);
  background: rgba(10,15,20,0.55);
  color: white;
  outline: none;
}
input:focus{
  border-color: rgba(60,140,255,0.55);
  box-shadow: 0 0 0 3px rgba(60,140,255,0.18);
}

.btn{
  width:100%;
  padding: 12px 14px;
  border-radius: 12px;
  border: 0;
  cursor:pointer;
  font-weight: 800;
  color: #071018;
  background: linear-gradient(90deg, rgba(60,140,255,1), rgba(20,210,255,1));
}

.msg{ margin: 12px 0 0; font-size: 14px; }
.error{ color: #ff8a8a; }
.ok{ color: #7fffd0; }

@media (max-width: 900px){
  .wrap{ grid-template-columns: 1fr; }
}
</style>
