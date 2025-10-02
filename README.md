# newp<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>JKS Group Multi-Service Platform</title>
  <style>
    /* Full CSS styling with dark neon theme as described */
    body {
      background: #20242b;
      color: #fff;
      font-family: 'Segoe UI', Arial, sans-serif;
      margin: 0; padding: 0;
    }
    header, nav {
      display: flex;
      justify-content: center;
      gap: 20px;
      background: #141b29;
      padding: 16px 0;
      position: sticky;
      top: 0;
      z-index: 1000;
      box-shadow: 0 2px 8px rgba(0,0,0,0.7);
    }
    header {
      font-weight: 700;
      font-size: 2.2rem;
      color: #00e1ff;
      letter-spacing: 2px;
      text-shadow: 0 0 20px #0fccfcbb;
    }
    nav button {
      background: none;
      border: 2.5px solid #0fccfc;
      border-radius: 10px;
      color: #0fccfc;
      padding: 12px 22px;
      font-weight: 700;
      font-size: 1rem;
      cursor: pointer;
      user-select: none;
      transition: all 0.3s ease;
    }
    nav button:hover {
      background-color: #0fccfc;
      color: #202733;
    }
    main {
      max-width: 1100px;
      margin: 35px auto 70px;
      padding: 0 15px;
    }
    .dashboard {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(230px, 1fr));
      gap: 40px 50px;
      justify-content: center;
      margin-bottom: 32px;
    }
    .folder-card, .service-card, .category-card, .event-card {
      background: #23273b;
      border: 3px solid #ffe27f;
      border-radius: 15px;
      padding: 44px 24px;
      font-weight: 700;
      font-size: 1.18em;
      color: #ffe27f;
      cursor: pointer;
      user-select: none;
      text-align: center;
      box-shadow: 0 0 18px 5px #ffec8e8a, 0 5px 36px #101722bf;
      transition: all 0.3s ease;
      min-width: 230px;
    }
    .folder-card:hover, .service-card:hover, .category-card:hover, .event-card:hover {
      background-color: #ffe27f;
      color: #202733;
      border-color: #0fccfc;
      box-shadow: 0 0 28px 9px #0fccfcbb, 0 6px 36px #23536faa;
      transform: scale(1.06);
    }
    .section-title {
      font-size: 1.68em;
      font-weight: 700;
      text-align: center;
      color: #ffe27f;
      margin: 18px 0 26px 0;
      letter-spacing: 1.3px;
      text-shadow: 0 0 16px #ffe27fac;
    }
    .service-list, .category-list, .events-categories {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 28px 42px;
      justify-content: center;
      margin-bottom: 36px;
      margin-top: 20px;
    }
    .back-btn {
      margin: 32px auto 24px auto;
      background-color: #ffe27f;
      color: #222a39;
      border: 2.5px solid #ffe27f;
      font-weight: 900;
      font-size: 1.24em;
      padding: 18px 68px;
      border-radius: 15px;
      box-shadow: 2px 2px 24px #fff88499;
      cursor: pointer;
      width: max-content;
      text-align: center;
      transition: all 0.3s ease;
      user-select: none;
    }
    .back-btn:hover {
      background-color: #00e1ff;
      border-color: #00e1ff;
      color: #fff;
      box-shadow: 0 0 36px 14px #00e1ffcc;
    }
    form.contact-form {
      max-width: 480px;
      background-color: #172440;
      padding: 30px 34px;
      margin: 20px auto 60px auto;
      border-radius: 16px;
      border: 2px solid #00e1ff90;
      color: #afdfff;
      font-size: 1.1em;
    }
    form.contact-form label {
      display: block;
      margin-bottom: 10px;
      font-weight: 700;
      color: #8ec7ff;
    }
    form.contact-form input, form.contact-form textarea, form.contact-form select {
      width: 100%;
      padding: 14px 16px;
      font-size: 16px;
      border-radius: 10px;
      background-color: #0f1e3a;
      border: 1.7px solid #38abf7;
      color: #cde4ff;
      margin-bottom: 24px;
      box-sizing: border-box;
      resize: vertical;
    }
    form.contact-form input:focus, form.contact-form textarea:focus, form.contact-form select:focus {
      outline: none;
      background-color: #1b3e7a;
      border-color: #00aeff;
    }
    form.contact-form button {
      width: 100%;
      padding: 18px 0;
      font-weight: 900;
      font-size: 1.28em;
      color: #192b3a;
      background-color: #00e1ff;
      border: none;
      border-radius: 14px;
      cursor: pointer;
      transition: background-color 0.28s ease;
    }
    form.contact-form button:hover {
      background-color: #3de1ff;
    }
    #map {
      max-width: 640px;
      height: 460px;
      border-radius: 14px;
      margin: 20px auto 50px auto;
      border: 3px solid #00e1ff94;
      box-shadow: 0 0 38px 20px #00e1ff55;
    }
    video#video {
      max-width: 100%;
      border-radius: 14px;
      border: 2px solid #00e1ff8f;
      margin-top: 20px;
    }
    @media (max-width: 900px) {
      .dashboard,
      .service-list,
      .category-list,
      .events-categories {
        grid-template-columns: 1fr;
        gap: 20px;
      }
      .folder-card,
      .service-card,
      .category-card,
      .event-card {
        width: 92%;
        padding: 30px 18px;
        font-size: 1.15em;
      }
    }
  </style>
