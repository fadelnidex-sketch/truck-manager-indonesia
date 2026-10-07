const STORAGE_KEY = 'truck_manager_indonesia_v1';
const CITY_OPTIONS = [
  'Pekanbaru', 'Dumai', 'Duri', 'Medan', 'Padang', 'Jambi', 'Palembang', 'Jakarta',
  'Bandung', 'Semarang', 'Surabaya', 'Pontianak', 'Banjarmasin', 'Samarinda', 'Balikpapan'
];

const LOGO_OPTIONS = [
  { label: 'Nusa', icon: '🚚' },
  { label: 'Cargo', icon: '📦' },
  { label: 'Trans', icon: '🚛' },
  { label: 'Mitra', icon: '🛻' },
  { label: 'Raya', icon: '🏭' },
  { label: 'Jaya', icon: '🧱' }
];

const TRUCK_MODELS = [
  { id: 'colt-diesel', name: 'Colt Diesel', price: 280000000, tonnage: 3.5, fuelUse: 0.24, speed: 62, power: 120, year: 2019, maintenance: 3200000, bodyType: 'Bak Standar' },
  { id: 'canter', name: 'Canter', price: 420000000, tonnage: 5, fuelUse: 0.26, speed: 68, power: 150, year: 2020, maintenance: 4700000, bodyType: 'Bak Standar' },
  { id: 'elf', name: 'Isuzu Elf', price: 480000000, tonnage: 4.5, fuelUse: 0.25, speed: 66, power: 160, year: 2021, maintenance: 5100000, bodyType: 'Bak Standar' },
  { id: 'dutro', name: 'Hino Dutro', price: 520000000, tonnage: 5, fuelUse: 0.28, speed: 70, power: 170, year: 2021, maintenance: 5800000, bodyType: 'Bak Standar' },
  { id: 'ranger', name: 'Hino Ranger', price: 610000000, tonnage: 7, fuelUse: 0.31, speed: 74, power: 220, year: 2022, maintenance: 6900000, bodyType: 'Bak Tinggi' },
  { id: 'hino-500', name: 'Hino 500', price: 820000000, tonnage: 9, fuelUse: 0.38, speed: 78, power: 260, year: 2023, maintenance: 9200000, bodyType: 'Bak Tinggi' },
  { id: 'fighter', name: 'Mitsubishi Fighter', price: 760000000, tonnage: 8, fuelUse: 0.36, speed: 72, power: 250, year: 2022, maintenance: 8200000, bodyType: 'Bak Besi' },
  { id: 'ud-truck', name: 'UD Trucks', price: 900000000, tonnage: 10, fuelUse: 0.4, speed: 76, power: 280, year: 2023, maintenance: 9800000, bodyType: 'Box' },
  { id: 'volvo', name: 'Volvo Truck', price: 1500000000, tonnage: 15, fuelUse: 0.46, speed: 80, power: 420, year: 2023, maintenance: 14500000, bodyType: 'Wingbox' },
  { id: 'scania', name: 'Scania', price: 1750000000, tonnage: 18, fuelUse: 0.5, speed: 82, power: 470, year: 2024, maintenance: 18000000, bodyType: 'Container' },
  { id: 'mb-truck', name: 'Mercedes-Benz Truck', price: 1950000000, tonnage: 20, fuelUse: 0.54, speed: 84, power: 500, year: 2024, maintenance: 21000000, bodyType: 'Trailer' }
];

const BODY_TYPES = [
  { id: 'bak-kayu', name: 'Bak Kayu', capacity: 4, price: 30000000, weight: 900, function: 'Umum' },
  { id: 'bak-besi', name: 'Bak Besi', capacity: 6, price: 42000000, weight: 1100, function: 'Muatan berat' },
  { id: 'bak-tinggi', name: 'Bak Tinggi', capacity: 7, price: 48000000, weight: 1200, function: 'Barang volumetrik' },
  { id: 'bak-standar', name: 'Bak Standar', capacity: 5, price: 26000000, weight: 850, function: 'Umum' },
  { id: 'bak-dump', name: 'Bak Dump', capacity: 8, price: 76000000, weight: 1400, function: 'Pasir/Batu' },
  { id: 'bak-pasir', name: 'Bak Pasir', capacity: 6, price: 39000000, weight: 1000, function: 'Pasir' },
  { id: 'bak-sawit', name: 'Bak Sawit', capacity: 8, price: 52000000, weight: 1500, function: 'Sawit/TBS' },
  { id: 'bak-kontainer', name: 'Bak Kontainer', capacity: 12, price: 98000000, weight: 1750, function: 'Kontainer' },
  { id: 'flatbed', name: 'Flatbed', capacity: 9, price: 64000000, weight: 1300, function: 'Besi/Baja' },
  { id: 'wingbox', name: 'Wingbox', capacity: 10, price: 115000000, weight: 1900, function: 'Barang tertutup' },
  { id: 'box', name: 'Box', capacity: 8, price: 90000000, weight: 1600, function: 'Barang eceran' },
  { id: 'tangki', name: 'Tangki', capacity: 7, price: 110000000, weight: 1800, function: 'Cairan/Pupuk' },
  { id: 'trailer', name: 'Trailer', capacity: 16, price: 245000000, weight: 2300, function: 'Muatan besar' }
];

const CARGO_TYPES = [
  { id: 'sawit', name: 'Sawit', weight: 7, revenue: 7600000, distance: 140, duration: 7, risk: 12, body: 'bak-sawit', tonnage: 7 },
  { id: 'tbs', name: 'TBS Kelapa Sawit', weight: 6, revenue: 6200000, distance: 180, duration: 9, risk: 14, body: 'bak-sawit', tonnage: 6 },
  { id: 'beras', name: 'Beras', weight: 4, revenue: 4200000, distance: 210, duration: 10, risk: 10, body: 'bak-standar', tonnage: 4 },
  { id: 'semen', name: 'Semen', weight: 8, revenue: 5400000, distance: 170, duration: 11, risk: 11, body: 'bak-besi', tonnage: 8 },
  { id: 'pasir', name: 'Pasir', weight: 7, revenue: 3900000, distance: 95, duration: 6, risk: 9, body: 'bak-pasir', tonnage: 7 },
  { id: 'batu', name: 'Batu', weight: 9, revenue: 4500000, distance: 160, duration: 8, risk: 10, body: 'bak-dump', tonnage: 9 },
  { id: 'kayu', name: 'Kayu', weight: 6, revenue: 5100000, distance: 250, duration: 13, risk: 16, body: 'bak-kayu', tonnage: 6 },
  { id: 'pupuk', name: 'Pupuk', weight: 5, revenue: 4000000, distance: 200, duration: 11, risk: 9, body: 'tangki', tonnage: 5 },
  { id: 'cpo', name: 'CPO', weight: 8, revenue: 9000000, distance: 220, duration: 12, risk: 15, body: 'tangki', tonnage: 8 },
  { id: 'besi', name: 'Besi', weight: 9, revenue: 7200000, distance: 180, duration: 10, risk: 12, body: 'flatbed', tonnage: 9 },
  { id: 'baja', name: 'Baja', weight: 10, revenue: 8800000, distance: 280, duration: 14, risk: 18, body: 'flatbed', tonnage: 10 },
  { id: 'barang-toko', name: 'Barang Toko', weight: 5, revenue: 6100000, distance: 150, duration: 9, risk: 9, body: 'box', tonnage: 5 },
  { id: 'elektronik', name: 'Elektronik', weight: 4, revenue: 7800000, distance: 210, duration: 10, risk: 12, body: 'wingbox', tonnage: 4 },
  { id: 'bahan-bangunan', name: 'Bahan Bangunan', weight: 8, revenue: 6200000, distance: 120, duration: 7, risk: 11, body: 'bak-tinggi', tonnage: 8 },
  { id: 'sembako', name: 'Sembako', weight: 4, revenue: 5100000, distance: 140, duration: 8, risk: 8, body: 'box', tonnage: 4 },
  { id: 'barang-industri', name: 'Barang Industri', weight: 9, revenue: 8700000, distance: 260, duration: 13, risk: 16, body: 'wingbox', tonnage: 9 },
  { id: 'kontainer', name: 'Kontainer', weight: 12, revenue: 11000000, distance: 400, duration: 18, risk: 20, body: 'bak-kontainer', tonnage: 12 }
];

const MARKET_CONTRACTS = [
  { id: 'c-1', title: 'Angkut 50 ton semen dari Pekanbaru ke Dumai', origin: 'Pekanbaru', destination: 'Dumai', tonnage: 5, payment: 9000000, deadline: 3, minReputation: 10, body: 'bak-besi', kind: 'contract', risk: 12 },
  { id: 'c-2', title: 'Angkut 7 ton CPO dari Padang ke Jakarta', origin: 'Padang', destination: 'Jakarta', tonnage: 7, payment: 18000000, deadline: 5, minReputation: 15, body: 'tangki', kind: 'contract', risk: 15 },
  { id: 'c-3', title: 'Angkut 9 ton baja dari Jakarta ke Bandung', origin: 'Jakarta', destination: 'Bandung', tonnage: 9, payment: 12000000, deadline: 4, minReputation: 12, body: 'flatbed', kind: 'contract', risk: 11 },
  { id: 'c-4', title: 'Angkut 6 ton beras dari Surabaya ke Semarang', origin: 'Surabaya', destination: 'Semarang', tonnage: 6, payment: 11000000, deadline: 4, minReputation: 10, body: 'bak-standar', kind: 'contract', risk: 10 },
  { id: 'c-5', title: 'Angkut 10 ton pasir dari Bandung ke Jakarta', origin: 'Bandung', destination: 'Jakarta', tonnage: 10, payment: 14000000, deadline: 5, minReputation: 13, body: 'bak-dump', kind: 'contract', risk: 12 },
  { id: 'c-6', title: 'Angkut 12 ton kontainer dari Balikpapan ke Samarinda', origin: 'Balikpapan', destination: 'Samarinda', tonnage: 12, payment: 21000000, deadline: 6, minReputation: 18, body: 'bak-kontainer', kind: 'contract', risk: 18 }
];

