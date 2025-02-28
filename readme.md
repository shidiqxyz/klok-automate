# Klok Automate

Kalo belum daftar bisa pake reff sy, https://klokapp.ai?referral_code=Y5ZB8DGS

1. Edit isi array ama pesan atau prompt yang mau dipake, kalo males paste aja chatgpt suru isi pake pesan 10 biji untuk koteksnya bebas aja.
2. Nanti paste aja di console browse, shortcutnya CTRL + SHIFT + J
3. Kalo ada tulisan gak bisa paste, ketik dulu 'allow pasting'

```javascipt
(async function() {
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

  // Fungsi untuk merandom array menggunakan algoritma Fisher-Yates
  function shuffleArray(array) {
    for (let i = array.length - 1; i > 0; i--) {
      const j = Math.floor(Math.random() * (i + 1));
      [array[i], array[j]] = [array[j], array[i]];
    }
    return array;
  }

  // Acak pesan tanpa mengubah array asli
  const randomizedMessages = shuffleArray([...messages]);

  // Fungsi utilitas untuk menunggu hingga sebuah elemen tersedia
  function waitForElement(selector, interval = 500, timeout = 10000) {
    return new Promise((resolve, reject) => {
      const start = Date.now();
      const check = () => {
        const el = document.querySelector(selector);
        if (el) {
          resolve(el);
        } else if (Date.now() - start >= timeout) {
          reject(new Error(`Elemen dengan selector "${selector}" tidak ditemukan dalam waktu ${timeout}ms`));
        } else {
          setTimeout(check, interval);
        }
      };
      check();
    });
  }

  // Seleksi elemen-elemen DOM
  const getChatCountElement = () =>
    document.querySelector('div[class*="text-[#e8e8e8]"][class*="text-[13px]"]');
  const getTextarea = () => document.querySelector('textarea[name="message"]');
  const getSubmitButton = () => document.querySelector('button[type="submit"]');

  // Fungsi untuk menunggu hingga tombol submit aktif (tidak disabled)
  async function waitForButtonToEnable() {
    await waitForElement('button[type="submit"]');
    const submitButton = getSubmitButton();
    while (submitButton.disabled) {
      console.log("Tombol submit masih disabled, mensimulasikan klik pada textarea untuk mengaktifkannya...");
      const textarea = getTextarea();
      if (textarea) {
        textarea.click();
        textarea.focus();
        textarea.dispatchEvent(new Event("focus", { bubbles: true }));
        textarea.dispatchEvent(new Event("input", { bubbles: true }));
      }
      await new Promise(resolve => setTimeout(resolve, 500));
    }
  }

  // Fungsi untuk mengirim pesan berdasarkan indeks dari array yang sudah diacak
  async function sendChat(index) {
    if (index >= randomizedMessages.length) return;

    // Pastikan textarea dan tombol submit sudah tersedia
    let textarea = getTextarea();
    while (!textarea) {
      console.log("Textarea tidak ditemukan, menunggu...");
      await new Promise(resolve => setTimeout(resolve, 1000));
      textarea = getTextarea();
    }

    let submitButton = getSubmitButton();
    while (!submitButton) {
      console.log("Tombol submit tidak ditemukan, menunggu...");
      await new Promise(resolve => setTimeout(resolve, 1000));
      submitButton = getSubmitButton();
    }

    // Tunggu hingga tombol submit aktif
    await waitForButtonToEnable();

    // Kirim pesan
    textarea.removeAttribute("disabled");
    textarea.value = randomizedMessages[index];
    textarea.dispatchEvent(new Event("input", { bubbles: true }));
    submitButton.click();
  }

  // MutationObserver untuk memantau perubahan jumlah chat
  const observer = new MutationObserver(() => {
    const chatCountDiv = getChatCountElement();
    if (!chatCountDiv) return;

    const currentCount = parseInt(chatCountDiv.textContent) || 0;
    console.log(`Jumlah chat saat ini: ${currentCount}`);

    if (currentCount < randomizedMessages.length) {
      sendChat(currentCount);
    } else {
      observer.disconnect();
      console.log("Proses automasi chat selesai (semua pesan terkirim).");
    }
  });

  // Fungsi untuk memulai observasi setelah elemen chat count tersedia
  async function startObserving() {
    await waitForElement('div[class*="text-[#e8e8e8]"][class*="text-[13px]"]');
    const chatCountDiv = getChatCountElement();
    observer.observe(chatCountDiv, { childList: true, characterData: true, subtree: true });
    sendChat(0);
  }

  startObserving();
})();
```
