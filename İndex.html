<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Müzik Kutusu – %100 Ücretsiz Telifsiz Müzik</title>
  <script src="https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2"></script>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    body { background: linear-gradient(135deg, #0f0f0f, #1a0033); min-height: 100vh; color: white; font-family: 'Segoe UI', sans-serif; }
    .card { transition: all 0.3s; }
    .card:hover { transform: translateY(-10px); }
  </style>
</head>
<body class="min-h-screen">

  bg-black text-white">

  <div id="app" class="container mx-auto px-4 py-10 max-w-6xl">
    <h1 class="text-5xl md:text-7xl font-bold text-center mb-4 bg-gradient-to-r from-pink-500 to-purple-500 bg-clip-text text-transparent">
      Müzik Kutusu
    </h1>
    <p class="text-center text-xl mb-12 opacity-90">Türkiye'nin %100 ücretsiz telifsiz müzik platformu</p>

    <div id="music-grid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8"></div>
  </div>

  <!-- Sabit Alt Çalar -->
  <div id="player" class="fixed bottom-0 left-0 right-0 bg-black/95 backdrop-blur-lg border-t border-pink-800 p-4 hidden">
    <div class="container mx-auto flex items-center justify-between">
      <div>
        <p id="now-title" class="font-bold text-lg"></p>
        <p class="text-sm opacity-70">Müzik Kutusu – %100 telifsiz</p>
      </div>
      <div class="flex items-center gap-6">
        <button id="prev-btn" class="text-3xl">⏮</button>
        <button id="play-btn" class="text-5xl">▶</button>
        <button id="next-btn" class="text-3xl">⏭</button>
        <a id="download-btn" class="bg-green-600 hover:bg-green-500 px-6 py-3 rounded-full font-bold">⬇ İndir</a>
      </div>
    </div>
  </div>

  <!-- Admin Butonu (sağ alt köşe) -->
  <button onclick="openAdmin()" class="fixed bottom-4 right-4 bg-purple-700 hover:bg-purple-600 px-6 py-3 rounded-full shadow-lg z-50">
    Admin ⚙
  </button>

  <!-- Admin Modal -->
  <div id="admin-modal" class="fixed inset-0 bg-black/90 flex items-center justify-center hidden z-50">
    <div class="bg-gray-900 p-8 rounded-2xl w-full max-w-2xl max-h-screen overflow-y-auto">
      <h2 class="text-3xl mb-6">Admin Panel</h2>
      <input id="admin-pass" type="password" placeholder="Şifre" class="w-full p-4 rounded bg-gray-800 mb-4"/>
      <button onclick="login()" class="w-full bg-pink-600 py-3 rounded mb-6">Giriş Yap</button>

      <div id="admin-content" class="hidden">
        <h3 class="text-2xl mb-4">Yeni Müzik Ekle</h3>
        <input id="title" placeholder="Müzik adı" class="w-full p-3 rounded bg-gray-800 mb-3"/>
        <input id="tags" placeholder="Etiketler (lofi, türkü, epik...)" class="w-full p-3 rounded bg-gray-800 mb-3"/>
        <input id="audio-file" type="file" accept="audio/*" class="w-full p-3 bg-gray-800 mb-3"/>
        <input id="cover-file" type="file" accept="image/*" class="w-full p-3 bg-gray-800 mb-6"/>
        <button onclick="addMusic()" class="w-full bg-green-600 hover:bg-green-500 py-3 rounded-full font-bold">+ Ekle & Yükle</button>

        <h3 class="text-xl mt-10 mb-4">Yüklü Müzikler</h3>
        <div id="admin-list" class="space-y-3"></div>
      </div>

      <button onclick="document.getElementById('admin-modal').classList.add('hidden')" class="mt-6 text-gray-400">Kapat</button>
    </div>
  </div>

<script>
// === SUPABASE BAĞLANTISI ===
const supabase = Supabase.createClient(
  'https://jzidtvylnrolmmlaegyr.supabase.co',
  'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Imp6aWR0dnlsbnJvbG1tbGFlZ3lyIiwicm9sZSI6ImFub24iLCJpYXQiOjE3NjUwMDQ4ODgsImV4cCI6MjA4MDU4MDg4OH0.S61VHALTStNxq2RY4B2GhrAuELTtgycsTrTw5cH04EA'
);

let allMusics = [];
let currentIndex = 0;
let audio = new Audio();

async function loadMusics() {
  const { data } = await supabase.from('musics').select('*');
  allMusics = data || [];
  renderMusics();
}

function renderMusics() {
  const grid = document.getElementById('music-grid');
  grid.innerHTML = '';
  allMusics.forEach((m, i) => {
    const div = document.createElement('div');
    div.className = 'card bg-white/10 backdrop-blur rounded-2xl overflow-hidden';
    div.innerHTML = `
      <img src="${m.cover_url || 'https://via.placeholder.com/400x400/440066/ffffff?text=Müzik+Kutusu'}" class="w-full h-64 object-cover"/>
      <div class="p-6">
        <h3 class="text-2xl font-bold mb-3">${m.title}</h3>
        <div class="flex flex-wrap gap-2 mb-4">
          \( {m.tags.split(',').map(t => `<span class="px-3 py-1 bg-pink-600/50 rounded-full text-sm"> \){t.trim()}</span>`).join('')}
        </div>
        <button onclick="playMusic(${i})" class="bg-pink-600 hover:bg-pink-500 px-8 py-4 rounded-full font-bold mr-3">▶ Oynat</button>
        <a href="${m.audio_url}" download class="inline-block bg-green-600 hover:bg-green-500 px-8 py-4 rounded-full font-bold">⬇ İndir</a>
        <p class="mt-6 text-sm opacity-70">♫ ${m.title} – Müzik Kutusu<br>%100 telifsiz, ticari kullanım serbest</p>
      </div>
    `;
    grid.appendChild(div);
  });
}

function playMusic(index) {
  currentIndex = index;
  const m = allMusics[index];
  audio.src = m.audio_url;
  audio.play();
  document.getElementById('now-title').textContent = m.title;
  document.getElementById('play-btn').innerHTML = '⏸';
  document.getElementById('download-btn').href = m.audio_url;
  document.getElementById('player').classList.remove('hidden');
}

document.getElementById('play-btn').onclick = () => {
  if (audio.paused) {
    audio.play();
    document.getElementById('play-btn').innerHTML = '⏸';
  } else {
    audio.pause();
    document.getElementById('play-btn').innerHTML = '▶';
  }
};

document.getElementById('next-btn').onclick = () => {
  currentIndex = (currentIndex + 1) % allMusics.length;
  playMusic(currentIndex);
};

document.getElementById('prev-btn').onclick = () => {
  currentIndex = (currentIndex - 1 + allMusics.length) % allMusics.length;
  playMusic(currentIndex);
};

audio.onended = () => {
  document.getElementById('next-btn').click();
};

// === ADMIN KISMI ===
let isAdmin = false;

function openAdmin() {
  document.getElementById('admin-modal').classList.remove('hidden');
}

async function login() {
  if (document.getElementById('admin-pass').value === 'efe12345efe') {
    isAdmin = true;
    document.getElementById('admin-content').classList.remove('hidden');
    loadAdminList();
  } else {
    alert('Şifre yanlış!');
  }
}

async function addMusic() {
  const title = document.getElementById('title').value;
  const tags = document.getElementById('tags').value;
  const audioFile = document.getElementById('audio-file').files[0];
  const coverFile = document.getElementById('cover-file').files[0];

  if (!title || !audioFile) return alert('Başlık ve ses dosyası zorunlu!');

  const audioPath = `audio/\( {Date.now()}_ \){audioFile.name}`;
  const coverPath = coverFile ? `cover/\( {Date.now()}_ \){coverFile.name}` : null;

  await supabase.storage.from('music').upload(audioPath, audioFile);
  if (coverFile) await supabase.storage.from('music').upload(coverPath, coverFile);

  const audio_url = `https://jzidtvylnrolmmlaegyr.supabase.co/storage/v1/object/public/music/${audioPath}`;
  const cover_url = coverFile ? `https://jzidtvylnrolmmlaegyr.supabase.co/storage/v1/object/public/music/${coverPath}` : null;

  await supabase.from('musics').insert({ title, tags, audio_url, cover_url });
  alert('Müzik eklendi!');
  loadMusics();
  loadAdminList();
}

async function loadAdminList() {
  const { data } = await supabase.from('musics').select('*');
  const list = document.getElementById('admin-list');
  list.innerHTML = '';
  data.forEach(m => {
    const div = document.createElement('div');
    div.className = 'bg-white/10 p-4 rounded flex justify-between';
    div.innerHTML = `<span>\( {m.title} – \){m.tags}</span>
      <button onclick="deleteMusic(${m.id})" class="bg-red-600 px-4 py-2 rounded">Sil</button>`;
    list.appendChild(div);
  });
}

async function deleteMusic(id) {
  if (confirm('Silmek istediğine emin misin?')) {
    await supabase.from('musics').delete().eq('id', id);
    loadMusics();
    loadAdminList();
  }
}

// Başlat
loadMusics();
</script>

</body>
</html>