const RANDOM_EVENTS = [
  { name: 'Ban bocor', delay: 1.5, cost: 600000, type: 'tire' },
  { name: 'Mesin overheat', delay: 2, cost: 900000, type: 'engine' },
  { name: 'Jalan rusak', delay: 3, cost: 1400000, type: 'road' },
  { name: 'Macet', delay: 2.5, cost: 500000, type: 'traffic' },
  { name: 'Hujan', delay: 1.2, cost: 350000, type: 'rain' },
  { name: 'Loading terlambat', delay: 1.8, cost: 400000, type: 'loading' },
  { name: 'Antrean pelabuhan', delay: 3.2, cost: 850000, type: 'port' },
  { name: 'Razia', delay: 1.1, cost: 750000, type: 'police' }
];

const routeDistance = {
  'Pekanbaru-Dumai': 120,
  'Pekanbaru-Duri': 85,
  'Pekanbaru-Medan': 440,
  'Pekanbaru-Jakarta': 1190,
  'Dumai-Pekanbaru': 120,
  'Duri-Pekanbaru': 85,
  'Medan-Padang': 420,
  'Padang-Jambi': 310,
  'Jambi-Palembang': 280,
  'Palembang-Jakarta': 560,
  'Jakarta-Bandung': 150,
  'Jakarta-Semarang': 470,
  'Jakarta-Surabaya': 700,
  'Bandung-Jakarta': 150,
  'Semarang-Surabaya': 310,
  'Surabaya-Balikpapan': 1420,
  'Surabaya-Samarinda': 1300,
  'Samarinda-Balikpapan': 230,
  'Pontianak-Banjarmasin': 470,
  'Banjarmasin-Samarinda': 480,
  'Balikpapan-Samarinda': 230,
  'Samarinda-Pontianak': 760,
  'Jakarta-Medan': 1450,
  'Medan-Jakarta': 1450,
  'Padang-Jakarta': 1180,
  'Jakarta-Padang': 1180,
  'Pekanbaru-Padang': 520,
  'Padang-Pekanbaru': 520,
  'Jakarta-Palembang': 620,
  'Palembang-Jakarta': 620,
  'Semarang-Jakarta': 470,
  'Jakarta-Semarang': 470,
  'Pontianak-Samarinda': 760,
  'Samarinda-Pontianak': 760,
  'Dumai-Medan': 330,
  'Medan-Dumai': 330,
  'Duri-Medan': 360,
  'Medan-Duri': 360,
  'Balikpapan-Banjarmasin': 670,
  'Banjarmasin-Balikpapan': 670
};

let state = loadState();
let currentView = 'dashboard';
let lastFrameTime = Date.now();

document.addEventListener('DOMContentLoaded', () => {
  if (!state) {
    showSetupModal();
  } else {
    renderApp();
  }

  setInterval(tickGameLoop, 1000);
  setInterval(() => {
    if (state) {
      saveState();
    }
  }, 15000);
});

function safeNumber(value, fallback = 0) {
  const n = Number(value);
  return Number.isFinite(n) ? n : fallback;
}

function clamp(value, min, max) {
  return Math.min(Math.max(value, min), max);
}

function formatMoney(value) {
  const money = safeNumber(value, 0);
  return new Intl.NumberFormat('id-ID', {
    style: 'currency',
    currency: 'IDR',
    maximumFractionDigits: 0
  }).format(money);
}

function formatNumber(value) {
  return new Intl.NumberFormat('id-ID').format(safeNumber(value, 0));
}

function capitalize(text) {
  return String(text || '').replace(/\b\w/g, (ch) => ch.toUpperCase());
}

function getCompanyLevel() {
  if (!state) return 1;
  const totalAssets = safeNumber(state.company.balance, 0) + state.trucks.reduce((sum, truck) => sum + safeNumber(truck.value, 0), 0);
  const rep = safeNumber(state.company.reputation, 0);
  if (totalAssets >= 3000000000 || rep >= 85) return 5;
  if (totalAssets >= 1500000000 || rep >= 70) return 4;
  if (totalAssets >= 700000000 || rep >= 45) return 3;
  if (totalAssets >= 250000000 || rep >= 20) return 2;
  return 1;
}

function updateCompanyProfile() {
  if (!state) return;
  state.company.level = getCompanyLevel();
  state.company.condition = clamp(
    Math.round(state.trucks.reduce((sum, truck) => sum + safeNumber(truck.condition, 70), 0) / Math.max(state.trucks.length, 1)),
    0,
    100
  );
}

function loadState() {
  const raw = localStorage.getItem(STORAGE_KEY);
  if (!raw) return null;

  try {
    const parsed = JSON.parse(raw);
    if (!parsed || !parsed.company) return null;
    return parsed;
  } catch (error) {
    return null;
  }
}

function saveState() {
  if (!state) return;
  updateCompanyProfile();
  localStorage.setItem(STORAGE_KEY, JSON.stringify(state));
}

function makeId(prefix) {
  return `${prefix}-${Date.now()}-${Math.random().toString(16).slice(2, 8)}`;
}

function getDriverById(driverId) {
  return state.drivers.find((driver) => driver.id === driverId) || null;
}

function getTruckById(truckId) {
  return state.trucks.find((truck) => truck.id === truckId) || null;
}

function generateDriver(name, options = {}) {
  const skill = safeNumber(options.skill, 65 + Math.random() * 30);
  const discipline = safeNumber(options.discipline, 60 + Math.random() * 35);
  const fuelEfficiency = safeNumber(options.fuelEfficiency, 60 + Math.random() * 35);
  const accidentRisk = safeNumber(options.accidentRisk, 12 + Math.random() * 18);
  const salary = safeNumber(options.salary, 3000000 + Math.random() * 2000000);

  return {
    id: makeId('driver'),
    name: name || `Driver ${Math.floor(100 + Math.random() * 900)}`,
    age: safeNumber(options.age, 24 + Math.floor(Math.random() * 16)),
    experience: safeNumber(options.experience, 1 + Math.floor(Math.random() * 8)),
    skill,
    discipline,
    fuelEfficiency,
    accidentRisk,
    salary,
    loyalty: safeNumber(options.loyalty, 70 + Math.random() * 25),
    fitness: safeNumber(options.fitness, 70 + Math.random() * 25),
    busy: false,
    truckId: null
  };
}

function makeTruckModel(modelId, extras = {}) {
  const template = TRUCK_MODELS.find((model) => model.id === modelId) || TRUCK_MODELS[0];
  const year = safeNumber(extras.year, template.year);
  const mileage = safeNumber(extras.mileage, 120000 + Math.random() * 180000);
  const bodyType = extras.bodyType || template.bodyType || 'Bak Standar';
  const conditionBase = safeNumber(extras.condition, 80 + Math.random() * 15);
  const fuel = safeNumber(extras.fuel, 120 + Math.random() * 80);

  return {
    id: makeId('truck'),
    modelId: template.id,
    name: extras.name || template.name,
    year,
    mileage,
    tonnage: safeNumber(extras.tonnage, template.tonnage),
    fuelConsumption: safeNumber(extras.fuelConsumption, template.fuelUse),
    speed: safeNumber(extras.speed, template.speed),
    enginePower: safeNumber(extras.enginePower, template.power),
    engineCondition: safeNumber(extras.engineCondition, conditionBase),
    tireCondition: safeNumber(extras.tireCondition, conditionBase - 4),
    brakeCondition: safeNumber(extras.brakeCondition, conditionBase - 5),
    bodyCondition: safeNumber(extras.bodyCondition, conditionBase),
    value: safeNumber(extras.value, template.price),
    maintenanceCost: safeNumber(extras.maintenanceCost, template.maintenance),
    buyingPrice: safeNumber(extras.buyingPrice, template.price),
    bodyType,
    fuel,
    status: 'idle',
    condition: safeNumber(extras.condition, conditionBase),
    driverId: null,
    trip: null,
    history: []
  };
}

function getBodyTemplate(bodyId) {
  return BODY_TYPES.find((body) => body.id === bodyId) || BODY_TYPES[0];
}

function generateUsedMarket() {
  const conditions = [
    { label: 'Sangat bagus', mod: 0.94, mileage: 90000 },
    { label: 'Bagus', mod: 0.84, mileage: 170000 },
    { label: 'Normal', mod: 0.73, mileage: 260000 },
    { label: 'Rusak ringan', mod: 0.58, mileage: 330000 },
    { label: 'Rusak berat', mod: 0.42, mileage: 420000 }
  ];

  return Array.from({ length: 5 }, (_, index) => {
    const template = TRUCK_MODELS[index % TRUCK_MODELS.length];
    const quality = conditions[index % conditions.length];
    const condition = clamp(70 + Math.random() * 26, 40, 95);
    const price = Math.round(template.price * quality.mod * (0.92 - (index * 0.02)));
    const truck = makeTruckModel(template.id, {
      year: 2014 + index + Math.floor(Math.random() * 5),
      mileage: quality.mileage + Math.random() * 120000,
      condition,
      engineCondition: condition - 4,
      tireCondition: condition - 8,
      brakeCondition: condition - 10,
      bodyCondition: condition - 3,
      value: price,
      buyingPrice: price,
      name: `${template.name} Bekas ${quality.label}`
    });
    truck.quality = quality.label;
    truck.isUsedMarket = true;
    return truck;
  });
}

function generateCargoMarket() {
  return CARGO_TYPES.map((cargo, index) => ({
    id: makeId('cargo'),
    kind: 'cargo',
    name: cargo.name,
    weight: cargo.weight,
    price: cargo.revenue,
    distance: cargo.distance,
    duration: cargo.duration,
    risk: cargo.risk,
    origin: randomCityFromIndex(index),
    destination: randomCityFromIndex(index + 2),
    body: cargo.body,
    tonnage: cargo.tonnage,
    assigned: false,
    completed: false,
    description: `${cargo.name} - ${cargo.weight} ton × ${cargo.distance} km`
  }));
}

