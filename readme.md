# UTS Galeri Seni - Goresan Rasa

Sebuah aplikasi web galeri seni digital lengkap dengan sistem autentikasi pengguna, manajemen profil, dan pengalaman browsing yang interaktif. Proyek ini merupakan implementasi comprehensive dari pembelajaran HTML, CSS, dan JavaScript dengan fokus pada user experience dan data management.

## 🎨 Deskripsi Proyek

"Goresan Rasa" adalah aplikasi galeri seni digital yang menggabungkan koleksi 48 lukisan klasik dengan sistem user management yang lengkap, memberikan pengalaman yang personal dan terpersonalisasi untuk setiap pengguna.

## 📁 Struktur Repository

```
├── index.html                          # Halaman utama galeri
├── styles.css                          # Stylesheet utama
├── login.html                          # Halaman login
├── registrasi.html                     # Halaman registrasi
├── input-profil.html                   # Form input profil pengguna
├── profil.html                         # Halaman tampilan profil
└── image/                              # Folder aset gambar
    ├── lukisan 1.jpg
    ├── ...
    ├── lukisan 48.jpg
    └── default-profile.jpg
```

## 🚀 Fitur Utama

### 1. Sistem Autentikasi Lengkap
- **Registrasi** dengan validasi form dan data storage
- **Login** dengan simulasi autentikasi
- **Session management** menggunakan Local Storage
- **Logout** dengan clear session data

### 2. Manajemen Profil Pengguna
- **Input profil** dengan upload foto
- **Kalkulasi umur** otomatis dari tanggal lahir
- **Display profil** dengan kartu yang elegan
- **File upload** untuk foto profil dengan preview

### 3. Galeri Interaktif
- **48 lukisan klasik** dengan metadata lengkap
- **Modal overlay** untuk detail viewing
- **Search functionality** real-time
- **Responsive grid** layout
- **Hover effects** dan smooth transitions

### 4. User Experience
- **Clean interface** dengan konsistensi design
- **Smooth animations** dan transitions
- **Mobile-responsive** design
- **Accessibility** considerations
- **Error handling** untuk edge cases

## 🛠 Teknologi yang Digunakan

### Frontend Stack
```html
<!-- HTML5 Semantic Structure -->
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Page Title</title>
  <link rel="stylesheet" href="styles.css">
</head>
```

### CSS3 Modern Features
```css
/* Grid Layout untuk Gallery */
.gallery {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 20px;
}

/* Backdrop Blur untuk Modal */
.overlay {
  backdrop-filter: blur(6px);
  background-color: rgba(0, 0, 0, 0.4);
}

/* Hover Animations */
.profile-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 6px 20px rgba(0, 0, 0, 0.3);
}
```

### JavaScript ES6+ Features
```javascript
// Local Storage untuk Data Persistence
localStorage.setItem('userData', JSON.stringify(data));
const userData = JSON.parse(localStorage.getItem('userData'));

// File Reader API untuk Photo Upload
const reader = new FileReader();
reader.onload = function(e) {
  localStorage.setItem('fotoProfil', e.target.result);
};
reader.readAsDataURL(file);

// Date Calculations
const hitungUmur = (tanggalLahir) => {
  const today = new Date();
  const birthDate = new Date(tanggalLahir);
  let umur = today.getFullYear() - birthDate.getFullYear();
  return umur;
};
```

## 🔐 Sistem Autentikasi

### Flow Autentikasi
1. **Registrasi** → **Login** → **Input Profil** → **Profil** → **Galeri**
2. **Session Management** dengan Local Storage
3. **Data Validation** pada setiap form
4. **Security Considerations** untuk production use

### Form Validation
```javascript
// Email Validation
<input type="email" required>

// Number-only Input
function hanyaAngka(event) {
  const charCode = event.which ? event.which : event.keyCode;
  return (charCode >= 48 && charCode <= 57);
}

// Required Fields Validation
<input type="text" required>
<textarea required></textarea>
```

## 🎨 Design System

### Color Palette
```css
:root {
  --primary-blue: #1e3a8a;
  --secondary-blue: #374151;
  --danger-red: #dc3545;
  --background-gray: #f3f4f6;
  --card-white: #ffffff;
  --text-dark: #333333;
  --text-light: #555555;
}
```

### Typography & Spacing
- **Font Family**: Arial, sans-serif untuk readability
- **Consistent Spacing**: 10px, 15px, 20px, 30px intervals
- **Border Radius**: 5px, 8px, 10px, 20px untuk hierarchy
- **Box Shadows**: Subtle depth dengan consistent opacity

### Component Styling
```css
/* Form Components */
.form-container {
  background: white;
  padding: 30px;
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
  width: 400px;
}

/* Button Styles */
button {
  width: 100%;
  padding: 10px;
  background-color: #1e3a8a;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.3s ease;
}
```

## 📱 Responsive Design

### Layout Strategy
- **Mobile-first** approach dengan progressive enhancement
- **CSS Grid** untuk galeri yang adaptive
- **Flexbox** untuk navigation dan form layouts
- **Viewport units** untuk full-screen elements

### Breakpoint Considerations
```css
/* Mobile: Default styles */
.gallery {
  grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
  gap: 20px;
  padding: 20px;
}

/* Tablet & Desktop: Enhanced spacing */
@media (min-width: 768px) {
  .form-container {
    width: 400px;
  }
}
```

## 🔧 Data Management

