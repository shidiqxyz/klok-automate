# Klok Automate

## Versi Console
Kalo belum daftar bisa pake reff sy, https://klokapp.ai?referral_code=Y5ZB8DGS

1. Edit isi array ama pesan atau prompt yang mau dipake, kalo males paste aja chatgpt suru isi pake pesan 10 biji untuk koteksnya bebas aja.
2. Nanti paste aja di console browse, shortcutnya CTRL + SHIFT + J
3. Kalo ada tulisan gak bisa paste, ketik dulu 'allow pasting'

```javascipt
(async function() {
  const S = ["blockchain", "kripto", "fintech"];
  const P = ["Jelaskan", "Deskripsikan", "Analisis"];
  const O = ["peran", "konsep", "manfaat"];
  const K = ["disrupsi", "inovasi", "transformasi"];

  function generateRandomPrompt() {
    const s = S[Math.floor(Math.random() * S.length)];
    const p = P[Math.floor(Math.random() * P.length)];
    const o = O[Math.floor(Math.random() * O.length)];
    const k = K[Math.floor(Math.random() * K.length)];
    return `${p} ${o} ${k} dalam konteks ${s}.`;
  }

  const messages = Array.from({length: 10}, generateRandomPrompt);
  console.log("Pesan yang dihasilkan:", messages);

  function shuffleArray(array) {
    for (let i = array.length - 1; i > 0; i--) {
      const j = Math.floor(Math.random() * (i + 1));
      [array[i], array[j]] = [array[j], array[i]];
    }
    return array;
  }
  const randomizedMessages = shuffleArray([...messages]);

  function waitForElement(selector, interval = 500, timeout = 10000) {
    return new Promise((resolve, reject) => {
      const start = Date.now();
      (function check() {
        const el = document.querySelector(selector);
        if (el) return resolve(el);
        if (Date.now() - start >= timeout) return reject(new Error(`Element ${selector} not found`));
        setTimeout(check, interval);
      })();
    });
  }

  const getChatCountElement = () =>
    document.querySelector('div[class*="text-[#e8e8e8]"][class*="text-[13px]"]');
  const getTextarea = () => document.querySelector('textarea[name="message"]');
  const getSubmitButton = () => document.querySelector('button[type="submit"]');

  async function waitForButtonToEnable() {
    await waitForElement('button[type="submit"]');
    const btn = getSubmitButton();
    while (btn.disabled) {
      const ta = getTextarea();
      if (ta) ta.dispatchEvent(new Event("input", { bubbles: true }));
      await new Promise(r => setTimeout(r, 300));
    }
  }

  // Fungsi mengetik per karakter dengan delay acak
  async function typeText(element, text) {
    element.value = "";
    for (let char of text) {
      element.value += char;
      element.dispatchEvent(new Event("input", { bubbles: true }));
      // delay acak antara 50–200ms per karakter
      await new Promise(r => setTimeout(r, 50 + Math.random() * 150));
    }
  }

  async function sendChat(index) {
    if (index >= randomizedMessages.length) return;
    const prompt = randomizedMessages[index];

    // tunggu elemen tersedia
    let ta = getTextarea();
    while (!ta) {
      await new Promise(r => setTimeout(r, 500));
      ta = getTextarea();
    }
    let btn = getSubmitButton();
    while (!btn) {
      await new Promise(r => setTimeout(r, 500));
      btn = getSubmitButton();
    }
    await waitForButtonToEnable();

    // delay acak sebelum mulai mengetik (1–10 detik)
    await new Promise(r => setTimeout(r, 1000 + Math.random() * 10000));

    // simulasi mengetik
    ta.removeAttribute("disabled");
    await typeText(ta, prompt);

    // jeda singkat sebelum klik submit
    await new Promise(r => setTimeout(r, 200 + Math.random() * 300));
    btn.click();
  }

  const observer = new MutationObserver(() => {
    const countEl = getChatCountElement();
    if (!countEl) return;
    const currentCount = parseInt(countEl.textContent) || 0;
    if (currentCount < randomizedMessages.length) {
      sendChat(currentCount);
    } else {
      observer.disconnect();
      console.log("Semua pesan terkirim.");
    }
  });

  async function startObserving() {
    await waitForElement('div[class*="text-[#e8e8e8]"][class*="text-[13px]"]');
    const countEl = getChatCountElement();
    observer.observe(countEl, { childList: true, characterData: true, subtree: true });
    sendChat(0);
  }

  startObserving();
})();

```
## Versi Boorkmark