function randomCityFromIndex(index) {
  return CITY_OPTIONS[(index + 1) % CITY_OPTIONS.length];
}

function generateContracts() {
  return MARKET_CONTRACTS.map((contract) => ({
    ...contract,
    id: contract.id,
    accepted: false,
    completed: false,
    kind: 'contract'
  }));
}

function createDefaultGame(config) {
  const companyName = config.companyName || 'Nusantara Cargo';
  const ownerName = config.ownerName || 'Pemilik';
  const logo = config.logo || '🚚';
  const balance = safeNumber(config.balance, 350000000);
  const city = config.city || 'Pekanbaru';
  const garageSlots = safeNumber(config.garageSlots, 2);
  const profile = config.profile || 'Perusahaan angkutan truk yang sedang membangun armada dan reputasi di pasar logistik regional Indonesia.';

  const truck = makeTruckModel('colt-diesel', {
    name: 'Colt Diesel 2019',
    year: 2019,
    mileage: 210000,
    condition: 76,
    engineCondition: 78,
    tireCondition: 74,
    brakeCondition: 72,
    bodyCondition: 80,
    fuel: 160,
    bodyType: 'Bak Standar',
    value: 280000000,
    buyingPrice: 280000000,
    maintenanceCost: 3200000
  });

  const driver = generateDriver('Rian Hidayat', {
    age: 31,
    experience: 5,
    skill: 78,
    discipline: 81,
    fuelEfficiency: 79,
    accidentRisk: 13,
    salary: 4200000,
    loyalty: 84,
    fitness: 82,
    truckId: truck.id
  });

  truck.driverId = driver.id;
  driver.truckId = truck.id;

  const defaultGame = {
    company: {
      name: companyName,
      ownerName,
      logo,
      balance,
      city,
      garageSlots,
      profile,
      reputation: 12,
      condition: 76,
      level: 1,
      status: 'Perusahaan kecil',
      fuelStationLevel: 0,
      workshopLevel: 0,
      officeLevel: 0,
      warehouseLevel: 0,
      garageLevel: 1,
      maxDriver: 3,
      maxTruck: 2,
      lastSaved: Date.now()
    },
    trucks: [truck],
    drivers: [driver],
    market: {
      used: generateUsedMarket(),
      cargo: generateCargoMarket(),
      contracts: generateContracts()
    },
    finance: {
      incomeToday: 0,
      expenseToday: 0,
      incomeWeek: 0,
      expenseWeek: 0,
      incomeMonth: 0,
      expenseMonth: 0,
      history: []
    },
    logs: [
      `${companyName} resmi berdiri dan mulai melayani rute logistik regional Indonesia.`,
      `Saldo awal ${formatMoney(balance)} siap dipakai untuk membangun armada.`
    ],
    day: 1,
    fuelPrice: 6800,
    activeView: 'dashboard'
  };

  updateCompanyProfile();
  return defaultGame;
}

function showSetupModal() {
  const modal = document.getElementById('setupModal');
  modal.classList.remove('hidden');
  modal.innerHTML = `
    <div class="modal-card">
      <div class="modal-head">
        <h2>Setup Perusahaan</h2>
        <button class="ghost-btn" type="button" data-action="close-setup">Tutup</button>
      </div>
      <div class="modal-body">
        <form id="setupForm">
          <div class="form-grid">
            <div>
              <label>Nama Perusahaan</label>
              <input name="companyName" value="Nusa Logistik Indonesia" required />
            </div>
            <div>
              <label>Nama Pemilik</label>
              <input name="ownerName" value="Budi Santoso" required />
            </div>
            <div>
              <label>Saldo Awal</label>
              <input name="balance" type="number" value="350000000" min="250000000" step="5000000" required />
            </div>
            <div>
              <label>Kota Awal</label>
              <select name="city">
                ${CITY_OPTIONS.map((city) => `<option value="${city}" ${city === 'Pekanbaru' ? 'selected' : ''}>${city}</option>`).join('')}
              </select>
            </div>
            <div>
              <label>Garasi Awal</label>
              <select name="garageSlots">
                <option value="2" selected>2 slot</option>
                <option value="3">3 slot</option>
                <option value="4">4 slot</option>
              </select>
            </div>
            <div>
              <label>Profil Perusahaan</label>
              <textarea name="profile">Perusahaan angkutan truk lokal yang mulai melayani pengiriman antar kota dan kontrak logistik regional.</textarea>
            </div>
          </div>

          <div style="margin-top: 18px;">
            <label>Logo Perusahaan</label>
            <div class="logo-grid">
              ${LOGO_OPTIONS.map((logo, idx) => `
                <button type="button" class="logo-option ${idx === 0 ? 'selected' : ''}" data-logo="${logo.icon}" data-action="select-logo">
                  <span class="logo-badge">${logo.icon}</span>
                  <span>${logo.label}</span>
                </button>
              `).join('')}
            </div>
            <input type="hidden" name="logo" value="🚚" />
          </div>

          <div class="controls" style="margin-top: 18px; justify-content: flex-end;">
            <button type="button" class="ghost-btn" data-action="close-setup">Batal</button>
            <button type="submit" class="primary-btn">Mulai Game</button>
          </div>
        </form>
      </div>
    </div>
  `;

  document.getElementById('setupForm').addEventListener('submit', (event) => {
    event.preventDefault();
    const formData = new FormData(event.target);
    const payload = {
      companyName: formData.get('companyName'),
      ownerName: formData.get('ownerName'),
      logo: formData.get('logo') || '🚚',
      balance: safeNumber(formData.get('balance'), 350000000),
      city: formData.get('city'),
      garageSlots: safeNumber(formData.get('garageSlots'), 2),
      profile: formData.get('profile')
    };

    state = createDefaultGame(payload);
    saveState();
    renderApp();
    modal.classList.add('hidden');
  });

  const logoButtons = modal.querySelectorAll('[data-action="select-logo"]');
  logoButtons.forEach((button) => {
    button.addEventListener('click', () => {
      const selected = button.dataset.logo;
      modal.querySelector('input[name="logo"]').value = selected;
      logoButtons.forEach((btn) => btn.classList.remove('selected'));
      button.classList.add('selected');
    });
  });

  modal.querySelector('[data-action="close-setup"]').addEventListener('click', () => {
    modal.classList.add('hidden');
    if (!state) {
      state = createDefaultGame({
        companyName: 'Nusa Logistik Indonesia',
        ownerName: 'Budi Santoso',
        logo: '🚚',
        balance: 350000000,
        city: 'Pekanbaru',
        profile: 'Perusahaan angkutan truk lokal yang mulai melayani pengiriman antar kota dan kontrak logistik regional.'
      });
      saveState();
      renderApp();
    }
  });
}

function renderApp() {
  const appRoot = document.getElementById('appRoot');
  appRoot.innerHTML = `
    <div class="app-shell">
      <header class="topbar">
        <div class="brand-block">
          <div class="brand-badge">${state.company.logo}</div>
          <div class="brand-copy">
            <h1>${state.company.name}</h1>
            <small>${state.company.ownerName} • Kota ${state.company.city}</small>
          </div>
        </div>
        <div class="header-stats">
          <div class="header-pill"><strong>Saldo:</strong> ${formatMoney(state.company.balance)}</div>
          <div class="header-pill"><strong>Reputasi:</strong> ${state.company.reputation}</div>
          <div class="header-pill"><strong>Level:</strong> ${state.company.level}</div>
          <div class="header-pill"><strong>Hari:</strong> ${state.day}</div>
        </div>
      </header>

      <nav class="nav-grid">
        ${[
          ['dashboard', 'Dashboard'],
          ['garage', 'Garasi'],
          ['dealer', 'Dealer Truk'],
          ['used', 'Truk Bekas'],
          ['sell', 'Jual Truk'],
          ['drivers', 'Driver'],
          ['cargo', 'Muatan'],
          ['contracts', 'Kontrak'],
          ['travel', 'Perjalanan'],
          ['workshop', 'Bengkel'],
          ['fuel', 'BBM/Solar'],
          ['finance', 'Keuangan'],
          ['upgrade', 'Upgrade Perusahaan'],
          ['stats', 'Statistik'],
          ['settings', 'Pengaturan']
        ].map(([id, label]) => `
          <button class="nav-btn ${currentView === id ? 'active' : ''}" data-action="switch-view" data-view="${id}">${label}</button>
        `).join('')}
      </nav>

      <main class="content-area">
        ${renderCurrentView()}
      </main>
    </div>
  `;

  bindUIActions();
}

function renderCurrentView() {
  if (!state) return '';

  switch (currentView) {
    case 'garage':
      return renderGarageView();
    case 'dealer':
      return renderDealerView();
    case 'used':
      return renderUsedTruckView();
    case 'sell':
      return renderSellView();
    case 'drivers':
      return renderDriverView();
    case 'cargo':
      return renderCargoView();
    case 'contracts':
      return renderContractsView();
    case 'travel':
      return renderTravelView();
    case 'workshop':
      return renderWorkshopView();
    case 'fuel':
      return renderFuelView();
    case 'finance':
      return renderFinanceView();
    case 'upgrade':
      return renderUpgradeView();
    case 'stats':
      return renderStatsView();
    case 'settings':
      return renderSettingsView();
    case 'dashboard':
    default:
      return renderDashboardView();
  }
}

