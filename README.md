<!doctype html>
<html lang="en">
 <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>PartsniBon - Premium Computer Parts</title>
  <script src="/_sdk/element_sdk.js"></script>
  <script src="/_sdk/data_sdk.js"></script>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
        body {
            box-sizing: border-box;
        }
        
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Inter:wght@300;400;500;600&display=swap');
        
        .neon-glow {
            box-shadow: 0 0 20px rgba(34, 197, 94, 0.3), 0 0 40px rgba(34, 197, 94, 0.1);
        }
        
        .neon-text {
            text-shadow: 0 0 10px rgba(34, 197, 94, 0.8);
        }
        
        .cyber-grid {
            background-image: 
                linear-gradient(rgba(34, 197, 94, 0.1) 1px, transparent 1px),
                linear-gradient(90deg, rgba(34, 197, 94, 0.1) 1px, transparent 1px);
            background-size: 50px 50px;
        }
        
        .hover-glow:hover {
            box-shadow: 0 0 30px rgba(34, 197, 94, 0.4);
            transform: translateY(-2px);
            transition: all 0.3s ease;
        }
        
        .category-card {
            transition: all 0.3s ease;
        }
        
        .category-card:hover {
            background: linear-gradient(135deg, rgba(34, 197, 94, 0.1), rgba(0, 0, 0, 0.8));
            border-color: rgba(34, 197, 94, 0.6);
            transform: translateY(-4px);
        }
        
        .build-section {
            background: linear-gradient(135deg, rgba(34, 197, 94, 0.05), rgba(0, 0, 0, 0.9));
        }
        
        .product-card {
            transition: all 0.3s ease;
        }
        
        .product-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 0 40px rgba(34, 197, 94, 0.3);
        }
        
        .stat-number {
            font-family: 'Orbitron', sans-serif;
        }

        .toast {
            position: fixed;
            top: 20px;
            right: 20px;
            background: #22c55e;
            color: #000;
            padding: 16px 24px;
            border-radius: 8px;
            font-weight: bold;
            z-index: 1000;
            animation: slideIn 0.3s ease;
        }

        @keyframes slideIn {
            from { transform: translateX(400px); opacity: 0; }
            to { transform: translateX(0); opacity: 1; }
        }

        .spinner {
            border: 3px solid rgba(34, 197, 94, 0.3);
            border-top: 3px solid #22c55e;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            animation: spin 0.8s linear infinite;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
    </style>
  <style>@view-transition { navigation: auto; }</style>
 </head>
 <body class="bg-black text-white" style="font-family: 'Inter', sans-serif; margin: 0; padding: 0; width: 100%; min-height: 100%;">
  <div style="width: 100%;"><!-- Header -->
   <header class="border-b border-gray-800 bg-black/90 backdrop-blur-sm sticky top-0 z-50">
    <div class="max-w-7xl mx-auto px-6 py-4">
     <div class="flex items-center justify-between"><a href="#" onclick="window.scrollTo({top: 0, behavior: 'smooth'}); return false;" class="flex items-center space-x-2 cursor-pointer">
       <div class="w-8 h-8 bg-green-500 rounded-lg neon-glow flex items-center justify-center"><span class="text-black font-bold text-lg">P</span>
       </div><h1 id="site-name" class="text-2xl font-bold neon-text" style="font-family: 'Orbitron', sans-serif;">PartsniBon</h1></a>
      <nav class="hidden md:flex space-x-8"><a href="#products" class="hover:text-green-400 transition-colors">Products</a> <a href="#build" class="hover:text-green-400 transition-colors">Build PC</a> <a href="#wishlist" class="hover:text-green-400 transition-colors">Wishlist</a> <a href="#contact" class="hover:text-green-400 transition-colors">Contact</a>
      </nav>
      <div class="flex items-center space-x-4"><button class="p-2 hover:bg-gray-800 rounded-lg transition-colors">
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewbox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
        </svg></button> <button onclick="scrollToWishlist()" class="p-2 hover:bg-gray-800 rounded-lg transition-colors relative">
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewbox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z" />
        </svg><span id="wishlist-count" class="absolute -top-1 -right-1 bg-green-500 text-black text-xs rounded-full w-5 h-5 flex items-center justify-center">0</span> </button> <!-- User Account Section --> <button id="sign-in-btn" onclick="showSignInModal()" class="px-4 py-2 bg-green-500 text-black font-semibold rounded-lg hover:bg-green-400 transition-colors"> Sign In </button>
       <div id="user-profile-btn" style="display: none;" class="flex items-center space-x-2 cursor-pointer hover:opacity-80 transition-opacity" onclick="toggleUserMenu()">
        <div class="w-8 h-8 bg-green-500 rounded-full flex items-center justify-center"><span id="user-initial" class="text-black font-bold text-sm">U</span>
        </div><span id="user-email-display" class="text-sm hidden md:block font-medium"></span>
       </div>
      </div>
     </div>
    </div>
   </header><!-- Sign In Modal -->
   <div id="signin-modal" style="display: none;" class="fixed inset-0 bg-black/80 backdrop-blur-sm z-50 flex items-center justify-center p-4">
    <div class="bg-gray-900 border-2 border-green-500 rounded-xl p-8 max-w-md w-full">
     <div class="text-center mb-6">
      <div class="w-16 h-16 bg-green-500 rounded-full flex items-center justify-center mx-auto mb-4 neon-glow">
       <svg class="w-8 h-8 text-black" fill="none" stroke="currentColor" viewbox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z" />
       </svg>
      </div>
      <h2 class="text-3xl font-bold mb-2 neon-text" style="font-family: 'Orbitron', sans-serif;">Welcome Back</h2>
      <p class="text-gray-400">Enter your email to access your account</p>
     </div>
     <form id="signin-form" onsubmit="handleSignIn(event)" class="space-y-4">
      <div><label for="signin-email" class="block text-sm text-gray-400 mb-2">Email Address</label> <input type="email" id="signin-email" required class="w-full bg-gray-800 border border-gray-700 rounded-lg px-4 py-3 text-white focus:border-green-500 outline-none transition-colors" placeholder="your@email.com">
      </div><button type="submit" id="signin-submit-btn" class="w-full py-3 bg-green-500 text-black font-bold rounded-lg hover:bg-green-400 transition-colors flex items-center justify-center hover-glow"> <span id="signin-submit-text">Sign In</span> <span id="signin-submit-spinner" style="display: none;" class="spinner ml-2"></span> </button>
     </form><button onclick="hideSignInModal()" class="w-full mt-4 py-2 text-gray-400 hover:text-white transition-colors"> Cancel </button>
     <div class="mt-6 pt-6 border-t border-gray-800 text-center text-sm text-gray-400">
      <p>🔒 No password required. Your email is stored securely and only used to personalize your experience.</p>
     </div>
    </div>
   </div><!-- User Menu Dropdown -->
   <div id="user-menu" style="display: none;" class="fixed top-20 right-6 bg-gray-900 border-2 border-gray-800 rounded-xl p-4 shadow-2xl z-50 min-w-64">
    <div class="mb-4 pb-4 border-b border-gray-800">
     <div class="text-sm text-gray-400 mb-1">
      Signed in as
     </div>
     <div id="user-menu-email" class="font-semibold text-green-400"></div>
    </div><button onclick="handleSignOut()" class="w-full py-2 bg-red-500/20 border border-red-500 text-red-400 rounded-lg hover:bg-red-500/30 transition-colors"> Sign Out </button>
   </div><!-- Purchase Modal -->
   <div id="purchase-modal" style="display: none;" class="fixed inset-0 bg-black/80 backdrop-blur-sm z-50 flex items-center justify-center p-4">
    <div class="bg-gray-900 border-2 border-green-500 rounded-xl p-8 max-w-2xl w-full max-h-[90%] overflow-y-auto">
     <div class="text-center mb-6">
      <div class="w-16 h-16 bg-green-500 rounded-full flex items-center justify-center mx-auto mb-4 neon-glow">
       <svg class="w-8 h-8 text-black" fill="none" stroke="currentColor" viewbox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z" />
       </svg>
      </div>
      <h2 class="text-3xl font-bold mb-2 neon-text" style="font-family: 'Orbitron', sans-serif;">Complete Your Purchase</h2>
      <p class="text-gray-400">Secure checkout for your order</p>
     </div>
     <div class="bg-gray-800 border border-gray-700 rounded-lg p-4 mb-6">
      <div class="text-sm text-gray-400 mb-2">
       Product
      </div>
      <div id="purchase-product-name" class="text-xl font-bold mb-2"></div>
      <div class="flex items-center justify-between">
       <div>
        <div class="text-sm text-gray-400">
         Unit Price
        </div>
        <div id="purchase-product-price" class="text-2xl font-bold text-green-400"></div>
       </div>
       <div><label for="purchase-quantity" class="block text-sm text-gray-400 mb-2">Quantity</label> <input type="number" id="purchase-quantity" min="1" max="10" value="1" onchange="updateTotalPrice()" class="w-20 bg-gray-700 border border-gray-600 rounded-lg px-3 py-2 text-white text-center focus:border-green-500 outline-none">
       </div>
      </div>
      <div class="mt-4 pt-4 border-t border-gray-700">
       <div class="flex justify-between items-center"><span class="text-lg font-semibold">Total Amount:</span> <span id="purchase-total-price" class="text-3xl font-bold text-green-400"></span>
       </div>
      </div>
     </div>
     <form id="purchase-form" onsubmit="handlePurchase(event)" class="space-y-4">
      <div><label for="purchase-email" class="block text-sm text-gray-400 mb-2">Email Address</label> <input type="email" id="purchase-email" required class="w-full bg-gray-800 border border-gray-700 rounded-lg px-4 py-3 text-white focus:border-green-500 outline-none transition-colors" placeholder="your@email.com">
      </div>
      <div><label for="purchase-phone" class="block text-sm text-gray-400 mb-2">Phone Number</label> <input type="tel" id="purchase-phone" required class="w-full bg-gray-800 border border-gray-700 rounded-lg px-4 py-3 text-white focus:border-green-500 outline-none transition-colors" placeholder="+63 XXX XXX XXXX">
      </div>
      <div><label for="purchase-address" class="block text-sm text-gray-400 mb-2">Shipping Address</label> <textarea id="purchase-address" required rows="3" class="w-full bg-gray-800 border border-gray-700 rounded-lg px-4 py-3 text-white focus:border-green-500 outline-none resize-none transition-colors" placeholder="Complete delivery address"></textarea>
      </div>
      <div><label for="purchase-payment" class="block text-sm text-gray-400 mb-2">Payment Method</label> <select id="purchase-payment" required class="w-full bg-gray-800 border border-gray-700 rounded-lg px-4 py-3 text-white focus:border-green-500 outline-none transition-colors"> <option value="">Select payment method</option> <option value="cash_on_delivery">Cash on Delivery (COD)</option> <option value="bank_transfer">Bank Transfer</option> <option value="gcash">GCash</option> <option value="paymaya">PayMaya</option> </select>
      </div>
      <div class="flex gap-3"><button type="button" onclick="hidePurchaseModal()" class="flex-1 py-3 border-2 border-gray-700 text-gray-300 rounded-lg hover:bg-gray-800 transition-colors"> Cancel </button> <button type="submit" id="purchase-submit-btn" class="flex-1 py-3 bg-green-500 text-black font-bold rounded-lg hover:bg-green-400 transition-colors flex items-center justify-center hover-glow"> <span id="purchase-submit-text">Complete Purchase</span> <span id="purchase-submit-spinner" style="display: none;" class="spinner ml-2"></span> </button>
      </div>
     </form>
     <div class="mt-6 pt-6 border-t border-gray-800 text-center text-sm text-gray-400">
      <p>🔒 Your order details will be saved securely. You'll receive an email receipt confirmation.</p>
     </div>
    </div>
   </div><!-- Hero Section -->
   <section class="relative flex items-center cyber-grid" style="min-height: 600px;">
    <div class="max-w-7xl mx-auto px-6 py-20 w-full">
     <div class="grid md:grid-cols-2 gap-12 items-center">
      <div>
       <div class="inline-block px-4 py-2 bg-green-500/10 border border-green-500/30 rounded-full mb-6"><span class="text-green-400 text-sm font-semibold">🚀 New RTX 5000 Series Available</span>
       </div>
       <h2 id="hero-title" class="text-5xl md:text-6xl font-bold mb-6 neon-text" style="font-family: 'Orbitron', sans-serif; line-height: 1.1;">Build Your Dream PC</h2>
       <p id="hero-subtitle" class="text-xl text-gray-300 mb-8 leading-relaxed">Premium components for ultimate performance. Experience the power of next-gen gaming and productivity.</p>
       <div class="flex flex-wrap gap-4"><button id="cta-button" class="px-8 py-4 bg-green-500 text-black font-bold rounded-lg hover-glow hover:bg-green-400 transition-all"> Explore Products </button> <button onclick="document.getElementById('build').scrollIntoView({behavior: 'smooth'})" class="px-8 py-4 border-2 border-green-500 text-green-400 font-semibold rounded-lg hover:bg-green-500/10 transition-all"> Build Your PC </button>
       </div>
      </div><!-- 3D Card Display -->
      <div class="relative">
       <div class="relative bg-gradient-to-br from-gray-900 to-black border-2 border-green-500/30 rounded-2xl p-8 neon-glow">
        <div class="absolute top-4 right-4 bg-green-500 text-black px-3 py-1 rounded-full text-sm font-bold">
         HOT
        </div>
        <svg class="w-full h-48 mb-6" viewbox="0 0 200 100" fill="none"><rect x="20" y="20" width="160" height="60" rx="4" fill="#22c55e" opacity="0.1" /> <rect x="30" y="30" width="50" height="40" rx="2" fill="#22c55e" opacity="0.3" /> <rect x="90" y="30" width="80" height="20" rx="2" fill="#22c55e" opacity="0.5" /> <circle cx="150" cy="50" r="15" fill="#22c55e" /> <path d="M140 35 L160 35 L150 55 Z" fill="#000000" />
        </svg>
        <h3 class="text-2xl font-bold mb-2" style="font-family: 'Orbitron', sans-serif;">RTX 5090 Ti</h3>
        <p class="text-gray-400 mb-4">Ultimate 4K Gaming Performance</p>
        <div class="flex items-center justify-between"><span class="text-3xl font-bold text-green-400">₱89,999</span> <button onclick="addToWishlist('RTX 5090 Ti', '₱89,999')" class="px-6 py-2 bg-green-500 text-black rounded-lg hover:bg-green-400 transition-colors"> Add to Wishlist </button>
        </div>
       </div>
      </div>
     </div>
    </div>
   </section><!-- Stats Section -->
   <section class="py-16 bg-gray-900/50 border-y border-gray-800">
    <div class="max-w-7xl mx-auto px-6">
     <div class="grid grid-cols-2 gap-8 max-w-2xl mx-auto">
      <div class="text-center">
       <div class="stat-number text-4xl md:text-5xl font-bold text-green-400 mb-2">
        99.9%
       </div>
       <div class="text-gray-400">
        Uptime
       </div>
      </div>
      <div class="text-center">
       <div class="stat-number text-4xl md:text-5xl font-bold text-green-400 mb-2">
        24/7
       </div>
       <div class="text-gray-400">
        Support
       </div>
      </div>
     </div>
    </div>
   </section><!-- Categories Section -->
   <section id="products" class="py-20">
    <div class="max-w-7xl mx-auto px-6">
     <div class="text-center mb-16">
      <h2 class="text-4xl md:text-5xl font-bold mb-4" style="font-family: 'Orbitron', sans-serif;">Shop by Category</h2>
      <p class="text-xl text-gray-400">Find the perfect components for your build</p>
     </div>
     <div class="grid md:grid-cols-3 gap-6">
      <div onclick="document.getElementById('graphics-cards').scrollIntoView({behavior: 'smooth'})" class="category-card bg-gray-900 border-2 border-gray-800 rounded-xl p-6 cursor-pointer">
       <div class="text-4xl mb-4">
        🎮
       </div>
       <h3 class="text-2xl font-bold mb-2">Graphics Cards</h3>
       <p class="text-gray-400 mb-4">Latest NVIDIA &amp; AMD GPUs</p><span class="text-green-400 font-semibold">Shop Now →</span>
      </div>
      <div onclick="document.getElementById('processors').scrollIntoView({behavior: 'smooth'})" class="category-card bg-gray-900 border-2 border-gray-800 rounded-xl p-6 cursor-pointer">
       <div class="text-4xl mb-4">
        ⚡
       </div>
       <h3 class="text-2xl font-bold mb-2">Processors</h3>
       <p class="text-gray-400 mb-4">Intel &amp; AMD CPUs</p><span class="text-green-400 font-semibold">Shop Now →</span>
      </div>
      <div onclick="document.getElementById('memory-storage').scrollIntoView({behavior: 'smooth'})" class="category-card bg-gray-900 border-2 border-gray-800 rounded-xl p-6 cursor-pointer">
       <div class="text-4xl mb-4">
        💾
       </div>
       <h3 class="text-2xl font-bold mb-2">Memory &amp; Storage</h3>
       <p class="text-gray-400 mb-4">RAM, SSDs, HDDs</p><span class="text-green-400 font-semibold">Shop Now →</span>
      </div>
      <div onclick="document.getElementById('motherboards').scrollIntoView({behavior: 'smooth'})" class="category-card bg-gray-900 border-2 border-gray-800 rounded-xl p-6 cursor-pointer">
       <div class="text-4xl mb-4">
        🔧
       </div>
       <h3 class="text-2xl font-bold mb-2">Motherboards</h3>
       <p class="text-gray-400 mb-4">ATX, Micro-ATX, Mini-ITX</p><span class="text-green-400 font-semibold">Shop Now →</span>
      </div>
      <div onclick="document.getElementById('cooling').scrollIntoView({behavior: 'smooth'})" class="category-card bg-gray-900 border-2 border-gray-800 rounded-xl p-6 cursor-pointer">
       <div class="text-4xl mb-4">
        ❄️
       </div>
       <h3 class="text-2xl font-bold mb-2">Cooling</h3>
       <p class="text-gray-400 mb-4">Air &amp; Liquid Coolers</p><span class="text-green-400 font-semibold">Shop Now →</span>
      </div>
      <div onclick="document.getElementById('power-supplies').scrollIntoView({behavior: 'smooth'})" class="category-card bg-gray-900 border-2 border-gray-800 rounded-xl p-6 cursor-pointer">
       <div class="text-4xl mb-4">
        🔌
       </div>
       <h3 class="text-2xl font-bold mb-2">Power Supplies</h3>
       <p class="text-gray-400 mb-4">80+ Certified PSUs</p><span class="text-green-400 font-semibold">Shop Now →</span>
      </div>
     </div>
    </div>
   </section><!-- Graphics Cards Section -->
   <section id="graphics-cards" class="py-20 bg-gray-900/30">
    <div class="max-w-7xl mx-auto px-6">
     <div class="text-center mb-16">
      <div class="text-4xl mb-4">
       🎮
      </div>
      <h2 class="text-4xl md:text-5xl font-bold mb-4" style="font-family: 'Orbitron', sans-serif;">Graphics Cards</h2>
      <p class="text-xl text-gray-400">Ultimate gaming performance from NVIDIA and AMD</p>
     </div>
     <div class="grid md:grid-cols-3 gap-8">
      <div class="product-card bg-black border-2 border-gray-800 rounded-xl overflow-hidden">
       <div class="bg-gradient-to-br from-green-500/20 to-black p-8 flex items-center justify-center" style="height: 200px;">
        <svg class="w-full h-full" viewbox="0 0 200 150" fill="none"><!-- GPU Card Body --> <rect x="20" y="40" width="160" height="70" rx="4" fill="#1a1a1a" stroke="#22c55e" stroke-width="2" /> <!-- Cooling Fans --> <circle cx="60" cy="75" r="20" fill="#22c55e" opacity="0.3" /> <circle cx="60" cy="75" r="15" fill="#22c55e" opacity="0.5" /> <path d="M55 75 L65 75 M60 70 L60 80" stroke="#000" stroke-width="2" /> <circle cx="100" cy="75" r="20" fill="#22c55e" opacity="0.3" /> <circle cx="100" cy="75" r="15" fill="#22c55e" opacity="0.5" /> <path d="M95 75 L105 75 M100 70 L100 80" stroke="#000" stroke-width="2" /> <circle cx="140" cy="75" r="20" fill="#22c55e" opacity="0.3" /> <circle cx="140" cy="75" r="15" fill="#22c55e" opacity="0.5" /> <path d="M135 75 L145 75 M140 70 L140 80" stroke="#000" stroke-width="2" /> <!-- PCB --> <rect x="25" y="110" width="150" height="10" rx="1" fill="#22c55e" opacity="0.4" /> <!-- Backplate --> <rect x="20" y="35" width="160" height="5" rx="2" fill="#22c55e" /> <!-- NVIDIA Logo --> <text x="100" y="55" font-family="Arial, sans-serif" font-size="12" font-weight="bold" fill="#22c55e" text-anchor="middle">
          RTX
         </text>
        </svg>
       </div>
       <div class="p-6">
        <div class="text-sm text-green-400 mb-2">
         NVIDIA GeForce
        </div>
        <h3 class="text-xl font-bold mb-2">RTX 5090 Ti</h3>
        <p class="text-gray-400 text-sm mb-4">24GB GDDR7 • 4K 240Hz</p>
        <div class="flex items-center justify-between mb-3"><span class="text-2xl font-bold text-green-400">₱89,999</span>
        </div>
        <div class="flex gap-2"><button onclick="addToWishlist('RTX 5090 Ti', '₱89,999')" class="flex-1 px-3 py-2 border-2 border-green-500 text-green-400 rounded-lg hover:bg-green-500/10 transition-colors text-sm"> ♡ Wishlist </button> <button onclick="buyProduct('RTX 5090 Ti', '₱89,999')" class="flex-1 px-3 py-2 bg-green-500 text-black font-semibold rounded-lg hover:bg-green-400 transition-colors text-sm"> Buy Now </button>
        </div>
       </div>
      </div>
      <div class="product-card bg-black border-2 border-gray-800 rounded-xl overflow-hidden">
       <div class="bg-gradient-to-br from-green-500/20 to-black p-8 flex items-center justify-center" style="height: 200px;">
        <svg class="w-full h-full" viewbox="0 0 200 150" fill="none"><!-- GPU Card Body --> <rect x="25" y="45" width="150" height="60" rx="4" fill="#1a1a1a" stroke="#22c55e" stroke-width="2" /> <!-- Dual Cooling Fans --> <circle cx="70" cy="75" r="22" fill="#22c55e" opacity="0.3" /> <circle cx="70" cy="75" r="17" fill="#22c55e" opacity="0.5" /> <path d="M65 75 L75 75 M70 68 L70 82" stroke="#000" stroke-width="2" /> <circle cx="130" cy="75" r="22" fill="#22c55e" opacity="0.3" /> <circle cx="130" cy="75" r="17" fill="#22c55e" opacity="0.5" /> <path d="M125 75 L135 75 M130 68 L130 82" stroke="#000" stroke-width="2" /> <!-- PCB --> <rect x="30" y="105" width="140" height="8" rx="1" fill="#22c55e" opacity="0.4" /> <!-- Backplate --> <rect x="25" y="40" width="150" height="5" rx="2" fill="#22c55e" /> <!-- RTX Logo --> <text x="100" y="55" font-family="Arial, sans-serif" font-size="11" font-weight="bold" fill="#22c55e" text-anchor="middle">
          RTX 5080
         </text>
        </svg>
       </div>
       <div class="p-6">
        <div class="text-sm text-green-400 mb-2">
         NVIDIA GeForce
        </div>
        <h3 class="text-xl font-bold mb-2">RTX 5080</h3>
        <p class="text-gray-400 text-sm mb-4">16GB GDDR7 • Ray Tracing</p>
        <div class="flex items-center justify-between mb-3"><span class="text-2xl font-bold text-green-400">₱64,999</span>
        </div>
        <div class="flex gap-2"><button onclick="addToWishlist('RTX 5080', '₱64,999')" class="flex-1 px-3 py-2 border-2 border-green-500 text-green-400 rounded-lg hover:bg-green-500/10 transition-colors text-sm"> ♡ Wishlist </button> <button onclick="buyProduct('RTX 5080', '₱64,999')" class="flex-1 px-3 py-2 bg-green-500 text-black font-semibold rounded-lg hover:bg-green-400 transition-colors text-sm"> Buy Now </button>
        </div>
       </div>
      </div>
      <div class="product-card bg-black border-2 border-gray-800 rounded-xl overflow-hidden">
       <div class="bg-gradient-to-br from-red-500/20 to-black p-8 flex items-center justify-center" style="height: 200px;">
        <svg class="w-full h-full" viewbox="0 0 200 150" fill="none"><!-- GPU Card Body --> <rect x="20" y="40" width="160" height="70" rx="4" fill="#1a1a1a" stroke="#ef4444" stroke-width="2" /> <!-- Triple Cooling Fans (AMD Style) --> <circle cx="60" cy="75" r="20" fill="#ef4444" opacity="0.3" /> <circle cx="60" cy="75" r="15" fill="#ef4444" opacity="0.5" /> <path d="M55 75 L65 75 M60 70 L60 80" stroke="#000" stroke-width="2" /> <circle cx="100" cy="75" r="20" fill="#ef4444" opacity="0.3" /> <circle cx="100" cy="75" r="15" fill="#ef4444" opacity="0.5" /> <path d="M95 75 L105 75 M100 70 L100 80" stroke="#000" stroke-width="2" /> <circle cx="140" cy="75" r="20" fill="#ef4444" opacity="0.3" /> <circle cx="140" cy="75" r="15" fill="#ef4444" opacity="0.5" /> <path d="M135 75 L145 75 M140 70 L140 80" stroke="#000" stroke-width="2" /> <!-- PCB --> <rect x="25" y="110" width="150" height="10" rx="1" fill="#ef4444" opacity="0.4" /> <!-- AMD Radeon Stripe --> <rect x="20" y="35" width="160" height="5" rx="2" fill="#ef4444" /> <!-- AMD Logo --> <text x="100" y="55" font-family="Arial, sans-serif" font-size="12" font-weight="bold" fill="#ef4444" text-anchor="middle">
          RADEON
         </text>
        </svg>
       </div>
       <div class="p-6">
        <div class="text-sm text-red-400 mb-2">
         AMD Radeon
        </div>
        <h3 class="text-xl font-bold mb-2">RX 8900 XT</h3>
        <p class="text-gray-400 text-sm mb-4">24GB GDDR6 • FSR 3.0</p>
        <div class="flex items-center justify-between mb-3"><span class="text-2xl font-bold text-green-400">₱79,999</span>
        </div>
        <div class="flex gap-2"><button onclick="addToWishlist('RX 8900 XT', '₱79,999')" class="flex-1 px-3 py-2 border-2 border-green-500 text-green-400 rounded-lg hover:bg-green-500/10 transition-colors text-sm"> ♡ Wishlist </button> <button onclick="buyProduct('RX 8900 XT', '₱79,999')" class="flex-1 px-3 py-2 bg-green-500 text-black font-semibold rounded-lg hover:bg-green-400 transition-colors text-sm"> Buy Now </button>
        </div>
       </div>
      </div>
     </div>
    </div>
   </section><!-- Processors Section -->
   <section id="processors" class="py-20">
    <div class="max-w-7xl mx-auto px-6">
     <div class="text-center mb-16">
      <div class="text-4xl mb-4">
       ⚡
      </div>
      <h2 class="text-4xl md:text-5xl font-bold mb-4" style="font-family: 'Orbitron', sans-serif;">Processors</h2>
      <p class="text-xl text-gray-400">High-performance CPUs for every build</p>
     </div>
     <div class="grid md:grid-cols-3 gap-8">
      <div class="product-card bg-black border-2 border-gray-800 rounded-xl overflow-hidden">
       <div class="bg-gradient-to-br from-blue-500/20 to-black p-8 flex items-center justify-center" style="height: 200px;">
        <svg class="w-full h-full" viewbox="0 0 150 150" fill="none"><!-- CPU Package --> <rect x="30" y="30" width="90" height="90" rx="4" fill="#1a1a1a" stroke="#3b82f6" stroke-width="2" /> <!-- CPU Die (center) --> <rect x="50" y="50" width="50" height="50" rx="2" fill="#3b82f6" opacity="0.6" /> <!-- Intel Logo Area --> <rect x="55" y="55" width="40" height="40" rx="2" fill="#3b82f6" opacity="0.8" /> <text x="75" y="78" font-family="Arial, sans-serif" font-size="10" font-weight="bold" fill="#fff" text-anchor="middle">
          INTEL
         </text> <text x="75" y="90" font-family="Arial, sans-serif" font-size="8" fill="#fff" text-anchor="middle">
          CORE i9
         </text> <!-- Contact Pads (golden pins simulation) --> <rect x="35" y="35" width="3" height="3" fill="#fbbf24" opacity="0.8" /> <rect x="42" y="35" width="3" height="3" fill="#fbbf24" opacity="0.8" /> <rect x="35" y="42" width="3" height="3" fill="#fbbf24" opacity="0.8" /> <rect x="112" y="35" width="3" height="3" fill="#fbbf24" opacity="0.8" /> <rect x="112" y="42" width="3" height="3" fill="#fbbf24" opacity="0.8" /> <rect x="35" y="112" width="3" height="3" fill="#fbbf24" opacity="0.8" /> <rect x="42" y="112" width="3" height="3" fill="#fbbf24" opacity="0.8" /> <rect x="112" y="112" width="3" height="3" fill="#fbbf24" opacity="0.8" />
        </svg>
       </div>
       <div class="p-6">
        <div class="text-sm text-blue-400 mb-2">
         Intel Core
        </div>
        <h3 class="text-xl font-bold mb-2">i9-14900K</h3>
        <p class="text-gray-400 text-sm mb-4">24 Cores • 5.8GHz Turbo</p>
        <div class="flex items-center justify-between mb-3"><span class="text-2xl font-bold text-green-400">₱29,499</span>
        </div>
        <div class="flex gap-2"><button onclick="addToWishlist('i9-14900K', '₱29,499')" class="flex-1 px-3 py-2 border-2 border-green-500 text-green-400 rounded-lg hover:bg-green-500/10 transition-colors text-sm"> ♡ Wishlist </button> <button onclick="buyProduct('i9-14900K', '₱29,499')" class="flex-1 px-3 py-2 bg-green-500 text-black font-semibold rounded-lg hover:bg-green-400 transition-colors text-sm"> Buy Now </button>
        </div>
       </div>
      </div>
      <div class="product-card bg-black border-2 border-gray-800 rounded-xl overflow-hidden">
       <div class="bg-gradient-to-br from-orange-500/20 to-black p-8 flex items-center justify-center" style="height: 200px;">
        <svg class="w-full h-full" viewbox="0 0 150 150" fill="none"><!-- CPU Package --> <rect x="30" y="30" width="90" height="90" rx="4" fill="#1a1a1a" stroke="#f97316" stroke-width="2" /> <!-- CPU Die with AMD Orange --> <rect x="50" y="50" width="50" height="50" rx="2" fill="#f97316" opacity="0.6" /> <!-- AMD Ryzen Logo Area --> <rect x="55" y="55" width="40" height="40" rx="2" fill="#f97316" opacity="0.8" /> <text x="75" y="75" font-family="Arial, sans-serif" font-size="9" font-weight="bold" fill="#000" text-anchor="middle">
          AMD
         </text> <text x="75" y="87" font-family="Arial, sans-serif" font-size="8" fill="#000" text-anchor="middle">
          RYZEN 9
         </text> <text x="75" y="97" font-family="Arial, sans-serif" font-size="6" fill="#000" text-anchor="middle">
          3D V-CACHE
         </text> <!-- Contact Pads --> <rect x="35" y="35" width="3" height="3" fill="#fbbf24" opacity="0.8" /> <rect x="42" y="35" width="3" height="3" fill="#fbbf24" opacity="0.8" /> <rect x="35" y="42" width="3" height="3" fill="#fbbf24" opacity="0.8" /> <rect x="112" y="35" width="3" height="3" fill="#fbbf24" opacity="0.8" /> <rect x="112" y="42" width="3" height="3" fill="#fbbf24" opacity="0.8" /> <rect x="35" y="112" width="3" height="3" fill="#fbbf24" opacity="0.8" /> <rect x="42" y="112" width="3" height="3" fill="#fbbf24" opacity="0.8" /> <rect x="112" y="112" width="3" height="3" fill="#fbbf24" opacity="0.8" />
        </svg>
       </div>
       <div class="p-6">
        <div class="text-sm text-orange-400 mb-2">
         AMD Ryzen
        </div>
        <h3 class="text-xl font-bold mb-2">9 7950X3D</h3>
        <p class="text-gray-400 text-sm mb-4">16 Cores • 3D V-Cache</p>
        <div class="flex items-center justify-between mb-3"><span class="text-2xl font-bold text-green-400">₱34,999</span>
        </div>
        <div class="flex gap-2"><button onclick="addToWishlist('Ryzen 9 7950X3D', '₱34,999')" class="flex-1 px-3 py-2 border-2 border-green-500 text-green-400 rounded-lg hover:bg-green-500/10 transition-colors text-sm"> ♡ Wishlist </button> <button onclick="buyProduct('Ryzen 9 7950X3D', '₱34,999')" class="flex-1 px-3 py-2 bg-green-500 text-black font-semibold rounded-lg hover:bg-green-400 transition-colors text-sm"> Buy Now </button>
        </div>
       </div>
      </div>
      <div class="product-card bg-black border-2 border-gray-800 rounded-xl overflow-hidden">
       <div class="bg-gradient-to-br from-blue-500/20 to-black p-8 flex items-center justify-center" style="height: 200px;">
        <svg class="w-full h-full" viewbox="0 0 150 150" fill="none"><!-- CPU Package --> <rect x="30" y="30" width="90" height="90" rx="4" fill="#1a1a1a" stroke="#3b82f6" stroke-width="2" /> <!-- CPU Die --> <rect x="50" y="50" width="50" height="50" rx="2" fill="#3b82f6" opacity="0.6" /> <!-- Intel Logo --> <rect x="55" y="55" width="40" height="40" rx="2" fill="#3b82f6" opacity="0.8" /> <text x="75" y="78" font-family="Arial, sans-serif" font-size="10" font-weight="bold" fill="#fff" text-anchor="middle">
          INTEL
         </text> <text x="75" y="90" font-family="Arial, sans-serif" font-size="8" fill="#fff" text-anchor="middle">
          CORE i7
         </text> <!-- Contact Pads --> <rect x="35" y="35" width="3" height="3" fill="#fbbf24" opacity="0.8" /> <rect x="42" y="35" width="3" height="3" fill="#fbbf24" opacity="0.8" /> <rect x="35" y="42" width="3" height="3" fill="#fbbf24" opacity="0.8" /> <rect x="112" y="35" width="3" height="3" fill="#fbbf24" opacity="0.8" /> <rect x="112" y="42" width="3" height="3" fill="#fbbf24" opacity="0.8" /> <rect x="35" y="112" width="3" height="3" fill="#fbbf24" opacity="0.8" /> <rect x="42" y="112" width="3" height="3" fill="#fbbf24" opacity="0.8" /> <rect x="112" y="112" width="3" height="3" fill="#fbbf24" opacity="0.8" />
        </svg>
       </div>
       <div class="p-6">
        <div class="text-sm text-blue-400 mb-2">
         Intel Core
        </div>
        <h3 class="text-xl font-bold mb-2">i7-14700K</h3>
        <p class="text-gray-400 text-sm mb-4">20 Cores • 5.6GHz Turbo</p>
        <div class="flex items-center justify-between mb-3"><span class="text-2xl font-bold text-green-400">₱22,999</span>
        </div>
        <div class="flex gap-2"><button onclick="addToWishlist('i7-14700K', '₱22,999')" class="flex-1 px-3 py-2 border-2 border-green-500 text-green-400 rounded-lg hover:bg-green-500/10 transition-colors text-sm"> ♡ Wishlist </button> <button onclick="buyProduct('i7-14700K', '₱22,999')" class="flex-1 px-3 py-2 bg-green-500 text-black font-semibold rounded-lg hover:bg-green-400 transition-colors text-sm"> Buy Now </button>
        </div>
       </div>
      </div>
     </div>
    </div>
   </section><!-- Memory & Storage Section -->
   <section id="memory-storage" class="py-20 bg-gray-900/30">
    <div class="max-w-7xl mx-auto px-6">
     <div class="text-center mb-16">
      <div class="text-4xl mb-4">
       💾
      </div>
      <h2 class="text-4xl md:text-5xl font-bold mb-4" style="font-family: 'Orbitron', sans-serif;">Memory &amp; Storage</h2>
      <p class="text-xl text-gray-400">Fast RAM and lightning-speed storage</p>
     </div>
     <div class="grid md:grid-cols-3 gap-8">
      <div class="product-card bg-black border-2 border-gray-800 rounded-xl overflow-hidden">
       <div class="bg-gradient-to-br from-purple-500/20 to-black p-8 flex items-center justify-center" style="height: 200px;">
        <svg class="w-full h-full" viewbox="0 0 180 150" fill="none"><!-- Dual RAM Sticks --> <!-- First RAM stick --> <rect x="35" y="30" width="35" height="90" rx="2" fill="#1a1a1a" stroke="#a855f7" stroke-width="2" /> <rect x="40" y="35" width="25" height="80" rx="1" fill="#a855f7" opacity="0.6" /> <!-- RGB lighting on top --> <rect x="38" y="32" width="29" height="6" rx="1" fill="#a855f7" /> <circle cx="45" cy="35" r="1.5" fill="#ff00ff" /> <circle cx="52" cy="35" r="1.5" fill="#00ffff" /> <circle cx="59" cy="35" r="1.5" fill="#ff00ff" /> <!-- Memory chips --> <rect x="42" y="45" width="21" height="8" fill="#000" opacity="0.3" /> <rect x="42" y="58" width="21" height="8" fill="#000" opacity="0.3" /> <rect x="42" y="71" width="21" height="8" fill="#000" opacity="0.3" /> <rect x="42" y="84" width="21" height="8" fill="#000" opacity="0.3" /> <rect x="42" y="97" width="21" height="8" fill="#000" opacity="0.3" /> <!-- Second RAM stick --> <rect x="80" y="30" width="35" height="90" rx="2" fill="#1a1a1a" stroke="#a855f7" stroke-width="2" /> <rect x="85" y="35" width="25" height="80" rx="1" fill="#a855f7" opacity="0.6" /> <!-- RGB lighting on top --> <rect x="83" y="32" width="29" height="6" rx="1" fill="#a855f7" /> <circle cx="90" cy="35" r="1.5" fill="#00ffff" /> <circle cx="97" cy="35" r="1.5" fill="#ff00ff" /> <circle cx="104" cy="35" r="1.5" fill="#00ffff" /> <!-- Memory chips --> <rect x="87" y="45" width="21" height="8" fill="#000" opacity="0.3" /> <rect x="87" y="58" width="21" height="8" fill="#000" opacity="0.3" /> <rect x="87" y="71" width="21" height="8" fill="#000" opacity="0.3" /> <rect x="87" y="84" width="21" height="8" fill="#000" opacity="0.3" /> <rect x="87" y="97" width="21" height="8" fill="#000" opacity="0.3" /> <!-- Brand label --> <text x="75" y="135" font-family="Arial, sans-serif" font-size="8" font-weight="bold" fill="#a855f7" text-anchor="middle">
          CORSAIR
         </text>
        </svg>
       </div>
       <div class="p-6">
        <div class="text-sm text-purple-400 mb-2">
         Corsair Vengeance
        </div>
        <h3 class="text-xl font-bold mb-2">DDR5 64GB</h3>
        <p class="text-gray-400 text-sm mb-4">6000MHz • RGB • CL36</p>
        <div class="flex items-center justify-between"><span class="text-2xl font-bold text-green-400">₱12,499</span> <button onclick="addToWishlist('DDR5 64GB', '₱12,499')" class="px-4 py-2 bg-green-500 text-black rounded-lg hover:bg-green-400 transition-colors">Add</button>
        </div>
       </div>
      </div>
      <div class="product-card bg-black border-2 border-gray-800 rounded-xl overflow-hidden">
       <div class="bg-gradient-to-br from-red-500/20 to-black p-8 flex items-center justify-center" style="height: 200px;">
        <svg class="w-full h-full" viewbox="0 0 180 150" fill="none"><!-- M.2 SSD --> <rect x="30" y="55" width="120" height="40" rx="3" fill="#1a1a1a" stroke="#ef4444" stroke-width="2" /> <!-- PCB --> <rect x="35" y="60" width="110" height="30" rx="2" fill="#ef4444" opacity="0.4" /> <!-- NAND Chips --> <rect x="40" y="65" width="20" height="20" rx="1" fill="#000" opacity="0.5" /> <rect x="65" y="65" width="20" height="20" rx="1" fill="#000" opacity="0.5" /> <rect x="90" y="65" width="20" height="20" rx="1" fill="#000" opacity="0.5" /> <rect x="115" y="65" width="20" height="20" rx="1" fill="#000" opacity="0.5" /> <!-- Controller chip (larger) --> <rect x="48" y="68" width="15" height="14" rx="1" fill="#ef4444" opacity="0.8" /> <!-- M.2 connector notch --> <rect x="32" y="70" width="4" height="10" fill="#ef4444" /> <!-- Label --> <text x="90" y="77" font-family="Arial, sans-serif" font-size="8" font-weight="bold" fill="#ef4444" text-anchor="middle">
          990 PRO
         </text> <text x="90" y="125" font-family="Arial, sans-serif" font-size="9" font-weight="bold" fill="#ef4444" text-anchor="middle">
          SAMSUNG
         </text>
        </svg>
       </div>
       <div class="p-6">
        <div class="text-sm text-red-400 mb-2">
         Samsung 990 PRO
        </div>
        <h3 class="text-xl font-bold mb-2">NVMe SSD 2TB</h3>
        <p class="text-gray-400 text-sm mb-4">7450MB/s • PCIe 4.0</p>
        <div class="flex items-center justify-between"><span class="text-2xl font-bold text-green-400">₱8,999</span> <button onclick="addToWishlist('Samsung 990 PRO 2TB', '₱8,999')" class="px-4 py-2 bg-green-500 text-black rounded-lg hover:bg-green-400 transition-colors">Add</button>
        </div>
       </div>
      </div>
      <div class="product-card bg-black border-2 border-gray-800 rounded-xl overflow-hidden">
       <div class="bg-gradient-to-br from-purple-500/20 to-black p-8 flex items-center justify-center" style="height: 200px;">
        <svg class="w-full h-full" viewbox="0 0 180 150" fill="none"><!-- Dual RAM Sticks (G.Skill) --> <!-- First RAM stick --> <rect x="35" y="30" width="35" height="90" rx="2" fill="#1a1a1a" stroke="#a855f7" stroke-width="2" /> <rect x="40" y="35" width="25" height="80" rx="1" fill="#a855f7" opacity="0.6" /> <!-- Trident heatsink design (triangular top) --> <path d="M38 32 L52.5 20 L67 32 Z" fill="#a855f7" stroke="#a855f7" stroke-width="1" /> <!-- RGB on heatsink --> <circle cx="48" cy="28" r="1.5" fill="#ff00ff" /> <circle cx="57" cy="28" r="1.5" fill="#00ffff" /> <!-- Memory chips --> <rect x="42" y="45" width="21" height="8" fill="#000" opacity="0.3" /> <rect x="42" y="58" width="21" height="8" fill="#000" opacity="0.3" /> <rect x="42" y="71" width="21" height="8" fill="#000" opacity="0.3" /> <rect x="42" y="84" width="21" height="8" fill="#000" opacity="0.3" /> <rect x="42" y="97" width="21" height="8" fill="#000" opacity="0.3" /> <!-- Second RAM stick --> <rect x="80" y="30" width="35" height="90" rx="2" fill="#1a1a1a" stroke="#a855f7" stroke-width="2" /> <rect x="85" y="35" width="25" height="80" rx="1" fill="#a855f7" opacity="0.6" /> <!-- Trident heatsink design --> <path d="M83 32 L97.5 20 L112 32 Z" fill="#a855f7" stroke="#a855f7" stroke-width="1" /> <!-- RGB on heatsink --> <circle cx="93" cy="28" r="1.5" fill="#00ffff" /> <circle cx="102" cy="28" r="1.5" fill="#ff00ff" /> <!-- Memory chips --> <rect x="87" y="45" width="21" height="8" fill="#000" opacity="0.3" /> <rect x="87" y="58" width="21" height="8" fill="#000" opacity="0.3" /> <rect x="87" y="71" width="21" height="8" fill="#000" opacity="0.3" /> <rect x="87" y="84" width="21" height="8" fill="#000" opacity="0.3" /> <rect x="87" y="97" width="21" height="8" fill="#000" opacity="0.3" /> <!-- Brand label --> <text x="75" y="135" font-family="Arial, sans-serif" font-size="8" font-weight="bold" fill="#a855f7" text-anchor="middle">
          G.SKILL
         </text>
        </svg>
       </div>
       <div class="p-6">
        <div class="text-sm text-purple-400 mb-2">
         G.Skill Trident Z5
        </div>
        <h3 class="text-xl font-bold mb-2">DDR5 32GB</h3>
        <p class="text-gray-400 text-sm mb-4">6400MHz • RGB • CL32</p>
        <div class="flex items-center justify-between"><span class="text-2xl font-bold text-green-400">₱7,499</span> <button onclick="addToWishlist('G.Skill DDR5 32GB', '₱7,499')" class="px-4 py-2 bg-green-500 text-black rounded-lg hover:bg-green-400 transition-colors">Add</button>
        </div>
       </div>
      </div>
     </div>
    </div>
   </section><!-- Motherboards Section -->
   <section id="motherboards" class="py-20">
    <div class="max-w-7xl mx-auto px-6">
     <div class="text-center mb-16">
      <div class="text-4xl mb-4">
       🔧
      </div>
      <h2 class="text-4xl md:text-5xl font-bold mb-4" style="font-family: 'Orbitron', sans-serif;">Motherboards</h2>
      <p class="text-xl text-gray-400">The foundation of your build</p>
     </div>
     <div class="grid md:grid-cols-3 gap-8">
      <div class="product-card bg-black border-2 border-gray-800 rounded-xl overflow-hidden">
       <div class="bg-gradient-to-br from-yellow-500/20 to-black p-8 flex items-center justify-center" style="height: 200px;">
        <svg class="w-32 h-32" viewbox="0 0 100 100" fill="none"><rect x="15" y="20" width="70" height="60" rx="2" fill="#eab308" opacity="0.3" /> <circle cx="30" cy="35" r="4" fill="#eab308" /> <circle cx="70" cy="35" r="4" fill="#eab308" /> <rect x="35" y="45" width="30" height="20" rx="2" fill="#eab308" />
        </svg>
       </div>
       <div class="p-6">
        <div class="text-sm text-yellow-400 mb-2">
         ASUS ROG
        </div>
        <h3 class="text-xl font-bold mb-2">Z790 HERO</h3>
        <p class="text-gray-400 text-sm mb-4">ATX • DDR5 • WiFi 7</p>
        <div class="flex items-center justify-between"><span class="text-2xl font-bold text-green-400">₱24,999</span> <button onclick="addToWishlist('ASUS Z790 HERO', '₱24,999')" class="px-4 py-2 bg-green-500 text-black rounded-lg hover:bg-green-400 transition-colors">Add</button>
        </div>
       </div>
      </div>
      <div class="product-card bg-black border-2 border-gray-800 rounded-xl overflow-hidden">
       <div class="bg-gradient-to-br from-red-500/20 to-black p-8 flex items-center justify-center" style="height: 200px;">
        <svg class="w-32 h-32" viewbox="0 0 100 100" fill="none"><rect x="15" y="20" width="70" height="60" rx="2" fill="#ef4444" opacity="0.3" /> <circle cx="30" cy="35" r="4" fill="#ef4444" /> <circle cx="70" cy="35" r="4" fill="#ef4444" /> <rect x="35" y="45" width="30" height="20" rx="2" fill="#ef4444" />
        </svg>
       </div>
       <div class="p-6">
        <div class="text-sm text-red-400 mb-2">
         MSI MAG
        </div>
        <h3 class="text-xl font-bold mb-2">X670E TOMAHAWK</h3>
        <p class="text-gray-400 text-sm mb-4">ATX • AM5 • PCIe 5.0</p>
        <div class="flex items-center justify-between"><span class="text-2xl font-bold text-green-400">₱18,999</span> <button onclick="addToWishlist('MSI X670E TOMAHAWK', '₱18,999')" class="px-4 py-2 bg-green-500 text-black rounded-lg hover:bg-green-400 transition-colors">Add</button>
        </div>
       </div>
      </div>
      <div class="product-card bg-black border-2 border-gray-800 rounded-xl overflow-hidden">
       <div class="bg-gradient-to-br from-blue-500/20 to-black p-8 flex items-center justify-center" style="height: 200px;">
        <svg class="w-32 h-32" viewbox="0 0 100 100" fill="none"><rect x="15" y="20" width="70" height="60" rx="2" fill="#3b82f6" opacity="0.3" /> <circle cx="30" cy="35" r="4" fill="#3b82f6" /> <circle cx="70" cy="35" r="4" fill="#3b82f6" /> <rect x="35" y="45" width="30" height="20" rx="2" fill="#3b82f6" />
        </svg>
       </div>
       <div class="p-6">
        <div class="text-sm text-blue-400 mb-2">
         Gigabyte AORUS
        </div>
        <h3 class="text-xl font-bold mb-2">B650 ELITE AX</h3>
        <p class="text-gray-400 text-sm mb-4">ATX • AM5 • WiFi 6E</p>
        <div class="flex items-center justify-between"><span class="text-2xl font-bold text-green-400">₱12,999</span> <button onclick="addToWishlist('Gigabyte B650 ELITE', '₱12,999')" class="px-4 py-2 bg-green-500 text-black rounded-lg hover:bg-green-400 transition-colors">Add</button>
        </div>
       </div>
      </div>
     </div>
    </div>
   </section><!-- Cooling Section -->
   <section id="cooling" class="py-20 bg-gray-900/30">
    <div class="max-w-7xl mx-auto px-6">
     <div class="text-center mb-16">
      <div class="text-4xl mb-4">
       ❄️
      </div>
      <h2 class="text-4xl md:text-5xl font-bold mb-4" style="font-family: 'Orbitron', sans-serif;">Cooling Solutions</h2>
      <p class="text-xl text-gray-400">Keep your system running cool and quiet</p>
     </div>
     <div class="grid md:grid-cols-3 gap-8">
      <div class="product-card bg-black border-2 border-gray-800 rounded-xl overflow-hidden">
       <div class="bg-gradient-to-br from-cyan-500/20 to-black p-8 flex items-center justify-center" style="height: 200px;">
        <svg class="w-32 h-32" viewbox="0 0 100 100" fill="none"><circle cx="50" cy="50" r="30" fill="#06b6d4" opacity="0.3" /> <circle cx="50" cy="50" r="20" fill="#06b6d4" /> <path d="M50 30 L50 70 M30 50 L70 50" stroke="#000000" stroke-width="3" />
        </svg>
       </div>
       <div class="p-6">
        <div class="text-sm text-cyan-400 mb-2">
         NZXT Kraken
        </div>
        <h3 class="text-xl font-bold mb-2">Z73 RGB 360mm</h3>
        <p class="text-gray-400 text-sm mb-4">AIO • LCD Display • RGB</p>
        <div class="flex items-center justify-between"><span class="text-2xl font-bold text-green-400">₱14,999</span> <button onclick="addToWishlist('NZXT Kraken Z73', '₱14,999')" class="px-4 py-2 bg-green-500 text-black rounded-lg hover:bg-green-400 transition-colors">Add</button>
        </div>
       </div>
      </div>
      <div class="product-card bg-black border-2 border-gray-800 rounded-xl overflow-hidden">
       <div class="bg-gradient-to-br from-gray-500/20 to-black p-8 flex items-center justify-center" style="height: 200px;">
        <svg class="w-32 h-32" viewbox="0 0 100 100" fill="none"><rect x="30" y="20" width="40" height="60" rx="2" fill="#6b7280" opacity="0.3" /> <rect x="35" y="25" width="30" height="50" rx="1" fill="#6b7280" /> <circle cx="50" cy="50" r="10" fill="#000000" />
        </svg>
       </div>
       <div class="p-6">
        <div class="text-sm text-gray-400 mb-2">
         Noctua NH-D15
        </div>
        <h3 class="text-xl font-bold mb-2">Dual Tower</h3>
        <p class="text-gray-400 text-sm mb-4">Air Cooler • Ultra Quiet</p>
        <div class="flex items-center justify-between"><span class="text-2xl font-bold text-green-400">₱5,999</span> <button onclick="addToWishlist('Noctua NH-D15', '₱5,999')" class="px-4 py-2 bg-green-500 text-black rounded-lg hover:bg-green-400 transition-colors">Add</button>
        </div>
       </div>
      </div>
      <div class="product-card bg-black border-2 border-gray-800 rounded-xl overflow-hidden">
       <div class="bg-gradient-to-br from-purple-500/20 to-black p-8 flex items-center justify-center" style="height: 200px;">
        <svg class="w-32 h-32" viewbox="0 0 100 100" fill="none"><circle cx="50" cy="50" r="30" fill="#a855f7" opacity="0.3" /> <circle cx="50" cy="50" r="20" fill="#a855f7" /> <path d="M50 30 L50 70 M30 50 L70 50" stroke="#000000" stroke-width="3" />
        </svg>
       </div>
       <div class="p-6">
        <div class="text-sm text-purple-400 mb-2">
         Corsair iCUE
        </div>
        <h3 class="text-xl font-bold mb-2">H150i ELITE 360mm</h3>
        <p class="text-gray-400 text-sm mb-4">AIO • RGB • LCD</p>
        <div class="flex items-center justify-between"><span class="text-2xl font-bold text-green-400">₱11,999</span> <button onclick="addToWishlist('Corsair H150i ELITE', '₱11,999')" class="px-4 py-2 bg-green-500 text-black rounded-lg hover:bg-green-400 transition-colors">Add</button>
        </div>
       </div>
      </div>
     </div>
    </div>
   </section><!-- Power Supplies Section -->
   <section id="power-supplies" class="py-20">
    <div class="max-w-7xl mx-auto px-6">
     <div class="text-center mb-16">
      <div class="text-4xl mb-4">
       🔌
      </div>
      <h2 class="text-4xl md:text-5xl font-bold mb-4" style="font-family: 'Orbitron', sans-serif;">Power Supplies</h2>
      <p class="text-xl text-gray-400">Reliable power for stable performance</p>
     </div>
     <div class="grid md:grid-cols-3 gap-8">
      <div class="product-card bg-black border-2 border-gray-800 rounded-xl overflow-hidden">
       <div class="bg-gradient-to-br from-yellow-500/20 to-black p-8 flex items-center justify-center" style="height: 200px;">
        <svg class="w-32 h-32" viewbox="0 0 100 100" fill="none"><rect x="25" y="30" width="50" height="40" rx="2" fill="#eab308" opacity="0.3" /> <rect x="30" y="35" width="40" height="30" rx="1" fill="#eab308" /> <path d="M45 45 L50 55 L55 45" stroke="#000000" stroke-width="2" fill="none" />
        </svg>
       </div>
       <div class="p-6">
        <div class="text-sm text-yellow-400 mb-2">
         Corsair RM1000x
        </div>
        <h3 class="text-xl font-bold mb-2">1000W 80+ Gold</h3>
        <p class="text-gray-400 text-sm mb-4">Modular • Silent Fan</p>
        <div class="flex items-center justify-between"><span class="text-2xl font-bold text-green-400">₱9,999</span> <button onclick="addToWishlist('Corsair RM1000x', '₱9,999')" class="px-4 py-2 bg-green-500 text-black rounded-lg hover:bg-green-400 transition-colors">Add</button>
        </div>
       </div>
      </div>
      <div class="product-card bg-black border-2 border-gray-800 rounded-xl overflow-hidden">
       <div class="bg-gradient-to-br from-platinum-500/20 to-black p-8 flex items-center justify-center" style="height: 200px;">
        <svg class="w-32 h-32" viewbox="0 0 100 100" fill="none"><rect x="25" y="30" width="50" height="40" rx="2" fill="#e5e7eb" opacity="0.3" /> <rect x="30" y="35" width="40" height="30" rx="1" fill="#e5e7eb" /> <path d="M45 45 L50 55 L55 45" stroke="#000000" stroke-width="2" fill="none" />
        </svg>
       </div>
       <div class="p-6">
        <div class="text-sm text-gray-300 mb-2">
         Seasonic PRIME
        </div>
        <h3 class="text-xl font-bold mb-2">850W 80+ Platinum</h3>
        <p class="text-gray-400 text-sm mb-4">Fully Modular • 12yr</p>
        <div class="flex items-center justify-between"><span class="text-2xl font-bold text-green-400">₱8,499</span> <button onclick="addToWishlist('Seasonic PRIME 850W', '₱8,499')" class="px-4 py-2 bg-green-500 text-black rounded-lg hover:bg-green-400 transition-colors">Add</button>
        </div>
       </div>
      </div>
      <div class="product-card bg-black border-2 border-gray-800 rounded-xl overflow-hidden">
       <div class="bg-gradient-to-br from-yellow-500/20 to-black p-8 flex items-center justify-center" style="height: 200px;">
        <svg class="w-32 h-32" viewbox="0 0 100 100" fill="none"><rect x="25" y="30" width="50" height="40" rx="2" fill="#eab308" opacity="0.3" /> <rect x="30" y="35" width="40" height="30" rx="1" fill="#eab308" /> <path d="M45 45 L50 55 L55 45" stroke="#000000" stroke-width="2" fill="none" />
        </svg>
       </div>
       <div class="p-6">
        <div class="text-sm text-yellow-400 mb-2">
         EVGA SuperNOVA
        </div>
        <h3 class="text-xl font-bold mb-2">750W 80+ Gold</h3>
        <p class="text-gray-400 text-sm mb-4">Modular • ECO Mode</p>
        <div class="flex items-center justify-between"><span class="text-2xl font-bold text-green-400">₱6,999</span> <button onclick="addToWishlist('EVGA SuperNOVA 750W', '₱6,999')" class="px-4 py-2 bg-green-500 text-black rounded-lg hover:bg-green-400 transition-colors">Add</button>
        </div>
       </div>
      </div>
     </div>
    </div>
   </section><!-- Build Your PC Section -->
   <section id="build" class="py-20 build-section">
    <div class="max-w-7xl mx-auto px-6">
     <div class="grid md:grid-cols-2 gap-12 items-center">
      <div>
       <h2 class="text-4xl md:text-5xl font-bold mb-6" style="font-family: 'Orbitron', sans-serif;">Build Your Perfect PC</h2>
       <p class="text-xl text-gray-300 mb-8">Use our interactive PC builder to create your dream setup. Get compatibility checks, power calculations, and expert recommendations.</p>
       <ul class="space-y-4 mb-8">
        <li class="flex items-start"><span class="text-green-400 text-2xl mr-3">✓</span> <span class="text-lg">Automatic compatibility checking</span></li>
        <li class="flex items-start"><span class="text-green-400 text-2xl mr-3">✓</span> <span class="text-lg">Real-time price updates</span></li>
        <li class="flex items-start"><span class="text-green-400 text-2xl mr-3">✓</span> <span class="text-lg">Expert build recommendations</span></li>
       </ul>
      </div>
      <div class="bg-gray-900 border-2 border-gray-800 rounded-xl p-8">
       <h3 class="text-2xl font-bold mb-6">Get PC Build Recommendations</h3>
       <form id="build-form" class="space-y-4" onsubmit="handleBuildRequest(event)">
        <div><label for="build-email" class="block text-sm text-gray-400 mb-2">Email</label> <input type="email" id="build-email" required class="w-full bg-gray-800 border border-gray-700 rounded-lg px-4 py-3 text-white focus:border-green-500 outline-none" placeholder="your@email.com">
        </div>
        <div><label for="build-budget" class="block text-sm text-gray-400 mb-2">Budget: ₱<span id="budget-display">100000</span></label> <input type="range" id="build-budget" min="25000" max="250000" value="100000" step="5000" class="w-full" style="accent-color: #22c55e;" oninput="updateBudgetDisplay(this.value)">
         <div class="flex justify-between text-sm mt-2"><span>₱25,000</span> <span>₱250,000</span>
         </div>
        </div><!-- Budget Recommendation Preview -->
        <div id="budget-recommendation" class="bg-gray-800 border border-gray-700 rounded-lg p-4">
         <div class="text-sm text-gray-400 mb-2">
          Recommended Build:
         </div>
         <div id="recommendation-content" class="text-sm space-y-1"><!-- Dynamically populated -->
         </div>
        </div><button type="submit" id="build-submit-btn" class="w-full py-3 bg-green-500 text-black font-bold rounded-lg hover:bg-green-400 transition-colors flex items-center justify-center"> <span id="build-submit-text">Send Recommendations to Email</span> <span id="build-submit-spinner" style="display: none;" class="spinner ml-2"></span> </button>
       </form>
       <div id="build-success" style="display: none;" class="mt-4 p-4 bg-green-500/20 border border-green-500 rounded-lg text-green-400">
        ✓ Recommendations sent to your email!
       </div>
      </div>
     </div>
    </div>
   </section><!-- Wishlist Section -->
   <section id="wishlist" class="py-20 bg-gray-900/30">
    <div class="max-w-7xl mx-auto px-6">
     <div class="text-center mb-16">
      <h2 class="text-4xl md:text-5xl font-bold mb-4" style="font-family: 'Orbitron', sans-serif;">Your Wishlist</h2>
      <p class="text-xl text-gray-400">Save your favorite components</p>
     </div>
     <div id="wishlist-container" class="grid md:grid-cols-3 gap-6">
      <div class="col-span-3 text-center text-gray-500 py-12">
       No items in wishlist yet. Add products to see them here!
      </div>
     </div>
    </div>
   </section><!-- Contact Section -->
   <section id="contact" class="py-20">
    <div class="max-w-4xl mx-auto px-6">
     <div class="text-center mb-12">
      <h2 class="text-4xl font-bold mb-4" style="font-family: 'Orbitron', sans-serif;">Get In Touch</h2>
      <p class="text-xl text-gray-300">Have questions? We're here to help!</p>
     </div>
     <div class="bg-gray-900 border-2 border-gray-800 rounded-xl p-8">
      <form id="contact-form" onsubmit="handleContactForm(event)" class="space-y-6">
       <div><label for="contact-email" class="block text-sm text-gray-400 mb-2">Email</label> <input type="email" id="contact-email" required class="w-full bg-gray-800 border border-gray-700 rounded-lg px-4 py-3 text-white focus:border-green-500 outline-none" placeholder="your@email.com">
       </div>
       <div><label for="contact-message" class="block text-sm text-gray-400 mb-2">Message</label> <textarea id="contact-message" required rows="5" class="w-full bg-gray-800 border border-gray-700 rounded-lg px-4 py-3 text-white focus:border-green-500 outline-none resize-none" placeholder="Tell us how we can help..."></textarea>
       </div><button type="submit" id="contact-submit-btn" class="w-full py-3 bg-green-500 text-black font-bold rounded-lg hover:bg-green-400 transition-colors flex items-center justify-center"> <span id="contact-submit-text">Send Message</span> <span id="contact-submit-spinner" style="display: none;" class="spinner ml-2"></span> </button>
      </form>
      <div id="contact-success" style="display: none;" class="mt-4 p-4 bg-green-500/20 border border-green-500 rounded-lg text-green-400">
       ✓ Message sent! We'll get back to you soon.
      </div>
     </div>
    </div>
   </section><!-- Newsletter Section -->
   <section class="py-20 bg-gradient-to-r from-green-500/10 to-blue-500/10">
    <div class="max-w-4xl mx-auto px-6 text-center">
     <h2 class="text-4xl font-bold mb-4" style="font-family: 'Orbitron', sans-serif;">Stay Updated</h2>
     <p class="text-xl text-gray-300 mb-8">Get the latest deals, new product launches, and tech news delivered to your inbox.</p>
     <form id="newsletter-form" class="flex flex-col sm:flex-row gap-4 max-w-xl mx-auto" onsubmit="handleNewsletterSubmit(event)"><input type="email" id="newsletter-email" placeholder="Enter your email" required class="flex-1 px-6 py-4 bg-gray-900 border-2 border-gray-800 rounded-lg focus:border-green-500 outline-none transition-colors"> <button type="submit" id="newsletter-submit-btn" class="px-8 py-4 bg-green-500 text-black font-bold rounded-lg hover-glow hover:bg-green-400 transition-all flex items-center justify-center"> <span id="newsletter-submit-text">Subscribe</span> <span id="newsletter-submit-spinner" style="display: none;" class="spinner ml-2"></span> </button>
     </form>
     <div id="newsletter-message" style="display: none;" class="mt-4 text-green-400 font-semibold">
      ✓ Thank you for subscribing!
     </div>
    </div>
   </section><!-- Footer -->
   <footer class="bg-black border-t border-gray-800 py-12">
    <div class="max-w-7xl mx-auto px-6">
     <div class="grid md:grid-cols-4 gap-8 mb-8">
      <div>
       <div class="flex items-center space-x-2 mb-4">
        <div class="w-8 h-8 bg-green-500 rounded-lg neon-glow flex items-center justify-center"><span class="text-black font-bold text-lg">P</span>
        </div>
        <h3 class="text-xl font-bold" style="font-family: 'Orbitron', sans-serif;">PartsniBon</h3>
       </div>
       <p class="text-gray-400 text-sm">Your trusted source for premium computer components.</p>
      </div>
      <div>
       <h4 class="font-bold mb-4">Shop</h4>
       <ul class="space-y-2 text-gray-400">
        <li><a href="#graphics-cards" class="hover:text-green-400 transition-colors">Graphics Cards</a></li>
        <li><a href="#processors" class="hover:text-green-400 transition-colors">Processors</a></li>
        <li><a href="#memory-storage" class="hover:text-green-400 transition-colors">Memory &amp; Storage</a></li>
        <li><a href="#motherboards" class="hover:text-green-400 transition-colors">Motherboards</a></li>
       </ul>
      </div>
      <div>
       <h4 class="font-bold mb-4">More Categories</h4>
       <ul class="space-y-2 text-gray-400">
        <li><a href="#cooling" class="hover:text-green-400 transition-colors">Cooling</a></li>
        <li><a href="#power-supplies" class="hover:text-green-400 transition-colors">Power Supplies</a></li>
        <li><a href="#contact" class="hover:text-green-400 transition-colors">Contact Us</a></li>
       </ul>
      </div>
     </div>
     <div class="border-t border-gray-800 pt-8 flex flex-col md:flex-row justify-between items-center">
      <p class="text-gray-400 text-sm mb-4 md:mb-0">© 2024 PartsniBon. All rights reserved.</p>
      <div class="flex space-x-6"><a href="#" class="text-gray-400 hover:text-green-400 transition-colors">Privacy</a> <a href="#" class="text-gray-400 hover:text-green-400 transition-colors">Terms</a> <a href="#" class="text-gray-400 hover:text-green-400 transition-colors">Cookies</a>
      </div>
     </div>
    </div>
   </footer>
  </div>
  <script>
        let allData = [];
        let currentUserEmail = null;
        let currentPurchaseProduct = null;
        let currentPurchasePrice = null;

        const defaultConfig = {
            site_name: "PartsniBon",
            hero_title: "Build Your Dream PC",
            hero_subtitle: "Premium components for ultimate performance. Experience the power of next-gen gaming and productivity.",
            cta_button: "Explore Products",
            background_color: "#000000",
            accent_color: "#22c55e",
            text_color: "#ffffff",
            surface_color: "#111827",
            button_color: "#22c55e",
            font_family: "Inter",
            font_size: 16
        };

        // Data SDK Handler
        const dataHandler = {
            onDataChanged(data) {
                allData = data;
                renderWishlist(data);
            }
        };

        // Initialize Data SDK
        (async () => {
            if (window.dataSdk) {
                const initResult = await window.dataSdk.init(dataHandler);
                if (!initResult.isOk) {
                    console.error("Failed to initialize data SDK");
                }
            }
            
            // Check for saved user session
            const savedEmail = localStorage.getItem('userEmail');
            if (savedEmail) {
                setUserSession(savedEmail);
            }
        })();

        // Authentication Functions
        function showSignInModal() {
            document.getElementById('signin-modal').style.display = 'flex';
            document.getElementById('signin-email').focus();
        }

        function hideSignInModal() {
            document.getElementById('signin-modal').style.display = 'none';
            document.getElementById('signin-form').reset();
        }

        async function handleSignIn(event) {
            event.preventDefault();
            
            const button = document.getElementById('signin-submit-btn');
            const buttonText = document.getElementById('signin-submit-text');
            const spinner = document.getElementById('signin-submit-spinner');

            button.disabled = true;
            buttonText.style.display = 'none';
            spinner.style.display = 'inline-block';

            const email = document.getElementById('signin-email').value;

            // Simulate authentication delay
            await new Promise(resolve => setTimeout(resolve, 800));

            // Save user session
            setUserSession(email);
            
            button.disabled = false;
            buttonText.style.display = 'inline';
            spinner.style.display = 'none';

            hideSignInModal();
            showToast(`✓ Welcome, ${email.split('@')[0]}!`);

            // Store in Data SDK for analytics
            if (window.dataSdk && allData.length < 999) {
                await window.dataSdk.create({
                    type: 'user_session',
                    email: email,
                    timestamp: new Date().toISOString()
                });
            }
        }

        function setUserSession(email) {
            currentUserEmail = email;
            localStorage.setItem('userEmail', email);
            
            // Update UI
            document.getElementById('sign-in-btn').style.display = 'none';
            document.getElementById('user-profile-btn').style.display = 'flex';
            
            const initial = email.charAt(0).toUpperCase();
            document.getElementById('user-initial').textContent = initial;
            document.getElementById('user-email-display').textContent = email.split('@')[0];
            document.getElementById('user-menu-email').textContent = email;
        }

        function toggleUserMenu() {
            const menu = document.getElementById('user-menu');
            menu.style.display = menu.style.display === 'none' ? 'block' : 'none';
        }

        function handleSignOut() {
            currentUserEmail = null;
            localStorage.removeItem('userEmail');
            
            // Update UI
            document.getElementById('sign-in-btn').style.display = 'block';
            document.getElementById('user-profile-btn').style.display = 'none';
            document.getElementById('user-menu').style.display = 'none';
            
            showToast('✓ Signed out successfully');
        }

        // Close menu when clicking outside
        document.addEventListener('click', function(event) {
            const menu = document.getElementById('user-menu');
            const profileBtn = document.getElementById('user-profile-btn');
            
            if (menu.style.display === 'block' && 
                !menu.contains(event.target) && 
                !profileBtn.contains(event.target)) {
                menu.style.display = 'none';
            }
        });

        // Close modal when clicking outside
        document.getElementById('signin-modal').addEventListener('click', function(event) {
            if (event.target === this) {
                hideSignInModal();
            }
        });

        function showToast(message) {
            const toast = document.createElement('div');
            toast.className = 'toast';
            toast.textContent = message;
            document.body.appendChild(toast);
            setTimeout(() => toast.remove(), 3000);
        }

        function buyProduct(productName, productPrice) {
            currentPurchaseProduct = productName;
            currentPurchasePrice = productPrice;
            
            document.getElementById('purchase-product-name').textContent = productName;
            document.getElementById('purchase-product-price').textContent = productPrice;
            document.getElementById('purchase-quantity').value = 1;
            
            if (currentUserEmail) {
                document.getElementById('purchase-email').value = currentUserEmail;
            }
            
            updateTotalPrice();
            document.getElementById('purchase-modal').style.display = 'flex';
        }

        function hidePurchaseModal() {
            document.getElementById('purchase-modal').style.display = 'none';
            document.getElementById('purchase-form').reset();
            currentPurchaseProduct = null;
            currentPurchasePrice = null;
        }

        function updateTotalPrice() {
            const quantity = parseInt(document.getElementById('purchase-quantity').value) || 1;
            const priceStr = currentPurchasePrice.replace(/[₱,]/g, '');
            const unitPrice = parseFloat(priceStr);
            const total = unitPrice * quantity;
            
            document.getElementById('purchase-total-price').textContent = `₱${total.toLocaleString()}`;
        }

        async function handlePurchase(event) {
            event.preventDefault();
            
            const button = document.getElementById('purchase-submit-btn');
            const buttonText = document.getElementById('purchase-submit-text');
            const spinner = document.getElementById('purchase-submit-spinner');

            const allRecords = allData;
            if (allRecords.length >= 999) {
                showToast('⚠️ Order limit reached. Please contact support.');
                return;
            }

            button.disabled = true;
            buttonText.style.display = 'none';
            spinner.style.display = 'inline-block';

            const email = document.getElementById('purchase-email').value;
            const phone = document.getElementById('purchase-phone').value;
            const address = document.getElementById('purchase-address').value;
            const payment = document.getElementById('purchase-payment').value;
            const quantity = parseInt(document.getElementById('purchase-quantity').value);
            
            const priceStr = currentPurchasePrice.replace(/[₱,]/g, '');
            const unitPrice = parseFloat(priceStr);
            const totalAmount = unitPrice * quantity;
            
            const orderId = `ORDER-${Date.now()}-${Math.floor(Math.random() * 1000)}`;

            const orderData = {
                type: 'purchase',
                order_id: orderId,
                product_name: currentPurchaseProduct,
                product_price: currentPurchasePrice,
                quantity: quantity,
                total_amount: `₱${totalAmount.toLocaleString()}`,
                email: email,
                phone_number: phone,
                shipping_address: address,
                payment_method: payment,
                timestamp: new Date().toISOString(),
                user_email: currentUserEmail || email
            };

            const result = await window.dataSdk.create(orderData);

            button.disabled = false;
            buttonText.style.display = 'inline';
            spinner.style.display = 'none';

            if (result.isOk) {
                hidePurchaseModal();
                showToast('✓ Order placed successfully!');
                sendReceipt(orderData);
            } else {
                showToast('❌ Failed to process order');
            }
        }

        function sendReceipt(orderData) {
            const receiptText = `
PartsniBon - Order Receipt
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Order ID: ${orderData.order_id}
Date: ${new Date(orderData.timestamp).toLocaleString()}

PRODUCT DETAILS
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Product: ${orderData.product_name}
Unit Price: ${orderData.product_price}
Quantity: ${orderData.quantity}
Total Amount: ${orderData.total_amount}

SHIPPING INFORMATION
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Email: ${orderData.email}
Phone: ${orderData.phone_number}
Address: ${orderData.shipping_address}

PAYMENT METHOD
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
${orderData.payment_method.replace(/_/g, ' ').toUpperCase()}

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Thank you for shopping with PartsniBon!

We will process your order within 1-2 business days.
You will receive a confirmation email at ${orderData.email}.

For inquiries about your order, please reference 
your Order ID: ${orderData.order_id}

Visit us: PartsniBon.com
Support: support@partsnibon.com

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
`;

            const subject = encodeURIComponent(`PartsniBon Order Receipt - ${orderData.order_id}`);
            const body = encodeURIComponent(receiptText);
            const mailtoLink = `mailto:${orderData.email}?subject=${subject}&body=${body}`;

            setTimeout(() => {
                window.open(mailtoLink, '_blank');
                showToast('📧 Receipt email opened! Please send it.');
            }, 1000);
        }

        document.getElementById('purchase-modal').addEventListener('click', function(event) {
            if (event.target === this) {
                hidePurchaseModal();
            }
        });

        async function addToWishlist(productName, productPrice) {
            const wishlistItems = allData.filter(item => item.type === 'wishlist');
            
            if (wishlistItems.length >= 999) {
                showToast('⚠️ Wishlist is full (999 items max)');
                return;
            }

            const result = await window.dataSdk.create({
                type: 'wishlist',
                product_name: productName,
                product_price: productPrice,
                user_email: currentUserEmail || 'guest',
                timestamp: new Date().toISOString()
            });

            if (result.isOk) {
                showToast('✓ Added to wishlist!');
            } else {
                showToast('❌ Failed to add to wishlist');
            }
        }

        async function removeFromWishlist(item) {
            const result = await window.dataSdk.delete(item);
            if (result.isOk) {
                showToast('✓ Removed from wishlist');
            } else {
                showToast('❌ Failed to remove from wishlist');
            }
        }

        function renderWishlist(data) {
            const wishlistItems = data.filter(item => item.type === 'wishlist');
            const container = document.getElementById('wishlist-container');
            const countBadge = document.getElementById('wishlist-count');
            
            countBadge.textContent = wishlistItems.length;

            if (wishlistItems.length === 0) {
                container.innerHTML = `
                    <div class="col-span-3 text-center text-gray-500 py-12">
                        No items in wishlist yet. Add products to see them here!
                    </div>
                `;
                return;
            }

            container.innerHTML = wishlistItems.map(item => `
                <div class="bg-gray-900 border-2 border-gray-800 rounded-xl p-6">
                    <h3 class="text-xl font-bold mb-2">${item.product_name}</h3>
                    <p class="text-2xl text-green-400 font-bold mb-4">${item.product_price}</p>
                    <button 
                        onclick='removeFromWishlist(${JSON.stringify(item).replace(/'/g, "&apos;")})'
                        class="w-full py-2 border-2 border-red-500 text-red-400 rounded-lg hover:bg-red-500/10 transition-colors"
                    >
                        Remove
                    </button>
                </div>
            `).join('');
        }

        async function handleBuildRequest(event) {
            event.preventDefault();
            
            const button = document.getElementById('build-submit-btn');
            const buttonText = document.getElementById('build-submit-text');
            const spinner = document.getElementById('build-submit-spinner');
            const successMsg = document.getElementById('build-success');

            const allRecords = allData;
            if (allRecords.length >= 999) {
                showToast('⚠️ Database limit reached (999 items)');
                return;
            }

            button.disabled = true;
            buttonText.style.display = 'none';
            spinner.style.display = 'inline-block';

            const email = document.getElementById('build-email').value;
            const budget = parseInt(document.getElementById('build-budget').value);

            const recommendation = getBudgetRecommendation(budget);

            const emailBody = `Hello!

Thank you for your interest in building a PC with PartsniBon!

Based on your budget of ₱${budget.toLocaleString()}, here's our recommendation:

${recommendation.tier}
${recommendation.description}

Recommended Components:
${recommendation.components.map((comp, i) => `${i + 1}. ${comp}`).join('\n')}

Estimated Total: ${recommendation.total}

These components offer excellent value and compatibility. Visit our store at PartsniBon to purchase these items.

Need more help? Reply to this email or visit our contact page.

Best regards,
PartsniBon Team`;

            try {
                const subject = encodeURIComponent(`PC Build Recommendation - ${recommendation.tier}`);
                const body = encodeURIComponent(emailBody);
                const mailtoLink = `mailto:${email}?subject=${subject}&body=${body}`;

                const formData = {
                    type: 'build_request',
                    email: email,
                    budget: budget,
                    recommendation: recommendation.tier,
                    message: emailBody,
                    timestamp: new Date().toISOString()
                };

                const result = await window.dataSdk.create(formData);

                button.disabled = false;
                buttonText.style.display = 'inline';
                spinner.style.display = 'none';

                if (result.isOk) {
                    window.open(mailtoLink, '_blank');
                    
                    successMsg.innerHTML = `✓ Email draft created! Check your email app to send the recommendation to ${email}`;
                    successMsg.style.display = 'block';
                    document.getElementById('build-form').reset();
                    updateBudgetDisplay(100000);
                    setTimeout(() => { successMsg.style.display = 'none'; }, 8000);
                } else {
                    showToast('❌ Failed to save recommendation');
                }
            } catch (error) {
                button.disabled = false;
                buttonText.style.display = 'inline';
                spinner.style.display = 'none';
                showToast('❌ Failed to create email');
            }
        }

        async function handleContactForm(event) {
            event.preventDefault();
            
            const button = document.getElementById('contact-submit-btn');
            const buttonText = document.getElementById('contact-submit-text');
            const spinner = document.getElementById('contact-submit-spinner');
            const successMsg = document.getElementById('contact-success');

            const allRecords = allData;
            if (allRecords.length >= 999) {
                showToast('⚠️ Database limit reached (999 items)');
                return;
            }

            button.disabled = true;
            buttonText.style.display = 'none';
            spinner.style.display = 'inline-block';

            const formData = {
                type: 'contact',
                email: document.getElementById('contact-email').value,
                message: document.getElementById('contact-message').value,
                timestamp: new Date().toISOString()
            };

            const result = await window.dataSdk.create(formData);

            button.disabled = false;
            buttonText.style.display = 'inline';
            spinner.style.display = 'none';

            if (result.isOk) {
                successMsg.style.display = 'block';
                document.getElementById('contact-form').reset();
                setTimeout(() => { successMsg.style.display = 'none'; }, 5000);
            } else {
                showToast('❌ Failed to send message');
            }
        }

        async function handleNewsletterSubmit(event) {
            event.preventDefault();
            
            const button = document.getElementById('newsletter-submit-btn');
            const buttonText = document.getElementById('newsletter-submit-text');
            const spinner = document.getElementById('newsletter-submit-spinner');
            const successMsg = document.getElementById('newsletter-message');

            const allRecords = allData;
            if (allRecords.length >= 999) {
                showToast('⚠️ Database limit reached (999 items)');
                return;
            }

            button.disabled = true;
            buttonText.style.display = 'none';
            spinner.style.display = 'inline-block';

            const formData = {
                type: 'newsletter',
                email: document.getElementById('newsletter-email').value,
                timestamp: new Date().toISOString()
            };

            const result = await window.dataSdk.create(formData);

            button.disabled = false;
            buttonText.style.display = 'inline';
            spinner.style.display = 'none';

            if (result.isOk) {
                successMsg.style.display = 'block';
                document.getElementById('newsletter-form').reset();
                setTimeout(() => { successMsg.style.display = 'none'; }, 3000);
            } else {
                showToast('❌ Failed to subscribe');
            }
        }

        function scrollToWishlist() {
            document.getElementById('wishlist').scrollIntoView({ behavior: 'smooth' });
        }

        function getBudgetRecommendation(budget) {
            if (budget < 35000) {
                return {
                    tier: "Entry Level Build",
                    components: [
                        "AMD Ryzen 5 5600G - ₱8,999",
                        "ASRock B550M - ₱5,499",
                        "16GB DDR4 3200MHz - ₱2,999",
                        "512GB NVMe SSD - ₱2,499",
                        "550W 80+ Bronze PSU - ₱2,999",
                        "Budget Case - ₱1,999"
                    ],
                    total: "~₱25,000",
                    description: "Perfect for everyday computing, light gaming at 1080p"
                };
            } else if (budget < 60000) {
                return {
                    tier: "Mid-Range Gaming Build",
                    components: [
                        "AMD Ryzen 5 7600 - ₱14,999",
                        "RX 7600 8GB - ₱18,999",
                        "MSI B650M - ₱9,999",
                        "16GB DDR5 5600MHz - ₱4,499",
                        "1TB NVMe Gen4 - ₱4,999",
                        "650W 80+ Gold PSU - ₱4,999"
                    ],
                    total: "~₱58,000",
                    description: "Excellent 1080p gaming, smooth 60+ FPS on high settings"
                };
            } else if (budget < 100000) {
                return {
                    tier: "High-End Gaming Build",
                    components: [
                        "Intel i7-14700K - ₱22,999",
                        "RTX 4070 Ti 12GB - ₱44,999",
                        "ASUS Z790 - ₱16,999",
                        "32GB DDR5 6000MHz - ₱7,499",
                        "2TB NVMe Gen4 - ₱8,999",
                        "850W 80+ Gold PSU - ₱7,999"
                    ],
                    total: "~₱109,000",
                    description: "Exceptional 1440p gaming, great for content creation"
                };
            } else if (budget < 150000) {
                return {
                    tier: "Enthusiast Build",
                    components: [
                        "AMD Ryzen 9 7950X3D - ₱34,999",
                        "RTX 4080 16GB - ₱64,999",
                        "MSI X670E - ₱18,999",
                        "64GB DDR5 6400MHz - ₱12,499",
                        "2TB NVMe Gen4 - ₱8,999",
                        "NZXT Kraken 360mm - ₱14,999",
                        "1000W 80+ Gold PSU - ₱9,999"
                    ],
                    total: "~₱165,000",
                    description: "Top-tier 1440p/4K gaming, professional workstation"
                };
            } else {
                return {
                    tier: "Ultimate Extreme Build",
                    components: [
                        "Intel i9-14900K - ₱29,499",
                        "RTX 5090 Ti 24GB - ₱89,999",
                        "ASUS ROG Z790 HERO - ₱24,999",
                        "64GB DDR5 6400MHz RGB - ₱12,499",
                        "4TB NVMe Gen4 - ₱17,999",
                        "NZXT Kraken Z73 - ₱14,999",
                        "1200W 80+ Platinum - ₱12,999"
                    ],
                    total: "~₱203,000",
                    description: "Maximum performance for 4K gaming, AI/ML, rendering"
                };
            }
        }

        function updateBudgetDisplay(value) {
            const budget = parseInt(value);
            document.getElementById('budget-display').textContent = budget.toLocaleString();
            
            const recommendation = getBudgetRecommendation(budget);
            const content = document.getElementById('recommendation-content');
            
            content.innerHTML = `
                <div class="font-bold text-green-400 mb-2">${recommendation.tier}</div>
                ${recommendation.components.map(comp => `<div class="text-gray-300">• ${comp}</div>`).join('')}
                <div class="text-green-400 font-bold mt-2">${recommendation.total}</div>
                <div class="text-gray-400 text-xs mt-2 italic">${recommendation.description}</div>
            `;
        }

        document.addEventListener('DOMContentLoaded', () => {
            updateBudgetDisplay(100000);
        });

        async function onConfigChange(config) {
            const siteName = config.site_name || defaultConfig.site_name;
            const heroTitle = config.hero_title || defaultConfig.hero_title;
            const heroSubtitle = config.hero_subtitle || defaultConfig.hero_subtitle;
            const ctaButton = config.cta_button || defaultConfig.cta_button;
            const bgColor = config.background_color || defaultConfig.background_color;
            const textColor = config.text_color || defaultConfig.text_color;
            const customFont = config.font_family || defaultConfig.font_family;
            const baseSize = config.font_size || defaultConfig.font_size;

            document.getElementById('site-name').textContent = siteName;
            document.getElementById('hero-title').textContent = heroTitle;
            document.getElementById('hero-subtitle').textContent = heroSubtitle;
            document.getElementById('cta-button').textContent = ctaButton;

            document.body.style.backgroundColor = bgColor;
            document.body.style.color = textColor;

            const baseFontStack = 'system-ui, -apple-system, sans-serif';
            document.body.style.fontFamily = `${customFont}, ${baseFontStack}`;
            document.body.style.fontSize = `${baseSize}px`;

            const titles = document.querySelectorAll('h2');
            titles.forEach(title => {
                title.style.fontSize = `${baseSize * 2.5}px`;
            });

            const subtitles = document.querySelectorAll('h3');
            subtitles.forEach(subtitle => {
                subtitle.style.fontSize = `${baseSize * 1.5}px`;
            });
        }

        function mapToCapabilities(config) {
            return {
                recolorables: [
                    {
                        get: () => config.background_color || defaultConfig.background_color,
                        set: (value) => {
                            config.background_color = value;
                            if (window.elementSdk) window.elementSdk.setConfig({ background_color: value });
                        }
                    },
                    {
                        get: () => config.accent_color || defaultConfig.accent_color,
                        set: (value) => {
                            config.accent_color = value;
                            if (window.elementSdk) window.elementSdk.setConfig({ accent_color: value });
                        }
                    },
                    {
                        get: () => config.text_color || defaultConfig.text_color,
                        set: (value) => {
                            config.text_color = value;
                            if (window.elementSdk) window.elementSdk.setConfig({ text_color: value });
                        }
                    },
                    {
                        get: () => config.surface_color || defaultConfig.surface_color,
                        set: (value) => {
                            config.surface_color = value;
                            if (window.elementSdk) window.elementSdk.setConfig({ surface_color: value });
                        }
                    },
                    {
                        get: () => config.button_color || defaultConfig.button_color,
                        set: (value) => {
                            config.button_color = value;
                            if (window.elementSdk) window.elementSdk.setConfig({ button_color: value });
                        }
                    }
                ],
                borderables: [],
                fontEditable: {
                    get: () => config.font_family || defaultConfig.font_family,
                    set: (value) => {
                        config.font_family = value;
                        if (window.elementSdk) window.elementSdk.setConfig({ font_family: value });
                    }
                },
                fontSizeable: {
                    get: () => config.font_size || defaultConfig.font_size,
                    set: (value) => {
                        config.font_size = value;
                        if (window.elementSdk) window.elementSdk.setConfig({ font_size: value });
                    }
                }
            };
        }

        function mapToEditPanelValues(config) {
            return new Map([
                ["site_name", config.site_name || defaultConfig.site_name],
                ["hero_title", config.hero_title || defaultConfig.hero_title],
                ["hero_subtitle", config.hero_subtitle || defaultConfig.hero_subtitle],
                ["cta_button", config.cta_button || defaultConfig.cta_button]
            ]);
        }

        if (window.elementSdk) {
            window.elementSdk.init({
                defaultConfig,
                onConfigChange,
                mapToCapabilities,
                mapToEditPanelValues
            });
        }
    </script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'9a43211877f5b9ff',t:'MTc2NDA5NDUwNC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
