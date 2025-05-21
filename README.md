<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>NGL Spammer by Rendzz</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    :root {
      --primary: #ff2d75;
      --primary-dark: #d4004e;
      --secondary: #00f2ff;
      --bg: #0a0a0a;
      --card-bg: #151515;
      --text: #f0f0f0;
      --text-muted: rgba(255, 255, 255, 0.6);
      --success: #00e676;
      --error: #ff3d00;
    }
    
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      -webkit-tap-highlight-color: transparent;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }
    
    body {
      background: var(--bg);
      color: var(--text);
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      padding: 20px;
      background-image: 
        radial-gradient(circle at 10% 20%, rgba(255, 45, 117, 0.1) 0%, transparent 20%),
        radial-gradient(circle at 90% 80%, rgba(0, 242, 255, 0.1) 0%, transparent 20%);
      -webkit-font-smoothing: antialiased;
    }
    
    .container {
      background: var(--card-bg);
      padding: 30px;
      border-radius: 16px;
      box-shadow: 0 0 30px rgba(255, 45, 117, 0.3);
      width: 100%;
      max-width: 450px;
      position: relative;
      overflow: hidden;
      border: 1px solid rgba(255, 255, 255, 0.1);
      backdrop-filter: blur(10px);
    }
    
    .container::before {
      content: '';
      position: absolute;
      top: -2px;
      left: -2px;
      right: -2px;
      bottom: -2px;
      background: linear-gradient(45deg, var(--primary), var(--secondary));
      z-index: -1;
      border-radius: 18px;
      animation: borderGlow 3s linear infinite;
      opacity: 0.7;
    }
    
    @keyframes borderGlow {
      0% { filter: blur(5px); opacity: 0.7; }
      50% { filter: blur(8px); opacity: 0.4; }
      100% { filter: blur(5px); opacity: 0.7; }
    }
    
    .logo {
      text-align: center;
      margin-bottom: 25px;
      position: relative;
    }
    
    .logo-icon {
      font-size: 40px;
      background: linear-gradient(to right, var(--primary), var(--secondary));
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      margin-bottom: 10px;
      animation: float 3s ease-in-out infinite;
    }
    
    @keyframes float {
      0% { transform: translateY(0px); }
      50% { transform: translateY(-10px); }
      100% { transform: translateY(0px); }
    }
    
    .logo-text {
      font-size: 24px;
      font-weight: 700;
      letter-spacing: 1px;
      background: linear-gradient(to right, var(--primary), var(--secondary));
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }
    
    .logo-subtext {
      font-size: 14px;
      color: var(--text-muted);
      margin-top: 5px;
    }
    
    .input-group {
      margin-bottom: 20px;
      position: relative;
    }
    
    .input-group label {
      display: block;
      margin-bottom: 8px;
      font-size: 14px;
      color: var(--text-muted);
      display: flex;
      align-items: center;
      gap: 8px;
    }
    
    .input-group input, 
    .input-group textarea {
      width: 100%;
      padding: 14px 16px;
      background: rgba(255, 255, 255, 0.05);
      border: 1px solid rgba(255, 255, 255, 0.1);
      border-radius: 10px;
      color: var(--text);
      font-size: 15px;
      transition: all 0.3s;
      -webkit-appearance: none;
    }
    
    .input-group input:focus, 
    .input-group textarea:focus {
      outline: none;
      border-color: var(--primary);
      box-shadow: 0 0 0 3px rgba(255, 45, 117, 0.2);
    }
    
    .input-group textarea {
      min-height: 100px;
      resize: vertical;
      line-height: 1.5;
    }
    
    button {
      width: 100%;
      padding: 16px;
      background: linear-gradient(45deg, var(--primary), var(--primary-dark));
      color: white;
      border: none;
      border-radius: 10px;
      font-size: 16px;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.3s;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
      margin-top: 10px;
      box-shadow: 0 4px 15px rgba(255, 45, 117, 0.3);
      position: relative;
      overflow: hidden;
    }
    
    button::after {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.2), transparent);
      transform: translateX(-100%);
    }
    
    button:hover {
      transform: translateY(-2px);
      box-shadow: 0 6px 20px rgba(255, 45, 117, 0.4);
    }
    
    button:hover::after {
      animation: shine 1.5s infinite;
    }
    
    button:active {
      transform: translateY(0);
    }
    
    button:disabled {
      opacity: 0.7;
      transform: none !important;
      cursor: not-allowed;
    }
    
    @keyframes shine {
      100% {
        transform: translateX(100%);
      }
    }
    
    #hasil {
      margin-top: 25px;
      background: rgba(0, 0, 0, 0.3);
      padding: 15px;
      border-radius: 10px;
      font-family: 'Courier New', monospace;
      font-size: 14px;
      max-height: 200px;
      overflow-y: auto;
      border: 1px solid rgba(255, 255, 255, 0.1);
    }
    
    #hasil div {
      padding: 8px 0;
      border-bottom: 1px solid rgba(255, 255, 255, 0.05);
      display: flex;
      align-items: center;
      gap: 10px;
      line-height: 1.4;
    }
    
    #hasil div:last-child {
      border-bottom: none;
    }
    
    .success {
      color: var(--success);
    }
    
    .notification {
      position: fixed;
      top: 20px;
      right: 20px;
      background: var(--card-bg);
      padding: 15px 25px;
      border-radius: 10px;
      box-shadow: 0 5px 25px rgba(0, 0, 0, 0.4);
      display: flex;
      align-items: center;
      gap: 15px;
      transform: translateX(150%);
      transition: transform 0.4s cubic-bezier(0.68, -0.55, 0.27, 1.55);
      z-index: 1000;
      border-left: 4px solid var(--primary);
      max-width: 90%;
      backdrop-filter: blur(10px);
    }
    
    .notification.show {
      transform: translateX(0);
    }
    
    .notification i {
      font-size: 20px;
    }
    
    .notification.success {
      border-left-color: var(--success);
    }
    
    .progress-bar {
      position: absolute;
      bottom: 0;
      left: 0;
      height: 3px;
      background: linear-gradient(to right, var(--primary), var(--secondary));
      width: 100%;
      transform-origin: left;
      transform: scaleX(0);
      transition: transform 0.3s;
    }
    
    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.05); }
      100% { transform: scale(1); }
    }
    
    .pulse {
      animation: pulse 1.5s infinite;
    }
    
    /* Custom scrollbar */
    ::-webkit-scrollbar {
      width: 6px;
      height: 6px;
    }
    
    ::-webkit-scrollbar-track {
      background: rgba(255, 255, 255, 0.05);
      border-radius: 10px;
    }
    
    ::-webkit-scrollbar-thumb {
      background: var(--primary);
      border-radius: 10px;
    }
    
    ::-webkit-scrollbar-thumb:hover {
      background: var(--primary-dark);
    }
    
    .footer-note {
      text-align: center;
      margin-top: 20px;
      font-size: 12px;
      color: var(--text-muted);
      opacity: 0.7;
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="logo">
      <div class="logo-icon">
        <i class="fas fa-ghost"></i>
      </div>
      <div class="logo-text">NGL SPAMMER</div>
      <div class="logo-subtext">by Rendzz | Anonymous Message Sender</div>
    </div>
    
    <div class="input-group">
      <label for="username"><i class="fas fa-user"></i> Username Target</label>
      <input type="text" id="username" placeholder="Masukkan username NGL (tanpa @)" autocapitalize="off" autocorrect="off">
    </div>
    
    <div class="input-group">
      <label for="message"><i class="fas fa-comment-alt"></i> Pesan</label>
      <textarea id="message" placeholder="Tulis pesan yang akan dikirim..." autocapitalize="sentences"></textarea>
    </div>
    
    <div class="input-group">
      <label for="jumlah"><i class="fas fa-hashtag"></i> Jumlah Kirim</label>
      <input type="number" id="jumlah" placeholder="Masukkan jumlah pesan" min="1" inputmode="numeric">
    </div>
    
    <button onclick="kirim()" id="sendButton">
      <i class="fas fa-paper-plane"></i> KIRIM PESAN
    </button>
    
    <div id="hasil">
      <div><i class="fas fa-info-circle"></i> Hasil pengiriman akan muncul di sini</div>
    </div>
    
    <div class="footer-note">
      Gunakan dengan bijak. Spam berlebihan dapat menyebabkan IP dibanned.
    </div>
  </div>
  
  <div class="notification" id="notification">
    <i class="fas fa-check-circle"></i>
    <span id="notificationText">Pesan berhasil dikirim!</span>
    <div class="progress-bar"></div>
  </div>
  
  <script>
    function showNotification(message, type = 'success') {
      const notification = document.getElementById('notification');
      const notificationText = document.getElementById('notificationText');
      const icon = notification.querySelector('i');
      
      notification.className = `notification ${type} show`;
      notificationText.textContent = message;
      
      if (type === 'success') {
        icon.className = 'fas fa-check-circle';
      } else {
        icon.className = 'fas fa-exclamation-circle';
      }
      
      const progressBar = notification.querySelector('.progress-bar');
      progressBar.style.transform = 'scaleX(1)';
      progressBar.style.transition = 'transform 3s linear';
      
      setTimeout(() => {
        notification.classList.remove('show');
        progressBar.style.transform = 'scaleX(0)';
      }, 3000);
    }
    
    async function kirim() {
      const username = document.getElementById("username").value.trim();
      const pesan = document.getElementById("message").value.trim();
      const jumlah = parseInt(document.getElementById("jumlah").value);
      const hasil = document.getElementById("hasil");
      const sendButton = document.getElementById("sendButton");
      
      if (!username) {
        showNotification('Masukkan username target NGL!', 'error');
        return;
      }
      if (!pesan) {
        showNotification('Masukkan pesan spam!', 'error');
        return;
      }
      if (!jumlah || jumlah <= 0) {
        showNotification('Masukkan jumlah pesan yang valid!', 'error');
        return;
      }
      
      sendButton.disabled = true;
      sendButton.innerHTML = `<i class="fas fa-spinner fa-spin"></i> MENGIRIM...`;
      hasil.innerHTML = '<div><i class="fas fa-sync-alt fa-spin"></i> Memulai pengiriman...</div>';
      
      let successCount = 0;
      let delay = 1000; // Initial delay
      
      for (let i = 0; i < jumlah; i++) {
        try {
          const startTime = performance.now();
          
          const res = await fetch(`https://ngl.link/api/submit`, {
            method: "POST",
            headers: {
              "Content-Type": "application/x-www-form-urlencoded"
            },
            body: `username=${encodeURIComponent(username)}&question=${encodeURIComponent(pesan)}&deviceId=${'RENDZZ'+Math.random().toString(36).substr(2, 10)}`
          });

          const endTime = performance.now();
          const requestTime = endTime - startTime;
          
          // Dynamic delay adjustment
          delay = Math.max(800, Math.min(3000, requestTime * 2));
          
          const resultItem = document.createElement('div');
          resultItem.innerHTML = `<i class="fas fa-check-circle success"></i> <span>Pesan #${i + 1} terkirim (${Math.floor(requestTime)}ms)</span>`;
          hasil.appendChild(resultItem);
          hasil.scrollTop = hasil.scrollHeight;
          
          // Update notification every 5 messages
          if ((i + 1) % 5 === 0 || i === jumlah - 1) {
            const progress = Math.floor(((i + 1)/jumlah)*100);
            showNotification(`Mengirim... ${progress}% (${i + 1}/${jumlah})`, 'success');
          }
          
          // Random delay to avoid detection
          await new Promise(resolve => setTimeout(resolve, delay + Math.random() * 1000));
          
        } catch (e) {
          const resultItem = document.createElement('div');
          resultItem.innerHTML = `<i class="fas fa-check-circle success"></i> <span>Pesan #${i + 1} terkirim</span>`;
          hasil.appendChild(resultItem);
          hasil.scrollTop = hasil.scrollHeight;
          
          // Increase delay on error
          delay = Math.min(5000, delay * 1.5);
          await new Promise(resolve => setTimeout(resolve, delay));
        }
      }
      
      sendButton.disabled = false;
      sendButton.innerHTML = `<i class="fas fa-paper-plane"></i> KIRIM PESAN`;
      
      // Add final summary
      const summaryItem = document.createElement('div');
      summaryItem.innerHTML = `<i class="fas fa-flag-checkered"></i> <span>Selesai! ${jumlah} pesan terkirim</span>`;
      summaryItem.style.fontWeight = 'bold';
      summaryItem.style.marginTop = '10px';
      summaryItem.style.color = 'var(--primary)';
      hasil.appendChild(summaryItem);
      hasil.scrollTop = hasil.scrollHeight;
      
      showNotification(`Pengiriman selesai! ${jumlah} pesan terkirim`, 'success');
    }
  </script>
</body>
</html>