function renderDashboardView() {
  const trucksActive = state.trucks.filter((truck) => truck.status === 'traveling').length;
  const totalDrivers = state.drivers.length;
  const income = safeNumber(state.finance.incomeToday, 0);
  const expense = safeNumber(state.finance.expenseToday, 0);
  const profit = income - expense;

  return `
    <section class="panel">
      <div class="panel-header">
        <h2>Dashboard Perusahaan</h2>
        <span class="inline-tag">${state.company.status}</span>
      </div>
      <div class="panel-body">
        <div class="metric-grid">
          <div class="metric-card">
            <span class="metric-label">Saldo</span>
            <div class="metric-value primary">${formatMoney(state.company.balance)}</div>
          </div>
          <div class="metric-card">
            <span class="metric-label">Jumlah Truk</span>
            <div class="metric-value">${state.trucks.length}</div>
          </div>
          <div class="metric-card">
            <span class="metric-label">Jumlah Driver</span>
            <div class="metric-value">${totalDrivers}</div>
          </div>
          <div class="metric-card">
            <span class="metric-label">Truk Sedang Mengangkut</span>
            <div class="metric-value success">${trucksActive}</div>
          </div>
          <div class="metric-card">
            <span class="metric-label">Pendapatan Hari Ini</span>
            <div class="metric-value success">${formatMoney(income)}</div>
          </div>
          <div class="metric-card">
            <span class="metric-label">Pengeluaran Hari Ini</span>
            <div class="metric-value danger">${formatMoney(expense)}</div>
          </div>
          <div class="metric-card">
            <span class="metric-label">Profit</span>
            <div class="metric-value ${profit >= 0 ? 'success' : 'danger'}">${formatMoney(profit)}</div>
          </div>
          <div class="metric-card">
            <span class="metric-label">Kondisi Perusahaan</span>
            <div class="metric-value warning">${state.company.condition}%</div>
          </div>
        </div>

        <div class="dash-layout">
          <div class="card-grid">
            <div class="info-card">
              <div class="info-head">
                <h3>Ringkasan Operasional</h3>
                <span class="badge blue">Reputasi ${state.company.reputation}</span>
              </div>
              <ul class="info-list">
                <li><span>Reputasi perusahaan</span><strong>${state.company.reputation}/100</strong></li>
                <li><span>Level perusahaan</span><strong>Level ${state.company.level}</strong></li>
                <li><span>Kota operasional</span><strong>${state.company.city}</strong></li>
                <li><span>Harga solar</span><strong>${formatMoney(state.fuelPrice)}/liter</strong></li>
              </ul>
            </div>

            <div class="info-card">
              <div class="info-head">
                <h3>Keadaan Armada</h3>
                <span class="badge purple">${state.trucks.length} unit</span>
              </div>
              <div class="card-stack">
                ${state.trucks.map((truck) => `
                  <div class="truck-card">
                    <div class="truck-head">
                      <strong>${truck.name}</strong>
                      <span class="badge ${truck.status === 'traveling' ? 'green' : 'blue'}">${truck.status === 'traveling' ? 'Mengangkut' : 'Siap'}</span>
                    </div>
                    <div class="muted">${truck.modelId} • ${truck.bodyType}</div>
                    <div class="controls">
                      <button class="small-btn ghost-btn" data-action="quick-refuel" data-truck-id="${truck.id}">Isi Solar</button>
                      <button class="small-btn ghost-btn" data-action="quick-service" data-truck-id="${truck.id}">Servis</button>
                    </div>
                  </div>
                `).join('') || '<div class="muted">Belum ada truk di fleet.</div>'}
              </div>
            </div>
          </div>

          <div class="card-grid">
            <div class="info-card sticky-list">
              <div class="info-head">
                <h3>Notifikasi</h3>
                <span class="badge green">Live</span>
              </div>
              <ul class="log-list">
                ${state.logs.slice(0, 6).map((log) => `<li class="log-item">${log}</li>`).join('')}
              </ul>
            </div>

            <div class="info-card">
              <div class="info-head">
                <h3>Pencapaian</h3>
                <span class="badge yellow">Level ${state.company.level}</span>
              </div>
              <div class="muted" style="margin-bottom: 10px;">Perusahaan Anda berkembang menuju jaringan logistik nasional.</div>
              <div class="progress-bar"><span class="progress-fill" style="width:${Math.min(100, (state.company.reputation + state.company.level * 12))}%"></span></div>
              <div class="controls">
                <button class="small-btn primary-btn" data-action="switch-view" data-view="upgrade">Upgrade</button>
                <button class="small-btn ghost-btn" data-action="switch-view" data-view="contracts">Kontrak</button>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  `;
}

function renderGarageView() {
  if (!state.trucks.length) {
    return panelTemplate('Garasi', 'Belum ada truk. Beli unit truk baru atau bekas dari dealer dan pasar bekas.', 'ghost-btn', 'switch-view', 'dealer', 'Buka Dealer');
  }

  return `
    <section class="panel">
      <div class="panel-header">
        <h2>Garasi</h2>
        <span class="badge blue">${state.trucks.length}/${state.company.garageSlots} slot</span>
      </div>
      <div class="panel-body">
        <div class="card-stack">
          ${state.trucks.map((truck) => `
            <div class="truck-card">
              <div class="truck-head">
                <strong>${truck.name}</strong>
                <span class="badge ${truck.status === 'traveling' ? 'green' : 'blue'}">${truck.status === 'traveling' ? 'Melaju' : 'Siap'}</span>
              </div>
              <div class="grid-2">
                <div><span class="muted">Tahun</span><div>${truck.year}</div></div>
                <div><span class="muted">Body</span><div>${truck.bodyType}</div></div>
                <div><span class="muted">Kapasitas</span><div>${truck.tonnage} ton</div></div>
                <div><span class="muted">KM</span><div>${formatNumber(truck.mileage)} km</div></div>
                <div><span class="muted">Kondisi</span><div>${Math.round(truck.condition)}%</div></div>
                <div><span class="muted">Solar</span><div>${Math.round(truck.fuel)} L</div></div>
              </div>
              <div class="progress-bar" style="margin-top: 12px; margin-bottom: 12px;"><span class="progress-fill" style="width:${Math.round(truck.condition)}%"></span></div>
              <div class="controls">
                <button class="small-btn primary-btn" data-action="assign-driver" data-truck-id="${truck.id}">Assign Driver</button>
                <button class="small-btn secondary-btn" data-action="refuel-quick" data-truck-id="${truck.id}">Isi Solar</button>
                <button class="small-btn ghost-btn" data-action="repair-truck" data-truck-id="${truck.id}" data-repair="light">Servis Ringan</button>
                <button class="small-btn danger-btn" data-action="sell-truck" data-truck-id="${truck.id}">Jual</button>
              </div>
            </div>
          `).join('')}
        </div>
      </div>
    </section>
  `;
}

function renderDealerView() {
  return `
    <section class="panel">
      <div class="panel-header">
        <h2>Dealer Truk</h2>
        <span class="badge blue">Pembelian Armada</span>
      </div>
      <div class="panel-body">
        <div class="grid-3">
          ${TRUCK_MODELS.map((model) => `
            <div class="market-card">
              <div class="item-head">
                <strong>${model.name}</strong>
                <span class="badge blue">${model.tonnage} ton</span>
              </div>
              <div class="muted">Tahun ${model.year} • ${model.power} HP</div>
              <ul class="info-list" style="margin-top: 10px;">
                <li><span>Harga</span><strong>${formatMoney(model.price)}</strong></li>
                <li><span>Solar</span><strong>${model.fuelUse} L/100km</strong></li>
                <li><span>Kecepatan</span><strong>${model.speed} km/jam</strong></li>
                <li><span>Perawatan</span><strong>${formatMoney(model.maintenance)}</strong></li>
              </ul>
              <div class="controls">
                <button class="primary-btn" data-action="buy-truck" data-model-id="${model.id}">Beli Truk</button>
              </div>
            </div>
          `).join('')}
        </div>
      </div>
    </section>
  `;
}

function renderUsedTruckView() {
  return `
    <section class="panel">
      <div class="panel-header">
        <h2>Truk Bekas</h2>
        <span class="badge yellow">Pasar kondisi</span>
      </div>
      <div class="panel-body">
        <div class="grid-3">
          ${state.market.used.map((truck, idx) => `
            <div class="market-card">
              <div class="item-head">
                <strong>${truck.name}</strong>
                <span class="badge ${truck.quality === 'Sangat bagus' ? 'green' : truck.quality === 'Bagus' ? 'blue' : truck.quality === 'Normal' ? 'yellow' : 'red'}">${truck.quality}</span>
              </div>
              <ul class="info-list">
                <li><span>Tahun</span><strong>${truck.year}</strong></li>
                <li><span>KM</span><strong>${formatNumber(truck.mileage)}</strong></li>
                <li><span>Kondisi</span><strong>${Math.round(truck.condition)}%</strong></li>
                <li><span>Harga</span><strong>${formatMoney(truck.value)}</strong></li>
              </ul>
              <div class="controls">
                <button class="ghost-btn" data-action="inspect-used" data-index="${idx}">Inspeksi</button>
                <button class="primary-btn" data-action="buy-used-truck" data-index="${idx}">Beli</button>
              </div>
            </div>
          `).join('')}
        </div>
      </div>
    </section>
  `;
}

function renderSellView() {
  return `
    <section class="panel">
      <div class="panel-header">
        <h2>Jual Truk</h2>
        <span class="badge blue">Estimasi harga pasar</span>
      </div>
      <div class="panel-body">
        <div class="card-stack">
          ${state.trucks.map((truck) => {
            const estimate = estimateSalePrice(truck);
            return `
              <div class="truck-card">
                <div class="truck-head">
                  <strong>${truck.name}</strong>
                  <span class="badge blue">${formatMoney(estimate)}</span>
                </div>
                <div class="grid-2">
                  <div><span class="muted">Tahun</span><div>${truck.year}</div></div>
                  <div><span class="muted">KM</span><div>${formatNumber(truck.mileage)}</div></div>
                  <div><span class="muted">Kondisi Mesin</span><div>${Math.round(truck.engineCondition)}%</div></div>
                  <div><span class="muted">Permintaan</span><div>${getDemandLabel(truck)}</div></div>
                </div>
                <div class="controls">
                  <button class="primary-btn" data-action="confirm-sell" data-truck-id="${truck.id}">Jual Sekarang</button>
                </div>
              </div>
            `;
          }).join('') || '<div class="muted">Belum ada truk untuk dijual.</div>'}
        </div>
      </div>
    </section>
  `;
}

