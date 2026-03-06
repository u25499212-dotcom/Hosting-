Thekgo Mamogobo- u25499212

<script setup lang="ts">
type WeatherResult = {
  ok: boolean
  current?: {
    temperature_2m?: number
    wind_speed_10m?: number
  }
  message?: string
}

type HolidaysResult = {
  ok: boolean
  country?: string
  year?: number
  holidays?: { date: string; name: string; localName: string }[]
  message?: string
}

const cityName = ref("Pretoria")

// Pretoria coords (change later if you want)
const lat = ref(-25.7479)
const lon = ref(28.2293)

const country = ref("ZA")
const year = ref(new Date().getFullYear())

const weather = ref<WeatherResult>({ ok: false })
const holidays = ref<HolidaysResult>({ ok: false })

const loadingWeather = ref(false)
const loadingHolidays = ref(false)

async function loadWeather() {
  loadingWeather.value = true
  try {
    const url =
      `https://api.open-meteo.com/v1/forecast?latitude=${lat.value}&longitude=${lon.value}` +
      `&current=temperature_2m,wind_speed_10m&timezone=Africa%2FJohannesburg`

    const data: any = await $fetch(url)
    weather.value = { ok: true, current: data?.current ?? {} }
  } catch {
    weather.value = { ok: false, message: "Failed to load weather." }
  } finally {
    loadingWeather.value = false
  }
}

async function loadHolidays() {
  loadingHolidays.value = true
  try {
    const url = `https://date.nager.at/api/v3/PublicHolidays/${year.value}/${country.value}`
    const data: any[] = await $fetch(url)

    holidays.value = {
      ok: true,
      country: country.value,
      year: year.value,
      holidays: (Array.isArray(data) ? data : []).map((h: any) => ({
        date: h.date,
        name: h.name,
        localName: h.localName
      }))
    }
  } catch {
    holidays.value = { ok: false, message: "Failed to load holidays." }
  } finally {
    loadingHolidays.value = false
  }
}

onMounted(() => {
  loadWeather()
  loadHolidays()
})
</script>

<template>
  <main class="page">
    <div class="container">
      <section class="card">
        <header class="head">
          <h1 class="h1">API</h1>
          <p class="small">
            Dynamic content from two public APIs: Weather (Open-Meteo) and Public Holidays (Nager.Date).
          </p>
        </header>

        <div class="grid">
          <!-- WEATHER CARD -->
          <section class="panel">
            <div class="row">
              <h2 class="h2">Weather</h2>
              <button class="btn" type="button" @click="loadWeather">Refresh</button>
            </div>

            <p class="small">Location: <strong>{{ cityName }}</strong></p>

            <p v-if="loadingWeather" class="small">Loading weather…</p>

            <div v-else-if="weather.ok && weather.current" class="data">
              <p><strong>Temperature:</strong> {{ weather.current.temperature_2m ?? "—" }} °C</p>
              <p><strong>Wind:</strong> {{ weather.current.wind_speed_10m ?? "—" }} km/h</p>
              <p class="small note">Source: Open-Meteo</p>
            </div>

            <p v-else class="small">{{ weather.message || "Could not load weather." }}</p>
          </section>

          <!-- HOLIDAYS CARD -->
          <section class="panel">
            <div class="row">
              <h2 class="h2">Public Holidays</h2>
              <button class="btn" type="button" @click="loadHolidays">Refresh</button>
            </div>

            <div class="filters">
              <div>
                <label>Country</label>
                <input v-model="country" placeholder="ZA" />
              </div>
              <div>
                <label>Year</label>
                <input v-model.number="year" type="number" />
              </div>
            </div>

            <p v-if="loadingHolidays" class="small">Loading holidays…</p>

            <div v-else-if="holidays.ok && holidays.holidays?.length">
              <ul class="list">
                <li v-for="h in holidays.holidays.slice(0, 10)" :key="h.date">
                  <strong>{{ h.date }}</strong> — {{ h.name }}
                  <span class="small">({{ h.localName }})</span>
                </li>
              </ul>
              <p class="small note">Showing first 10 holidays.</p>
            </div>

            <p v-else class="small">{{ holidays.message || "Could not load holidays." }}</p>
          </section>
        </div>
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
  width: min(1100px, 100%);
}

.card{
  background: #fff;
  border-radius: 18px;
  box-shadow: 0 18px 60px rgba(0,0,0,.18);
  padding: 22px;
  border: 1px solid rgba(8,26,42,.10);
}

.head{
  margin-bottom: 14px;
}

.h1{
  margin: 0 0 8px;
  font-size: 2.2rem;
  font-weight: 900;
  color: #081a2a;
}



.small{ opacity: .82; color: rgba(8,26,42,.75); }
.note{ margin-top: 10px; }

.grid{
  margin-top: 16px;
  display: grid;
  gap: 16px;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
}

.panel{
  border: 1px solid rgba(8,26,42,.12);
  border-radius: 16px;
  padding: 16px;
  background: rgba(244,209,58,.35) ;/* soft yellow tint */
}

.row{
  display:flex;
  justify-content:space-between;
  align-items:center;
  gap: 10px;
  margin-bottom: 8px;
}

.h2{
  margin: 0;
  font-size: 1.3rem;
  font-weight: 900;
  color: #081a2a;
}

.btn{
  border: 2px solid #081a2a;
  background: #081a2a;
  color: white;
  padding: 8px 14px;
  border-radius: 999px;
  font-weight: 900;
  cursor: pointer;
}

.btn:hover{ transform: translateY(-1px); }

.filters{
  margin: 10px 0 12px;
  display:grid;
  gap: 10px;
  grid-template-columns: 1fr 1fr;
}

label{
  display:block;
  font-weight: 800;
  margin-bottom: 6px;
  color: #081a2a;
}

input{
  width: 100%;
  padding: 10px 10px;
  border-radius: 14px;
  border: 1px solid rgba(8,26,42,.25);
  background: #fff;
  font: inherit;
}

.list{
  margin: 0;
  padding-left: 18px;
  line-height: 1.6;
}
</style>