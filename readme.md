# Klok Automate

## Versi Console
Kalo belum daftar bisa pake reff sy, https://klokapp.ai?referral_code=Y5ZB8DGS

1. Edit isi array ama pesan atau prompt yang mau dipake, kalo males paste aja chatgpt suru isi pake pesan 10 biji untuk koteksnya bebas aja.
2. Nanti paste aja di console browse, shortcutnya CTRL + SHIFT + J
3. Kalo ada tulisan gak bisa paste, ketik dulu 'allow pasting'

```javascipt
(async function() {
  // 1. Array pesan dengan 10 prompt singkat tentang blockchain
  const messages = [
   "Explain how artificial intelligence works.",
  "What are the latest advancements in robotics?",
  "Describe the impact of blockchain technology.",
  "How does 5G technology improve connectivity?",
  "Explain the concept of the Internet of Things (IoT).",
  "What are the benefits of cloud computing?",
  "Describe how quantum computing works.",
  "What is cybersecurity and why is it important?",
  "Explain how machine learning differs from deep learning.",
  "How do self-driving cars work?",
  "What are the ethical concerns of AI development?",
  "Describe how virtual reality (VR) is changing entertainment.",
  "What are the risks of deepfake technology?",
  "How does encryption protect online data?",
  "Explain the process of software development.",
  "What is edge computing and how does it work?",
  "Describe the future of space technology.",
  "How do smart assistants like Siri and Alexa function?",
  "What is the impact of big data on businesses?",
  "Explain how search engine algorithms work.",
  "Describe the role of AI in healthcare.",
  "How do facial recognition systems work?",
  "What are the advantages and disadvantages of smart homes?",
  "Explain the importance of ethical hacking.",
  "How does augmented reality (AR) enhance user experience?",
  "Describe how blockchain is used beyond cryptocurrency.",
  "What is the role of AI in automation?",
  "Explain how drone technology is evolving.",
  "What are the risks of social media algorithms?",
  "How do recommendation systems like Netflix and YouTube work?",
  "Describe the future of wearable technology.",
  "How do neural networks mimic the human brain?",
  "What are the key features of Web3 technology?",
  "Explain the impact of AI on job automation.",
  "How do smart contracts work on the blockchain?",
  "Describe the evolution of mobile phones.",
  "What are the benefits of renewable energy technology?",
  "How does a VPN enhance internet security?",
  "Explain how satellites support global communication.",
  "What is the role of AI in game development?",
  "How does biometric authentication improve security?",
  "Describe the process of ethical AI development.",
  "What is the metaverse and how will it shape the future?",
  "How do recommendation engines use AI?",
  "What are the biggest cybersecurity threats today?",
  "Explain the importance of coding in modern technology.",
  "How does AI help in climate change research?",
  "Describe how nanotechnology is used in medicine.",
  "What are the future trends in robotics?",
  "How does AI generate human-like text and images?",
   "How will AI transform the healthcare industry in the next 10 years?",
  "Explain the concept of nihilism in Friedrich Nietzsche's philosophy.",
  "What are the effects of inflation on consumer purchasing power?",
  "How can blockchain enhance data security?",
  "Can artificial intelligence develop consciousness?",
  "Describe the relationship between existentialism and individual freedom.",
  "What are the key factors influencing a country's economic growth?",
  "How can 5G technology revolutionize global communication?",
  "Do humans have free will, or is everything predetermined?",
  "How does monetary policy help control inflation?",
  "What is the impact of automation on the job market?",
  "Explain the difference between utilitarianism and deontology in ethics.",
  "How can artificial intelligence be applied in education?",
  "What is the Ship of Theseus paradox in the philosophy of identity?",
  "How do tech startups disrupt traditional industries?",
  "Will the singularity lead to superintelligent AI surpassing humans?",
  "What role does quantum computing play in the future of cybersecurity?",
  "Is capitalism the best economic system for innovation?",
  "How does the concept of the 'Overman' shape Nietzsche's philosophy?",
  "What are the ethical dilemmas of genetic engineering?",
  "Can decentralized finance (DeFi) replace traditional banking?",
  "What is the difference between Keynesian and classical economics?",
  "How does the simulation hypothesis challenge our perception of reality?",
  "Will renewable energy fully replace fossil fuels in the future?",
  "What are the philosophical implications of the trolley problem?",
  "How does game theory apply to real-world decision-making?",
  "What is the role of big data in shaping modern economies?",
  "How can AI help solve global climate change challenges?",
  "What are the economic risks of increasing national debt?",
  "Is universal basic income (UBI) a viable solution for the future economy?",
  "How does the metaverse impact digital identity and privacy?",
  "What are the consequences of algorithmic bias in AI systems?",
  "Should governments regulate cryptocurrencies?",
  "How does postmodernism critique traditional philosophical thought?",
  "Can machines ever truly understand human emotions?",
  "What are the implications of automation for economic inequality?",
  "Is war an inevitable part of human nature?",
  "How does transhumanism aim to enhance human capabilities?",
  "What are the philosophical arguments for and against determinism?",
  "How does artificial intelligence affect the future of creative industries?",
  "What are the key differences between socialism and capitalism?",
  "Can neuroscience explain human consciousness?",
  "What are the ethical considerations of AI in warfare?",
  "How do network effects contribute to the success of tech monopolies?",
  "What is the impact of globalization on local economies?",
  "Is privacy becoming obsolete in the digital age?",
  "How does the concept of 'The Absurd' define existentialist thought?",
  "What role does ethics play in the development of new technologies?",
  "Will automation lead to mass unemployment or create new job opportunities?",
  "What are the consequences of over-reliance on artificial intelligence?",
  "How do behavioral economics challenge traditional economic theories?",
  "Is space colonization a realistic goal for humanity?",
  "What are the benefits and risks of brain-computer interfaces?",
  "How does machine learning improve financial market predictions?",
  "What is the future of human-AI collaboration in the workplace?",
  "Can morality exist without religion?",
  "How do economic sanctions impact global trade?",
  "What is the role of philosophy in artificial intelligence development?",
  "How does digital currency challenge traditional monetary systems?",
  "What are the dangers of deepfake technology?",
  "Should AI be granted legal rights and personhood?",
  "How does the concept of 'The Will to Power' shape human ambition?",
  "What are the key factors behind cryptocurrency price fluctuations?",
  "Can democracy survive in an age of mass surveillance?",
  "How do incentives shape human behavior in economic theory?",
  "What are the consequences of wealth inequality on global stability?",
  "How does AI influence the future of scientific discoveries?",
  "Should AI-generated art be considered original?",
  "What are the long-term effects of technological unemployment?",
  "Can philosophy provide practical solutions for modern societal problems?",
  "What are the risks and rewards of nuclear energy?",
  "How does post-scarcity economics challenge traditional market principles?",
  "What role does cyber warfare play in modern geopolitics?",
  "Can virtual reality change the way we perceive reality?",
  "How does the precautionary principle apply to emerging technologies?",
  "What is the future of decentralized autonomous organizations (DAOs)?",
  "How does the philosophy of pragmatism apply to technological innovation?",
  "Will AI ever surpass human intelligence in creative thinking?",
  "What is the relationship between technology and social inequality?",
  "How does machine learning impact personalized medicine?",
  "What are the ethical concerns surrounding mass data collection?",
  "Can consciousness be artificially replicated?",
  "How does scarcity affect decision-making in economics?",
  "What are the philosophical arguments for and against artificial superintelligence?",
  "How do global supply chains influence economic resilience?",
  "Can blockchain technology prevent election fraud?",
  "What are the moral implications of self-driving cars?",
  "How does cognitive bias affect decision-making in economics?",
  "What is the role of philosophy in the age of artificial intelligence?",
  "Should technological singularity be feared or embraced?",
  "How does automation impact small businesses compared to large corporations?",
  "What are the consequences of over-reliance on social media algorithms?",
  "Can technological progress be separated from ethical considerations?",
  "What are the limitations of AI in understanding human emotions?",
  "How does economic game theory apply to international relations?",
  "Is artificial general intelligence (AGI) an inevitable outcome?",
  "What is the impact of robotics on human employment?",
  "How does the digital economy influence wealth distribution?",
  "Can AI be held accountable for ethical decision-making?",
  "What are the risks of AI surpassing human intelligence?",
  "How does philosophy shape our understanding of virtual reality?",
  "What are the key ethical concerns of mass surveillance?",
  "Is technological progress inherently good for humanity?"
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
## Versi Boorkmark

1. Pencet CTRL + SHIFT + B
2. Setelah itu ada bar baru, tambahkan Add Page
3. Untuk name isi Klok Automate
4. Untuk URL isi kode dibawah ini
```javascript
javascript:(async function(){const messages=[ "Explain how artificial intelligence works.",  "What are the latest advancements in robotics?",  "Describe the impact of blockchain technology.",  "How does 5G technology improve connectivity?",  "Explain the concept of the Internet of Things (IoT).",  "What are the benefits of cloud computing?",  "Describe how quantum computing works.",  "What is cybersecurity and why is it important?",  "Explain how machine learning differs from deep learning.",  "How do self-driving cars work?",  "What are the ethical concerns of AI development?",  "Describe how virtual reality (VR) is changing entertainment.",  "What are the risks of deepfake technology?",  "How does encryption protect online data?",  "Explain the process of software development.",  "What is edge computing and how does it work?",  "Describe the future of space technology.",  "How do smart assistants like Siri and Alexa function?",  "What is the impact of big data on businesses?",  "Explain how search engine algorithms work.",  "Describe the role of AI in healthcare.",  "How do facial recognition systems work?",  "What are the advantages and disadvantages of smart homes?",  "Explain the importance of ethical hacking.",  "How does augmented reality (AR) enhance user experience?",  "Describe how blockchain is used beyond cryptocurrency.",  "What is the role of AI in automation?",  "Explain how drone technology is evolving.",  "What are the risks of social media algorithms?",  "How do recommendation systems like Netflix and YouTube work?",  "Describe the future of wearable technology.",  "How do neural networks mimic the human brain?",  "What are the key features of Web3 technology?",  "Explain the impact of AI on job automation.",  "How do smart contracts work on the blockchain?",  "Describe the evolution of mobile phones.",  "What are the benefits of renewable energy technology?",  "How does a VPN enhance internet security?",  "Explain how satellites support global communication.",  "What is the role of AI in game development?",  "How does biometric authentication improve security?",  "Describe the process of ethical AI development.",  "What is the metaverse and how will it shape the future?",  "How do recommendation engines use AI?",  "What are the biggest cybersecurity threats today?",  "Explain the importance of coding in modern technology.",  "How does AI help in climate change research?",  "Describe how nanotechnology is used in medicine.",  "What are the future trends in robotics?",  "How does AI generate human-like text and images?",   "How will AI transform the healthcare industry in the next 10 years?",  "Explain the concept of nihilism in Friedrich Nietzsche%27s philosophy.",  "What are the effects of inflation on consumer purchasing power?",  "How can blockchain enhance data security?",  "Can artificial intelligence develop consciousness?",  "Describe the relationship between existentialism and individual freedom.",  "What are the key factors influencing a country%27s economic growth?",  "How can 5G technology revolutionize global communication?",  "Do humans have free will, or is everything predetermined?",  "How does monetary policy help control inflation?",  "What is the impact of automation on the job market?",  "Explain the difference between utilitarianism and deontology in ethics.",  "How can artificial intelligence be applied in education?",  "What is the Ship of Theseus paradox in the philosophy of identity?",  "How do tech startups disrupt traditional industries?",  "Will the singularity lead to superintelligent AI surpassing humans?",  "What role does quantum computing play in the future of cybersecurity?",  "Is capitalism the best economic system for innovation?",  "How does the concept of the %27Overman%27 shape Nietzsche%27s philosophy?",  "What are the ethical dilemmas of genetic engineering?",  "Can decentralized finance (DeFi) replace traditional banking?",  "What is the difference between Keynesian and classical economics?",  "How does the simulation hypothesis challenge our perception of reality?",  "Will renewable energy fully replace fossil fuels in the future?",  "What are the philosophical implications of the trolley problem?",  "How does game theory apply to real-world decision-making?",  "What is the role of big data in shaping modern economies?",  "How can AI help solve global climate change challenges?",  "What are the economic risks of increasing national debt?",  "Is universal basic income (UBI) a viable solution for the future economy?",  "How does the metaverse impact digital identity and privacy?",  "What are the consequences of algorithmic bias in AI systems?",  "Should governments regulate cryptocurrencies?",  "How does postmodernism critique traditional philosophical thought?",  "Can machines ever truly understand human emotions?",  "What are the implications of automation for economic inequality?",  "Is war an inevitable part of human nature?",  "How does transhumanism aim to enhance human capabilities?",  "What are the philosophical arguments for and against determinism?",  "How does artificial intelligence affect the future of creative industries?",  "What are the key differences between socialism and capitalism?",  "Can neuroscience explain human consciousness?",  "What are the ethical considerations of AI in warfare?",  "How do network effects contribute to the success of tech monopolies?",  "What is the impact of globalization on local economies?",  "Is privacy becoming obsolete in the digital age?",  "How does the concept of %27The Absurd%27 define existentialist thought?",  "What role does ethics play in the development of new technologies?",  "Will automation lead to mass unemployment or create new job opportunities?",  "What are the consequences of over-reliance on artificial intelligence?",  "How do behavioral economics challenge traditional economic theories?",  "Is space colonization a realistic goal for humanity?",  "What are the benefits and risks of brain-computer interfaces?",  "How does machine learning improve financial market predictions?",  "What is the future of human-AI collaboration in the workplace?",  "Can morality exist without religion?",  "How do economic sanctions impact global trade?",  "What is the role of philosophy in artificial intelligence development?",  "How does digital currency challenge traditional monetary systems?",  "What are the dangers of deepfake technology?",  "Should AI be granted legal rights and personhood?",  "How does the concept of %27The Will to Power%27 shape human ambition?",  "What are the key factors behind cryptocurrency price fluctuations?",  "Can democracy survive in an age of mass surveillance?",  "How do incentives shape human behavior in economic theory?",  "What are the consequences of wealth inequality on global stability?",  "How does AI influence the future of scientific discoveries?",  "Should AI-generated art be considered original?",  "What are the long-term effects of technological unemployment?",  "Can philosophy provide practical solutions for modern societal problems?",  "What are the risks and rewards of nuclear energy?",  "How does post-scarcity economics challenge traditional market principles?",  "What role does cyber warfare play in modern geopolitics?",  "Can virtual reality change the way we perceive reality?",  "How does the precautionary principle apply to emerging technologies?",  "What is the future of decentralized autonomous organizations (DAOs)?",  "How does the philosophy of pragmatism apply to technological innovation?",  "Will AI ever surpass human intelligence in creative thinking?",  "What is the relationship between technology and social inequality?",  "How does machine learning impact personalized medicine?",  "What are the ethical concerns surrounding mass data collection?",  "Can consciousness be artificially replicated?",  "How does scarcity affect decision-making in economics?",  "What are the philosophical arguments for and against artificial superintelligence?",  "How do global supply chains influence economic resilience?",  "Can blockchain technology prevent election fraud?",  "What are the moral implications of self-driving cars?",  "How does cognitive bias affect decision-making in economics?",  "What is the role of philosophy in the age of artificial intelligence?",  "Should technological singularity be feared or embraced?",  "How does automation impact small businesses compared to large corporations?",  "What are the consequences of over-reliance on social media algorithms?",  "Can technological progress be separated from ethical considerations?",  "What are the limitations of AI in understanding human emotions?",  "How does economic game theory apply to international relations?",  "Is artificial general intelligence (AGI) an inevitable outcome?",  "What is the impact of robotics on human employment?",  "How does the digital economy influence wealth distribution?",  "Can AI be held accountable for ethical decision-making?",  "What are the risks of AI surpassing human intelligence?",  "How does philosophy shape our understanding of virtual reality?",  "What are the key ethical concerns of mass surveillance?",  "Is technological progress inherently good for humanity?"];function shuffleArray(array){for(let i=array.length-1;i>0;i--){const j=Math.floor(Math.random()*(i+1));[array[i],array[j]]=[array[j],array[i]]}return array}const randomizedMessages=shuffleArray([...messages]);function waitForElement(selector,interval=500,timeout=10000){return new Promise((resolve,reject)=>{const start=Date.now();const check=()=>{const el=document.querySelector(selector);if(el){resolve(el)}else if(Date.now()-start>=timeout){reject(new Error(`Elemen dengan selector "${selector}" tidak ditemukan dalam waktu ${timeout}ms`))}else{setTimeout(check,interval)}};check()})}const getChatCountElement=()=>document.querySelector(%27div[class*="text-[#e8e8e8]"][class*="text-[13px]"]');const getTextarea=()=>document.querySelector('textarea[name="message"]');const getSubmitButton=()=>document.querySelector('button[type="submit"]');async function waitForButtonToEnable(){await waitForElement('button[type="submit"]');const submitButton=getSubmitButton();while(submitButton.disabled){console.log("Tombol submit masih disabled, mensimulasikan klik pada textarea untuk mengaktifkannya...");const textarea=getTextarea();if(textarea){textarea.click();textarea.focus();textarea.dispatchEvent(new Event("focus",{bubbles:true}));textarea.dispatchEvent(new Event("input",{bubbles:true}))}await new Promise(resolve=>setTimeout(resolve,500))}}async function sendChat(index){if(index>=randomizedMessages.length)return;let textarea=getTextarea();while(!textarea){console.log("Textarea tidak ditemukan, menunggu...");await new Promise(resolve=>setTimeout(resolve,1000));textarea=getTextarea()}let submitButton=getSubmitButton();while(!submitButton){console.log("Tombol submit tidak ditemukan, menunggu...");await new Promise(resolve=>setTimeout(resolve,1000));submitButton=getSubmitButton()}await waitForButtonToEnable();textarea.removeAttribute("disabled");textarea.value=randomizedMessages[index];textarea.dispatchEvent(new Event("input",{bubbles:true}));submitButton.click()}const observer=new MutationObserver(()=>{const chatCountDiv=getChatCountElement();if(!chatCountDiv)return;const currentCount=parseInt(chatCountDiv.textContent)||0;console.log(%60Jumlah chat saat ini: ${currentCount}%60);if(currentCount<randomizedMessages.length){sendChat(currentCount)}else{observer.disconnect();console.log("Proses automasi chat selesai (semua pesan terkirim).")}});async function startObserving(){await waitForElement('div[class*="text-[#e8e8e8]"][class*="text-[13px]"]');const chatCountDiv=getChatCountElement();observer.observe(chatCountDiv,{childList:true,characterData:true,subtree:true});sendChat(0)};startObserving()})();
```
5. Nanti tinggal masuk web klok, terus pencet boormark yang udah dibikin
