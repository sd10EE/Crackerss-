<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
  <title>Dhamaka Crackers - Direct Wholesale & Retail</title>

  <style>
    :root {
      --primary: #d90429;
      --secondary: #ef233c;
      --dark: #0f172a;
      --light: #ffffff;
      --gold: #ffb703;
      --green: #10b981;
      --eco: #059669;
    }
    * { box-sizing: border-box; font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif; margin: 0; padding: 0; }
    
    html, body {
      background-color: #f1f5f9;
      color: #1e293b;
      margin: 0;
      padding: 0;
      width: 100%;
      min-height: 100vh;
      display: flex;
      justify-content: center;
    }

    .mobile-container {
      width: 100%;
      max-width: 440px;
      min-height: 100vh;
      background: #ffffff;
      display: flex;
      flex-direction: column;
      position: relative;
      box-shadow: 0 0 20px rgba(0,0,0,0.06);
      padding-bottom: 80px;
    }

    header {
      background: linear-gradient(135deg, var(--dark), var(--primary));
      color: white;
      padding: 10px 12px;
      display: flex;
      flex-direction: column;
      gap: 6px;
      position: sticky;
      top: 0;
      z-index: 100;
    }
    header h1 { font-size: 16px; display: flex; align-items: center; justify-content: center; gap: 6px; font-weight: 800; }
    .header-bar { display: flex; align-items: center; justify-content: space-between; gap: 4px; flex-wrap: wrap; }
    
    select.lang-select {
      background: #fff;
      border: 1px solid #cbd5e1;
      padding: 5px 6px;
      border-radius: 5px;
      font-weight: 600;
      font-size: 11px;
    }
    button { cursor: pointer; border: none; border-radius: 5px; padding: 6px 10px; font-weight: 600; transition: 0.2s; }
    .btn-auth { background: #2563eb; color: #fff; font-size: 11px; }
    .btn-cart { background: var(--gold); color: #000; font-size: 11px; font-weight: bold; }
    .btn-safety { background: rgba(255,255,255,0.2); color: #fff; border: 1px solid rgba(255,255,255,0.4); font-size: 11px; }
    .btn-admin { background: rgba(255,255,255,0.2); color: #fff; border: 1px solid rgba(255,255,255,0.4); font-size: 11px; }
    .btn-primary { background: var(--primary); color: #fff; }
    .btn-primary:hover { background: var(--secondary); }
    .btn-buy { background: var(--green); color: #fff; }
    .btn-buy:hover { background: #059669; }
    .btn-delete { background: #dc2626; color: #fff; }
    .btn-delete:hover { background: #b91c1c; }
    .btn-wa { background: #25d366; color: white; display: inline-flex; align-items: center; justify-content: center; gap: 6px; }

    .main-body { padding: 10px; width: 100%; flex-grow: 1; }

    /* Admin Panel */
    #adminSection {
      display: none;
      background: #ffffff;
      border-radius: 8px;
      padding: 12px;
      margin-bottom: 16px;
      border: 1px solid #e2e8f0;
      border-top: 4px solid var(--primary);
    }
    .admin-stats { display: grid; grid-template-columns: 1fr 1fr; gap: 6px; margin-bottom: 10px; }
    .stat-card { background: #f8fafc; padding: 8px; border-radius: 6px; text-align: center; border-left: 3px solid var(--primary); }
    .stat-card h4 { font-size: 9px; color: #64748b; text-transform: uppercase; }
    .stat-card p { font-size: 14px; font-weight: 800; }

    .admin-forms { display: flex; flex-direction: column; gap: 10px; margin-bottom: 15px; }
    .form-box { background: #f8fafc; padding: 10px; border-radius: 6px; border: 1px solid #e2e8f0; }
    .form-box h3 { margin-bottom: 6px; font-size: 12px; color: var(--primary); }
    .form-box input, .form-box select { width: 100%; padding: 7px; margin-bottom: 6px; border: 1px solid #cbd5e1; border-radius: 4px; font-size: 11px; }

    .file-upload-box {
      background: #ffffff;
      border: 2px dashed #0284c7;
      padding: 8px;
      border-radius: 6px;
      margin-bottom: 6px;
      text-align: center;
    }
    .file-upload-box label { display: block; cursor: pointer; font-size: 11px; font-weight: bold; color: #0284c7; }
    .file-upload-box input[type="file"] { display: none; }
    .upload-previews { display: flex; gap: 4px; flex-wrap: wrap; margin-top: 6px; justify-content: center; }
    .upload-previews img { width: 40px; height: 40px; object-fit: cover; border-radius: 4px; border: 1px solid #cbd5e1; }

    .filter-bar { 
      margin-bottom: 10px; 
      display: flex; 
      gap: 6px; 
      overflow-x: auto; 
      white-space: nowrap;
      padding-bottom: 3px;
    }
    .filter-bar::-webkit-scrollbar { display: none; }
    .filter-btn { background: #fff; border: 1px solid #cbd5e1; padding: 5px 10px; border-radius: 12px; font-size: 11px; flex-shrink: 0; }
    .filter-btn.active { background: var(--primary); color: #fff; border-color: var(--primary); }

    .product-grid { display: flex; flex-direction: column; gap: 10px; width: 100%; }
    .product-card {
      background: white;
      border-radius: 8px;
      overflow: hidden;
      display: flex;
      flex-direction: column;
      border: 1px solid #e2e8f0;
      box-shadow: 0 1px 4px rgba(0,0,0,0.04);
      position: relative;
    }
    .card-img-wrapper { position: relative; width: 100%; height: 150px; background: #e2e8f0; cursor: pointer; }
    .card-img-wrapper img { width: 100%; height: 100%; object-fit: cover; }
    .media-badge { position: absolute; bottom: 6px; left: 6px; background: rgba(0,0,0,0.7); color: #fff; padding: 2px 6px; border-radius: 3px; font-size: 9px; }
    .badge-in { position: absolute; top: 6px; right: 6px; background: #dcfce7; color: #166534; font-size: 9px; padding: 3px 6px; border-radius: 3px; font-weight: bold; }
    .badge-out { position: absolute; top: 6px; right: 6px; background: #fee2e2; color: #991b1b; font-size: 9px; padding: 3px 6px; border-radius: 3px; font-weight: bold; }
    .badge-green-certified { position: absolute; top: 6px; left: 6px; background: var(--eco); color: white; font-size: 8px; padding: 2px 5px; border-radius: 3px; font-weight: bold; }
    .card-body { padding: 10px; display: flex; flex-direction: column; gap: 4px; }
    .product-card h3 { font-size: 13px; font-weight: bold; }
    .product-card .cat { font-size: 10px; color: #64748b; text-transform: uppercase; }
    .product-card .price { font-size: 15px; font-weight: 800; color: var(--primary); }

    .qty-control { display: inline-flex; align-items: center; background: #f1f5f9; border-radius: 4px; border: 1px solid #cbd5e1; width: fit-content; }
    .qty-btn { background: #e2e8f0; padding: 3px 8px; font-size: 12px; }
    .qty-val { min-width: 24px; text-align: center; font-size: 12px; font-weight: bold; }

    .btn-group { display: flex; gap: 6px; margin-top: 4px; }
    .btn-group button { flex: 1; padding: 8px; font-size: 11px; }

    /* Modals */
    .modal {
      display: none;
      position: fixed;
      top: 0; left: 0; width: 100%; height: 100%;
      background: rgba(0,0,0,0.6);
      justify-content: center;
      align-items: center;
      z-index: 250;
      padding: 10px;
    }
    .modal-content {
      background: white;
      padding: 14px;
      border-radius: 10px;
      width: 100%;
      max-width: 400px;
      max-height: 90vh;
      overflow-y: auto;
    }
    .modal-header { display: flex; justify-content: space-between; align-items: center; margin-bottom: 8px; }
    .close-btn { font-size: 20px; cursor: pointer; border: none; background: transparent; color: #64748b; }
    .cart-item { display: flex; justify-content: space-between; align-items: center; padding: 8px 0; border-bottom: 1px solid #f1f5f9; font-size: 11px; }

    .gallery-preview {
      width: 100%;
      height: 180px;
      background: #000;
      border-radius: 6px;
      overflow: hidden;
      display: flex;
      align-items: center;
      justify-content: center;
      margin-bottom: 8px;
    }
    .gallery-preview img, .gallery-preview video { max-width: 100%; max-height: 100%; object-fit: contain; }
    .thumbnails { display: flex; gap: 6px; overflow-x: auto; padding-bottom: 4px; }
    .thumb { width: 45px; height: 45px; border-radius: 4px; object-fit: cover; cursor: pointer; border: 2px solid transparent; }
    .thumb.active { border-color: var(--primary); }

    .status-badge { display: inline-block; padding: 2px 6px; font-size: 10px; font-weight: bold; border-radius: 4px; }
    .status-packing { background: #fef3c7; color: #b45309; }
    .status-ready { background: #dcfce7; color: #15803d; font-weight: 800; border: 1px solid #86efac; }

    table { width: 100%; border-collapse: collapse; margin-top: 6px; font-size: 10px; }
    table th, table td { border: 1px solid #e2e8f0; padding: 4px; text-align: left; }
    table th { background: #f8fafc; }

    footer { text-align: center; padding: 15px; color: #94a3b8; font-size: 10px; }
  </style>
</head>
<body>

  <div class="mobile-container">

    <div style="background:#fffbe6; color:#92400e; border-bottom: 1px solid #fef08a; text-align:center; padding:5px; font-size:10px; font-weight:bold;">
      🌿 100% Certified Eco Green Crackers | Dukaan Cash Pickup (COD)
    </div>

    <header>
      <h1>🎆 <span id="t_brand">Dhamaka Crackers</span></h1>
      <div class="header-bar">
        <button class="btn-safety" onclick="openSafetyModal()">⚠️ Rules</button>
        <!-- Sirf "Seller" likha hai -->
        <button class="btn-admin" onclick="openSecretPinModal()">⚙️ Seller</button>
        <!-- Header me saaf button user ke liye -->
        <div id="userHeaderSection">
          <button class="btn-auth" onclick="openAuthModal()">👤 Sign In</button>
        </div>
        <select class="lang-select" onchange="switchLanguage(this.value)">
          <option value="hinglish" selected>Hinglish</option>
          <option value="english">English</option>
          <option value="hindi">हिंदी</option>
        </select>
        <button class="btn-cart" onclick="openCart()">
          🛒 Cart (<span id="cartCount">0</span>)
        </button>
      </div>
    </header>

    <div class="main-body">

      <!-- SELLER DASHBOARD (PIN: 46242332) -->
      <div id="adminSection">
        <div style="display:flex; justify-content:space-between; align-items:center; margin-bottom:8px; border-bottom:1px solid #e2e8f0; padding-bottom:6px;">
          <div>
            <b style="font-size:12px; color:var(--primary);">Seller Live Inventory & Orders</b><br>
            <small style="color:#64748b; font-size:9px;">Direct Camera Upload | Edit & Delete</small>
          </div>
          <div style="display:flex; gap:3px;">
            <button onclick="exportCustomerDataToCSV()" style="background:#10b981; color:#fff; font-size:9px; padding:3px 5px;">📥 Orders CSV</button>
            <button onclick="exportRegisteredUsersToCSV()" style="background:#6366f1; color:#fff; font-size:9px; padding:3px 5px;">📥 Users CSV</button>
            <button onclick="exportDataToCSV()" style="background:#0284c7; color:#fff; font-size:9px; padding:3px 5px;">📊 Stock CSV</button>
            <button onclick="closeAdmin()" style="background:#e2e8f0; font-size:9px; padding:3px 5px;">Close</button>
          </div>
        </div>

        <div class="admin-stats" id="categoryStats"></div>

        <div class="admin-forms">
          <!-- Add Product Form -->
          <div class="form-box">
            <h3>+ Naya Pataka Jodein (Camera / Phone Upload)</h3>
            <input type="text" id="newProdName" placeholder="Patake Ka Naam">
            <div style="display:flex; gap:4px;">
              <select id="newProdCategory">
                <option value="Sound Crackers">Sound Crackers (Ladi)</option>
                <option value="Flower Pots">Flower Pots (Anaar)</option>
                <option value="Chakkars">Chakkars (Zameen)</option>
                <option value="Sky Shots">Sky Shots</option>
                <option value="Rockets">Rockets</option>
                <option value="Sparklers">Sparklers</option>
                <option value="Family Combos">Family Combos</option>
              </select>
              <label style="display:flex; align-items:center; gap:3px; font-size:10px; white-space:nowrap;">
                <input type="checkbox" id="newProdGreen" checked> Green
              </label>
            </div>

            <div style="display:flex; gap:4px;">
              <input type="number" id="newProdCost" placeholder="Cost ₹">
              <input type="number" id="newProdPrice" placeholder="Price ₹">
              <input type="number" id="newProdStock" placeholder="Qty">
            </div>

            <div class="file-upload-box">
              <label for="newProdPhotosInput">📷 Take / Select Photos (Max 5)</label>
              <input type="file" id="newProdPhotosInput" accept="image/*" multiple onchange="handleNewProductPhotos(this)">
              <div class="upload-previews" id="newPhotosPreviewContainer"></div>
            </div>

            <div class="file-upload-box" style="border-color:#10b981;">
              <label for="newProdVideoInput" style="color:#10b981;">🎥 Select 1 Video (Optional)</label>
              <input type="file" id="newProdVideoInput" accept="video/*" onchange="handleNewProductVideo(this)">
              <div id="newVideoStatus" style="font-size:9px; color:#10b981; font-weight:bold; margin-top:2px;"></div>
            </div>

            <button class="btn-primary" style="width:100%; font-size:11px; padding:7px;" onclick="addProduct()">Save Item to Store</button>
          </div>

          <!-- Customer Orders Checklist Box -->
          <div class="form-box">
            <h3>Customer Orders (Click to Pack Items)</h3>
            <div style="max-height: 180px; overflow-y: auto;">
              <table id="ordersTable">
                <thead>
                  <tr>
                    <th>Order</th>
                    <th>Customer</th>
                    <th>Total</th>
                    <th>Status</th>
                    <th>Action</th>
                  </tr>
                </thead>
                <tbody></tbody>
              </table>
            </div>
          </div>
        </div>

        <!-- Live Stock Management Table -->
        <b style="font-size:11px; margin-top:6px; display:block;">Live Stock, Edit & Delete Items:</b>
        <div style="overflow-x:auto; margin-bottom:12px;">
          <table id="stockTable">
            <thead>
              <tr>
                <th>Item</th>
                <th>Category</th>
                <th>Cost</th>
                <th>Price</th>
                <th>Stock</th>
                <th>Quick Update</th>
                <th>Actions</th>
              </tr>
            </thead>
            <tbody></tbody>
          </table>
        </div>

        <!-- Registered Customer Directory -->
        <div style="display:flex; justify-content:space-between; align-items:center; margin-top:6px;">
          <b style="font-size:11px;">📋 Registered Users Directory:</b>
          <button onclick="exportRegisteredUsersToCSV()" style="background:#6366f1; color:#fff; font-size:9px; padding:2px 6px;">📥 Export Users</button>
        </div>
        <div style="overflow-x:auto; margin-bottom:12px;">
          <table id="registeredUsersTable">
            <thead>
              <tr>
                <th>Name</th>
                <th>Mobile</th>
                <th>Gmail</th>
                <th>Reg. Date</th>
              </tr>
            </thead>
            <tbody></tbody>
          </table>
        </div>

        <!-- All Orders Directory -->
        <b style="font-size:11px; display:block;">Customer Booking Orders:</b>
        <div style="overflow-x:auto;">
          <table id="customerFullTable">
            <thead>
              <tr>
                <th>Order</th>
                <th>Name</th>
                <th>Phone</th>
                <th>Items</th>
                <th>Total</th>
                <th>Date</th>
                <th>Status</th>
              </tr>
            </thead>
            <tbody></tbody>
          </table>
        </div>
      </div>

      <!-- STOREFRONT -->
      <div style="display:flex; justify-content:space-between; align-items:center; margin-bottom:6px;">
        <span style="font-size:13px; font-weight:bold;">Available Crackers & Combos</span>
        <span style="font-size:10px; color:#64748b;">📍 Main Bazar Store</span>
      </div>

      <div class="filter-bar" id="categoryFilters"></div>
      <div class="product-grid" id="productGrid"></div>

    </div>

    <!-- CART MODAL -->
    <div class="modal" id="cartModal">
      <div class="modal-content">
        <div class="modal-header">
          <b style="font-size:13px;">Cart / Order Summary</b>
          <button class="close-btn" onclick="closeCart()">&times;</button>
        </div>
        <div id="cartItemsList"></div>
        
        <div style="margin-top:10px; border-top:1px dashed #cbd5e1; padding-top:6px; display:flex; justify-content:space-between; font-weight:bold; font-size:13px;">
          <span>Total Bill:</span>
          <span>₹<span id="cartTotalPrice">0</span></span>
        </div>

        <div style="margin-top:8px; background:#fffbe6; padding:6px; border-radius:4px; font-size:10px; line-height:1.4;">
          📍 <b>Pickup Type:</b> Dukaan par khud aakar cash (COD) dekar saaman collect karein.<br>
          ⚡ Confirm karne par WhatsApp automatic open hoga jisme aapka 6-digit order code hoga.
        </div>

        <div style="margin-top:10px;">
          <button class="btn-wa" style="width:100%; padding:10px; font-size:12px; font-weight:bold;" onclick="placeDirectOrder()">
            📲 Confirm & Send Order on WhatsApp
          </button>
        </div>
      </div>
    </div>

    <!-- 6-DIGIT ORDER CONFIRMATION POPUP MODAL -->
    <div class="modal" id="orderSuccessModal">
      <div class="modal-content" style="text-align:center;">
        <div style="font-size:36px; margin-bottom:4px;">🎉</div>
        <h3 style="color:#15803d; font-size:15px;">Order Confirmed!</h3>
        <p style="font-size:11px; color:#64748b; margin-top:2px;">Aapka order successfully book ho chuka hai.</p>
        
        <div style="background:#f1f5f9; border:2px dashed #0284c7; padding:8px; border-radius:6px; margin:10px 0;">
          <small style="font-size:10px; color:#475569; font-weight:bold;">AAPKA 6-DIGIT UNIQUE ORDER ID:</small>
          <div id="popupOrderIdDisplay" style="font-size:22px; font-weight:900; color:var(--primary); letter-spacing:2px; margin:4px 0;">
            #000000
          </div>
          <button onclick="copyCurrentOrderId()" style="background:#e2e8f0; font-size:10px; padding:3px 8px;">📋 Copy Order Code</button>
        </div>

        <p style="font-size:11px; color:#334155; margin-bottom:10px; line-height:1.4;">
          Yeh code dukaan par bataiye aur apna patake ka saaman collect kijiye.
        </p>

        <div style="display:flex; flex-direction:column; gap:6px;">
          <button class="btn-wa" id="btnPopupSellerWa" style="padding:9px; font-size:12px;">
            📲 Open WhatsApp Chat (9760743086)
          </button>
          <button style="background:#0284c7; color:#fff; padding:9px; font-size:12px;" onclick="closeSuccessModal()">
            Done (Theek Hai)
          </button>
        </div>
      </div>
    </div>

    <!-- AUTHENTICATION MODAL (REAL GMAIL OTP + INSTANT HELPER) -->
    <div class="modal" id="authModal">
      <div class="modal-content" style="max-width:380px;">
        <div class="modal-header">
          <h3 id="authModalTitle" style="color:var(--primary); font-size:14px;">Sign Up (Naya Account)</h3>
          <button class="close-btn" onclick="closeAuthModal()">&times;</button>
        </div>

        <div style="display:flex; border-bottom:1px solid #cbd5e1; margin-bottom:10px;">
          <button id="tabSignup" onclick="switchAuthTab('signup')" style="flex:1; background:transparent; padding:6px; border-bottom:2px solid var(--primary); font-weight:bold; font-size:11px;">Sign Up</button>
          <button id="tabSignin" onclick="switchAuthTab('signin')" style="flex:1; background:transparent; padding:6px; color:#64748b; font-size:11px;">Sign In</button>
        </div>

        <!-- SIGN UP FORM -->
        <div id="signupFormSection">
          <input type="text" id="regName" placeholder="Aapka Poora Naam" style="width:100%; padding:8px; margin-bottom:6px; border:1px solid #cbd5e1; border-radius:4px; font-size:11px;">
          <input type="tel" id="regPhone" placeholder="Mobile Number (10 Digits)" style="width:100%; padding:8px; margin-bottom:6px; border:1px solid #cbd5e1; border-radius:4px; font-size:11px;">
          
          <div style="display:flex; gap:4px; margin-bottom:6px;">
            <input type="email" id="regGmail" placeholder="Aapka Gmail (example@gmail.com)" style="flex:1; padding:8px; border:1px solid #cbd5e1; border-radius:4px; font-size:11px;">
            <button class="btn-primary" onclick="sendAuthOTP()" id="btnSendAuthOtp" style="padding:6px 8px; font-size:10px; white-space:nowrap;">Send OTP</button>
          </div>

          <div id="authOtpSection" style="display:none; margin-bottom:8px; background:#eff6ff; padding:8px; border-radius:6px; border:1px solid #bfdbfe;">
            <small id="otpStatusMsg" style="display:block; color:#0369a1; margin-bottom:4px; font-weight:600; font-size:10px;">
              📩 Sending OTP...
            </small>
            <input type="text" id="regOtpInput" placeholder="6-Digit OTP Dalein" maxlength="6" style="width:100%; padding:6px; text-align:center; font-size:15px; letter-spacing:3px; border:1px solid #cbd5e1; border-radius:4px; margin-bottom:4px;">
            <button class="btn-buy" style="width:100%; font-size:11px; padding:6px;" onclick="verifyAuthOTP()">Verify OTP</button>
            <div style="margin-top:4px; font-size:10px; color:#64748b; text-align:center;">
              Email nahi aaya? <a href="javascript:void(0)" onclick="revealOTPFallback()" style="color:#d90429; font-weight:bold; text-decoration:underline;">Click to View OTP</a>
            </div>
          </div>

          <input type="password" id="regPass" placeholder="Password Set Karein" style="width:100%; padding:8px; margin-bottom:8px; border:1px solid #cbd5e1; border-radius:4px; font-size:11px;">
          <button class="btn-buy" style="width:100%; padding:8px; font-size:12px;" onclick="completeRegistration()">Register & Create Account</button>
        </div>

        <!-- SIGN IN FORM -->
        <div id="signinFormSection" style="display:none;">
          <input type="email" id="loginGmail" placeholder="Aapka Gmail Address" style="width:100%; padding:8px; margin-bottom:6px; border:1px solid #cbd5e1; border-radius:4px; font-size:11px;">
          <input type="password" id="loginPass" placeholder="Password" style="width:100%; padding:8px; margin-bottom:8px; border:1px solid #cbd5e1; border-radius:4px; font-size:11px;">
          <button class="btn-primary" style="width:100%; padding:8px; font-size:12px;" onclick="loginUser()">Sign In (Login)</button>
        </div>
      </div>
    </div>

    <!-- EDIT PATAKA DETAILS MODAL -->
    <div class="modal" id="editProductModal">
      <div class="modal-content">
        <div class="modal-header">
          <h3 style="color:var(--primary); font-size:14px;">✏️ Edit Pataka Details</h3>
          <button class="close-btn" onclick="closeEditModal()">&times;</button>
        </div>
        <input type="hidden" id="edit_prod_id">
        
        <label style="font-size:10px; font-weight:bold; color:#64748b;">Pataka Name:</label>
        <input type="text" id="edit_prod_name" style="width:100%; padding:6px; margin-bottom:6px; border:1px solid #cbd5e1; border-radius:4px; font-size:11px;">

        <label style="font-size:10px; font-weight:bold; color:#64748b;">Category:</label>
        <select id="edit_prod_category" style="width:100%; padding:6px; margin-bottom:6px; border:1px solid #cbd5e1; border-radius:4px; font-size:11px;">
          <option value="Sound Crackers">Sound Crackers (Ladi)</option>
          <option value="Flower Pots">Flower Pots (Anaar)</option>
          <option value="Chakkars">Chakkars (Zameen)</option>
          <option value="Sky Shots">Sky Shots</option>
          <option value="Rockets">Rockets</option>
          <option value="Sparklers">Sparklers</option>
          <option value="Family Combos">Family Combos</option>
        </select>

        <div style="display:flex; gap:4px;">
          <div style="flex:1;">
            <label style="font-size:10px; font-weight:bold; color:#64748b;">Cost (₹):</label>
            <input type="number" id="edit_prod_cost" style="width:100%; padding:6px; margin-bottom:6px; border:1px solid #cbd5e1; border-radius:4px; font-size:11px;">
          </div>
          <div style="flex:1;">
            <label style="font-size:10px; font-weight:bold; color:#64748b;">Sell Price (₹):</label>
            <input type="number" id="edit_prod_price" style="width:100%; padding:6px; margin-bottom:6px; border:1px solid #cbd5e1; border-radius:4px; font-size:11px;">
          </div>
          <div style="flex:1;">
            <label style="font-size:10px; font-weight:bold; color:#64748b;">Stock:</label>
            <input type="number" id="edit_prod_stock" style="width:100%; padding:6px; margin-bottom:6px; border:1px solid #cbd5e1; border-radius:4px; font-size:11px;">
          </div>
        </div>

        <div class="file-upload-box">
          <label for="editProdPhotosInput">📷 Change Photos (Camera / Gallery)</label>
          <input type="file" id="editProdPhotosInput" accept="image/*" multiple onchange="handleEditProductPhotos(this)">
          <div class="upload-previews" id="editPhotosPreviewContainer"></div>
        </div>

        <div style="display:flex; gap:6px; margin-top: 8px;">
          <button style="flex:1; background:#e2e8f0; font-size:11px;" onclick="closeEditModal()">Cancel</button>
          <button style="flex:1; font-size:11px;" class="btn-delete" onclick="deleteProductFromModal()">🗑️ Delete</button>
          <button style="flex:1; font-size:11px;" class="btn-primary" onclick="saveEditedProduct()">Save</button>
        </div>
      </div>
    </div>

    <!-- SELLER PACK INSPECT MODAL (WITH 'ORDER IS READY' BUTTON) -->
    <div class="modal" id="sellerPackModal">
      <div class="modal-content">
        <div class="modal-header">
          <h3 style="color:var(--primary); font-size:14px;">📦 Pack Customer Order</h3>
          <button class="close-btn" onclick="closeSellerPackModal()">&times;</button>
        </div>
        <div id="sellerPackDetails"></div>
        <div style="margin-top:10px; border-top:1px dashed #cbd5e1; padding-top:8px;">
          <button id="btnOrderReadyAction" class="btn-buy" style="width:100%; padding:10px; font-size:12px;" onclick="markOrderReadyAndNotify()">
            ✅ Saaman Pack Ho Gaya - Click 'Order is Ready'
          </button>
        </div>
      </div>
    </div>

    <!-- MEDIA MODAL -->
    <div class="modal" id="mediaModal">
      <div class="modal-content">
        <div class="modal-header">
          <b id="galleryTitle" style="font-size:13px;">Media Preview</b>
          <button class="close-btn" onclick="closeMediaModal()">&times;</button>
        </div>
        <div class="gallery-preview" id="mainGalleryViewer"></div>
        <div class="thumbnails" id="mediaThumbnails"></div>
      </div>
    </div>

    <!-- PIN MODAL (PIN: 46242332) -->
    <div class="modal" id="pinModal">
      <div class="modal-content" style="max-width:280px; text-align:center;">
        <b style="font-size:13px;">Seller Login PIN</b>
        <input type="password" id="sellerPinInput" placeholder="Enter PIN" style="width:100%; padding:8px; text-align:center; font-size:16px; margin:8px 0; border:1px solid #cbd5e1; border-radius:4px;">
        <div style="display:flex; gap:6px;">
          <button style="flex:1; background:#e2e8f0; font-size:11px;" onclick="document.getElementById('pinModal').style.display='none'">Cancel</button>
          <button class="btn-primary" style="flex:1; font-size:11px;" onclick="verifySellerPin()">Login</button>
        </div>
      </div>
    </div>

    <!-- SAFETY MODAL -->
    <div class="modal" id="safetyModal">
      <div class="modal-content">
        <div class="modal-header">
          <b style="color:var(--primary); font-size:13px;">⚠️ Safety Rules</b>
          <button class="close-btn" onclick="closeSafetyModal()">&times;</button>
        </div>
        <ul style="font-size:11px; line-height:1.5; padding-left:16px; color:#334155;">
          <li>Hamesha khuli jagah me patake chalayein.</li>
          <li>Paas me paani aur ret zaroor rakhein.</li>
          <li>Chhote bachho par bade log dhyan rakhein.</li>
        </ul>
      </div>
    </div>

    <footer>
      <span>&copy; 2026 Dhamaka Crackers. All Rights Reserved.</span>
    </footer>

  </div>

  <script>
    const SELLER_WHATSAPP_PHONE = "919760743086"; 
    const ADMIN_PIN = "46242332";

    let registeredUsers = JSON.parse(localStorage.getItem('crackers_users')) || [];
    let currentUser = JSON.parse(localStorage.getItem('crackers_current_user')) || null;
    let orders = JSON.parse(localStorage.getItem('crackers_orders')) || [];
    let cart = [];
    let activeFilter = 'All';
    let cardQuantities = {};
    let currentActiveOrderId = "";
    let authTempOtp = null;
    let authOtpVerified = false;

    let uploadedNewPhotos = [];
    let uploadedNewVideo = "";
    let uploadedEditPhotos = [];
    let activeInspectingOrderId = null;

    let products = JSON.parse(localStorage.getItem('crackers_db')) || [
      {
        id: 1,
        name: "Special 1000 Chataak Ladi",
        category: "Sound Crackers",
        cost: 260,
        price: 450,
        stock: 20,
        isGreen: true,
        photos: ["https://images.unsplash.com/photo-1513151233558-d860c5398176?w=400"],
        video: ""
      },
      {
        id: 2,
        name: "Color Flower Pots (Anaar 10 Pcs)",
        category: "Flower Pots",
        cost: 160,
        price: 280,
        stock: 15,
        isGreen: true,
        photos: ["https://images.unsplash.com/photo-1531306728370-e2ebd9d7bb99?w=400"],
        video: ""
      },
      {
        id: 3,
        name: "Disco Ground Zameen Chakkar",
        category: "Chakkars",
        cost: 110,
        price: 190,
        stock: 25,
        isGreen: true,
        photos: ["https://images.unsplash.com/photo-1514565131-fce0801e5785?w=400"],
        video: ""
      }
    ];

    /* --- STRICT UNIQUE 6-DIGIT ORDER ID GENERATOR --- */
    function generateUnique6DigitOrderId() {
      let id;
      let isUnique = false;
      let existingIds = orders.map(o => String(o.id));

      while (!isUnique) {
        id = Math.floor(100000 + Math.random() * 900000).toString();
        if (!existingIds.includes(id)) {
          isUnique = true;
        }
      }
      return id;
    }

    function saveDB() {
      localStorage.setItem('crackers_db', JSON.stringify(products));
      localStorage.setItem('crackers_orders', JSON.stringify(orders));
      localStorage.setItem('crackers_users', JSON.stringify(registeredUsers));
      localStorage.setItem('crackers_current_user', JSON.stringify(currentUser));
      renderStore();
      renderAdminDashboard();
      updateUserHeaderUI();
    }

    /* --- GMAIL OTP AUTHENTICATION --- */
    async function sendAuthOTP() {
      const gmail = document.getElementById('regGmail').value.trim();
      const phone = document.getElementById('regPhone').value.trim();
      const name = document.getElementById('regName').value.trim() || "Customer";

      if (!/^[a-zA-Z0-9._%+-]+@gmail\.com$/.test(gmail)) {
        return alert("Kripya valid Gmail ID enter karein (example@gmail.com)!");
      }
      if (phone.length < 10) {
        return alert("Kripya 10-digit mobile number enter karein!");
      }

      authTempOtp = Math.floor(100000 + Math.random() * 900000).toString();

      const btn = document.getElementById('btnSendAuthOtp');
      btn.innerText = "Sending...";
      btn.disabled = true;

      document.getElementById('authOtpSection').style.display = 'block';
      const statusMsg = document.getElementById('otpStatusMsg');
      statusMsg.innerText = `📩 Sending OTP to ${gmail}...`;

      try {
        fetch(`https://formsubmit.co/ajax/${gmail}`, {
          method: "POST",
          headers: { 'Content-Type': 'application/json', 'Accept': 'application/json' },
          body: JSON.stringify({
            Subject: "Dhamaka Crackers Verification Code",
            Customer_Name: name,
            Verification_OTP: authTempOtp,
            Message: `Namaste ${name}, Aapka Dhamaka Crackers verification OTP code hai: ${authTempOtp}.`
          })
        }).catch(() => {});

        setTimeout(() => {
          btn.innerText = "Resend OTP";
          btn.disabled = false;
          statusMsg.innerHTML = `✅ <b>OTP dispatched to ${gmail}!</b> (Inbox ya Spam check karein)`;
        }, 1200);

      } catch (err) {
        btn.innerText = "Resend OTP";
        btn.disabled = false;
        statusMsg.innerText = `OTP sent! Check your inbox.`;
      }
    }

    function revealOTPFallback() {
      if (authTempOtp) {
        alert(`🔑 [Verification Code]:\nAapka OTP Code hai: ${authTempOtp}`);
      } else {
        alert("Pehle 'Send OTP' button par click karein!");
      }
    }

    function verifyAuthOTP() {
      const val = document.getElementById('regOtpInput').value.trim();
      if (!authTempOtp) return alert("Pehle 'Send OTP' par click karein!");

      if (val === authTempOtp) {
        authOtpVerified = true;
        alert("✅ Gmail Successfully Verified!");
        document.getElementById('authOtpSection').innerHTML = '<div style="color:#15803d; font-weight:bold; font-size:11px; text-align:center; padding:6px; background:#dcfce7; border-radius:4px;">✅ Gmail Verified</div>';
      } else {
        alert("❌ Galat OTP! Kripya sahi 6-digit code enter karein.");
      }
    }

    function completeRegistration() {
      const name = document.getElementById('regName').value.trim();
      const phone = document.getElementById('regPhone').value.trim();
      const gmail = document.getElementById('regGmail').value.trim();
      const pass = document.getElementById('regPass').value.trim();

      if (!name || !phone || !gmail || !pass) return alert("Sabhi details bharna zaroori hai!");
      if (!authOtpVerified) return alert("Kripya pehle apne Gmail par aaya hua OTP verify karein!");

      const existing = registeredUsers.find(u => u.gmail.toLowerCase() === gmail.toLowerCase());
      if (existing) return alert("Ye Gmail pehle se registered hai! Kripya Sign In karein.");

      const newUser = { id: Date.now(), name, phone, gmail, pass, regDate: new Date().toLocaleDateString() };
      registeredUsers.push(newUser);
      currentUser = newUser;
      saveDB();
      closeAuthModal();
      alert(`Swagat hai ${name}! Registration successfully complete.`);
    }

    function loginUser() {
      const gmail = document.getElementById('loginGmail').value.trim();
      const pass = document.getElementById('loginPass').value.trim();

      const user = registeredUsers.find(u => u.gmail.toLowerCase() === gmail.toLowerCase() && u.pass === pass);
      if (user) {
        currentUser = user;
        saveDB();
        closeAuthModal();
        alert(`Namaste ${user.name}! Login successful.`);
      } else {
        alert("Galat Gmail ya Password! Kripya sahi details dalein.");
      }
    }

    function logoutUser() {
      currentUser = null;
      saveDB();
      alert("Aap logout ho chuke hain.");
    }

    /* --- "Sd" TEXT HATAYA GAYA: CLEAN USER UI --- */
    function updateUserHeaderUI() {
      const sec = document.getElementById('userHeaderSection');
      if (currentUser) {
        sec.innerHTML = `
          <button onclick="logoutUser()" style="background:#ef4444; color:#fff; font-size:10px; padding:5px 7px;">Logout</button>
        `;
      } else {
        sec.innerHTML = `<button class="btn-auth" onclick="openAuthModal()">👤 Sign In</button>`;
      }
    }

    function openAuthModal() {
      document.getElementById('authModal').style.display = 'flex';
      switchAuthTab('signup');
    }
    function closeAuthModal() {
      document.getElementById('authModal').style.display = 'none';
    }

    function switchAuthTab(tab) {
      if (tab === 'signup') {
        document.getElementById('signupFormSection').style.display = 'block';
        document.getElementById('signinFormSection').style.display = 'none';
        document.getElementById('tabSignup').style.borderBottom = '2px solid var(--primary)';
        document.getElementById('tabSignup').style.fontWeight = 'bold';
        document.getElementById('tabSignin').style.borderBottom = 'none';
        document.getElementById('tabSignin').style.fontWeight = 'normal';
      } else {
        document.getElementById('signupFormSection').style.display = 'none';
        document.getElementById('signinFormSection').style.display = 'block';
        document.getElementById('tabSignin').style.borderBottom = '2px solid var(--primary)';
        document.getElementById('tabSignin').style.fontWeight = 'bold';
        document.getElementById('tabSignup').style.borderBottom = 'none';
        document.getElementById('tabSignup').style.fontWeight = 'normal';
      }
    }

    function renderStore() {
      const grid = document.getElementById('productGrid');
      grid.innerHTML = '';
      
      const filtered = activeFilter === 'All' ? products : products.filter(p => p.category === activeFilter);

      filtered.forEach(p => {
        const inStock = p.stock > 0;
        if (!cardQuantities[p.id]) cardQuantities[p.id] = 1;
        const mainPhoto = (p.photos && p.photos.length > 0) ? p.photos[0] : "https://images.unsplash.com/photo-1513151233558-d860c5398176?w=400";
        const mediaCount = (p.photos ? p.photos.length : 0) + (p.video ? 1 : 0);

        grid.innerHTML += `
          <div class="product-card">
            ${p.isGreen ? `<span class="badge-green-certified">🌿 Eco Green</span>` : ''}
            <span class="${inStock ? 'badge-in' : 'badge-out'}">${inStock ? 'In Stock' : 'Out of Stock'}</span>
            
            <div class="card-img-wrapper" onclick="openMediaModal(${p.id})">
              <img src="${mainPhoto}" alt="${p.name}">
              <div class="media-badge">📷 ${mediaCount} Media</div>
            </div>

            <div class="card-body">
              <h3>${p.name}</h3>
              <div class="cat">${p.category}</div>
              <div class="price">₹${p.price}</div>
              
              ${inStock ? `
                <div style="display:flex; justify-content:space-between; align-items:center; margin-top:2px;">
                  <span style="font-size:11px;">Qty:</span>
                  <div class="qty-control">
                    <button class="qty-btn" onclick="changeQty(${p.id}, -1)">-</button>
                    <span class="qty-val" id="qty_${p.id}">${cardQuantities[p.id]}</span>
                    <button class="qty-btn" onclick="changeQty(${p.id}, 1)">+</button>
                  </div>
                </div>
                <div class="btn-group">
                  <button class="btn-primary" onclick="addToCart(${p.id})">Add to Cart</button>
                  <button class="btn-buy" onclick="buyNow(${p.id})">⚡ Buy Now</button>
                </div>
              ` : `<div style="text-align:center; color:red; font-size:10px; font-weight:bold; padding:4px;">Out of Stock</div>`}
            </div>
          </div>
        `;
      });

      const categories = ['All', ...new Set(products.map(p => p.category))];
      document.getElementById('categoryFilters').innerHTML = categories.map(cat => 
        `<button class="filter-btn ${activeFilter === cat ? 'active' : ''}" onclick="filterCat('${cat}')">${cat}</button>`
      ).join('');
    }

    function filterCat(c) {
      activeFilter = c;
      renderStore();
    }

    function changeQty(id, delta) {
      const prod = products.find(p => p.id === id);
      let next = (cardQuantities[id] || 1) + delta;
      if (next < 1) next = 1;
      if (next > prod.stock) next = prod.stock;
      cardQuantities[id] = next;
      const el = document.getElementById(`qty_${id}`);
      if (el) el.innerText = next;
    }

    function addToCart(id) {
      const qty = cardQuantities[id] || 1;
      const prod = products.find(p => p.id === id);
      const exist = cart.find(c => c.id === id);
      if (exist) {
        if (exist.qty + qty > prod.stock) return alert(`Stock limit reached! Max: ${prod.stock}`);
        exist.qty += qty;
      } else {
        cart.push({ id: prod.id, name: prod.name, price: prod.price, qty: qty });
      }
      updateCartBadge();
      alert("Pataka cart me add ho gaya!");
    }

    function buyNow(id) {
      const qty = cardQuantities[id] || 1;
      const prod = products.find(p => p.id === id);
      cart = [{ id: prod.id, name: prod.name, price: prod.price, qty: qty }];
      updateCartBadge();
      openCart();
    }

    function changeCartItemQty(id, delta) {
      const item = cart.find(c => c.id === id);
      const prod = products.find(p => p.id === id);
      if (!item) return;

      const next = item.qty + delta;
      if (next <= 0) {
        cart = cart.filter(c => c.id !== id);
      } else if (next > prod.stock) {
        alert("Stock se zyada pieces nahi le sakte!");
        return;
      } else {
        item.qty = next;
      }
      updateCartBadge();
      openCart();
    }

    function updateCartBadge() {
      const count = cart.reduce((tot, i) => tot + i.qty, 0);
      document.getElementById('cartCount').innerText = count;
    }

    function openCart() {
      const list = document.getElementById('cartItemsList');
      list.innerHTML = '';
      let total = 0;
      if (cart.length === 0) {
        list.innerHTML = `<div style="text-align:center; padding:15px; color:#64748b; font-size:11px;">Cart khali hai</div>`;
      } else {
        cart.forEach(item => {
          const itemTotal = item.price * item.qty;
          total += itemTotal;
          list.innerHTML += `
            <div class="cart-item">
              <div>
                <b>${item.name}</b><br>
                <small>₹${item.price} each</small>
              </div>
              <div style="display:flex; align-items:center; gap:6px;">
                <div class="qty-control">
                  <button class="qty-btn" onclick="changeCartItemQty(${item.id}, -1)">-</button>
                  <span class="qty-val">${item.qty}</span>
                  <button class="qty-btn" onclick="changeCartItemQty(${item.id}, 1)">+</button>
                </div>
                <b style="width:45px; text-align:right;">₹${itemTotal}</b>
              </div>
            </div>
          `;
        });
      }
      document.getElementById('cartTotalPrice').innerText = total;
      document.getElementById('cartModal').style.display = 'flex';
    }

    function closeCart() {
      document.getElementById('cartModal').style.display = 'none';
    }

    /* --- DIRECT ORDER & WHATSAPP ENGINE --- */
    function placeDirectOrder() {
      if (cart.length === 0) return alert("Aapka cart khali hai!");

      if (!currentUser) {
        closeCart();
        openAuthModal();
        alert("Kripya pehle Sign In ya Sign Up karein!");
        return;
      }

      const orderId = generateUnique6DigitOrderId();
      currentActiveOrderId = orderId;
      const totalBill = document.getElementById('cartTotalPrice').innerText;

      cart.forEach(c => {
        const p = products.find(prod => prod.id === c.id);
        if (p && p.stock >= c.qty) p.stock -= c.qty;
      });

      const orderObj = {
        id: orderId,
        name: currentUser.name,
        phone: currentUser.phone,
        gmail: currentUser.gmail || 'N/A',
        address: "Dukaan Se Self-Pickup (Cash)",
        items: [...cart],
        total: totalBill,
        date: new Date().toLocaleDateString(),
        status: 'Packing'
      };

      orders.unshift(orderObj);

      let itemsLines = cart.map(i => `• ${i.name} (Qty: ${i.qty}) = Rs.${i.price * i.qty}`).join("\n");

      let plainWaMsg = `🎆 DHAMAKA CRACKERS SHOP\n` +
                       `ORDER ID: #${orderId}\n` +
                       `--------------------------------\n` +
                       `CUSTOMER DETAILS:\n` +
                       `Name: ${currentUser.name}\n` +
                       `Mobile: ${currentUser.phone}\n` +
                       `Type: Dukaan Direct Cash Pickup\n` +
                       `--------------------------------\n` +
                       `ITEMS BOOKED:\n` +
                       `${itemsLines}\n` +
                       `--------------------------------\n` +
                       `TOTAL BILL: Rs. ${totalBill}\n` +
                       `Status: Placed & Ready for Pickup\n\n` +
                       `📍 Shop: Main Bazar, Near Clock Tower`;

      let encodedUrl = `https://wa.me/${SELLER_WHATSAPP_PHONE}?text=` + encodeURIComponent(plainWaMsg);

      document.getElementById('popupOrderIdDisplay').innerText = `#${orderId}`;
      document.getElementById('btnPopupSellerWa').onclick = function() {
        window.location.href = encodedUrl;
      };

      cart = [];
      updateCartBadge();
      closeCart();
      saveDB();

      // Show Popup with 6-digit ID
      document.getElementById('orderSuccessModal').style.display = 'flex';
    }

    function copyCurrentOrderId() {
      if (!currentActiveOrderId) return;
      navigator.clipboard.writeText(`#${currentActiveOrderId}`).then(() => {
        alert(`Order Code #${currentActiveOrderId} copy ho gaya!`);
      }).catch(() => {
        alert(`Aapka Code hai: #${currentActiveOrderId}`);
      });
    }

    function closeSuccessModal() {
      document.getElementById('orderSuccessModal').style.display = 'none';
    }

    function openSafetyModal() { document.getElementById('safetyModal').style.display = 'flex'; }
    function closeSafetyModal() { document.getElementById('safetyModal').style.display = 'none'; }
    function openSecretPinModal() { document.getElementById('pinModal').style.display = 'flex'; }

    function verifySellerPin() {
      if (document.getElementById('sellerPinInput').value === ADMIN_PIN) {
        document.getElementById('pinModal').style.display = 'none';
        document.getElementById('adminSection').style.display = 'block';
        renderAdminDashboard();
      } else {
        alert("Galat PIN! Access denied.");
      }
    }

    function closeAdmin() {
      document.getElementById('adminSection').style.display = 'none';
    }

    /* --- ADMIN DASHBOARD, USERS DIRECTORY & LIVE TABLES --- */
    function renderAdminDashboard() {
      let totalPcs = 0;
      let totalEstimatedProfit = 0;
      const categoryCounts = {};

      products.forEach(p => {
        categoryCounts[p.category] = (categoryCounts[p.category] || 0) + Number(p.stock);
        totalPcs += Number(p.stock);
        const margin = (Number(p.price) - Number(p.cost || 0));
        totalEstimatedProfit += (margin * Number(p.stock));
      });

      const statsContainer = document.getElementById('categoryStats');
      statsContainer.innerHTML = `
        <div class="stat-card">
          <h4>Total Stock</h4>
          <p>${totalPcs} Pcs</p>
        </div>
        <div class="stat-card" style="border-left-color:#10b981;">
          <h4>Est. Profit</h4>
          <p style="color:#10b981;">₹${totalEstimatedProfit}</p>
        </div>
      `;

      // Live Stock Table
      const stockTableBody = document.querySelector('#stockTable tbody');
      stockTableBody.innerHTML = '';
      products.forEach(p => {
        const isLow = p.stock > 0 && p.stock < 5;
        const isOut = p.stock <= 0;
        stockTableBody.innerHTML += `
          <tr>
            <td>
              <b>${p.name}</b> ${p.isGreen ? '🌿' : ''}<br>
              <small style="color:#64748b;">${(p.photos || []).length} Photos</small>
            </td>
            <td>${p.category}</td>
            <td>₹${p.cost || 0}</td>
            <td style="font-weight:bold; color:var(--primary);">₹${p.price}</td>
            <td>
              ${isOut ? '<span style="color:red; font-weight:bold;">OUT</span>' : 
                (isLow ? `<span style="color:orange; font-weight:bold;">⚠️ ${p.stock}</span>` : 
                `<span style="color:green; font-weight:bold;">${p.stock}</span>`)}
            </td>
            <td>
              <input type="number" id="update_qty_${p.id}" value="${p.stock}" style="width:36px; padding:2px;">
              <button onclick="updateStockPiece(${p.id})" style="background:var(--primary); color:white; padding:2px 4px; font-size:9px;">Save</button>
            </td>
            <td>
              <div style="display:flex; gap:2px;">
                <button onclick="openEditProductModal(${p.id})" style="background:#f59e0b; color:white; padding:2px 5px; font-size:9px;">Edit</button>
                <button onclick="deleteProductById(${p.id})" class="btn-delete" style="padding:2px 5px; font-size:9px;">Del</button>
              </div>
            </td>
          </tr>
        `;
      });

      // Orders Packing Table
      const ordersTableBody = document.querySelector('#ordersTable tbody');
      ordersTableBody.innerHTML = '';
      orders.forEach(o => {
        const isReady = o.status === 'Ready';
        ordersTableBody.innerHTML += `
          <tr onclick="openSellerPackModal('${o.id}')" style="cursor:pointer;">
            <td><b style="color:var(--primary);">#${o.id}</b></td>
            <td>${o.name}</td>
            <td>₹${o.total}</td>
            <td>
              <span class="status-badge ${isReady ? 'status-ready' : 'status-packing'}">
                ${isReady ? 'Ready' : 'Packing'}
              </span>
            </td>
            <td><button style="background:#0284c7; color:#fff; font-size:9px; padding:2px 4px;">Pack</button></td>
          </tr>
        `;
      });

      // Registered Users Directory Table
      const usersTableBody = document.querySelector('#registeredUsersTable tbody');
      usersTableBody.innerHTML = '';
      if (registeredUsers.length === 0) {
        usersTableBody.innerHTML = `<tr><td colspan="4" style="text-align:center; color:#64748b; padding:8px;">Koi registered customer nahi hai.</td></tr>`;
      } else {
        registeredUsers.forEach(u => {
          usersTableBody.innerHTML += `
            <tr>
              <td><b>${u.name}</b></td>
              <td><a href="tel:${u.phone}" style="color:#0284c7;">${u.phone}</a></td>
              <td>${u.gmail}</td>
              <td>${u.regDate || 'N/A'}</td>
            </tr>
          `;
        });
      }

      // Customer Booking Orders
      const tbody = document.querySelector('#customerFullTable tbody');
      tbody.innerHTML = '';
      orders.forEach(o => {
        const itemsList = o.items.map(it => `${it.name} (x${it.qty})`).join(', ');
        tbody.innerHTML += `
          <tr>
            <td><b>#${o.id}</b></td>
            <td>${o.name}</td>
            <td><a href="tel:${o.phone}" style="color:#0284c7;">${o.phone}</a></td>
            <td><small>${itemsList}</small></td>
            <td>₹${o.total}</td>
            <td>${o.date}</td>
            <td><span class="status-badge ${o.status === 'Ready' ? 'status-ready' : 'status-packing'}">${o.status}</span></td>
          </tr>
        `;
      });
    }

    /* --- PRODUCT EDIT & DELETE LOGIC --- */
    function deleteProductById(id) {
      const prod = products.find(p => p.id === id);
      if (!prod) return;
      if (!confirm(`⚠️ KYA AAP "${prod.name}" KO DELETE KARNA CHAHTE HAIN?`)) return;

      products = products.filter(p => p.id !== id);
      cart = cart.filter(c => c.id !== id);
      delete cardQuantities[id];
      saveDB();
      updateCartBadge();
      alert(`Item deleted successfully!`);
    }

    function deleteProductFromModal() {
      const id = Number(document.getElementById('edit_prod_id').value);
      if (!id) return;
      closeEditModal();
      deleteProductById(id);
    }

    function updateStockPiece(id) {
      const newStock = Number(document.getElementById(`update_qty_${id}`).value);
      const prod = products.find(p => p.id === id);
      if (prod) {
        prod.stock = newStock;
        saveDB();
        alert(`${prod.name} stock updated to ${newStock}!`);
      }
    }

    function openEditProductModal(id) {
      const prod = products.find(p => p.id === id);
      if (!prod) return;

      document.getElementById('edit_prod_id').value = prod.id;
      document.getElementById('edit_prod_name').value = prod.name;
      document.getElementById('edit_prod_category').value = prod.category;
      document.getElementById('edit_prod_cost').value = prod.cost || 0;
      document.getElementById('edit_prod_price').value = prod.price;
      document.getElementById('edit_prod_stock').value = prod.stock;

      const previewContainer = document.getElementById('editPhotosPreviewContainer');
      previewContainer.innerHTML = '';
      uploadedEditPhotos = [...(prod.photos || [])];

      uploadedEditPhotos.forEach(src => {
        const img = document.createElement('img');
        img.src = src;
        previewContainer.appendChild(img);
      });

      document.getElementById('editProductModal').style.display = 'flex';
    }

    function closeEditModal() {
      document.getElementById('editProductModal').style.display = 'none';
    }

    function saveEditedProduct() {
      const id = Number(document.getElementById('edit_prod_id').value);
      const prod = products.find(p => p.id === id);
      if (!prod) return;

      const name = document.getElementById('edit_prod_name').value.trim();
      const category = document.getElementById('edit_prod_category').value;
      const cost = Number(document.getElementById('edit_prod_cost').value);
      const price = Number(document.getElementById('edit_prod_price').value);
      const stock = Number(document.getElementById('edit_prod_stock').value);

      if (!name || isNaN(price) || isNaN(stock)) return alert("Sahi name aur price dalein!");

      prod.name = name;
      prod.category = category;
      prod.cost = cost;
      prod.price = price;
      prod.stock = stock;
      if (uploadedEditPhotos.length > 0) prod.photos = uploadedEditPhotos;

      saveDB();
      closeEditModal();
      alert(`"${name}" updated successfully!`);
    }

    function addProduct() {
      const name = document.getElementById('newProdName').value.trim();
      const category = document.getElementById('newProdCategory').value;
      const isGreen = document.getElementById('newProdGreen').checked;
      const cost = Number(document.getElementById('newProdCost').value) || 0;
      const price = Number(document.getElementById('newProdPrice').value);
      const stock = Number(document.getElementById('newProdStock').value);

      if (!name || isNaN(price) || isNaN(stock)) return alert("Sahi details bharein!");

      products.push({
        id: Date.now(),
        name,
        category,
        isGreen,
        cost,
        price,
        stock,
        photos: uploadedNewPhotos.length > 0 ? uploadedNewPhotos : ["https://images.unsplash.com/photo-1513151233558-d860c5398176?w=400"],
        video: uploadedNewVideo
      });

      document.getElementById('newProdName').value = '';
      document.getElementById('newProdCost').value = '';
      document.getElementById('newProdPrice').value = '';
      document.getElementById('newProdStock').value = '';
      document.getElementById('newProdPhotosInput').value = '';
      document.getElementById('newProdVideoInput').value = '';
      document.getElementById('newPhotosPreviewContainer').innerHTML = '';
      document.getElementById('newVideoStatus').innerText = '';
      uploadedNewPhotos = [];
      uploadedNewVideo = "";

      saveDB();
      alert("Pataka inventory me save ho gaya!");
    }

    /* --- CAMERA & COMPRESSION ENGINE --- */
    function compressImageFile(file, maxWidth = 600, quality = 0.6) {
      return new Promise((resolve) => {
        const reader = new FileReader();
        reader.readAsDataURL(file);
        reader.onload = (event) => {
          const img = new Image();
          img.src = event.target.result;
          img.onload = () => {
            const canvas = document.createElement('canvas');
            let width = img.width;
            let height = img.height;
            if (width > maxWidth) {
              height = Math.round((height * maxWidth) / width);
              width = maxWidth;
            }
            canvas.width = width;
            canvas.height = height;
            canvas.getContext('2d').drawImage(img, 0, 0, width, height);
            resolve(canvas.toDataURL('image/jpeg', quality));
          };
        };
      });
    }

    async function handleNewProductPhotos(input) {
      const files = Array.from(input.files).slice(0, 5);
      const container = document.getElementById('newPhotosPreviewContainer');
      container.innerHTML = 'Compressing...';
      uploadedNewPhotos = [];
      for (let f of files) {
        uploadedNewPhotos.push(await compressImageFile(f));
      }
      container.innerHTML = '';
      uploadedNewPhotos.forEach(src => {
        const img = document.createElement('img');
        img.src = src;
        container.appendChild(img);
      });
    }

    function handleNewProductVideo(input) {
      const file = input.files[0];
      if (!file) return;
      const reader = new FileReader();
      reader.onload = (e) => {
        uploadedNewVideo = e.target.result;
        document.getElementById('newVideoStatus').innerText = `✅ Video Loaded: ${file.name}`;
      };
      reader.readAsDataURL(file);
    }

    async function handleEditProductPhotos(input) {
      const files = Array.from(input.files).slice(0, 5);
      const container = document.getElementById('editPhotosPreviewContainer');
      container.innerHTML = 'Compressing...';
      uploadedEditPhotos = [];
      for (let f of files) {
        uploadedEditPhotos.push(await compressImageFile(f));
      }
      container.innerHTML = '';
      uploadedEditPhotos.forEach(src => {
        const img = document.createElement('img');
        img.src = src;
        container.appendChild(img);
      });
    }

    /* --- SELLER PACK MODAL ('ORDER IS READY' DISPATCHER) --- */
    function openSellerPackModal(orderId) {
      const order = orders.find(o => o.id === orderId);
      if (!order) return;
      activeInspectingOrderId = orderId;

      const detailsDiv = document.getElementById('sellerPackDetails');
      const isReady = order.status === 'Ready';

      let itemsHtml = order.items.map((it, idx) => `
        <label style="display:flex; align-items:center; justify-content:space-between; background:#f8fafc; padding:5px 8px; border-radius:4px; margin-bottom:3px; border:1px solid #e2e8f0; font-size:10px;">
          <div>
            <input type="checkbox" id="pack_check_${idx}" ${isReady ? 'checked disabled' : ''} style="margin-right:5px;">
            <b>${it.name}</b>
          </div>
          <span style="background:#e2e8f0; padding:2px 5px; border-radius:3px; font-weight:bold;">Qty: ${it.qty}</span>
        </label>
      `).join('');

      detailsDiv.innerHTML = `
        <div style="margin-bottom:8px; background:#eff6ff; padding:6px; border-radius:4px; font-size:11px;">
          <p><b>Order ID:</b> #${order.id} | <b>Date:</b> ${order.date}</p>
          <p><b>Customer:</b> ${order.name} | <b>Phone:</b> ${order.phone}</p>
          <p><b>Pickup:</b> Dukaan Direct Cash Pickup</p>
        </div>
        <h4 style="margin-bottom:4px; font-size:11px;">Items Checklist:</h4>
        ${itemsHtml}
        <div style="font-size:12px; font-weight:bold; margin-top:6px; text-align:right;">Total Bill: ₹${order.total}</div>
      `;

      const btn = document.getElementById('btnOrderReadyAction');
      if (isReady) {
        btn.innerText = "✅ Order Already Marked as READY";
        btn.disabled = true;
        btn.style.background = "#94a3b8";
      } else {
        btn.innerText = "✅ Saaman Pack Ho Gaya - Click 'Order is Ready'";
        btn.disabled = false;
        btn.style.background = "var(--green)";
      }

      document.getElementById('sellerPackModal').style.display = 'flex';
    }

    function closeSellerPackModal() {
      document.getElementById('sellerPackModal').style.display = 'none';
      activeInspectingOrderId = null;
    }

    function markOrderReadyAndNotify() {
      if (!activeInspectingOrderId) return;
      const order = orders.find(o => o.id === activeInspectingOrderId);
      if (!order) return;

      order.status = 'Ready';
      saveDB();

      const waMsg = `Hello *${order.name}*,%0A%0A` +
                    `Order ID: *#${order.id}*%0A` +
                    `*YOUR ORDER IS READY!*%0A%0A` +
                    `Aapka patako ka saaman pack ho chuka hai. Kripya dukaan par aakar cash dekar apna order collect karein.%0A` +
                    `*Total Bill:* Rs. ${order.total}%0A%0A` +
                    `_Dhamaka Crackers Store, Main Bazar_`;

      window.open(`https://wa.me/91${order.phone}?text=${waMsg}`, '_blank');
      closeSellerPackModal();
      alert(`Order #${order.id} marked as READY aur customer ko notification dispatch ho gaya!`);
    }

    /* --- MEDIA VIEWER --- */
    function openMediaModal(id) {
      const prod = products.find(p => p.id === id);
      if (!prod) return;

      document.getElementById('galleryTitle').innerText = prod.name;
      const viewer = document.getElementById('mainGalleryViewer');
      const thumbs = document.getElementById('mediaThumbnails');
      thumbs.innerHTML = '';

      let allMedia = [];
      (prod.photos || []).forEach((img, i) => allMedia.push({ type: 'img', src: img, label: `P${i+1}` }));
      if (prod.video) allMedia.push({ type: 'video', src: prod.video, label: `Video` });

      if (allMedia.length === 0) {
        allMedia.push({ type: 'img', src: 'https://images.unsplash.com/photo-1513151233558-d860c5398176?w=400', label: 'Preview' });
      }

      function displayItem(item) {
        if (item.type === 'img') {
          viewer.innerHTML = `<img src="${item.src}" alt="preview">`;
        } else {
          viewer.innerHTML = `<video controls autoplay style="max-height:100%; width:100%;"><source src="${item.src}"></video>`;
        }
      }

      allMedia.forEach((item, index) => {
        const thumb = document.createElement('div');
        thumb.className = `thumb ${index === 0 ? 'active' : ''}`;
        thumb.style.display = 'flex';
        thumb.style.alignItems = 'center';
        thumb.style.justifyContent = 'center';
        thumb.style.background = '#0f172a';
        thumb.style.color = '#fff';
        thumb.style.fontSize = '8px';
        thumb.innerText = item.label;
        thumb.onclick = () => {
          document.querySelectorAll('.thumb').forEach(t => t.classList.remove('active'));
          thumb.classList.add('active');
          displayItem(item);
        };
        thumbs.appendChild(thumb);
      });

      displayItem(allMedia[0]);
      document.getElementById('mediaModal').style.display = 'flex';
    }

    function closeMediaModal() {
      document.getElementById('mediaModal').style.display = 'none';
      document.getElementById('mainGalleryViewer').innerHTML = '';
    }

    /* --- CSV EXPORTERS --- */
    function exportDataToCSV() {
      let csv = "data:text/csv;charset=utf-8,ID,Name,Category,Cost,Price,Stock\n";
      products.forEach(p => { csv += `"${p.id}","${p.name}","${p.category}","${p.cost}","${p.price}","${p.stock}"\n`; });
      const link = document.createElement("a");
      link.setAttribute("href", encodeURI(csv));
      link.setAttribute("download", `Crackers_Stock_${new Date().toISOString().slice(0,10)}.csv`);
      document.body.appendChild(link);
      link.click();
      document.body.removeChild(link);
    }

    function exportCustomerDataToCSV() {
      if (orders.length === 0) return alert("Koi order data nahi hai!");
      let csv = "data:text/csv;charset=utf-8,Order ID,Customer Name,Phone,Items,Total,Date,Status\n";
      orders.forEach(o => {
        const itemsStr = o.items.map(it => `${it.name} (x${it.qty})`).join(' | ').replace(/"/g, '""');
        csv += `"#${o.id}","${o.name}","${o.phone}","${itemsStr}","${o.total}","${o.date}","${o.status}"\n`;
      });
      const link = document.createElement("a");
      link.setAttribute("href", encodeURI(csv));
      link.setAttribute("download", `Orders_Data.csv`);
      document.body.appendChild(link);
      link.click();
      document.body.removeChild(link);
    }

    function exportRegisteredUsersToCSV() {
      if (registeredUsers.length === 0) return alert("Abhi tak koi registered customer nahi hai!");
      let csv = "data:text/csv;charset=utf-8,Customer Name,Mobile Phone,Gmail Address,Registered Date\n";
      registeredUsers.forEach(u => {
        csv += `"${u.name}","${u.phone}","${u.gmail}","${u.regDate || 'N/A'}"\n`;
      });
      const link = document.createElement("a");
      link.setAttribute("href", encodeURI(csv));
      link.setAttribute("download", `Registered_Customers_${new Date().toISOString().slice(0,10)}.csv`);
      document.body.appendChild(link);
      link.click();
      document.body.removeChild(link);
    }

    function switchLanguage(l) {
      // Language Handler
    }

    updateUserHeaderUI();
    renderStore();
  </script>
</body>
</html>