### Local Storage Schema
```javascript
// User Authentication Data
{
  email: "user@example.com",
  password: "hashedPassword",
  phone: "1234567890",
  dob: "1990-01-01",
  address: "User Address"
}

// Profile Data
{
  nama: "John Doe",
  kelas: "10A",
  tanggalLahir: "1990-01-01",
  alamat: "Complete Address",
  fotoProfil: "data:image/jpeg;base64,..."
}
```

### File Upload Handling
```javascript
function simpanProfil() {
  const photo = document.getElementById('photo').files[0];
  
  if (photo) {
    const reader = new FileReader();
    reader.onload = function(e) {
      localStorage.setItem('fotoProfil', e.target.result);
      window.location.href = 'profil.html';
    };
    reader.readAsDataURL(photo);
  }
}
```

## 🖼 Galeri Features

### Data Structure
```javascript
const dataLukisan = [
  {
    nama: "Painting Title\nArtist Name (Nationality, Years)",
    gambar: "image/lukisan X.jpg",
    deskripsi: "Detailed artistic description..."
  }
];
```

### Interactive Features
- **Modal overlay** dengan click-outside-to-close
- **Search functionality** dengan real-time filtering
- **Image lazy loading** considerations
- **Keyboard navigation** support

## 📄 Page Breakdown

### 1. registrasi.html
- **Purpose**: User registration dengan comprehensive form
- **Features**: Email validation, number-only phone input, required fields
- **Flow**: Registrasi → Login
- **Data**: Stores basic account information

### 2. login.html
- **Purpose**: User authentication
- **Features**: Simple email/password form
- **Flow**: Login → Input Profil
- **Security**: Basic form validation

### 3. input-profil.html
- **Purpose**: Collect detailed user profile
- **Features**: File upload, date picker, textarea
- **Flow**: Input Profil → Profil
- **Data**: Stores personal information dan photo

### 4. profil.html
- **Purpose**: Display user profile
- **Features**: Age calculation, photo display, hover effects
- **Flow**: Profil → Galeri atau Logout
- **UX**: Elegant card design dengan animations

### 5. index.html
- **Purpose**: Main gallery experience
- **Features**: 48 paintings, modal details, search
- **Flow**: Main application destination
- **Data**: Rich painting metadata dengan descriptions

## 🎯 Educational Outcomes

### HTML Skills
- **Form elements** dan input types
- **Semantic structure** untuk accessibility
- **Meta tags** untuk proper document setup
- **Link relationships** antar halaman

### CSS Skills
- **Grid dan Flexbox** untuk modern layouts
- **Transitions dan animations** untuk smooth UX
- **Responsive design** dengan mobile-first approach
- **Component-based** styling approach

### JavaScript Skills
- **DOM manipulation** untuk dynamic content
- **Event handling** untuk user interactions
- **Local Storage** untuk data persistence
- **File API** untuk image uploads
- **Date manipulation** untuk age calculation

## 🔒 Security Considerations

### Current Implementation
- **Client-side only** - suitable untuk educational purposes
- **Local Storage** untuk data persistence
- **No encryption** - data stored in plain text
- **Basic validation** - form-level only

### Production Enhancements Needed
```javascript
// Password Hashing (would need backend)
const hashedPassword = await bcrypt.hash(password, 10);

// JWT Tokens untuk session management
const token = jwt.sign({userId}, secretKey, {expiresIn: '24h'});

// HTTPS only cookies
document.cookie = "session=token; Secure; HttpOnly; SameSite=Strict";
```

## 🚀 Cara Menjalankan

### Setup
1. **Download** semua file ke folder yang sama
2. **Pastikan struktur** folder sesuai dengan hierarchy
3. **Siapkan folder image/** dengan 48 lukisan (lukisan 1.jpg - lukisan 48.jpg)
4. **Tambahkan default-profile.jpg** untuk placeholder foto

### User Journey
```bash
# Flow normal untuk new user:
registrasi.html → login.html → input-profil.html → profil.html → index.html

# Flow untuk returning user:
login.html → profil.html → index.html
```

### Testing Scenarios
1. **Complete Flow**: Registrasi → Login → Input → Profile → Gallery
2. **Form Validation**: Test required fields, email format
3. **File Upload**: Test photo upload dan display
4. **Search Feature**: Test gallery search functionality
5. **Responsive**: Test pada berbagai screen sizes

## 💡 Best Practices Implemented

### Code Organization
- **Separation of concerns** dengan external CSS
- **Consistent naming** conventions
- **Comment documentation** untuk complex functions
- **Error handling** untuk user inputs

### User Experience
- **Clear navigation** flow antar pages
- **Consistent design** language di semua pages
- **Loading states** dan feedback messages
- **Accessibility** considerations

### Performance
- **Minimal dependencies** - vanilla JS only
- **Efficient DOM** manipulation
- **Optimized images** sizing
- **Local data** storage untuk fast access

## 🔧 Pengembangan Lebih Lanjut

### Backend Integration
- **Database** untuk user management
- **Authentication** dengan JWT tokens
- **File storage** dengan cloud services
- **API endpoints** untuk data operations

### Enhanced Features
- **Email verification** untuk registration
- **Password reset** functionality
- **Social media** login integration
- **Favorites** system untuk paintings
- **Comments** dan ratings untuk artworks

### Advanced UX
- **Progressive Web App** features
- **Offline** functionality
- **Push notifications** untuk updates
- **Advanced search** dengan filters
- **Virtual tours** atau AR features

---

**🎨 Goresan Rasa - Menggabungkan Seni Klasik dengan Teknologi Modern**

*Dibuat untuk UTS dengan fokus pada full-stack web development concepts menggunakan frontend technologies*