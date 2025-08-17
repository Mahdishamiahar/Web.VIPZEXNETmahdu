<!DOCTYPE html>
<html lang="fa" dir="rtl">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Al.VIPZEXNET — چت با هوش مصنوعی</title>
  <meta name="description" content="چت با مدل‌های متنوع هوش مصنوعی + آپلود فایل تا 10GB — Al.VIPZEXNET" />
  <link href="https://fonts.googleapis.com/css2?family=Vazirmatn:wght@300;400;700&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg-1:#0b1020;
      --bg-2:#0f1724;
      --card:#0f1728d9;
      --accent:#00d4ff;
      --accent-dark:#00aacc;
      --muted:#9fb3c8;
      --success:#22c55e;
      --danger:#ff5252;
      --glass: rgba(255,255,255,0.03);
    }
    *{box-sizing:border-box}
    html,body{height:100%;margin:0;font-family:"Vazirmatn",system-ui,-apple-system,Segoe UI,Roboto,"Tahoma",sans-serif;background:
      radial-gradient(800px 400px at 10% 10%, rgba(0,212,255,0.03), transparent),
      linear-gradient(180deg,var(--bg-1),var(--bg-2));color:#e6f0f6}
    header{display:flex;align-items:center;gap:14px;padding:18px 22px;border-bottom:1px solid rgba(255,255,255,.03);backdrop-filter:blur(6px)}
    .brand{display:flex;align-items:center;gap:12px;font-weight:800;color:var(--accent)}
    .brand-logo{width:42px;height:42px;border-radius:10px;background:linear-gradient(135deg,var(--accent),#0affb3);display:grid;place-items:center;color:#03201a;font-weight:900;box-shadow:0 8px 30px rgba(0,0,0,.5)}
    .title{font-size:18px}
    .layout{display:grid;grid-template-columns:360px 1fr;gap:18px;padding:18px;max-width:1200px;margin:18px auto;align-items:start}
    @media (max-width:980px){.layout{grid-template-columns:1fr;padding:12px}}
    /* left panel */
    .panel{background:var(--card);border-radius:14px;padding:16px;border:1px solid rgba(255,255,255,.03);box-shadow:0 10px 30px rgba(0,0,0,.5)}
    .panel h3{margin:0 0 10px;font-size:16px;color:var(--accent)}
    label.small{display:block;font-size:13px;color:var(--muted);margin-bottom:6px}
    select,input[type="text"],textarea{width:100%;padding:10px;border-radius:10px;border:1px solid rgba(255,255,255,.04);background:transparent;color:inherit}
    button.btn{background:var(--accent);border:none;color:#062015;padding:10px 14px;border-radius:10px;font-weight:700;cursor:pointer}
    button.btn:hover{background:var(--accent-dark)}
    .models{display:flex;flex-direction:column;gap:8px}
    .small-muted{font-size:13px;color:var(--muted);margin-top:6px}
    .row{display:flex;gap:8px;align-items:center}
    .footer-note{font-size:12px;color:var(--muted);margin-top:10px}

    /* chat area */
    .chat-area{display:flex;flex-direction:column;height:75vh;min-height:520px;border-radius:14px;overflow:hidden;border:1px solid rgba(255,255,255,.03)}
    @media (max-width:980px){.chat-area{height:70vh;min-height:420px}}
    .chat-top{padding:12px 16px;background:linear-gradient(180deg, rgba(255,255,255,.02), transparent);display:flex;align-items:center;justify-content:space-between;border-bottom:1px solid rgba(255,255,255,.02)}
    .chat-top .meta{display:flex;flex-direction:column}
    .chat-top .meta .site{font-weight:800;color:var(--accent)}
    .chat-top .meta .sub{font-size:13px;color:var(--muted)}
    .chat-body{flex:1;overflow:auto;padding:18px;display:flex;flex-direction:column;gap:12px;background:
      linear-gradient(180deg, rgba(255,255,255,0.008), transparent)}
    .bubbles{display:flex;flex-direction:column;gap:10px;max-width:100%}
    .bubble{max-width:78%;padding:12px 14px;border-radius:14px;line-height:1.6;word-break:break-word;box-shadow:0 6px 18px rgba(0,0,0,.45)}
    .bubble.user{align-self:flex-end;background:linear-gradient(180deg,var(--accent),#00f0b5);color:#062015;border-bottom-right-radius:6px}
    .bubble.bot{align-self:flex-start;background:#0e1420;color:#cfeef0;border-bottom-left-radius:6px;border:1px solid rgba(255,255,255,.02)}
    .bubble.error{background:linear-gradient(180deg,#ff6b6b,#ff3b3b);color:#fff}
    .typing{font-style:italic;opacity:.9;color:var(--muted)}

    .chat-bottom{padding:14px;background:linear-gradient(180deg, transparent, rgba(0,0,0,0.2));display:flex;gap:10px;align-items:flex-end;border-top:1px solid rgba(255,255,255,.02)}
    .input-wrap{flex:1;display:flex;flex-direction:column;gap:8px}
    .controls{display:flex;gap:8px;align-items:center}
    .file-preview{font-size:13px;color:var(--muted)}
    .tool-btn{background:var(--glass);border:1px solid rgba(255,255,255,.04);padding:8px 10px;border-radius:10px;color:var(--muted);cursor:pointer}
    .tool-btn:hover{color:var(--accent)}
    .small{font-size:13px;color:var(--muted)}

    /* nice scrollbar */
    .chat-body::-webkit-scrollbar{width:10px}
    .chat-body::-webkit-scrollbar-thumb{background:rgba(255,255,255,.05);border-radius:10px}
    .chat-body::-webkit-scrollbar-track{background:transparent}

    /* responsive adjustments */
    @media (max-width:600px){
      .bubble{max-width:90%}
      .layout{gap:12px}
    }
  </style>
</head>
<body>
  <header>
    <div class="brand">
      <div class="brand-logo">A</div>
      <div class="title">Al.VIPZEXNET</div>
    </div>
    <div style="flex:1"></div>
    <div style="font-size:13px;color:var(--muted)">چت با مدل‌های هوش مصنوعی — آپلود فایل تا 10GB</div>
  </header>

  <main class="layout">
    <!-- left panel: settings -->
    <aside class="panel" aria-labelledby="settings">
      <h3 id="settings">تنظیمات & مدل‌ها</h3>

      <label class="small" for="backendSelect">انتخاب وب‌سرویس (Backend)</label>
      <select id="backendSelect" aria-label="انتخاب وب سرویس">
        <option value="api2">api2.api-code.ir (POST)</option>
        <option value="hoshi">hoshi-app.ir (GET)</option>
      </select>
      <div class="small-muted">برای api2 پارامترهای userid/prompt/model ارسال می‌شود. برای hoshi فقط متن در پارامتر text</div>

      <div style="height:10px"></div>

      <label class="small" for="modelSelect">انتخاب مدل (model)</label>
      <select id="modelSelect" aria-label="انتخاب مدل">
        <option value="openai">openai</option>
        <option value="deepseek">deepseek</option>
        <option value="mistral">mistral (تصویر)</option>
        <option value="openai-large">openai-large (GPT-4)</option>
      </select>
      <div class="footer-note">می‌توانید مدل را قبل از شروع چت انتخاب کنید یا در حین چت تغییر دهید.</div>

      <hr style="margin:12px 0;border:none;border-top:1px solid rgba(255,255,255,.02)">

      <h3>تنظیمات کاربر</h3>
      <label class="small" for="userId">User ID (دلخواه)</label>
      <input id="userId" type="text" value="user123" placeholder="user123" />

      <div style="height:10px"></div>

      <h3>آپلود فایل (اختیاری)</h3>
      <div class="small-muted">فایل‌ها تا 10GB. بعد از آپلود لینک مستقیم نمایش داده و (در صورت فعال) به مدل ارسال می‌شود.</div>
      <div style="height:8px"></div>
      <div class="row">
        <input id="fileInputPanel" type="file" style="display:block" />
      </div>
      <div style="height:8px"></div>
      <label style="display:flex;gap:8px;align-items:center">
        <input id="autoSendFileToAI" type="checkbox" /> <span class="small">بعد از آپلود لینک فایل را به مدل ارسال کن</span>
      </label>

      <hr style="margin:12px 0;border:none;border-top:1px solid rgba(255,255,255,.02)">

      <button class="btn" id="startBtn" onclick="startChat()">شروع چت</button>
      <div class="footer-note">نکته: APIها باید CORS را فعال کرده باشند تا پاسخ در مرورگر دریافت شود.</div>
    </aside>

    <!-- chat area -->
    <section class="panel chat-area" aria-live="polite">
      <div class="chat-top">
        <div class="meta">
          <div class="site">Al.VIPZEXNET — Chat</div>
          <div class="sub">مدل: <span id="currentModel" style="color:var(--accent)"></span> · سرویس: <span id="currentBackend" style="color:var(--accent)"></span></div>
        </div>
        <div>
          <button class="tool-btn" onclick="clearChat()" title="پاک کردن چت">پاک کردن چت</button>
        </div>
      </div>

      <div id="chatBody" class="chat-body" role="log" aria-atomic="true">
        <div class="bubbles" id="bubbles">
          <div class="bubble bot">👋 سلام! خوش آمدی. مدل و سرویس رو انتخاب کن و شروع کن.</div>
        </div>
      </div>

      <div class="chat-bottom">
        <div class="input-wrap">
          <textarea id="userInput" rows="2" placeholder="پیام خود را بنویسید... (Enter = ارسال، Shift+Enter = خط جدید)"></textarea>
          <div class="controls" style="justify-content:space-between">
            <div>
              <label class="small" style="margin-left:8px">ارسال به عنوان:</label>
              <select id="messageTarget">
                <option value="ai">ارسال به مدل انتخاب شده</option>
                <option value="system">پیام سیستمی (metadata)</option>
              </select>
            </div>

            <div style="display:flex;gap:8px;align-items:center">
              <label class="small">ارسال فایل:</label>
              <button class="tool-btn" id="attachBtn" title="پیوست فایل" onclick="document.getElementById('fileInput').click()">📎 پیوست</button>
              <span id="fileName" class="file-preview small-muted"></span>
              <button class="tool-btn" id="sendFileBtn" onclick="sendAttachedFile()" title="آپلود و ارسال فایل">📤 آپلود</button>
              <button class="btn" id="sendBtn" onclick="handleSend()">ارسال</button>
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>

  <script>
    // ---------- Helper & state ----------
    const bubbles = document.getElementById('bubbles');
    const userInput = document.getElementById('userInput');
    const modelSelect = document.getElementById('modelSelect');
    const backendSelect = document.getElementById('backendSelect');
    const currentModelEl = document.getElementById('currentModel');
    const currentBackendEl = document.getElementById('currentBackend');
    const userIdInput = document.getElementById('userId');
    const fileInput = document.getElementById('fileInput');
    const fileInputPanel = document.getElementById('fileInputPanel');
    const fileNameEl = document.getElementById('fileName');
    const autoSendFileToAI = document.getElementById('autoSendFileToAI');

    let attachedFile = null;
    let chatEnabled = false;

    function startChat(){
      chatEnabled = true;
      updateHeader();
      document.querySelector('#home')?.style?.setProperty('display','none');
      // focus textarea
      userInput.focus();
      addBotBubble(`چت آماده است. مدل "${modelSelect.value}" و سرویس "${backendSelect.value}" انتخاب شد.`);
    }

    function updateHeader(){
      currentModelEl.textContent = modelSelect.value;
      currentBackendEl.textContent = backendSelect.value;
    }

    modelSelect.addEventListener('change', updateHeader);
    backendSelect.addEventListener('change', updateHeader);

    // ---------- UI helpers ----------
    function addBubble(text, who='bot', opts={}) {
      const div = document.createElement('div');
      div.className = 'bubble ' + (who==='user' ? 'user' : (opts.error? 'error bot' : 'bot'));
      // allow small HTML for links
      div.innerHTML = text;
      bubbles.appendChild(div);
      // scroll to bottom
      const chatBody = document.getElementById('chatBody');
      setTimeout(()=> chatBody.scrollTop = chatBody.scrollHeight, 30);
      return div;
    }
    function addUserBubble(text){ return addBubble(escapeHtml(text), 'user'); }
    function addBotBubble(html){ return addBubble(html, 'bot'); }
    function addErrorBubble(text){ return addBubble(escapeHtml(text), 'bot', {error:true}); }

    function escapeHtml(s){ return String(s).replace(/[&<>"']/g, c => ({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c])); }

    function clearChat(){
      bubbles.innerHTML = '';
      addBotBubble('👋 چت پاک شد. آماده شروع مجدد.');
    }

    // ---------- send flow ----------
    async function handleSend(){
      if(!chatEnabled){ alert('ابتدا روی "شروع چت" کلیک کنید.'); return; }
      const text = userInput.value.trim();
      if(!text) return;
      // show user bubble
      addUserBubble(text);
      userInput.value = '';
      // call AI
      await callSelectedBackend(text);
    }

    // Allow Enter to send (Shift+Enter newline)
    userInput.addEventListener('keydown', (e)=>{
      if(e.key==='Enter' && !e.shiftKey){
        e.preventDefault();
        handleSend();
      }
    });

    // ---------- backend calls ----------
    async function callSelectedBackend(promptText){
      updateHeader();
      const backend = backendSelect.value;
      const model = modelSelect.value;
      const userid = userIdInput.value || 'user123';

      // add typing indicator
      const typingNode = addBotBubble('<span class="typing">در حال گرفتن پاسخ...</span>');

      try{
        let aiResponse = '';

        if(backend === 'api2'){
          // POST form: userid, prompt, model
          const form = new FormData();
          form.append('userid', userid);
          form.append('prompt', promptText);
          form.append('model', model);

          const res = await fetch('https://api2.api-code.ir/gpt-save-v2/', {
            method: 'POST',
            body: form
          });
          // try JSON then text fallback
          const ct = res.headers.get('content-type') || '';
          if(ct.includes('application/json')){
            const json = await res.json();
            // common field? we don't know exact structure — try common props
            aiResponse = json.response || json.result || json.data || JSON.stringify(json);
          } else {
            aiResponse = await res.text();
          }
        } else if(backend === 'hoshi'){
          // GET with text param
          const url = 'https://hoshi-app.ir/api/chat-gpt.php?text=' + encodeURIComponent(promptText);
          const res = await fetch(url);
          aiResponse = await res.text();
        } else {
          aiResponse = 'Backend انتخاب شده پشتیبانی نمی‌شود.';
        }

        // remove typing and show response
        typingNode.remove();
        if(!aiResponse) aiResponse = '[پاسخ خالی از سرور دریافت شد]';
        // allow HTML anchors if response contains URL — convert newlines to <br>
        addBotBubble(linkifyHtml(aiResponse));
      } catch(err){
        typingNode.remove();
        console.error(err);
        addErrorBubble('❌ خطا در گرفتن پاسخ از سرور. لطفاً اتصال API/CORS را بررسی کنید.');
      }
    }

    // ---------- file attach & upload ----------
    // file input in chat bottom
    document.getElementById('fileInput').addEventListener('change', (e)=>{
      attachedFile = e.target.files[0] || null;
      fileNameEl.textContent = attachedFile ? attachedFile.name : '';
    });
    // left panel file
    fileInputPanel.addEventListener('change', (e)=>{
      const f = e.target.files[0];
      if(!f) return;
      // if user wants, upload from left panel and optionally notify AI
      uploadFileToServer(f, {autoSend: autoSendFileToAI.checked});
    });

    async function sendAttachedFile(){
      if(!attachedFile){
        alert('فایلی پیوست نشده است. از دکمه 📎 فایل انتخاب کنید.');
        return;
      }
      // upload and (optionally) send link to AI
      await uploadFileToServer(attachedFile, {autoSend: true});
      // clear attached
      attachedFile = null;
      document.getElementById('fileInput').value = '';
      fileNameEl.textContent = '';
    }

    async function uploadFileToServer(file, opts={autoSend:false}){
      // show user bubble about upload start
      addUserBubble('آپلود فایل: ' + file.name);
      const form = new FormData();
      form.append('file', file, file.name);

      try{
        const res = await fetch('https://vddaniyel.top/upload_api.php', {
          method: 'POST',
          body: form
        });
        const json = await res.json();
        if(json && json.success){
          const link = json.direct_link;
          addBotBubble(`✅ فایل آپلود شد: <a href="${link}" target="_blank" rel="noopener">${escapeHtml(link)}</a>`);
          // if user asked to auto-send file link to AI, do it
          if(opts.autoSend){
            // send link as prompt to AI (prepend note)
            const prompt = `این لینک فایل آپلود شده را بررسی کن: ${link}`;
            await callSelectedBackend(prompt);
          }
        } else {
          addErrorBubble('❌ آپلود موفق نبود. پاسخ سرور: ' + (JSON.stringify(json)));
        }
      } catch(err){
        console.error(err);
        addErrorBubble('❌ خطا در اتصال به سرویس آپلود. امکان آپلود وجود ندارد.');
      }
    }

    // ---------- utilities ----------
    function linkifyHtml(text){
      // escape then convert URLs to anchors and newlines to <br>
      const esc = escapeHtml(text);
      const urlRegex = /(https?:\/\/[^\s<]+)/g;
      const withLinks = esc.replace(urlRegex, '<a href="$1" target="_blank" rel="noopener">$1</a>');
      return withLinks.replace(/\n/g, '<br>');
    }

    // initial header update
    updateHeader();

    // expose some functions to global for console if needed
    window.clearChat = clearChat;
    window.startChat = startChat;
    window.sendAttachedFile = sendAttachedFile;
    window.handleSend = handleSend;
  </script>
</body>
</html>
