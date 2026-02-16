<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Style Hub · Complete E-commerce Platform</title>
  
  <!-- Font Awesome -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Bengali:wght@400;500;700&display=swap" rel="stylesheet">
  <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Devanagari:wght@400;500;700&display=swap" rel="stylesheet">
  
  <!-- Firebase SDK -->
  <script src="https://www.gstatic.com/firebasejs/10.8.0/firebase-app-compat.js"></script>
  <script src="https://www.gstatic.com/firebasejs/10.8.0/firebase-auth-compat.js"></script>
  <script src="https://www.gstatic.com/firebasejs/10.8.0/firebase-firestore-compat.js"></script>
  
  <style>
    /* ==================== GLOBAL STYLES ==================== */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', 'Noto Sans Bengali', 'Noto Sans Devanagari', sans-serif;
      background: #f0f2f5;
      color: #1e293b;
      line-height: 1.5;
    }

    :root {
      --primary: #2563eb;
      --primary-dark: #1d4ed8;
      --secondary: #10b981;
      --danger: #ef4444;
      --warning: #f59e0b;
      --dark: #1e293b;
      --light: #f8fafc;
      --gray: #64748b;
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 20px;
    }

    /* ==================== HEADER ==================== */
    .header {
      background: white;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
      padding: 15px 0;
      position: sticky;
      top: 0;
      z-index: 100;
    }

    .header-content {
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 15px;
    }

    .logo {
      font-size: 28px;
      font-weight: 800;
      color: var(--primary);
      cursor: pointer;
    }

    /* Language Switcher */
    .lang-switcher {
      display: flex;
      gap: 8px;
    }

    .lang-btn {
      padding: 6px 12px;
      border: 1px solid #e2e8f0;
      background: white;
      border-radius: 20px;
      cursor: pointer;
      font-size: 14px;
      font-weight: 500;
      transition: all 0.2s;
    }

    .lang-btn:hover {
      background: #e5eeff;
      border-color: var(--primary);
    }

    .lang-btn.active {
      background: var(--primary);
      color: white;
      border-color: var(--primary);
    }

    /* Auth Buttons */
    .auth-buttons {
      display: flex;
      gap: 10px;
    }

    .btn {
      padding: 10px 20px;
      border: none;
      border-radius: 8px;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.2s;
      font-family: inherit;
    }

    .btn-primary {
      background: var(--primary);
      color: white;
    }

    .btn-primary:hover {
      background: var(--primary-dark);
    }

    .btn-outline {
      background: transparent;
      border: 1px solid #e2e8f0;
    }

    .btn-outline:hover {
      background: #f1f5f9;
    }

    .btn-danger {
      background: var(--danger);
      color: white;
    }

    .user-info {
      display: flex;
      align-items: center;
      gap: 15px;
    }

    .user-name {
      font-weight: 600;
      color: var(--primary);
    }

    /* Cart Icon */
    .cart-icon {
      position: relative;
      font-size: 22px;
      cursor: pointer;
    }

    .cart-badge {
      position: absolute;
      top: -10px;
      right: -10px;
      background: var(--danger);
      color: white;
      font-size: 12px;
      padding: 2px 6px;
      border-radius: 50%;
      min-width: 18px;
      text-align: center;
    }

    /* ==================== PROFILE SECTION ==================== */
    .profile-section {
      background: white;
      border-radius: 12px;
      overflow: hidden;
      margin: 20px 0;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
    }

    .cover-slider {
      height: 300px;
      position: relative;
      overflow: hidden;
    }

    .cover-container {
      width: 100%;
      height: 100%;
      position: relative;
    }

    .cover-image {
      position: absolute;
      width: 100%;
      height: 100%;
      background-size: cover;
      background-position: center;
      opacity: 0;
      transition: opacity 1s;
    }

    .cover-image.active {
      opacity: 1;
    }

    .cover-dots {
      position: absolute;
      bottom: 15px;
      left: 50%;
      transform: translateX(-50%);
      display: flex;
      gap: 8px;
    }

    .dot {
      width: 10px;
      height: 10px;
      border-radius: 50%;
      background: rgba(255,255,255,0.5);
      cursor: pointer;
    }

    .dot.active {
      background: white;
    }

    .profile-info {
      padding: 20px;
      display: flex;
      gap: 20px;
      align-items: flex-end;
    }

    .profile-pic {
      margin-top: -80px;
    }

    .profile-pic img {
      width: 150px;
      height: 150px;
      border-radius: 50%;
      border: 4px solid white;
      object-fit: cover;
    }

    .profile-details {
      flex: 1;
    }

    .profile-details h2 {
      font-size: 28px;
      margin-bottom: 5px;
    }

    .profile-details p {
      color: var(--gray);
    }

    .edit-btn {
      padding: 10px 20px;
      background: var(--primary);
      color: white;
      border: none;
      border-radius: 8px;
      cursor: pointer;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    /* ==================== PRODUCTS ==================== */
    .products-section {
      background: white;
      border-radius: 12px;
      padding: 20px;
      margin: 20px 0;
    }

    .section-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 20px;
    }

    .section-header h2 {
      font-size: 24px;
    }

    .product-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
      gap: 20px;
    }

    .product-card {
      border: 1px solid #e2e8f0;
      border-radius: 10px;
      overflow: hidden;
      transition: 0.3s;
    }

    .product-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 5px 15px rgba(0,0,0,0.1);
    }

    .product-image {
      width: 100%;
      height: 200px;
      object-fit: cover;
    }

    .product-info {
      padding: 15px;
    }

    .product-name {
      font-weight: 600;
      margin-bottom: 5px;
    }

    .product-price {
      color: var(--primary);
      font-weight: 700;
      font-size: 18px;
      margin: 10px 0;
    }

    .add-to-cart {
      width: 100%;
      padding: 10px;
      background: var(--primary);
      color: white;
      border: none;
      border-radius: 6px;
      cursor: pointer;
      font-weight: 500;
    }

    .add-to-cart:hover {
      background: var(--primary-dark);
    }

    /* ==================== MODALS ==================== */
    .modal {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0,0,0,0.5);
      z-index: 1000;
      align-items: center;
      justify-content: center;
    }

    .modal.active {
      display: flex;
    }

    .modal-content {
      background: white;
      padding: 30px;
      border-radius: 12px;
      max-width: 400px;
      width: 90%;
      max-height: 80vh;
      overflow-y: auto;
      position: relative;
    }

    .close {
      position: absolute;
      top: 15px;
      right: 20px;
      font-size: 24px;
      cursor: pointer;
      color: var(--gray);
    }

    .modal h2 {
      margin-bottom: 20px;
    }

    .form-group {
      margin-bottom: 15px;
    }

    .form-group input {
      width: 100%;
      padding: 12px;
      border: 1px solid #e2e8f0;
      border-radius: 6px;
      font-family: inherit;
    }

    .form-group input:focus {
      outline: none;
      border-color: var(--primary);
    }

    .cart-item {
      display: flex;
      gap: 10px;
      margin-bottom: 15px;
      padding-bottom: 15px;
      border-bottom: 1px solid #e2e8f0;
    }

    .cart-item img {
      width: 60px;
      height: 60px;
      border-radius: 8px;
      object-fit: cover;
    }

    .cart-total {
      font-weight: 700;
      font-size: 18px;
      text-align: right;
      margin: 20px 0;
    }

    /* Payment Methods */
    .payment-method {
      border: 2px solid #e2e8f0;
      border-radius: 8px;
      padding: 15px;
      margin: 10px 0;
      cursor: pointer;
      display: flex;
      align-items: center;
      gap: 15px;
    }

    .payment-method.selected {
      border-color: var(--primary);
      background: #eff6ff;
    }

    .payment-method i {
      font-size: 24px;
    }

    .bkash { color: #e2136e; }
    .nagad { color: #f5821f; }
    .rocket { color: #662d91; }
    .card { color: var(--primary); }

    /* Toast */
    .toast {
      position: fixed;
      bottom: 20px;
      right: 20px;
      background: #1e293b;
      color: white;
      padding: 12px 24px;
      border-radius: 40px;
      z-index: 2000;
      display: none;
    }

    /* Responsive */
    @media (max-width: 768px) {
      .profile-info {
        flex-direction: column;
        align-items: center;
        text-align: center;
      }
      
      .profile-pic {
        margin-top: -60px;
      }
      
      .profile-pic img {
        width: 120px;
        height: 120px;
      }
      
      .cover-slider {
        height: 200px;
      }
    }
  </style>
</head>
<body>
  <!-- Header -->
  <header class="header">
    <div class="container header-content">
      <div class="logo" onclick="window.scrollTo({top:0,behavior:'smooth'})">STYLE HUB</div>

      <!-- Language Switcher -->
      <div class="lang-switcher">
        <button class="lang-btn active" onclick="changeLanguage('en')">EN</button>
        <button class="lang-btn" onclick="changeLanguage('bn')">বাংলা</button>
        <button class="lang-btn" onclick="changeLanguage('hi')">हिंदी</button>
      </div>

      <!-- Auth & Cart -->
      <div style="display: flex; align-items: center; gap: 20px;">
        <div id="authSection">
          <div class="auth-buttons" id="authButtons">
            <button class="btn btn-outline" onclick="showAuthModal('login')">Login</button>
            <button class="btn btn-primary" onclick="showAuthModal('register')">Register</button>
          </div>
          <div class="user-info" id="userInfo" style="display: none;">
            <span class="user-name" id="userName"></span>
            <button class="btn btn-danger" onclick="logout()">Logout</button>
          </div>
        </div>
        
        <div class="cart-icon" onclick="showCart()">
          <i class="fas fa-shopping-cart"></i>
          <span class="cart-badge" id="cartCount">0</span>
        </div>
      </div>
    </div>
  </header>

  <div class="container">
    <!-- Profile Section -->
    <div class="profile-section">
      <!-- Cover Slider -->
      <div class="cover-slider" id="coverSlider">
        <div class="cover-container">
          <div class="cover-image active" style="background-image: url('https://images.unsplash.com/photo-1441986300917-64674bd600d8?w=1200')"></div>
          <div class="cover-image" style="background-image: url('https://images.unsplash.com/photo-1441984904996-e0b6ba687e04?w=1200')"></div>
          <div class="cover-image" style="background-image: url('https://images.unsplash.com/photo-1472851294608-062f824d29cc?w=1200')"></div>
          <div class="cover-image" style="background-image: url('https://images.unsplash.com/photo-1483985988355-763728e1935b?w=1200')"></div>
        </div>
        <div class="cover-dots" id="coverDots">
          <span class="dot active" onclick="changeCover(0)"></span>
          <span class="dot" onclick="changeCover(1)"></span>
          <span class="dot" onclick="changeCover(2)"></span>
          <span class="dot" onclick="changeCover(3)"></span>
        </div>
      </div>

      <!-- Profile Info -->
      <div class="profile-info">
        <div class="profile-pic">
          <img src="https://images.unsplash.com/photo-1535713875002-d1d0cf377fde?w=200" alt="Profile" id="profilePic">
        </div>
        <div class="profile-details">
          <h2 id="profileName">Welcome to Style Hub</h2>
          <p id="profileBio">Please login to start shopping</p>
        </div>
        <button class="edit-btn" onclick="if(currentUser) showEditProfile() else showAuthModal('login')">
          <i class="fas fa-pen"></i> Edit Profile
        </button>
      </div>
    </div>

    <!-- Products Section -->
    <div class="products-section">
      <div class="section-header">
        <h2>Featured Products</h2>
      </div>
      <div class="product-grid" id="productGrid"></div>
    </div>
  </div>

  <!-- Auth Modal -->
  <div class="modal" id="authModal">
    <div class="modal-content">
      <span class="close" onclick="closeModal('authModal')">&times;</span>
      <h2 id="authTitle">Login</h2>
      <form onsubmit="handleAuth(event)">
        <div class="form-group" id="nameField" style="display: none;">
          <input type="text" id="authName" placeholder="Full Name">
        </div>
        <div class="form-group">
          <input type="email" id="authEmail" placeholder="Email" required>
        </div>
        <div class="form-group">
          <input type="password" id="authPassword" placeholder="Password" required>
        </div>
        <button type="submit" class="btn btn-primary" style="width: 100%;">Continue</button>
      </form>
    </div>
  </div>

  <!-- Cart Modal -->
  <div class="modal" id="cartModal">
    <div class="modal-content">
      <span class="close" onclick="closeModal('cartModal')">&times;</span>
      <h2>Shopping Cart</h2>
      <div id="cartItems"></div>
      <div class="cart-total" id="cartTotal">Total: $0.00</div>
      <button class="btn btn-primary" style="width: 100%;" onclick="checkout()">Checkout</button>
    </div>
  </div>

  <!-- Payment Modal -->
  <div class="modal" id="paymentModal">
    <div class="modal-content">
      <span class="close" onclick="closePaymentModal()">&times;</span>
      <h2>Payment</h2>
      <div id="orderSummary"></div>
      <div class="payment-method" onclick="selectPayment('bkash')">
        <i class="fas fa-mobile-alt bkash"></i>
        <span>bKash</span>
      </div>
      <div class="payment-method" onclick="selectPayment('nagad')">
        <i class="fas fa-mobile-alt nagad"></i>
        <span>Nagad</span>
      </div>
      <div class="payment-method" onclick="selectPayment('rocket')">
        <i class="fas fa-mobile-alt rocket"></i>
        <span>Rocket</span>
      </div>
      <div class="payment-method" onclick="selectPayment('card')">
        <i class="fas fa-credit-card card"></i>
        <span>Credit Card</span>
      </div>
      <button class="btn btn-primary" style="width: 100%; margin-top: 20px;" onclick="processPayment()">Pay Now</button>
    </div>
  </div>

  <!-- Edit Profile Modal -->
  <div class="modal" id="editProfileModal">
    <div class="modal-content">
      <span class="close" onclick="closeModal('editProfileModal')">&times;</span>
      <h2>Edit Profile</h2>
      <div class="form-group">
        <input type="text" id="editName" placeholder="Name">
      </div>
      <div class="form-group">
        <input type="text" id="editBio" placeholder="Bio">
      </div>
      <div class="form-group">
        <input type="text" id="editPic" placeholder="Profile Picture URL">
      </div>
      <button class="btn btn-primary" style="width: 100%;" onclick="saveProfile()">Save Changes</button>
    </div>
  </div>

  <!-- Toast -->
  <div class="toast" id="toast"></div>

  <script>
    // ==================== FIREBASE CONFIG ====================
    const firebaseConfig = {
      apiKey: "AIzaSyDxOMNduC5AU5AaHmga2yC_V3RHjhX2ykQ",
      authDomain: "style-hub-fe257.firebaseapp.com",
      projectId: "style-hub-fe257",
      storageBucket: "style-hub-fe257.firebasestorage.app",
      messagingSenderId: "544518937543",
      appId: "1:544518937543:web:74dbc18a88b1f1d16f97e2"
    };

    // Initialize Firebase
    firebase.initializeApp(firebaseConfig);
    const auth = firebase.auth();
    const db = firebase.firestore();

    // ==================== GLOBAL VARIABLES ====================
    let currentUser = null;
    let cart = JSON.parse(localStorage.getItem('cart')) || [];
    let products = [];
    let currentLang = 'en';

    // ==================== LANGUAGE TRANSLATIONS ====================
    const translations = {
      en: {
        login: 'Login',
        register: 'Register',
        logout: 'Logout',
        cart: 'Shopping Cart',
        checkout: 'Checkout',
        addToCart: 'Add to Cart',
        total: 'Total',
        emptyCart: 'Cart is empty',
        welcome: 'Welcome to Style Hub',
        pleaseLogin: 'Please login to start shopping',
        editProfile: 'Edit Profile',
        name: 'Name',
        email: 'Email',
        password: 'Password',
        continue: 'Continue',
        save: 'Save Changes',
        payNow: 'Pay Now',
        added: 'Added to cart!',
        removed: 'Removed from cart',
        loginSuccess: 'Login successful!',
        registerSuccess: 'Registration successful!',
        logoutSuccess: 'Logged out successfully',
        paymentSuccess: 'Payment successful!'
      },
      bn: {
        login: 'লগইন',
        register: 'রেজিস্টার',
        logout: 'লগআউট',
        cart: 'কার্ট',
        checkout: 'চেকআউট',
        addToCart: 'কার্টে যোগ করুন',
        total: 'মোট',
        emptyCart: 'কার্ট খালি',
        welcome: 'স্টাইল হাবে স্বাগতম',
        pleaseLogin: 'শপিং শুরু করতে লগইন করুন',
        editProfile: 'প্রোফাইল এডিট',
        name: 'নাম',
        email: 'ইমেইল',
        password: 'পাসওয়ার্ড',
        continue: 'চালিয়ে যান',
        save: 'সংরক্ষণ করুন',
        payNow: 'এখনই পে করুন',
        added: 'কার্টে যোগ হয়েছে!',
        removed: 'কার্ট থেকে সরানো হয়েছে',
        loginSuccess: 'লগইন সফল!',
        registerSuccess: 'রেজিস্ট্রেশন সফল!',
        logoutSuccess: 'লগআউট সফল',
        paymentSuccess: 'পেমেন্ট সফল!'
      },
      hi: {
        login: 'लॉगिन',
        register: 'रजिस्टर',
        logout: 'लॉगआउट',
        cart: 'कार्ट',
        checkout: 'चेकआउट',
        addToCart: 'कार्ट में जोड़ें',
        total: 'कुल',
        emptyCart: 'कार्ट खाली है',
        welcome: 'स्टाइल हब में स्वागत है',
        pleaseLogin: 'शॉपिंग शुरू करने के लिए लॉगिन करें',
        editProfile: 'प्रोफाइल संपादित करें',
        name: 'नाम',
        email: 'ईमेल',
        password: 'पासवर्ड',
        continue: 'जारी रखें',
        save: 'सहेजें',
        payNow: 'अब भुगतान करें',
        added: 'कार्ट में जोड़ा गया!',
        removed: 'कार्ट से हटाया गया',
        loginSuccess: 'लॉगिन सफल!',
        registerSuccess: 'रजिस्ट्रेशन सफल!',
        logoutSuccess: 'लॉगआउट सफल',
        paymentSuccess: 'भुगतान सफल!'
      }
    };

    // ==================== PRODUCTS DATA ====================
    const productsData = [
      {
        id: 1,
        name: 'Classic Oxford Shirt',
        price: 49.99,
        image: 'https://images.unsplash.com/photo-1598033129075-9c5f7c7f3c7a?w=400'
      },
      {
        id: 2,
        name: 'Slim Fit Jeans',
        price: 79.99,
        image: 'https://images.unsplash.com/photo-1541099649105-f69ad21f3246?w=400'
      },
      {
        id: 3,
        name: 'Running Sneakers',
        price: 89.99,
        image: 'https://images.unsplash.com/photo-1542291026-7eec264c27ff?w=400'
      },
      {
        id: 4,
        name: 'Leather Watch',
        price: 149.99,
        image: 'https://images.unsplash.com/photo-1524805444758-089113d48a6d?w=400'
      },
      {
        id: 5,
        name: 'Cotton T-Shirt',
        price: 24.99,
        image: 'https://images.unsplash.com/photo-1581655353564-df123a1eb820?w=400'
      },
      {
        id: 6,
        name: 'Summer Hat',
        price: 19.99,
        image: 'https://images.unsplash.com/photo-1514327605112-b887c0e61c0a?w=400'
      }
    ];

    // Generate more products
    for (let i = 7; i <= 20; i++) {
      const base = productsData[i % 6];
      products.push({
        id: i,
        name: `${base.name} ${i}`,
        price: base.price + (i % 20),
        image: base.image.replace('w=400', `w=400&sig=${i}`)
      });
    }

    // ==================== AUTH STATE OBSERVER ====================
    auth.onAuthStateChanged(async (user) => {
      if (user) {
        // Get user data from Firestore
        const doc = await db.collection('users').doc(user.uid).get();
        if (doc.exists) {
          currentUser = { uid: user.uid, ...doc.data() };
        } else {
          currentUser = {
            uid: user.uid,
            email: user.email,
            name: user.email.split('@')[0],
            bio: 'Fashion enthusiast',
            photo: 'https://images.unsplash.com/photo-1535713875002-d1d0cf377fde?w=200'
          };
          // Save to Firestore
          await db.collection('users').doc(user.uid).set(currentUser);
        }
        updateUIForLoggedInUser();
        showToast(translations[currentLang].loginSuccess);
      } else {
        currentUser = null;
        updateUIForLoggedOutUser();
      }
    });

    // ==================== UI UPDATE FUNCTIONS ====================
    function updateUIForLoggedInUser() {
      document.getElementById('authButtons').style.display = 'none';
      document.getElementById('userInfo').style.display = 'flex';
      document.getElementById('userName').textContent = currentUser.name;
      document.getElementById('profileName').textContent = currentUser.name;
      document.getElementById('profileBio').textContent = currentUser.bio || 'Fashion enthusiast';
      if (currentUser.photo) {
        document.getElementById('profilePic').src = currentUser.photo;
      }
    }

    function updateUIForLoggedOutUser() {
      document.getElementById('authButtons').style.display = 'flex';
      document.getElementById('userInfo').style.display = 'none';
      document.getElementById('profileName').textContent = translations[currentLang].welcome;
      document.getElementById('profileBio').textContent = translations[currentLang].pleaseLogin;
      document.getElementById('profilePic').src = 'https://images.unsplash.com/photo-1535713875002-d1d0cf377fde?w=200';
    }

    // ==================== AUTH FUNCTIONS ====================
    window.showAuthModal = function(type) {
      document.getElementById('authTitle').textContent = type === 'login' ? translations[currentLang].login : translations[currentLang].register;
      document.getElementById('nameField').style.display = type === 'register' ? 'block' : 'none';
      document.getElementById('authModal').classList.add('active');
    };

    window.closeModal = function(modalId) {
      document.getElementById(modalId).classList.remove('active');
    };

    window.handleAuth = async function(e) {
      e.preventDefault();
      
      const email = document.getElementById('authEmail').value;
      const password = document.getElementById('authPassword').value;
      const name = document.getElementById('authName').value;
      const title = document.getElementById('authTitle').textContent;

      try {
        if (title === translations[currentLang].register) {
          // Register
          const userCred = await auth.createUserWithEmailAndPassword(email, password);
          await db.collection('users').doc(userCred.user.uid).set({
            name: name || email.split('@')[0],
            email: email,
            bio: 'Fashion enthusiast',
            photo: 'https://images.unsplash.com/photo-1535713875002-d1d0cf377fde?w=200',
            createdAt: new Date().toISOString()
          });
          showToast(translations[currentLang].registerSuccess);
        } else {
          // Login
          await auth.signInWithEmailAndPassword(email, password);
        }
        closeModal('authModal');
        document.getElementById('authEmail').value = '';
        document.getElementById('authPassword').value = '';
        document.getElementById('authName').value = '';
      } catch (error) {
        showToast(error.message);
      }
    };

    window.logout = async function() {
      await auth.signOut();
      showToast(translations[currentLang].logoutSuccess);
    };

    // ==================== PROFILE FUNCTIONS ====================
    window.showEditProfile = function() {
      if (!currentUser) {
        showAuthModal('login');
        return;
      }
      document.getElementById('editName').value = currentUser.name || '';
      document.getElementById('editBio').value = currentUser.bio || '';
      document.getElementById('editPic').value = currentUser.photo || '';
      document.getElementById('editProfileModal').classList.add('active');
    };

    window.saveProfile = async function() {
      const name = document.getElementById('editName').value;
      const bio = document.getElementById('editBio').value;
      const photo = document.getElementById('editPic').value;

      if (!currentUser) return;

      await db.collection('users').doc(currentUser.uid).update({
        name: name,
        bio: bio,
        photo: photo
      });

      currentUser = { ...currentUser, name, bio, photo };
      document.getElementById('userName').textContent = name;
      document.getElementById('profileName').textContent = name;
      document.getElementById('profileBio').textContent = bio;
      document.getElementById('profilePic').src = photo;

      closeModal('editProfileModal');
      showToast('Profile updated!');
    };

    // ==================== COVER SLIDER ====================
    let currentCover = 0;
    let coverInterval = setInterval(() => {
      const slides = document.querySelectorAll('.cover-image');
      const dots = document.querySelectorAll('.dot');
      
      slides[currentCover].classList.remove('active');
      dots[currentCover].classList.remove('active');
      
      currentCover = (currentCover + 1) % slides.length;
      
      slides[currentCover].classList.add('active');
      dots[currentCover].classList.add('active');
    }, 5000);

    window.changeCover = function(index) {
      const slides = document.querySelectorAll('.cover-image');
      const dots = document.querySelectorAll('.dot');
      
      slides[currentCover].classList.remove('active');
      dots[currentCover].classList.remove('active');
      
      currentCover = index;
      
      slides[currentCover].classList.add('active');
      dots[currentCover].classList.add('active');
    };

    // ==================== CART FUNCTIONS ====================
    function displayProducts() {
      const grid = document.getElementById('productGrid');
      grid.innerHTML = products.map(p => `
        <div class="product-card">
          <img src="${p.image}" alt="${p.name}" class="product-image">
          <div class="product-info">
            <div class="product-name">${p.name}</div>
            <div class="product-price">$${p.price.toFixed(2)}</div>
            <button class="add-to-cart" onclick="addToCart(${p.id})">
              <i class="fas fa-cart-plus"></i> ${translations[currentLang].addToCart}
            </button>
          </div>
        </div>
      `).join('');
    }

    window.addToCart = function(productId) {
      if (!currentUser) {
        showToast('Please login first');
        showAuthModal('login');
        return;
      }

      const product = products.find(p => p.id === productId);
      const existing = cart.find(item => item.id === productId);
      
      if (existing) {
        existing.quantity++;
      } else {
        cart.push({ ...product, quantity: 1 });
      }
      
      updateCart();
      showToast(translations[currentLang].added);
    };

    function updateCart() {
      const count = cart.reduce((sum, item) => sum + item.quantity, 0);
      document.getElementById('cartCount').textContent = count;
      localStorage.setItem('cart', JSON.stringify(cart));
    }

    window.showCart = function() {
      const modal = document.getElementById('cartModal');
      const itemsDiv = document.getElementById('cartItems');
      const totalSpan = document.getElementById('cartTotal');

      if (cart.length === 0) {
        itemsDiv.innerHTML = `<p style="text-align:center;">${translations[currentLang].emptyCart}</p>`;
        totalSpan.textContent = `${translations[currentLang].total}: $0.00`;
      } else {
        itemsDiv.innerHTML = cart.map(item => `
          <div class="cart-item">
            <img src="${item.image}" alt="${item.name}">
            <div style="flex:1;">
              <div style="font-weight:600;">${item.name}</div>
              <div>$${item.price} x ${item.quantity}</div>
            </div>
            <div>
              <div>$${(item.price * item.quantity).toFixed(2)}</div>
              <button onclick="removeFromCart(${item.id})" style="color:var(--danger); background:none; border:none; cursor:pointer;">Remove</button>
            </div>
          </div>
        `).join('');

        const total = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
        totalSpan.textContent = `${translations[currentLang].total}: $${total.toFixed(2)}`;
      }

      modal.classList.add('active');
    };

    window.removeFromCart = function(productId) {
      cart = cart.filter(item => item.id !== productId);
      updateCart();
      showCart();
      showToast(translations[currentLang].removed);
    };

    // ==================== PAYMENT FUNCTIONS ====================
    let selectedPayment = 'bkash';

    window.checkout = function() {
      if (!currentUser) {
        showToast('Please login first');
        showAuthModal('login');
        return;
      }

      if (cart.length === 0) {
        showToast(translations[currentLang].emptyCart);
        return;
      }

      closeModal('cartModal');
      
      const total = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
      document.getElementById('orderSummary').innerHTML = `
        <div style="background:#f8fafc; padding:15px; border-radius:8px; margin:20px 0;">
          <h3 style="margin-bottom:10px;">Order Summary</h3>
          <div style="display:flex; justify-content:space-between;">
            <span>Total:</span>
            <span style="font-weight:700;">$${total.toFixed(2)}</span>
          </div>
        </div>
      `;

      document.querySelectorAll('.payment-method').forEach(el => el.classList.remove('selected'));
      document.querySelector('.payment-method').classList.add('selected');
      document.getElementById('paymentModal').classList.add('active');
    };

    window.selectPayment = function(method) {
      selectedPayment = method;
      document.querySelectorAll('.payment-method').forEach(el => el.classList.remove('selected'));
      event.currentTarget.classList.add('selected');
    };

    window.processPayment = function() {
      showToast(translations[currentLang].paymentSuccess);
      cart = [];
      updateCart();
      closePaymentModal();
    };

    window.closePaymentModal = function() {
      document.getElementById('paymentModal').classList.remove('active');
    };

    // ==================== LANGUAGE ====================
    window.changeLanguage = function(lang) {
      currentLang = lang;
      
      document.querySelectorAll('.lang-btn').forEach(btn => {
        btn.classList.toggle('active', btn.textContent.includes(lang.toUpperCase()) || 
                                      (lang === 'bn' && btn.textContent.includes('বাংলা')) ||
                                      (lang === 'hi' && btn.textContent.includes('हिंदी')));
      });

      document.getElementById('authTitle').textContent = translations[lang].login;
      
      if (!currentUser) {
        document.getElementById('profileName').textContent = translations[lang].welcome;
        document.getElementById('profileBio').textContent = translations[lang].pleaseLogin;
      }
      
      displayProducts();
    };

    // ==================== TOAST ====================
    function showToast(message) {
      const toast = document.getElementById('toast');
      toast.textContent = message;
      toast.style.display = 'block';
      setTimeout(() => {
        toast.style.display = 'none';
      }, 2000);
    }

    // ==================== INIT ====================
    displayProducts();
    updateCart();
    changeLanguage('en');

    // Close modals when clicking outside
    window.onclick = function(event) {
      if (event.target.classList.contains('modal')) {
        event.target.classList.remove('active');
      }
    };
  </script>
</body>
</html>