</head>
<body>
<header>JKS Group of Business</header>
<nav>
  <button onclick="showPage('dashboard')">Dashboard</button>
  <button onclick="showPage('profile')">Profile</button>
  <button onclick="showPage('wallet')">Wallet</button>
  <button onclick="showPage('orders')">Orders</button>
  <button onclick="showPage('camera')">Camera</button>
  <button onclick="showPage('maps')">Google Maps</button>
</nav>
<main>
  <section id="dashboard" class="dashboard"></section>

  <section id="profile" style="display:none;">
    <h2 class="section-title">Profile</h2>
    <form class="contact-form">
      <label>Name:</label><input id="profileName" type="text" />
      <label>Email:</label><input id="profileEmail" type="email" />
      <label>Phone:</label><input id="profilePhone" type="tel" />
      <label>Address:</label><textarea id="profileAddress" rows="3"></textarea>
      <button type="button" onclick="alert('Profile saved!')">Save</button>
    </form>
    <button class="back-btn" onclick="showPage('dashboard')">Back to Dashboard</button>
  </section>

  <section id="wallet" style="display:none;">
    <h2 class="section-title">Wallet</h2>
    <p>Balance: ₹<span id="walletBalance">10000</span></p>
    <form class="contact-form" onsubmit="addMoney(event)">
      <label>Add Money:</label>
      <input id="addMoneyInput" type="number" min="1" required />
      <button type="submit">Add Funds</button>
    </form>
    <button class="back-btn" onclick="showPage('dashboard')">Back to Dashboard</button>
  </section>

  <section id="orders" style="display:none;">
    <h2 class="section-title">Orders</h2>
    <table style="width: 100%; border-collapse: collapse; background: #1c2238; color: #fff; border-radius: 8px; overflow: hidden;">
      <thead>
        <tr>
          <th style="padding: 14px;">Order ID</th>
          <th>Product / Service</th>
          <th>Status</th>
        </tr>
      </thead>
      <tbody>
        <tr><td>001</td><td>Pizza</td><td style="color: #3eff9d;">Delivered</td></tr>
        <tr><td>002</td><td>Car Wash</td><td style="color: #ffe27f;">Pending</td></tr>
        <tr><td>003</td><td>Loan Enquiry</td><td style="color: #0bcfff;">In Progress</td></tr>
      </tbody>
    </table>
    <button class="back-btn" onclick="showPage('dashboard')">Back to Dashboard</button>
  </section>

  <section id="serviceView" style="display:none; flex-direction: column; align-items: center;">
    <div class="section-title" id="serviceTitle"></div>
    <div class="service-list" id="serviceList"></div>
    <form class="contact-form" id="contactForm" style="display:none;">
      <h3 id="contactTitle"></h3>
      <label>Name:</label><input type="text" id="userName" required />
      <label>Mobile:</label><input type="tel" id="userPhone" maxlength="10" pattern="[6-9][0-9]{9}" required />
      <label>Message:</label><textarea id="userMessage" rows="4" required></textarea>
      <button type="button" onclick="submitContactForm()">Submit WhatsApp</button>
      <button type="button" class="back-btn" onclick="backToServiceList()">Back to Services</button>
    </form>
    <button class="back-btn" onclick="showPage('dashboard')">Back to Dashboard</button>
  </section>

  <section id="eventsView" style="display:none; flex-direction: column; align-items: center;">
    <div class="section-title" id="eventsCategoryTitle"></div>
    <div class="events-categories" id="eventsCategories"></div>
    <div class="service-list" id="eventsServiceList"></div>
    <form id="eventContactForm" class="contact-form" style="display:none;">
      <h3 id="eventsContactTitle"></h3>
      <label>Name:</label>
      <input id="eventsUserName" type="text" required />
      <label>Mobile:</label>
      <input id="eventsUserPhone" type="tel" maxlength="10" pattern="[6-9][0-9]{9}" required />
      <div id="customFields"></div>
      <label>Message:</label>
      <textarea id="eventsUserMessage" rows="4" required></textarea>
      <button type="button" onclick="submitEventsForm()">Submit WhatsApp</button>
      <button type="button" class="back-btn" onclick="backToEventsCategory()">Back</button>
    </form>
    <button class="back-btn" onclick="showPage('dashboard')">Back to Dashboard</button>
  </section>

  <section id="ecomView" style="display:none;">
    <div class="section-title">My E-commerce</div>
    <nav style="margin-bottom: 18px;">
      <button onclick="openEcomCategory('Groceries')">Groceries</button>
      <button onclick="openEcomCategory('Food')">Food</button>
      <button onclick="openEcomCategory('Pharmacy')">Pharmacy</button>
      <button onclick="showPage('camera')" style="margin-left: 25px;">Camera</button>
      <button onclick="showPage('maps')">Google Maps</button>
    </nav>
    <div class="service-list" id="ecomServiceList"></div>
    <form id="ecomOrderForm" class="contact-form" style="display:none;">
      <h3 id="ecomOrderTitle"></h3>
      <label>Name:</label>
      <input name="name" type="text" required />
      <label>Mobile:</label>
      <input name="phone" type="tel" maxlength="10" pattern="[6-9][0-9]{9}" required />
      <label>Order Details:</label>
      <textarea name="orderDetails" rows="3" required></textarea>
      <label>Delivery Address:</label>
      <textarea name="address" required></textarea>
      <button type="submit">Order WhatsApp</button>
      <button type="button" class="back-btn" onclick="backToEcomServices()">Back</button>
    </form>
    <button class="back-btn" onclick="showPage('dashboard')">Back to Dashboard</button>
  </section>

  <section id="camera" style="display:none; text-align:center;">
    <h2 class="section-title">Camera</h2>
    <video id="video" autoplay muted playsinline></video>
    <div style="margin:20px;">
      <button onclick="switchCamera()">Switch Camera</button>
      <button onclick="capturePhoto()">Capture Photo</button>
    </div>
    <canvas id="canvas" style="display:none;"></canvas>
    <div id="photoOutput" style="margin-top:20px;"></div>
    <button class="back-btn" onclick="showPage('dashboard')">Back</button>
  </section>

  <section id="maps" style="display:none; text-align:center;">
    <h2 class="section-title">Google Maps</h2>
    <div id="map" style="height: 450px; max-width: 640px; margin: auto; border-radius: 14px; border: 3px solid #00e1ff94; box-shadow: 0 0 35px 18px #00e1ff54;"></div>
    <button class="back-btn" onclick="showPage('dashboard')">Back</button>
  </section>
