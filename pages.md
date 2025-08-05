**Pages**

Pada Inertia.js, *pages* adalah komponen utama yang merepresentasikan setiap halaman aplikasi. biasanya berupa file komponen (misal, Vue, React, atau Svelte) yang akan dirender oleh Inertia saat user mengunjungi route tertentu.

**Cara Kerja Pages di Inertia.js:**
- Setiap route di backend (misal Laravel) akan mengembalikan response Inertia yang menunjuk ke sebuah page.
- Page menerima *props* dari backend, sehingga data bisa langsung digunakan di komponen frontend.
- Navigasi antar page dilakukan tanpa reload penuh, sehingga pengalaman pengguna lebih cepat dan mulus.

**Contoh Routing di Laravel:**
```php
use Inertia\Inertia;

Route::get('/dashboard', function () {
    return Inertia::render('Dashboard', [
        'user' => Auth::user(),
    ]);
});
```

**Contoh Page di React:**
```jsx
import React from 'react';

export default function Dashboard({ user }) {
  return (
    <div>
      <h1>Dashboard</h1>
      <p>Selamat datang, {user.name}</p>
    </div>
  );
}
```

Pada contoh di atas, komponen `Dashboard` menerima props `user` yang dikirim dari backend Laravel. Dengan pendekatan ini, setiap page di aplikasi React Anda cukup berupa komponen biasa yang menerima data dari backend melalui props.

Dengan konsep pages ini, pengembangan aplikasi SPA menjadi lebih sederhana dan terstruktur.

Referensi: [Inertia.js Pages Documentation](https://inertiajs.com/pages)