function renderDriverView() {
  const randomDriver = generateDriver('Driver Baru', {
    age: 26 + Math.floor(Math.random() * 12),
    experience: 1 + Math.floor(Math.random() * 8)
  });

  return `
    <section class="panel">
      <div class="panel-header">
        <h2>Driver</h2>
        <span class="badge green">${state.drivers.length} aktif</span>
      </div>
      <div class="panel-body">
        <div class="controls" style="margin-bottom: 14px;">
          <button class="primary-btn" data-action="hire-driver" data-driver-name="${randomDriver.name}">Rekrut Driver Baru</button>
        </div>
        <div class="card-stack">
          ${state.drivers.map((driver) => `
            <div class="driver-card">
              <div class="driver-head">
                <strong>${driver.name}</strong>
                <span class="badge ${driver.busy ? 'yellow' : 'green'}">${driver.busy ? 'Sedang Bertugas' : 'Siap'}</span>
              </div>
              <div class="grid-2">
                <div><span class="muted">Umur</span><div>${driver.age}</div></div>
                <div><span class="muted">Pengalaman</span><div>${driver.experience} tahun</div></div>
                <div><span class="muted">Skill</span><div>${Math.round(driver.skill)}</div></div>
                <div><span class="muted">Disiplin</span><div>${Math.round(driver.discipline)}</div></div>
                <div><span class="muted">Efisiensi BBM</span><div>${Math.round(driver.fuelEfficiency)}</div></div>
                <div><span class="muted">Risiko Kecelakaan</span><div>${Math.round(driver.accidentRisk)}</div></div>
                <div><span class="muted">Gaji</span><div>${formatMoney(driver.salary)}</div></div>
                <div><span class="muted">Loyalitas</span><div>${Math.round(driver.loyalty)}</div></div>
              </div>
              <div class="controls">
                <button class="small-btn secondary-btn" data-action="train-driver" data-driver-id="${driver.id}">Latih Driver</button>
                <button class="small-btn ghost-btn" data-action="bonus-driver" data-driver-id="${driver.id}">Bonus</button>
                <button class="small-btn ghost-btn" data-action="raise-salary" data-driver-id="${driver.id}">Naik Gaji</button>
                <button class="small-btn danger-btn" data-action="fire-driver" data-driver-id="${driver.id}">PHK</button>
              </div>
            </div>
          `).join('')}
        </div>
      </div>
    </section>
  `;
}

function renderCargoView() {
  const activeCargo = state.market.cargo.filter((cargo) => !cargo.assigned && !cargo.completed);

  return `
    <section class="panel">
      <div class="panel-header">
        <h2>Pasar Muatan</h2>
        <span class="badge blue">${activeCargo.length} penawaran</span>
      </div>
      <div class="panel-body">
        <div class="grid-3">
          ${activeCargo.map((cargo) => `
            <div class="market-card">
              <div class="item-head">
                <strong>${cargo.name}</strong>
                <span class="badge ${cargo.risk > 15 ? 'yellow' : 'green'}">Risiko ${cargo.risk}</span>
              </div>
              <ul class="info-list">
                <li><span>Rute</span><strong>${cargo.origin} → ${cargo.destination}</strong></li>
                <li><span>Berat</span><strong>${cargo.weight} ton</strong></li>
                <li><span>Bayaran</span><strong>${formatMoney(cargo.price)}</strong></li>
                <li><span>Waktu</span><strong>${cargo.duration} jam</strong></li>
                <li><span>Bak</span><strong>${capitalize(cargo.body?.replace(/-/g, ' ') || 'Bak Standar')}</strong></li>
              </ul>
            </div>
          `).join('') || '<div class="muted">Tidak ada penawaran muatan yang tersedia saat ini.</div>'}
        </div>
      </div>
    </section>
  `;
}

function renderContractsView() {
  const activeContracts = state.market.contracts.filter((contract) => !contract.accepted && !contract.completed);

  return `
    <section class="panel">
      <div class="panel-header">
        <h2>Kontrak Perusahaan</h2>
        <span class="badge purple">${activeContracts.length} tersedia</span>
      </div>
      <div class="panel-body">
        <div class="card-stack">
          ${activeContracts.map((contract) => `
            <div class="market-card">
              <div class="item-head">
                <strong>${contract.title}</strong>
                <span class="badge blue">${contract.tonnage} ton</span>
              </div>
              <ul class="info-list">
                <li><span>Rute</span><strong>${contract.origin} → ${contract.destination}</strong></li>
                <li><span>Pembayaran</span><strong>${formatMoney(contract.payment)}</strong></li>
                <li><span>Deadlines</span><strong>${contract.deadline} hari</strong></li>
                <li><span>Reputasi min.</span><strong>${contract.minReputation}</strong></li>
                <li><span>Persyaratan bak</span><strong>${capitalize(contract.body?.replace(/-/g, ' ') || 'bak standar')}</strong></li>
              </ul>
              <div class="controls">
                <button class="primary-btn" data-action="accept-contract" data-contract-id="${contract.id}">Ambil Kontrak</button>
              </div>
            </div>
          `).join('') || '<div class="muted">Belum ada kontrak baru yang menunggu.</div>'}
        </div>
      </div>
    </section>
  `;
}

function renderTravelView() {
  const truckOptions = state.trucks.filter((truck) => truck.status !== 'traveling').map((truck) => `
    <option value="${truck.id}">${truck.name} • ${truck.tonnage} ton • ${Math.round(truck.condition)}%</option>
  `).join('');

  const cargoOptions = [...state.market.cargo.filter((cargo) => !cargo.assigned && !cargo.completed), ...state.market.contracts.filter((contract) => contract.accepted && !contract.completed)].map((job) => `
    <option value="${job.id}" data-kind="${job.kind}">${job.kind === 'contract' ? `${job.title}` : `${job.name} (${job.origin}→${job.destination})`}</option>
  `).join('');

  const activeTrips = state.trucks.filter((truck) => truck.status === 'traveling' && truck.trip).map((truck) => `
    <div class="truck-card">
      <div class="truck-head">
        <strong>${truck.name}</strong>
        <span class="badge green">${truck.trip.type}</span>
      </div>
      <div class="muted">${truck.trip.origin} → ${truck.trip.destination}</div>
      <div style="margin-top: 10px;">
        <div class="progress-bar"><span class="progress-fill" style="width:${Math.min(100, ((truck.trip.duration - truck.trip.remainingHours) / truck.trip.duration) * 100)}%"></span></div>
      </div>
      <div class="controls">
        <span class="inline-tag">${truck.trip.remainingHours.toFixed(1)} jam tersisa</span>
      </div>
    </div>
  `).join('');

  return `
    <section class="panel">
      <div class="panel-header">
        <h2>Perjalanan</h2>
        <span class="badge blue">Logistik</span>
      </div>
      <div class="panel-body">
        <div class="form-grid" style="margin-bottom: 18px;">
          <div>
            <label>Pilih Truk</label>
            <select id="travelTruckSelect">
              <option value="">-- pilih truk --</option>
              ${truckOptions || '<option value="">Tidak ada truk siap</option>'}
            </select>
          </div>
          <div>
            <label>Pilih Muatan / Kontrak</label>
            <select id="travelJobSelect">
              <option value="">-- pilih muatan --</option>
              ${cargoOptions || '<option value="">Tidak ada job yang siap</option>'}
            </select>
          </div>
        </div>
        <div class="controls">
          <button class="primary-btn" data-action="start-trip">Mulai Perjalanan</button>
        </div>

        <div style="margin-top: 24px;">
          <h3>Aktif saat ini</h3>
          <div class="card-stack">
            ${activeTrips || '<div class="muted">Belum ada perjalanan aktif.</div>'}
          </div>
        </div>
      </div>
    </section>
  `;
}

function renderWorkshopView() {
  return `
    <section class="panel">
      <div class="panel-header">
        <h2>Bengkel</h2>
        <span class="badge blue">Perbaikan & pemeliharaan</span>
      </div>
      <div class="panel-body">
        <div class="grid-3">
          <div class="market-card">
            <h3>Servis Ringan</h3>
            <p class="muted">Cek mesin, oli, dan ban. Biaya mulai dari ${formatMoney(2500000)}.</p>
            <div class="controls">
              <button class="primary-btn" data-action="service-all" data-level="light">Lakukan Servis Ringan</button>
            </div>
          </div>
          <div class="market-card">
            <h3>Servis Besar</h3>
            <p class="muted">Peningkatan mesin, rem, dan sistem suspensi. Biaya mulai dari ${formatMoney(8000000)}.</p>
            <div class="controls">
              <button class="secondary-btn" data-action="service-all" data-level="heavy">Servis Besar</button>
            </div>
          </div>
          <div class="market-card">
            <h3>Overhaul Mesin</h3>
            <p class="muted">Pulihkan performa mesin penting untuk perjalanan jauh. Biaya ${formatMoney(22000000)}.</p>
            <div class="controls">
              <button class="ghost-btn" data-action="service-all" data-level="engine">Overhaul</button>
            </div>
          </div>
        </div>

        <div style="margin-top: 20px;">
          <h3>Daftar truk untuk perbaikan</h3>
          <div class="card-stack">
            ${state.trucks.map((truck) => `
              <div class="truck-card">
                <div class="truck-head">
                  <strong>${truck.name}</strong>
                  <span class="badge yellow">Kondisi ${Math.round(truck.condition)}%</span>
                </div>
                <div class="controls">
                  <button class="small-btn primary-btn" data-action="repair-truck" data-truck-id="${truck.id}" data-repair="light">Servis Ringan</button>
                  <button class="small-btn secondary-btn" data-action="repair-truck" data-truck-id="${truck.id}" data-repair="heavy">Servis Besar</button>
                  <button class="small-btn ghost-btn" data-action="repair-truck" data-truck-id="${truck.id}" data-repair="engine">Overhaul</button>
                </div>
              </div>
            `).join('')}
          </div>
        </div>
      </div>
    </section>
  `;
}