</main>
<script src="https://maps.googleapis.com/maps/api/js?key=YOUR_GOOGLE_MAPS_API_KEY&callback=initMap" async defer></script>
<script>
  const folders = [
    {id: 'ecommerce', label: 'My E-commerce'},
    {id: 'events', label: 'Events & Catering'},
    {id: 'courier', label: 'Courier & Ride Booking'},
    {id: 'job', label: 'Job Consultancy & Services'},
    {id: 'tours', label: 'Tours & Travels'},
    {id: 'realestate', label: 'Real Estate & Construction'},
    {id: 'investment', label: 'Investment & Business'},
    {id: 'loans', label: 'Loans & Insurance'},
    {id: 'home', label: 'Home Services'}
  ];

  const moduleServices = {
    courier: ['Courier Booking', 'Ride Booking', 'Tracking', 'Support', 'Rental Vehicles'],
    job: ['Job Search', 'Post Resume', 'Local Jobs', 'Non-Local Jobs', 'PG & Hostel', 'Services Marketplace'],
    tours: ['Tour Bookings', 'Custom & Regular Tours', 'Stay Booking', 'Vehicle Booking', 'Train/Bus/Flight Tickets'],
    realestate: ['Buy', 'Sell', 'Rent', 'Key Services', 'Construction', 'Industry'],
    investment: ['Gold', 'Silver', 'Real Estate', 'Business Opportunity', 'Mutual Funds'],
    loans: ['Loan Enquiry', 'Car Insurance', 'Bike Insurance', 'Housing Loans', 'Personal Loans', 'Health Insurance'],
    home: ['CC Camera Installation', 'Computer Repair', 'Car Wash', 'Mobile Repair', 'Chef Services', 'Bouncers', 'Bike Mechanic', 'Car Mechanic', 'Electrician', 'Painter', 'Plumber', 'Driver']
  };

  const ecom = {
    Groceries: ['Milk', 'Meat', 'Fruits', 'Vegetables', 'Flowers', 'Others'],
    Food: ['Biriyani', 'Tiffins', 'Ice Cream', 'Pizza', 'Burgers', 'Rolls'],
    Pharmacy: ['Medicines', 'Health Products', 'Supplements', 'Care Products']
  };

  const eventsCategories = {
    package: [
      {name: "Silver", amount: "50k - 160k"},
      {name: "Gold", amount: "150k - 300k"},
      {name: "Diamond", amount: "500k - 5M"},
      {name: "Platinum", amount: "500k - 800k"}
    ],
    customized: [
      "Decoration", "Catering", "Photography & Videography", "Anchor & Actors", "DJ & Singers", "Guest House", "Chocolate & Cake", "Games & Entertainment", "Jewellery", "Invitation Cards", "Vehicles", "Return Gifts", "Makeup Artist", "Mehandi Artist", "Clothing & Accessories"
    ],
    premium: [
      "Decoration", "Catering", "Photography & Videography", "Anchor & Actors", "DJ & Singers", "Guest House", "Chocolate & Cake", "Games & Entertainment", "Jewellery", "Invitation Cards", "Vehicles", "Return Gifts", "Makeup Artist", "Mehandi Artist", "Clothing & Accessories"
    ]
  };

  let currentModule = '', currentService = '', currentEventCategory = '', currentEventService = '', currentEcomCategory = '';

  function showPage(page) {
    document.querySelectorAll('main > section').forEach(s => s.style.display = 'none');
    document.getElementById(page).style.display = 'block';
    if(page === 'dashboard') renderDashboard();
    if(page === 'events') openEventsDashboard();
    if(page === 'ecommerce') openEcomDashboard();
    if(page === 'serviceView') {} // can expand if needed
    if(page ==='camera') startCamera();
    if(page === 'maps' && !window.mapLoaded) {
      initMap();
      window.mapLoaded = true;
    }
  }

  function renderDashboard() {
    const dash = document.getElementById('dashboard');
    dash.innerHTML = '';
    folders.forEach(f => {
      const d = document.createElement('div');
      d.className = 'folder-card';
      d.textContent = f.label;
      d.onclick = () => openModule(f.id);
      dash.appendChild(d);
    });
  }

  function openModule(mod) {
    currentModule = mod;
    currentService = '';
    if(mod === 'events') {
      openEventsDashboard();
      return;
    }
    if(mod === 'ecommerce') {
      openEcomDashboard();
      return;
    }
    const listEl = document.getElementById('serviceList');
    listEl.innerHTML = '';
    (moduleServices[mod] || []).forEach(svc => {
      const d = document.createElement('div');
      d.className = 'service-card';
      d.textContent = svc;
      d.onclick = () => openContactForm(svc);
      listEl.appendChild(d);
    });
    document.getElementById('serviceTitle').textContent = folders.find(f => f.id === mod).label;
    showPage('serviceView');
  }

  function openContactForm(service) {
    currentService = service;
    document.getElementById('serviceList').style.display = 'none';
    const form = document.getElementById('contactForm');
    form.style.display = 'block';
    document.getElementById('contactTitle').textContent = `Contact for ${service}`;
    clearInputs(['userName', 'userPhone', 'userMessage']);
  }

  function backToServiceList() {
    document.getElementById('contactForm').style.display = 'none';
    document.getElementById('serviceList').style.display = 'grid';
  }

  function submitContactForm() {
    const name = document.getElementById('userName').value.trim();
    const phone = document.getElementById('userPhone').value.trim();
    const message = document.getElementById('userMessage').value.trim();
    if (!name || !phone || !message) {
      alert('Please fill all fields.');
      return;
    }
    const encodedMessage = `Name: ${encodeURIComponent(name)}%0APhone: ${encodeURIComponent(phone)}%0AService: ${encodeURIComponent(currentService)}%0AMessage: ${encodeURIComponent(message)}`;
    window.open(`https://wa.me/8977143043?text=${encodedMessage}`, '_blank');
  }

  function clearInputs(ids) {
    ids.forEach(id => {
      const el = document.getElementById(id);
      if(el) el.value = '';
    });
  }

  // Events and Catering functions
  function openEventsDashboard() {
    currentEventCategory = '';
    currentEventService = '';
    document.getElementById('dashboard').style.display = 'none';
    document.getElementById('serviceView').style.display = 'none';
    document.getElementById('ecomView').style.display = 'none';
    document.getElementById('eventsView').style.display = 'flex';
    const catsDiv = document.getElementById('eventsCategories');
    catsDiv.innerHTML = '';
    ['package','customized','premium'].forEach(cat => {
      let catDiv = document.createElement('div');
      catDiv.className = 'category-card';
      catDiv.textContent = cat.charAt(0).toUpperCase() + cat.slice(1);
      catDiv.onclick = () => openEventsCategory(cat);
      catsDiv.appendChild(catDiv);
    });
    document.getElementById('eventsServiceList').innerHTML = '';
    document.getElementById('eventContactForm').style.display = 'none';
    document.getElementById('eventsCategoryTitle').textContent='Events & Catering Categories';
  }

  function openEventsCategory(cat) {
    currentEventCategory = cat;
    currentEventService = '';
    const svcList = document.getElementById('eventsServiceList');
    document.getElementById('eventContactForm').style.display = 'none';
    svcList.style.display = 'grid';
    svcList.innerHTML = '';
    if(cat === "package") {
      eventsCategories.package.forEach(pkg => {
        let div = document.createElement('div');
        div.className = 'service-card';
        div.textContent = `${pkg.name} (${pkg.amount})`;
        div.onclick = () => openEventContactForm(pkg.name, cat);
        svcList.appendChild(div);
      });
    } else {
      eventsCategories[cat].forEach(svc => {
        let div = document.createElement('div');
        div.className = 'service-card';
        div.textContent = svc;
        div.onclick = () => openEventContactForm(svc, cat);
        svcList.appendChild(div);
      });
    }
    document.getElementById('eventsCategoryTitle').textContent = cat.charAt(0).toUpperCase() + cat.slice(1) + ' Services';
  }

  function openEventContactForm(service, cat) {
    currentEventService = service;
    document.getElementById('eventsServiceList').style.display = 'none';
    let form = document.getElementById('eventContactForm');
    form.style.display = 'block';
    document.getElementById('eventsContactTitle').textContent = 'Contact for ' + service;
    document.getElementById('eventsUserName').value = '';
    document.getElementById('eventsUserPhone').value = '';
    document.getElementById('eventsUserMessage').value = '';
    const customFields = document.getElementById('customFields');
    if (cat === 'customized') {
      customFields.innerHTML = `
      <label>Budget:</label>
      <select id="eventsBudget" required>
        <option value="">Select Budget</option>
        <option>10k to 50k</option>
        <option>50k to 1L</option>
        <option>1L to 5L</option>
        <option>5L to 10L</option>
        <option>Above 10L</option>
      </select>
      <label>Capacity:</label>
      <select id="eventsCapacity" required>
        <option value="">Select Capacity</option>
        <option>5-30 people</option>
        <option>30-60 people</option>
        <option>60-90 people</option>
        <option>90-130 people</option>
        <option>Above 130 people</option>
      </select>`;
    } else {
      customFields.innerHTML = '';
    }
  }

  function backToEventsCategory() {
    document.getElementById('eventContactForm').style.display = 'none';
    document.getElementById('eventsServiceList').style.display = 'grid';
  }

  function submitEventsForm() {
    const name = document.getElementById('eventsUserName').value.trim();
    const phone = document.getElementById('eventsUserPhone').value.trim();
    const message = document.getElementById('eventsUserMessage').value.trim();
    let budget = '';
    let capacity = '';
    if(currentEventCategory === 'customized') {
      budget = document.getElementById('eventsBudget').value;
      capacity = document.getElementById('eventsCapacity').value;
      if(!budget || !capacity) {
        alert('Please select budget and capacity');
        return;
      }
    }
    if(!name || !phone || !message) {
      alert('Please fill all fields');
      return;
    }
    let whatsappMsg = `Name: ${encodeURIComponent(name)}%0APhone: ${encodeURIComponent(phone)}%0AService: ${encodeURIComponent(currentEventService)}%0ACategory: ${encodeURIComponent(currentEventCategory)}%0AMessage: ${encodeURIComponent(message)}`;
    if(budget) whatsappMsg += `%0ABudget: ${encodeURIComponent(budget)}`;
    if(capacity) whatsappMsg += `%0ACapacity: ${encodeURIComponent(capacity)}`;
    window.open(`https://wa.me/8977143043?text=${whatsappMsg}`, '_blank');
  }

  // E-commerce functions
  function openEcomDashboard() {
    currentEcomCategory = '';
    document.getElementById('dashboard').style.display = 'none';
    document.getElementById('serviceView').style.display = 'none';
    document.getElementById('eventsView').style.display = 'none';
    document.getElementById('ecomView').style.display = 'flex';
    document.getElementById('ecomServiceList').innerHTML = '';
    document.getElementById('ecomOrderForm').style.display = 'none';
  }

  function openEcomCategory(cat) {
    currentEcomCategory = cat;
    const svcList = document.getElementById('ecomServiceList');
    svcList.innerHTML = '';
    (ecom[cat] || []).forEach(service => {
      const d = document.createElement('div');
      d.className = 'service-card';
      d.textContent = service;
      d.onclick = () => openEcomOrderForm(cat, service);
      svcList.appendChild(d);
    });
    document.getElementById('ecomOrderForm').style.display = 'none';
    svcList.style.display = 'grid';
  }

  function openEcomOrderForm(cat, service) {
    document.getElementById('ecomOrderForm').style.display = 'block';
    document.getElementById('ecomOrderTitle').textContent = `Order ${service} in ${cat}`;
    document.getElementById('ecomOrderForm').onsubmit = e => submitOrderForm(e, cat, service);
  }

  function backToEcomServices() {
    document.getElementById('ecomOrderForm').style.display = 'none';
  }

  function submitOrderForm(e, cat, service) {
    e.preventDefault();
    const form = e.target;
    const name = form.name.value.trim();
    const phone = form.phone.value.trim();
    const details = form.orderDetails.value.trim();
    const address = form.address.value.trim();
    if (!name || !phone || !details || !address) {
      alert('Please fill all order form fields');
      return;
    }
    let msg = `Order from JKS E-commerce%0ACategory: ${cat}%0AProduct: ${service}%0AName: ${name}%0APhone: ${phone}%0AOrder Details: ${details}%0AAddress: ${address}`;
    window.open(`https://wa.me/8977143043?text=${encodeURIComponent(msg)}`, '_blank');
  }

  // Camera
  let currentStream = null;
  let usingFrontCamera = true;

  function startCamera() {
    const video = document.getElementById('video');
    if(currentStream) currentStream.getTracks().forEach(t => t.stop());
    navigator.mediaDevices.getUserMedia({ video: { facingMode: usingFrontCamera ? 'user' : 'environment' } }).then((stream) => {
      currentStream = stream;
      video.srcObject = stream;
      video.play();
    }).catch(() => alert('Camera access denied or not available'));
  }

  function switchCamera() {
    usingFrontCamera = !usingFrontCamera;
    startCamera();
  }

  function capturePhoto() {
    const video = document.getElementById('video');
    const canvas = document.getElementById('canvas');
    canvas.width = video.videoWidth;
    canvas.height = video.videoHeight;
    const ctx = canvas.getContext('2d');
    ctx.drawImage(video, 0, 0);
    const dataUrl = canvas.toDataURL('image/png');
    document.getElementById('photoOutput').innerHTML = `<img src="${dataUrl}" style="max-width: 320px; border-radius: 12px;">`;
  }

  // Wallet
  function addMoney(e) {
    e.preventDefault();
    const amountInput = document.getElementById('addMoneyInput');
    const amount = parseFloat(amountInput.value);
    if(isNaN(amount) || amount <= 0) {
      alert('Enter a valid amount');
      return;
    }
    const balElem = document.getElementById('walletBalance');
    let balance = parseFloat(balElem.textContent);
    balance += amount;
    balElem.textContent = balance.toFixed(2);
    alert(`₹${amount.toFixed(2)} added to wallet.`);
    amountInput.value = '';
  }

  // Google Maps
  function initMap() {
    new google.maps.Map(document.getElementById('map'), {
      center: { lat: 17.3850, lng: 78.4867 },
      zoom: 13
    });
  }

  document.addEventListener('DOMContentLoaded', () => {
    showPage('dashboard');
  });
</script>
</body>
</html>
