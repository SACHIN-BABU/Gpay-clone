# Gpay-clone
## Date:10-07-2025

# HTML Code
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>GPay UI Clone - Educational Finance Project</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="gpay-container">
    <header>
      <!-- Official GPay icon SVG (brand-compliant, inline for sharpness) -->
      <img src="Gpay.png" alt="Google Pay" class="gpay-logo">
      <span class="gpay-title">Google Pay</span>
    </header>
    <nav class="gpay-tabs">
      <button class="tab active" onclick="showTab('pay')">Pay</button>
      <button class="tab" onclick="showTab('recharge')">Mobile Recharge</button>
      <button class="tab" onclick="showTab('offers')">Offers</button>
      <button class="tab" onclick="showTab('rewards')">Rewards</button>
    </nav>

    <main>
      <!-- Pay Tab: Replicating GPay Send Money Area -->
      <section id="pay" class="tab-section">
        <div class="send-money-area">
          <div class="recipient">
            <img src="sach.JPG" alt="Recipient" class="recipient-avatar">
            <div>
              <div class="recipient-name">Sachin</div>
              <div class="recipient-upi">sachin27@okicici</div>
            </div>
          </div>
          <form class="gpay-form">
            <label for="amount">Enter Amount</label>
            <input type="number" id="amount" name="amount" placeholder="₹0.00" min="1" step="0.01" required>
            <button type="submit" class="gpay-pay-btn">
              <!-- GPay icon on button -->
              <img src="Gpay.png" alt="GPay" class="pay-btn-icon">
              Pay with Google Pay
            </button>
          </form>
        </div>
      </section>

      <!-- Mobile Recharge Tab -->
      <section id="recharge" class="tab-section" style="display:none;">
        <form class="gpay-form">
          <label for="mobile">Mobile Number</label>
          <input type="tel" id="mobile" name="mobile" placeholder="Enter mobile number" pattern="[6-9]\d{9}" maxlength="10" required>
          
          <label for="operator">Operator</label>
          <select id="operator" name="operator" required>
            <option value="">Select Operator</option>
            <option value="airtel">Airtel</option>
            <option value="jio">Jio</option>
            <option value="vi">Vi</option>
            <option value="bsnl">BSNL</option>
          </select>
          
          <label for="recharge-amount">Recharge Amount</label>
          <input type="number" id="recharge-amount" name="recharge-amount" placeholder="₹0.00" min="10" required>
          
          <button type="submit" class="gpay-pay-btn">
            <img src="https://upload.wikimedia.org/wikipedia/commons/0/0b/Google_Pay_Logo.svg" alt="GPay" class="pay-btn-icon">
            Recharge Now
          </button>
        </form>
      </section>

      <!-- Offers Tab -->
      <section id="offers" class="tab-section" style="display:none;">
        <div class="info-box">
          <span>🎁</span>
          <p>No current offers. Check back soon!</p>
        </div>
      </section>

      <!-- Rewards Tab -->
      <section id="rewards" class="tab-section" style="display:none;">
        <div class="info-box">
          <span>🏆</span>
          <p>No rewards yet. Start making payments to earn rewards!</p>
        </div>
      </section>
    </main>

    <footer>
      <span class="ref-text">UI inspired by Google Pay for educational use</span>
    </footer>
  </div>
  <script>
    function showTab(tabName) {
      document.querySelectorAll('.tab-section').forEach(sec => sec.style.display = 'none');
      document.getElementById(tabName).style.display = 'block';
      document.querySelectorAll('.gpay-tabs .tab').forEach(btn => btn.classList.remove('active'));
      const tabOrder = ['pay', 'recharge', 'offers', 'rewards'];
      document.querySelectorAll('.gpay-tabs .tab')[tabOrder.indexOf(tabName)].classList.add('active');
    }
  </script>
</body>
</html>
```

## Css code
```
body {
  background: #f5f6fa;
  font-family: 'Google Sans', Arial, sans-serif;
  margin: 0;
  padding: 0;
}

.gpay-container {
  max-width: 370px;
  margin: 40px auto;
  background: #fff;
  border-radius: 16px;
  box-shadow: 0 4px 24px rgba(60, 64, 67, 0.12);
  padding: 24px 18px 16px 18px;
}

header {
  display: flex;
  align-items: center;
  margin-bottom: 18px;
}

.gpay-logo {
  width: 40px;
  margin-right: 10px;
}

.gpay-title {
  font-size: 1.5rem;
  font-weight: 600;
  color: #1a73e8;
}

.gpay-tabs {
  display: flex;
  justify-content: space-between;
  margin-bottom: 24px;
}

.tab {
  flex: 1;
  background: none;
  border: none;
  font-size: 1rem;
  padding: 10px 0;
  cursor: pointer;
  color: #5f6368;
  border-bottom: 2px solid transparent;
  transition: color 0.2s, border-bottom 0.2s;
}

.tab.active,
.tab:hover {
  color: #1a73e8;
  border-bottom: 2px solid #1a73e8;
}

.send-money-area {
  background: #f0f4fa;
  border-radius: 12px;
  padding: 18px 14px;
  margin-bottom: 18px;
  box-shadow: 0 1px 4px rgba(60, 64, 67, 0.07);
}

.recipient {
  display: flex;
  align-items: center;
  margin-bottom: 18px;
}

.recipient-avatar {
  width: 48px;
  height: 48px;
  border-radius: 50%;
  margin-right: 12px;
  border: 2px solid #fff;
  box-shadow: 0 2px 8px rgba(60, 64, 67, 0.08);
}

.recipient-name {
  font-weight: 600;
  font-size: 1.1rem;
  color: #222;
}

.recipient-upi {
  font-size: 0.95rem;
  color: #888;
}

.gpay-form {
  display: flex;
  flex-direction: column;
  gap: 14px;
}

.gpay-form label {
  font-size: 1rem;
  color: #444;
  margin-bottom: 4px;
  text-align: left;
}

.gpay-form input,
.gpay-form select {
  padding: 12px;
  font-size: 1.1rem;
  border: 1.5px solid #e0e0e0;
  border-radius: 8px;
  outline: none;
  transition: border-color 0.2s;
}

.gpay-form input:focus,
.gpay-form select:focus {
  border-color: #1a73e8;
}

.gpay-pay-btn {
  background: #1a73e8;
  color: #fff;
  font-size: 1rem;
  padding: 12px 0;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  font-weight: 600;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
  transition: background 0.2s;
}

.gpay-pay-btn:hover {
  background: #1765c1;
}

.pay-btn-icon {
  width: 28px;
  height: 28px;
  vertical-align: middle;
}

.info-box {
  display: flex;
  flex-direction: column;
  align-items: center;
  color: #888;
  font-size: 1.1rem;
  margin-top: 30px;
}

.info-box span {
  font-size: 2rem;
  margin-bottom: 10px;
}

footer {
  margin-top: 28px;
  text-align: center;
}

.ref-text {
  font-size: 0.85rem;
  color: #888;
}
```