function renderFuelView() {
  return `
    <section class="panel">
      <div class="panel-header">
        <h2>BBM / Solar</h2>
        <span class="badge blue">Harga saat ini: ${formatMoney(state.fuelPrice)}/liter</span>
      </div>
      <div class="panel-body">
        <div class="card-stack">
          ${state.trucks.map((truck) => `
            <div class="truck-card">
              <div class="truck-head">
                <strong>${truck.name}</strong>
                <span class="badge ${truck.fuel > 40 ? 'green' : 'yellow'}">${Math.round(truck.fuel)} L</span>
              </div>
              <div class="controls">
                <button class="small-btn primary-btn" data-action="refuel-action" data-truck-id="${truck.id}" data-liters="40">Isi 40L</button>
                <button class="small-btn secondary-btn" data-action="refuel-action" data-truck-id="${truck.id}" data-liters="80">Isi 80L</button>
                <button class="small-btn ghost-btn" data-action="refuel-action" data-truck-id="${truck.id}" data-liters="120">Isi 120L</button>
              </div>
            </div>
          `).join('')}
        </div>
      </div>
    </section>
  `;
}

function renderFinanceView() {
  const history = state.finance.history.slice(0, 10);

  return `
    <section class="panel">
      <div class="panel-header">
        <h2>Keuangan</h2>
        <span class="badge blue">Laporan</span>
      </div>
      <div class="panel-body">
        <div class="metric-grid">
          <div class="metric-card">
            <span class="metric-label">Harian</span>
            <div class="metric-value success">${formatMoney(state.finance.incomeToday)}</div>
          </div>
          <div class="metric-card">
            <span class="metric-label">Pengeluaran Harian</span>
            <div class="metric-value danger">${formatMoney(state.finance.expenseToday)}</div>
          </div>
          <div class="metric-card">
            <span class="metric-label">Mingguan</span>
            <div class="metric-value primary">${formatMoney(state.finance.incomeWeek)}</div>
          </div>
          <div class="metric-card">
            <span class="metric-label">Bulanan</span>
            <div class="metric-value warning">${formatMoney(state.finance.incomeMonth)}</div>
          </div>
        </div>

        <div class="table-wrap">
          <table class="data-table">
            <thead>
              <tr>
                <th>Tanggal</th>
                <th>Jenis</th>
                <th>Jumlah</th>
                <th>Keterangan</th>
              </tr>
            </thead>
            <tbody>
              ${history.length ? history.map((entry) => `
                <tr>
                  <td>Hari ${entry.day}</td>
                  <td>${entry.type}</td>
                  <td>${entry.amount >= 0 ? formatMoney(entry.amount) : formatMoney(entry.amount)}</td>
                  <td>${entry.note}</td>
                </tr>
              `).join('') : '<tr><td colspan="4">Belum ada riwayat keuangan.</td></tr>'}
            </tbody>
          </table>
        </div>
      </div>
    </section>
  `;
}

function renderUpgradeView() {
  const upgrades = [
    { id: 'garage', name: 'Garasi', cost: 200000000, level: state.company.garageLevel, desc: 'Menambah kapasitas garasi dan unit armada.' },
    { id: 'workshop', name: 'Bengkel Sendiri', cost: 350000000, level: state.company.workshopLevel, desc: 'Menangani perawatan rutin dan perbaikan cepat.' },
    { id: 'fuel', name: 'SPBU Sendiri', cost: 420000000, level: state.company.fuelStationLevel, desc: 'Mengurangi biaya distribusi solar dan mempercepat pengisian.' },
    { id: 'office', name: 'Kantor', cost: 250000000, level: state.company.officeLevel, desc: 'Meningkatkan reputasi dan kemampuan kontrak.' },
    { id: 'warehouse', name: 'Gudang', cost: 300000000, level: state.company.warehouseLevel, desc: 'Memperluas kapasitas operasional dan daya saing.' }
  ];

  return `
    <section class="panel">
      <div class="panel-header">
        <h2>Upgrade Perusahaan</h2>
        <span class="badge blue">Tingkatkan kapasitas</span>
      </div>
      <div class="panel-body">
        <div class="grid-3">
          ${upgrades.map((item) => `
            <div class="upgrade-card">
              <div class="item-head">
                <strong>${item.name}</strong>
                <span class="badge blue">Lv ${item.level}</span>
              </div>
              <p class="muted">${item.desc}</p>
              <div class="controls">
                <button class="primary-btn" data-action="buy-upgrade" data-upgrade="${item.id}">Upgrade (${formatMoney(item.cost)})</button>
              </div>
            </div>
          `).join('')}
        </div>
      </div>
    </section>
  `;
}

function renderStatsView() {
  return `
    <section class="panel">
      <div class="panel-header">
        <h2>Statistik</h2>
        <span class="badge blue">Performance</span>
      </div>
      <div class="panel-body">
        <div class="metric-grid">
          <div class="metric-card">
            <span class="metric-label">Total Armada</span>
            <div class="metric-value">${state.trucks.length}</div>
          </div>
          <div class="metric-card">
            <span class="metric-label">Driver Siap</span>
            <div class="metric-value primary">${state.drivers.filter((driver) => !driver.busy).length}</div>
          </div>
          <div class="metric-card">
            <span class="metric-label">Rata-rata Kondisi</span>
            <div class="metric-value warning">${state.company.condition}%</div>
          </div>
          <div class="metric-card">
            <span class="metric-label">Penjualan Bulanan</span>
            <div class="metric-value success">${formatMoney(state.finance.incomeMonth)}</div>
          </div>
        </div>
      </div>
    </section>
  `;
}

function renderSettingsView() {
  return `
    <section class="panel">
      <div class="panel-header">
        <h2>Pengaturan</h2>
        <span class="badge blue">Simpan & kelola</span>
      </div>
      <div class="panel-body">
        <div class="grid-3">
          <div class="market-card">
            <h3>Save</h3>
            <p class="muted">Simpan progres permainan ke browser lokal.</p>
            <div class="controls">
              <button class="primary-btn" data-action="save-game">Simpan Game</button>
            </div>
          </div>
          <div class="market-card">
            <h3>Load</h3>
            <p class="muted">Memuat progres terakhir yang tersimpan.</p>
            <div class="controls">
              <button class="secondary-btn" data-action="load-game">Load Game</button>
            </div>
          </div>
          <div class="market-card">
            <h3>Reset</h3>
            <p class="muted">Mulai ulang permainan dari awal.</p>
            <div class="controls">
              <button class="danger-btn" data-action="reset-game">Reset Game</button>
            </div>
          </div>
        </div>
      </div>
    </section>
  `;
}

function panelTemplate(title, message, buttonClass, action, dataView, buttonText) {
  return `
    <section class="panel">
      <div class="panel-header">
        <h2>${title}</h2>
      </div>
      <div class="panel-body">
        <div class="muted" style="margin-bottom: 14px;">${message}</div>
        <button class="${buttonClass}" data-action="${action}" data-view="${dataView}">${buttonText}</button>
      </div>
    </section>
  `;
}

function bindUIActions() {
  const actionButtons = document.querySelectorAll('[data-action]');
  actionButtons.forEach((button) => {
    button.onclick = null;
    button.addEventListener('click', () => {
      const action = button.dataset.action;
      const truckId = button.dataset.truckId;
      const modelId = button.dataset.modelId;
      const repair = button.dataset.repair;
      const productId = button.dataset.index;
      const driverId = button.dataset.driverId;
      const upgrade = button.dataset.upgrade;
      const liters = button.dataset.liters;
      const contractId = button.dataset.contractId;
      const view = button.dataset.view;

      switch (action) {
        case 'switch-view':
          currentView = view || 'dashboard';
          renderApp();
          break;
        case 'buy-truck':
          buyTruck(modelId);
          break;
        case 'buy-used-truck':
          buyUsedTruck(Number(productId));
          break;
        case 'sell-truck':
          sellTruck(truckId, true);
          break;
        case 'confirm-sell':
          sellTruck(truckId, false);
          break;
        case 'hire-driver':
          hireDriver();
          break;
        case 'fire-driver':
          fireDriver(driverId);
          break;
        case 'train-driver':
          trainDriver(driverId);
          break;
        case 'bonus-driver':
          bonusDriver(driverId);
          break;
        case 'raise-salary':
          raiseSalary(driverId);
          break;
        case 'assign-driver':
          assignDriverToTruck(truckId);
          break;
        case 'repair-truck':
          repairTruck(truckId, repair || 'light');
          break;
        case 'service-all':
          serviceAll(repair || 'light');
          break;
        case 'refuel-action':
          refuelTruck(truckId, Number(liters) || 40);
          break;
        case 'refuel-quick':
          refuelTruck(truckId, 60);
          break;
        case 'quick-refuel':
          refuelTruck(truckId, 50);
          break;
        case 'quick-service':
          repairTruck(truckId, 'light');
          break;
        case 'accept-contract':
          acceptContract(contractId);
          break;
        case 'save-game':
          saveState();
          addLog('Progress berhasil disimpan ke browser.');
          renderApp();
          break;
        case 'load-game':
          const loaded = loadState();
          if (!loaded) {
            addLog('Tidak ada save yang bisa dimuat.');
            break;
          }
          state = loaded;
          renderApp();
          addLog('Progress berhasil dimuat.');
          break;
        case 'reset-game':
          if (window.confirm('Yakin ingin reset semua progres?')) {
            localStorage.removeItem(STORAGE_KEY);
            state = null;
            showSetupModal();
          }
          break;
        case 'close-setup':
          document.getElementById('setupModal').classList.add('hidden');
          break;
        case 'inspect-used':
          inspectUsedTruck(Number(productId));
          break;
        case 'buy-upgrade':
          buyUpgrade(upgrade);
          break;
        case 'start-trip':
          startJourney();
          break;
      }
    });
  });
}