1. Pencet CTRL + SHIFT + B
2. Setelah itu ada bar baru, tambahkan Add Page
3. Untuk name isi Klok Automate
4. Untuk URL isi kode dibawah ini
   
```javascript
javascript:(async function() {
  const S=["blockchain","kripto","fintech"];
  const P=["Jelaskan","Deskripsikan","Analisis"];
  const O=["peran","konsep","manfaat"];
  const K=["disrupsi","inovasi","transformasi"];
  function generateRandomPrompt(){const s=S[Math.floor(Math.random()*S.length)],p=P[Math.floor(Math.random()*P.length)],o=O[Math.floor(Math.random()*O.length)],k=K[Math.floor(Math.random()*K.length)];return`${p} ${o} ${k} dalam konteks ${s}.`}
  const messages=Array.from({length:10},generateRandomPrompt);
  function shuffleArray(a){for(let i=a.length-1;i>0;i--){const j=Math.floor(Math.random()*(i+1));[a[i],a[j]]=[a[j],a[i]]}return a}
  const randomizedMessages=shuffleArray([...messages]);
  function waitForElement(s,i=500,t=10000){return new Promise((r,j)=>{const d=Date.now();(function c(){const e=document.querySelector(s);if(e)return r(e);if(Date.now()-d>=t)return j(new Error(`Element ${s} not found`));setTimeout(c,i)})()})}
  const getChatCountElement=()=>document.querySelector('div[class*="text-[#e8e8e8]"][class*="text-[13px]"]');
  const getTextarea=()=>document.querySelector('textarea[name="message"]');
  const getSubmitButton=()=>document.querySelector('button[type="submit"]');
  async function waitForButtonToEnable(){await waitForElement('button[type="submit"]');const btn=getSubmitButton();while(btn.disabled){const ta=getTextarea();if(ta)ta.dispatchEvent(new Event("input",{bubbles:true}));await new Promise(r=>setTimeout(r,300))}}
  async function typeText(e,t){e.value="";for(let c of t){e.value+=c;e.dispatchEvent(new Event("input",{bubbles:true}));await new Promise(r=>setTimeout(r,50+Math.random()*150))}}
  async function sendChat(i){if(i>=randomizedMessages.length)return;const prompt=randomizedMessages[i];let ta=getTextarea();while(!ta){await new Promise(r=>setTimeout(r,500));ta=getTextarea()}let btn=getSubmitButton();while(!btn){await new Promise(r=>setTimeout(r,500));btn=getSubmitButton()}await waitForButtonToEnable();await new Promise(r=>setTimeout(r,1000+Math.random()*10000));ta.removeAttribute("disabled");await typeText(ta,prompt);await new Promise(r=>setTimeout(r,200+Math.random()*300));btn.click()}
  const observer=new MutationObserver(()=>{const countEl=getChatCountElement();if(!countEl)return;const c=parseInt(countEl.textContent)||0;if(c<randomizedMessages.length){sendChat(c)}else{observer.disconnect();console.log("Semua pesan terkirim.")}});
  async function startObserving(){await waitForElement('div[class*="text-[#e8e8e8]"][class*="text-[13px]"]');const countEl=getChatCountElement();observer.observe(countEl,{childList:true,characterData:true,subtree:true});sendChat(0)}
  startObserving();
})();
```
5. Nanti tinggal masuk web klok, terus pencet boormark yang udah dibikin
