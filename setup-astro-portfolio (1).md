# Setup: Astro Portfolio + React + Animasi

## Step 1 — Buat Project

```bash
npm create astro@latest portfolio -- --template basics --typescript strict --no-install --no-git
cd portfolio
npm install
```

## Step 2 — Tambah Tailwind CSS v4

```bash
npx astro add tailwind --yes
```

## Step 3 — Tambah React

```bash
npx astro add react --yes
```

## Step 4 — Install Library Animasi

```bash
npm install framer-motion gsap @studio-freight/lenis
```

- `framer-motion` — animasi React component (hover, mount, scroll reveal)
- `gsap` — animasi timeline kompleks dan scroll-triggered
- `lenis` — smooth scroll

## Step 5 — Setup Font Satoshi

```bash
mkdir -p public/fonts
```

Download manual di https://www.fontshare.com/fonts/satoshi  
Taruh file `Satoshi-Variable.woff2` di `public/fonts/`

## Step 6 — Struktur Folder

```bash
mkdir -p src/components/react src/components/astro src/layouts src/styles
touch src/styles/global.css
```

Struktur akhir:

```
src/
├── components/
│   ├── react/      ← komponen interaktif (.tsx)
│   └── astro/      ← komponen statis (.astro)
├── layouts/
├── pages/
│   └── index.astro
└── styles/
    └── global.css
```

## Step 7 — Jalankan Dev Server

```bash
npm run dev
```

Buka `http://localhost:4321`

---

## Catatan Penting

Komponen React di Astro perlu directive `client:*` supaya JavaScript-nya aktif di browser:

```astro
<!-- Langsung load saat halaman dibuka -->
<MyComponent client:load />

<!-- Load saat komponen masuk viewport -->
<MyComponent client:visible />
```

Komponen statis (tanpa animasi/interaksi) tetap pakai `.astro` biasa tanpa directive.
```