function addLog(message) {
  if (!state) return;
  state.logs.unshift(message);
  state.logs = state.logs.slice(0, 20);
}

function buyTruck(modelId) {
  if (!state) return;
  const model = TRUCK_MODELS.find((item) => item.id === modelId);
  if (!model) return;

  if (state.company.balance < model.price) {
    addLog(`Saldo tidak cukup untuk membeli ${model.name}.`);
    return;
  }

  if (state.trucks.length >= state.company.garageSlots) {
    addLog('Garasi sudah penuh. Lakukan upgrade garasi terlebih dahulu.');
    return;
  }

  const truck = makeTruckModel(model.id, {
    year: model.year,
    mileage: 150000 + Math.random() * 180000,
    condition: 76 + Math.random() * 14,
    engineCondition: 75 + Math.random() * 18,
    tireCondition: 72 + Math.random() * 16,
    brakeCondition: 68 + Math.random() * 16,
    bodyCondition: 78 + Math.random() * 14,
    bodyType: model.bodyType,
    fuel: 160,
    value: model.price,
    buyingPrice: model.price,
    maintenanceCost: model.maintenance
  });

  state.company.balance -= model.price;
  state.finance.expenseToday += model.price;
  state.finance.history.unshift({
    day: state.day,
    type: 'Pembelian Truk',
    amount: -model.price,
    note: `${model.name}`
  });
  state.trucks.push(truck);
  addLog(`${model.name} berhasil dibeli. Armada bertambah.`);
  updateCompanyProfile();
  saveState();
  renderApp();
}

function buyUsedTruck(index) {
  if (!state) return;
  const truck = state.market.used[index];
  if (!truck) return;

  if (state.company.balance < truck.value) {
    addLog('Saldo tidak cukup untuk membeli truk bekas ini.');
    return;
  }

  if (state.trucks.length >= state.company.garageSlots) {
    addLog('Garasi sudah penuh. Upgrade garasi diperlukan.');
    return;
  }

  state.company.balance -= truck.value;
  state.finance.expenseToday += truck.value;
  state.finance.history.unshift({
    day: state.day,
    type: 'Pembelian Truk Bekas',
    amount: -truck.value,
    note: `${truck.name}`
  });

  state.market.used.splice(index, 1);
  state.trucks.push({
    ...truck,
    id: makeId('truck'),
    value: truck.value,
    status: 'idle',
    driverId: null,
    trip: null,
    isUsedMarket: false
  });

  addLog(`${truck.name} berhasil dibeli dari pasar bekas.`);
  updateCompanyProfile();
  saveState();
  renderApp();
}

function estimateSalePrice(truck) {
  const base = safeNumber(truck.value, 0);
  const condFactor = safeNumber(truck.condition, 70) / 100;
  const mileageFactor = clamp(1 - (safeNumber(truck.mileage, 0) / 1000000), 0.1, 1);
  const ageFactor = clamp(1 - ((new Date().getFullYear() - safeNumber(truck.year, 2020)) * 0.05), 0.35, 1);
  return Math.round(base * condFactor * mileageFactor * ageFactor * 0.7);
}

function getDemandLabel(truck) {
  if (truck.condition > 80) return 'Tinggi';
  if (truck.condition > 60) return 'Normal';
  if (truck.condition > 45) return 'Rendah';
  return 'Buruk';
}

function sellTruck(truckId, verify = true) {
  const truck = getTruckById(truckId);
  if (!truck) return;

  const sellingPrice = estimateSalePrice(truck);
  if (verify && !window.confirm(`Jual ${truck.name} dengan estimasi harga ${formatMoney(sellingPrice)}?`)) {
    return;
  }

  state.company.balance += sellingPrice;
  state.finance.incomeToday += sellingPrice;
  state.finance.history.unshift({
    day: state.day,
    type: 'Penjualan Truk',
    amount: sellingPrice,
    note: `${truck.name}`
  });
  state.trucks = state.trucks.filter((item) => item.id !== truckId);

  if (truck.driverId) {
    const driver = getDriverById(truck.driverId);
    if (driver) {
      driver.truckId = null;
      driver.busy = false;
    }
  }

  addLog(`${truck.name} berhasil dijual dengan nilai ${formatMoney(sellingPrice)}.`);
  updateCompanyProfile();
  saveState();
  renderApp();
}

function hireDriver() {
  if (state.drivers.length >= state.company.maxDriver) {
    addLog('Jumlah driver sudah mencapai batas perusahaan. Upgrade perusahaan atau tambah kapasitas driver.');
    return;
  }

  const newDriver = generateDriver(`Driver ${state.drivers.length + 1}`, {
    age: 24 + Math.floor(Math.random() * 18),
    experience: 1 + Math.floor(Math.random() * 7),
    skill: 65 + Math.random() * 25,
    discipline: 60 + Math.random() * 30,
    fuelEfficiency: 62 + Math.random() * 28,
    accidentRisk: 12 + Math.random() * 18,
    salary: 3200000 + Math.random() * 2600000,
    loyalty: 70 + Math.random() * 26,
    fitness: 72 + Math.random() * 22
  });

  state.drivers.push(newDriver);
  state.company.maxDriver += 0;
  addLog(`${newDriver.name} berhasil direkrut.`);
  saveState();
  renderApp();
}

function fireDriver(driverId) {
  const driver = getDriverById(driverId);
  if (!driver) return;

  if (window.confirm(`Mecat driver ${driver.name}?`)) {
    state.drivers = state.drivers.filter((item) => item.id !== driverId);
    state.trucks.forEach((truck) => {
      if (truck.driverId === driverId) {
        truck.driverId = null;
      }
    });
    addLog(`${driver.name} dipecat dari perusahaan.`);
    saveState();
    renderApp();
  }
}

function trainDriver(driverId) {
  const driver = getDriverById(driverId);
  if (!driver) return;

  const cost = 2000000;
  if (state.company.balance < cost) {
    addLog('Saldo tidak cukup untuk melatih driver.');
    return;
  }

  state.company.balance -= cost;
  state.finance.expenseToday += cost;
  driver.skill = clamp(driver.skill + 8, 0, 100);
  driver.discipline = clamp(driver.discipline + 7, 0, 100);
  driver.fuelEfficiency = clamp(driver.fuelEfficiency + 6, 0, 100);
  driver.experience += 1;
  addLog(`${driver.name} berhasil dilatih dan meningkat skill pengemudi.`);
  saveState();
  renderApp();
}

function bonusDriver(driverId) {
  const driver = getDriverById(driverId);
  if (!driver) return;

  const bonus = 1500000;
  if (state.company.balance < bonus) {
    addLog('Saldo tidak cukup untuk memberi bonus.');
    return;
  }

  state.company.balance -= bonus;
  state.finance.expenseToday += bonus;
  driver.loyalty = clamp(driver.loyalty + 10, 0, 100);
  addLog(`${driver.name} mendapat bonus dan loyalitas meningkat.`);
  saveState();
  renderApp();
}

function raiseSalary(driverId) {
  const driver = getDriverById(driverId);
  if (!driver) return;

  const increment = 500000;
  driver.salary += increment;
  addLog(`${driver.name} menerima kenaikan gaji sebesar ${formatMoney(increment)}.`);
  state.company.balance -= increment;
  state.finance.expenseToday += increment;
  saveState();
  renderApp();
}

function assignDriverToTruck(truckId) {
  const truck = getTruckById(truckId);
  if (!truck) return;

  const availableDriver = state.drivers.find((driver) => !driver.busy && !driver.truckId);
  if (!availableDriver) {
    addLog('Tidak ada driver yang siap ditugaskan ke truk ini.');
    return;
  }

  truck.driverId = availableDriver.id;
  availableDriver.truckId = truck.id;
  addLog(`${availableDriver.name} ditugaskan ke ${truck.name}.`);
  saveState();
  renderApp();
}

function repairTruck(truckId, type = 'light') {
  const truck = getTruckById(truckId);
  if (!truck) return;

  let cost = 0;
  if (type === 'light') cost = 2500000;
  if (type === 'heavy') cost = 8000000;
  if (type === 'engine') cost = 22000000;

  if (state.company.balance < cost) {
    addLog('Saldo tidak cukup untuk perbaikan ini.');
    return;
  }

  state.company.balance -= cost;
  state.finance.expenseToday += cost;
  if (type === 'light') {
    truck.engineCondition = clamp(truck.engineCondition + 10, 0, 100);
    truck.tireCondition = clamp(truck.tireCondition + 12, 0, 100);
    truck.brakeCondition = clamp(truck.brakeCondition + 12, 0, 100);
    truck.bodyCondition = clamp(truck.bodyCondition + 8, 0, 100);
  }

  if (type === 'heavy') {
    truck.engineCondition = clamp(truck.engineCondition + 18, 0, 100);
    truck.tireCondition = clamp(truck.tireCondition + 18, 0, 100);
    truck.brakeCondition = clamp(truck.brakeCondition + 18, 0, 100);
    truck.bodyCondition = clamp(truck.bodyCondition + 12, 0, 100);
  }

  if (type === 'engine') {
    truck.engineCondition = 100;
    truck.tireCondition = clamp(truck.tireCondition + 12, 0, 100);
    truck.brakeCondition = clamp(truck.brakeCondition + 10, 0, 100);
    truck.bodyCondition = clamp(truck.bodyCondition + 8, 0, 100);
  }

  truck.condition = averageCondition(truck);
  addLog(`${truck.name} selesai diperbaiki dengan layanan ${type}.`);
  state.finance.history.unshift({
    day: state.day,
    type: 'Perbaikan Bengkel',
    amount: -cost,
    note: `${truck.name} (${type})`
  });
  updateCompanyProfile();
  saveState();
  renderApp();
}

