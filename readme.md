# Klok Automate

Kalo belum daftar bisa pake reff sy, https://klokapp.ai?referral_code=Y5ZB8DGS

1. Edit isi array ama pesan atau prompt yang mau dipake, kalo males paste aja chatgpt suru isi pake pesan 10 biji untuk koteksnya bebas aja.
2. Nanti paste aja di console browse, shortcutnya CTRL + SHIFT + J
3. Kalo ada tulisan gak bisa paste, ketik dulu 'allow pasting'

```javascipt
(async function() {
  // 1. Array pesan dengan 10 prompt singkat tentang blockchain
  const messages = [
  "What is your favorite childhood memory?",
  "If you could have any superpower, what would it be and why?",
  "What is the most interesting book you've ever read?",
  "If you could visit any country in the world, where would you go?",
  "What is your biggest fear?",
  "If you could have dinner with any historical figure, who would it be?",
  "What was your dream job as a child?",
  "If you had a time machine, would you go to the past or the future?",
  "What is one skill you wish you could master?",
  "If you could meet any fictional character, who would it be?",
  "What is your favorite movie of all time?",
  "Do you believe in fate or free will?",
  "What is your guilty pleasure?",
  "If you won the lottery, what would be the first thing you'd do?",
  "What is the most adventurous thing you've ever done?",
  "What is one habit you want to break?",
  "If you had to live in one place for the rest of your life, where would it be?",
  "What is your favorite way to spend a weekend?",
  "If you could switch lives with someone for a day, who would it be?",
  "What is your favorite type of music?",
  "If you could speak any language fluently, which one would it be?",
  "Do you prefer cities or nature?",
  "What is one thing you can't live without?",
  "If you could bring back any extinct animal, which one would it be?",
  "What is your dream vacation?",
  "What is the most embarrassing thing that has ever happened to you?",
  "If you could be any fictional villain, who would you be?",
  "What is the best concert you've ever been to?",
  "What is something new you want to try this year?",
  "Do you believe in aliens?",
  "If you could relive one day of your life, which day would it be?",
  "What is your spirit animal?",
  "If you could only eat one type of food for the rest of your life, what would it be?",
  "What is one thing you regret not doing?",
  "What was your first job?",
  "Do you prefer morning or night?",
  "What is your favorite holiday and why?",
  "What is the weirdest thing you've ever eaten?",
  "If you could own any exotic pet, what would it be?",
  "Do you believe in destiny?",
  "If you could time travel to witness one historical event, what would it be?",
  "What is your biggest accomplishment so far?",
  "If you could trade lives with a celebrity for a day, who would it be?",
  "What is your favorite quote?",
  "What motivates you to keep going during tough times?",
  "If you could invent something, what would it be?",
  "Would you rather explore space or the deep ocean?",
  "What is one random fun fact about yourself?",
  "If you had to describe yourself in three words, what would they be?"
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
