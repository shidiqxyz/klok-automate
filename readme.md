# Klok Automate

Kalo belum daftar bisa pake reff sy, https://klokapp.ai?referral_code=Y5ZB8DGS

1. Edit isi array ama pesan atau prompt yang mau dipake, kalo males paste aja chatgpt suru isi pake pesan 10 biji untuk koteksnya bebas aja.
2. Nanti paste aja di console browse, shortcutnya CTRL + SHIFT + J
3. Kalo ada tulisan gak bisa paste, ketik dulu 'allow pasting'

```javascipt
// 1. Array pesan dengan 10 prompt singkat tentang blockchain
const messages = [
    "Isi pake pesan 10 biji dalam array ini",
    "Isi pake pesan 10 biji dalam array ini",
    "Isi pake pesan 10 biji dalam array ini",
    "Isi pake pesan 10 biji dalam array ini",
    "Isi pake pesan 10 biji dalam array ini",
    "Isi pake pesan 10 biji dalam array ini",
    "Isi pake pesan 10 biji dalam array ini",
    "Isi pake pesan 10 biji dalam array ini",
    "Isi pake pesan 10 biji dalam array ini",
    "Isi pake pesan 10 biji dalam array ini",
    "Isi pake pesan 10 biji dalam array ini"
];

// 2. Seleksi elemen jumlah chat dan textarea input secara aman
  function getChatCountElement() {
    return document.querySelector('div[class*="text-[#e8e8e8]"][class*="text-[13px]"]');
  }
  
  function getTextarea() {
    return document.querySelector('textarea[name="message"]');
  }
  
  function getSubmitButton() {
    return document.querySelector('button[type="submit"]');
  }
  
  // Fungsi untuk menunggu hingga tombol submit tidak disabled
  function waitForButtonToEnable(callback) {
    const submitButton = getSubmitButton();
    if (!submitButton) {
      console.log("Tombol submit tidak ditemukan, menunggu...");
      setTimeout(() => waitForButtonToEnable(callback), 1000);
      return;
    }
    if (submitButton.disabled) {
      console.log("Tombol submit masih disabled, mensimulasikan klik pada textarea untuk mengaktifkannya...");
      const textarea = getTextarea();
      if (textarea) {
        textarea.click(); // Simulasi klik pada textarea
        textarea.focus();
        textarea.dispatchEvent(new Event('focus', { bubbles: true }));
        textarea.dispatchEvent(new Event('input', { bubbles: true }));
      }
      setTimeout(() => waitForButtonToEnable(callback), 500);
    } else {
      callback();
    }
  }
  
  // 3. Fungsi untuk mengirim pesan berdasarkan indeks array
  function sendChat(index) {
    if (index >= messages.length) return;
  
    const textarea = getTextarea();
    if (!textarea) {
      console.log("Textarea tidak ditemukan, menunggu...");
      setTimeout(() => sendChat(index), 1000);
      return;
    }
  
    const submitButton = getSubmitButton();
    if (!submitButton) {
      console.log("Tombol submit tidak ditemukan, menunggu...");
      setTimeout(() => sendChat(index), 1000);
      return;
    }
  
    // Tunggu hingga tombol submit aktif (tidak disabled)
    waitForButtonToEnable(() => {
      textarea.removeAttribute('disabled');
      textarea.value = messages[index];
      
      const event = new Event('input', { bubbles: true });
      textarea.dispatchEvent(event);
      
      submitButton.click();
    });
  }
  
  // 4. MutationObserver untuk memantau perubahan jumlah chat
  const observer = new MutationObserver(() => {
    const chatCountDiv = getChatCountElement();
    if (!chatCountDiv) return;
  
    const currentCount = parseInt(chatCountDiv.textContent) || 0;
    console.log("Jumlah chat saat ini: ${currentCount}");
  
    if (currentCount < messages.length) {
      sendChat(currentCount);
    } else {
      observer.disconnect();
      console.log("Proses automasi chat selesai (10 pesan terkirim).");
    }
  });
  
  // Menunggu elemen tersedia sebelum mulai observasi
  function startObserving() {
    const chatCountDiv = getChatCountElement();
    if (chatCountDiv) {
      observer.observe(chatCountDiv, { childList: true, characterData: true, subtree: true });
      sendChat(0);
    } else {
      console.log("Menunggu elemen jumlah chat...");
      setTimeout(startObserving, 1000);
    }
  }
  
  startObserving();
```