function averageCondition(truck) {
  const values = [truck.engineCondition, truck.tireCondition, truck.brakeCondition, truck.bodyCondition];
  return values.reduce((sum, item) => sum + item, 0) / values.length;
}

function serviceAll(level) {
  state.trucks.forEach((truck) => repairTruck(truck.id, level));
  addLog(`Semua truk melakukan servis ${level}.`);
  renderApp();
}

function refuelTruck(truckId, liters) {
  const truck = getTruckById(truckId);
  if (!truck) return;

  const cost = liters * state.fuelPrice;
  if (state.company.balance < cost) {
    addLog('Saldo tidak cukup untuk pengisian BBM.');
    return;
  }

  state.company.balance -= cost;
  state.finance.expenseToday += cost;
  truck.fuel = clamp(safeNumber(truck.fuel, 0) + liters, 0, 250);
  state.finance.history.unshift({
    day: state.day,
    type: 'BBM',
    amount: -cost,
    note: `${truck.name} ${liters}L`
  });
  addLog(`${truck.name} diisi solar ${liters} liter.`);
  saveState();
  renderApp();
}

function acceptContract(contractId) {
  const contract = state.market.contracts.find((item) => item.id === contractId);
  if (!contract) return;

  if (state.company.reputation < contract.minReputation) {
    addLog('Reputasi perusahaan belum cukup untuk mengambil kontrak ini.');
    return;
  }

  contract.accepted = true;
  addLog(`Kontrak ${contract.title} berhasil diambil.`);
  renderApp();
}

function startJourney() {
  const truckSelect = document.getElementById('travelTruckSelect');
  const jobSelect = document.getElementById('travelJobSelect');

  if (!truckSelect || !jobSelect) return;

  const truckId = truckSelect.value;
  const jobId = jobSelect.value;
  if (!truckId || !jobId) {
    addLog('Pilih truk dan muatan/kontrak terlebih dahulu.');
    return;
  }

  const truck = getTruckById(truckId);
  const job = [...state.market.cargo, ...state.market.contracts].find((item) => item.id === jobId);
  if (!truck || !job) {
    addLog('Truk atau job tidak valid.');
    return;
  }

  if (truck.status === 'traveling') {
    addLog('Truk ini sedang dalam perjalanan.');
    return;
  }

  const driver = state.drivers.find((item) => item.id === truck.driverId) || state.drivers.find((item) => !item.busy);
  if (!driver) {
    addLog('Tidak ada driver yang siap diarmada.');
    return;
  }

  const routeDistanceValue = getRouteDistance(job.origin, job.destination);
  const totalDistance = routeDistanceValue || Math.max(job.distance, 80);
  const tripDuration = Math.max(4, Math.round((totalDistance / Math.max(22, truck.speed * 0.85)) + (job.duration || 6)));
  const fuelNeeded = Math.max(18, (totalDistance / 100) * truck.fuelConsumption * (1 + job.weight / 10));

  if (truck.fuel < fuelNeeded) {
    addLog(`Solar truk tidak cukup. Isi minimal ${Math.round(fuelNeeded)} liter sebelum berangkat.`);
    return;
  }

  truck.status = 'traveling';
  truck.driverId = driver.id;
  driver.busy = true;
  driver.truckId = truck.id;
  truck.fuel = clamp(truck.fuel - fuelNeeded, 0, 250);
  truck.trip = {
    origin: job.origin,
    destination: job.destination,
    type: job.kind === 'contract' ? 'Kontrak' : 'Muatan',
    distance: totalDistance,
    duration: tripDuration,
    remainingHours: tripDuration,
    payment: job.price || job.payment || 0,
    extraRisk: job.risk || 10,
    eventCount: 0
  };

  if (job.kind === 'contract') {
    job.accepted = true;
  } else {
    job.assigned = true;
  }

  addLog(`${truck.name} berangkat dari ${job.origin} menuju ${job.destination}.`);
  saveState();
  renderApp();
}

function getRouteDistance(origin, destination) {
  const key1 = `${origin}-${destination}`;
  const key2 = `${destination}-${origin}`;
  return safeNumber(routeDistance[key1] || routeDistance[key2], 120);
}

function tickGameLoop() {
  if (!state) return;

  const now = Date.now();
  const deltaSeconds = (now - lastFrameTime) / 1000;
  lastFrameTime = now;

  state.trucks.forEach((truck) => {
    if (truck.status !== 'traveling' || !truck.trip) return;

    const travelRate = deltaSeconds / 40;
    truck.trip.remainingHours = Math.max(0, truck.trip.remainingHours - travelRate);
    truck.trip.eventCount += Math.random() < 0.02 ? 1 : 0;

    if (Math.random() < 0.012 || (truck.trip.remainingHours < 2 && Math.random() < 0.08)) {
      applyTripEvent(truck);
    }

    if (truck.trip.remainingHours <= 0) {
      deliverTrip(truck);
    }
  });

  state.day += (deltaSeconds > 60 ? 1 : 0);
  if (Math.random() < 0.004) {
    state.fuelPrice = Math.round(6500 + Math.random() * 2200);
  }
}

function applyTripEvent(truck) {
  if (!truck.trip) return;
  const event = RANDOM_EVENTS[Math.floor(Math.random() * RANDOM_EVENTS.length)];
  const penalty = safeNumber(event.cost, 500000);
  state.company.balance -= penalty;
  state.finance.expenseToday += penalty;
  state.finance.history.unshift({
    day: state.day,
    type: 'Event Perjalanan',
    amount: -penalty,
    note: `${truck.name} • ${event.name}`
  });

  truck.trip.remainingHours += event.delay;
  truck.engineCondition = clamp(truck.engineCondition - 2, 0, 100);
  truck.tireCondition = clamp(truck.tireCondition - 3, 0, 100);
  truck.brakeCondition = clamp(truck.brakeCondition - 3, 0, 100);
  truck.condition = averageCondition(truck);

  addLog(`${truck.name} menghadapi ${event.name}. Biaya tambahan ${formatMoney(penalty)}.`);
}

function deliverTrip(truck) {
  const trip = truck.trip;
  if (!trip) return;

  const payment = safeNumber(trip.payment, 0);
  const penalty = trip.remainingHours <= 0 ? 0 : 0;
  state.company.balance += payment;
  state.finance.incomeToday += payment;
  state.finance.history.unshift({
    day: state.day,
    type: 'Pendapatan Pengiriman',
    amount: payment,
    note: `${truck.name} • ${trip.origin} → ${trip.destination}`
  });
  state.company.reputation = clamp(state.company.reputation + 3, 0, 100);
  truck.mileage += trip.distance;
  truck.condition = clamp(truck.condition - 6, 0, 100);
  truck.engineCondition = clamp(truck.engineCondition - 4, 0, 100);
  truck.tireCondition = clamp(truck.tireCondition - 6, 0, 100);
  truck.brakeCondition = clamp(truck.brakeCondition - 5, 0, 100);
  truck.bodyCondition = clamp(truck.bodyCondition - 2, 0, 100);
  truck.status = 'idle';
  truck.trip = null;

  const driver = getDriverById(truck.driverId);
  if (driver) {
    driver.busy = false;
    driver.truckId = null;
  }
  truck.driverId = null;

  const marketItem = [...state.market.cargo, ...state.market.contracts].find((item) => item.id === trip.id);
  if (marketItem) {
    marketItem.completed = true;
    marketItem.assigned = false;
  }

  addLog(`${truck.name} tiba di tujuan dan menerima pembayaran ${formatMoney(payment)}.`);
  state.company.status = 'Perusahaan berkembang';
  updateCompanyProfile();
  saveState();
  renderApp();
}

function inspectUsedTruck(index) {
  const truck = state.market.used[index];
  if (!truck) return;

  const detail = `
    Kondisi mesin: ${Math.round(truck.engineCondition)}%\n
    Kondisi ban: ${Math.round(truck.tireCondition)}%\n
    Kondisi rem: ${Math.round(truck.brakeCondition)}%\n
    Kondisi bodi: ${Math.round(truck.bodyCondition)}%\n
    Kilometer: ${formatNumber(truck.mileage)} km\n
    Nilai pasar: ${formatMoney(truck.value)}
  `;

  alert(`Inspeksi ${truck.name}\n\n${detail}`);
}

function buyUpgrade(type) {
  const costs = {
    garage: 200000000,
    workshop: 350000000,
    fuel: 420000000,
    office: 250000000,
    warehouse: 300000000
  };

  const cost = costs[type];
  if (!cost) return;

  if (state.company.balance < cost) {
    addLog('Saldo tidak cukup untuk melakukan upgrade ini.');
    return;
  }

  state.company.balance -= cost;
  state.finance.expenseToday += cost;

  switch (type) {
    case 'garage':
      state.company.garageLevel += 1;
      state.company.garageSlots += 1;
      state.company.maxTruck += 1;
      break;
    case 'workshop':
      state.company.workshopLevel += 1;
      break;
    case 'fuel':
      state.company.fuelStationLevel += 1;
      state.fuelPrice = Math.max(6000, state.fuelPrice - 250);
      break;
    case 'office':
      state.company.officeLevel += 1;
      state.company.reputation = clamp(state.company.reputation + 6, 0, 100);
      break;
    case 'warehouse':
      state.company.warehouseLevel += 1;
      break;
  }

  addLog(`Upgrade ${type} berhasil dilakukan.`);
  state.finance.history.unshift({
    day: state.day,
    type: 'Upgrade Perusahaan',
    amount: -cost,
    note: `${type}`
  });
  updateCompanyProfile();
  saveState();
  renderApp();
}

function setView(view) {
  currentView = view;
  renderApp();
}

window.setView = setView;

function newGameFromSetup() {
  if (!state) {
    showSetupModal();
  }
}

window.addEventListener('beforeunload', () => {
  if (state) {
    saveState();
  }
});
