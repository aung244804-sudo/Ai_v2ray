# AI V2RAY CLIENT — STANDALONE PURE UI CODE PACK (UI ONLY)
## Architecture: Pure UI Presentation Layer (No backend, No native VPN engine required)
## Deliverables Included:
## 1. `index.html` (Standalone Single-File Web UI with Tailwind, CSS Animations & Interactivity)
## 2. `MainDashboardScreen.kt` (Jetpack Compose Material 3 Pure UI File for Android Studio)

---

### ၁။ Standalone Single-File Web UI (`index.html`)
Browser ပေါ်တွင် double-click နှိပ်ရုံဖြင့် တိုက်ရိုက်ဖွင့်နိုင်ပြီး Responsive Mobile 390px အဖြစ် ဖန်တီးထားသော Complete HTML/CSS UI File ဖြစ်ပါသည်။

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8"/>
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no"/>
  <title>AI V2Ray Client - Violet Neon Glass UI</title>
  <script src="https://cdn.tailwindcss.com?plugins=forms,container-queries"></script>
  <link rel="preconnect" href="https://fonts.googleapis.com"/>
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin=""/>
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@600;700;800;900&family=Padauk:wght@400;700&family=Rajdhani:wght@500;600;700&family=Share+Tech+Mono&display=swap" rel="stylesheet"/>
  
  <style>
    body {
      background-color: #0b0a12;
      background-image: 
        radial-gradient(ellipse 80% 50% at 50% -10%, rgba(139, 92, 246, 0.22), transparent 70%),
        radial-gradient(ellipse 60% 40% at 50% 110%, rgba(99, 102, 241, 0.18), transparent 70%),
        radial-gradient(circle at 10% 45%, rgba(168, 85, 247, 0.08), transparent 40%),
        radial-gradient(circle at 90% 65%, rgba(6, 182, 212, 0.08), transparent 40%);
      font-family: 'Share Tech Mono', monospace;
      color: #e2e8f0;
      -webkit-font-smoothing: antialiased;
      margin: 0;
      padding: 0;
      overflow-x: hidden;
      user-select: none;
    }

    .neon-glass-panel {
      position: relative;
      background: linear-gradient(135deg, rgba(168, 85, 247, 0.12) 0%, rgba(30, 20, 55, 0.55) 45%, rgba(15, 10, 30, 0.75) 100%);
      backdrop-filter: blur(20px);
      -webkit-backdrop-filter: blur(20px);
      border: 1px solid rgba(192, 132, 252, 0.45);
      box-shadow: 
        0 0 16px -2px rgba(168, 85, 247, 0.4),
        0 0 32px -4px rgba(139, 92, 246, 0.2),
        inset 0 1px 1px 0 rgba(243, 232, 255, 0.6),
        inset 0 -1px 2px 0 rgba(147, 51, 234, 0.3);
      overflow: hidden;
    }

    .neon-glass-panel::before {
      content: '';
      position: absolute;
      top: -1px;
      left: 14%;
      width: 48px;
      height: 3px;
      background: #ffffff;
      border-radius: 9999px;
      box-shadow: 
        0 0 8px 3px rgba(255, 255, 255, 0.95),
        0 0 18px 6px rgba(192, 132, 252, 0.9),
        0 0 28px 10px rgba(147, 51, 234, 0.7);
      pointer-events: none;
      z-index: 10;
    }

    .neon-glass-pill {
      position: relative;
      background: linear-gradient(135deg, rgba(168, 85, 247, 0.14) 0%, rgba(25, 18, 48, 0.6) 100%);
      backdrop-filter: blur(16px);
      -webkit-backdrop-filter: blur(16px);
      border: 1px solid rgba(192, 132, 252, 0.4);
      box-shadow: 0 0 14px -1px rgba(168, 85, 247, 0.35), inset 0 1px 1px rgba(255, 255, 255, 0.5);
      transition: all 0.2s ease;
    }

    .neon-glass-pill.active {
      background: linear-gradient(135deg, rgba(192, 132, 252, 0.28) 0%, rgba(79, 70, 229, 0.45) 100%);
      border-color: rgba(216, 180, 254, 0.85);
      box-shadow: 0 0 18px rgba(168, 85, 247, 0.65), inset 0 1px 2px rgba(255, 255, 255, 0.8);
    }

    .neon-inner-well {
      background: rgba(9, 6, 18, 0.75);
      border: 1px solid rgba(168, 85, 247, 0.25);
      box-shadow: inset 0 2px 6px rgba(0, 0, 0, 0.85), 0 0 10px rgba(139, 92, 246, 0.1);
    }

    .engraved-title-neon {
      font-family: 'Orbitron', sans-serif;
      background: linear-gradient(180deg, #ffffff 0%, #f0abfc 40%, #c084fc 70%, #a855f7 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      filter: drop-shadow(0 0 12px rgba(192, 132, 252, 0.8)) drop-shadow(0 0 4px rgba(255, 255, 255, 0.4));
    }

    @keyframes ecgStreak {
      0% { stroke-dashoffset: 420; opacity: 0; }
      10% { opacity: 1; }
      85% { opacity: 1; }
      100% { stroke-dashoffset: -420; opacity: 0; }
    }
    .ecg-beam-pulse {
      stroke-dasharray: 55 365;
      stroke-dashoffset: 420;
      animation: ecgStreak 2.4s cubic-bezier(0.4, 0.0, 0.2, 1) infinite;
    }

    @keyframes rainbowBorderRun {
      0% { stroke-dashoffset: 0; }
      100% { stroke-dashoffset: -1100; }
    }
    .rainbow-border-laser {
      stroke-dasharray: 120 430;
      animation: rainbowBorderRun 4.5s linear infinite;
    }

    @keyframes zigzagLaser {
      0% { stroke-dashoffset: 950; opacity: 0; }
      8% { opacity: 0.95; }
      90% { opacity: 0.95; }
      100% { stroke-dashoffset: 0; opacity: 0; }
    }
    .switch-on-zigzag {
      stroke-dasharray: 140 810;
      animation: zigzagLaser 3.2s cubic-bezier(0.25, 0.1, 0.25, 1) infinite;
    }

    .neon-breathing {
      animation: powerGlowNeon 2.8s ease-in-out infinite;
    }
    @keyframes powerGlowNeon {
      0%, 100% { box-shadow: 0 0 18px 4px rgba(168, 85, 247, 0.7); }
      50% { box-shadow: 0 0 32px 9px rgba(192, 132, 252, 0.95); }
    }
  </style>
</head>
<body class="flex justify-center items-start min-h-screen py-1 px-1">
  <main class="w-[390px] min-h-[844px] flex flex-col justify-between p-3.5 box-border select-none relative">
    
    <!-- Top Header -->
    <div class="space-y-1.5">
      <header class="flex justify-between items-center text-[10.5px] font-bold tracking-wider text-[#cbd5e1] px-1">
        <span class="text-[#a855f7] font-mono">CH-01 // AI-HW</span>
        <div class="flex items-center neon-glass-pill px-3 py-0.5 rounded-full">
          <span class="w-2 h-2 rounded-full bg-[#10b981] mr-1.5 animate-pulse"></span>
          <span class="text-[9px] text-[#f8fafc] font-extrabold uppercase">SECURE TUNNEL</span>
        </div>
        <span>BAT 98% ⚡</span>
      </header>

      <!-- Main Title with Laser ECG -->
      <section class="neon-glass-panel rounded-2xl px-4 py-2.5 relative">
        <div class="text-center relative py-0.5">
          <h1 class="engraved-title-neon text-[22px] font-black tracking-wider leading-none">AI V2RAY CLIENT</h1>
          <div class="relative w-full h-4 my-0.5 flex items-center justify-center pointer-events-none">
            <svg class="w-full h-full overflow-visible" viewBox="0 0 340 20">
              <defs>
                <linearGradient id="ecgGrad" x1="0%" y1="0%" x2="100%" y2="0%">
                  <stop offset="0%" stop-color="#00f0ff" stop-opacity="0"></stop>
                  <stop offset="70%" stop-color="#00f0ff" stop-opacity="0.9"></stop>
                  <stop offset="100%" stop-color="#ffffff" stop-opacity="1"></stop>
                </linearGradient>
              </defs>
              <line x1="0" y1="10" x2="340" y2="10" stroke="#a855f7" stroke-width="0.8" stroke-dasharray="2 2" opacity="0.35"></line>
              <path d="M 0 10 L 110 10 L 122 10 L 128 2 L 134 18 L 140 6 L 146 13 L 152 10 L 198 10 L 205 10 L 210 2 L 217 18 L 223 7 L 228 13 L 234 10 L 340 10" fill="none" stroke="#f43f5e" stroke-width="1.7"></path>
              <path class="ecg-beam-pulse" d="M 0 10 L 110 10 L 122 10 L 128 2 L 134 18 L 140 6 L 146 13 L 152 10 L 198 10 L 205 10 L 210 2 L 217 18 L 223 7 L 228 13 L 234 10 L 340 10" fill="none" stroke="url(#ecgGrad)" stroke-width="2.6" stroke-linecap="round"></path>
            </svg>
          </div>
          <p class="text-[9px] text-[#c084fc] tracking-[0.16em] font-extrabold uppercase">
            PRECISION TUNNEL ENGINE ■ XRAY CORE V1.8.16
          </p>
        </div>
      </section>
    </div>

    <!-- Gemini Engine API Section -->
    <section class="neon-glass-panel rounded-2xl p-2.5 my-1.5">
      <div class="flex items-center justify-between mb-2">
        <span class="text-[10px] font-black text-[#f8fafc] uppercase font-['Orbitron']">GEMINI AI TUNNEL ENGINE</span>
        <a class="neon-glass-pill px-2 py-0.5 rounded-full text-[8px] font-bold text-[#c084fc]" href="https://aistudio.google.com" target="_blank">aistudio.google.com ↗</a>
      </div>
      <div class="neon-inner-well rounded-xl p-1.5 flex items-center justify-between">
        <input class="bg-transparent text-[9.5px] font-mono text-[#f8fafc] w-full border-none p-0 focus:outline-none" placeholder="Paste Gemini API Key..." type="password" value="AIzaSyD-98124xK93..."/>
        <button class="neon-glass-pill active px-2.5 py-1 rounded-lg text-[8.5px] font-black uppercase text-[#f8fafc]" onclick="alert('Verified')">VERIFY</button>
      </div>
    </section>

    <!-- Speedometer & Central Chassis Knob -->
    <section class="neon-glass-panel rounded-3xl p-3 my-1 relative">
      <svg class="absolute inset-0 w-full h-full pointer-events-none z-20 overflow-visible" viewBox="0 0 362 196">
        <defs>
          <linearGradient id="rainbowSpectrum" x1="0%" y1="0%" x2="100%" y2="100%">
            <stop offset="0%" stop-color="#ff0055"></stop>
            <stop offset="50%" stop-color="#00f0ff"></stop>
            <stop offset="100%" stop-color="#a855f7"></stop>
          </linearGradient>
        </defs>
        <rect class="rainbow-border-laser" x="1" y="1" width="360" height="194" rx="23" ry="23" fill="none" stroke="url(#rainbowSpectrum)" stroke-width="1.3"></rect>
        <path class="switch-on-zigzag" d="M 24 2 L 338 2 L 360 24 L 360 88 L 2 110 L 360 135 L 360 172 L 338 194 L 24 194 L 2 172 L 2 24 Z" fill="none" stroke="url(#rainbowSpectrum)" stroke-width="1.1"></path>
      </svg>

      <div class="grid grid-cols-3 gap-1 items-center justify-items-center relative z-10">
        <!-- Latency -->
        <div class="flex flex-col items-center">
          <div class="w-[72px] h-[72px] rounded-full bg-[#0a0715]/90 border border-[#a855f7]/40 flex flex-col items-center justify-center">
            <span class="text-[#ff9f1c] font-black text-[12px]">38</span>
            <span class="text-[7px] text-[#c084fc] uppercase">MS PING</span>
          </div>
          <span class="text-[8.5px] font-extrabold text-[#d8b4fe] mt-1">LATENCY</span>
        </div>

        <!-- Reactor Knob -->
        <div class="flex flex-col items-center">
          <button class="w-[88px] h-[88px] rounded-full bg-gradient-to-b from-[#2e1065] to-[#090314] neon-breathing border border-[#c084fc] flex flex-col items-center justify-center active:scale-95 transition-all shadow-[0_0_20px_rgba(168,85,247,0.7)]" onclick="this.classList.toggle('active')">
            <span class="text-white text-base">⚡</span>
            <span class="text-[#34d399] text-[8px] font-black tracking-widest mt-0.5">ONLINE</span>
          </button>
          <span class="text-[8.5px] font-extrabold text-[#d8b4fe] mt-1">MAIN CHASSIS</span>
        </div>

        <!-- Bandwidth -->
        <div class="flex flex-col items-center">
          <div class="w-[72px] h-[72px] rounded-full bg-[#0a0715]/90 border border-[#06b6d4]/40 flex flex-col items-center justify-center">
            <span class="text-[#22d3ee] font-black text-[12px]">24.8</span>
            <span class="text-[7px] text-[#67e8f9] uppercase">MB/S</span>
          </div>
          <span class="text-[8.5px] font-extrabold text-[#d8b4fe] mt-1">BANDWIDTH</span>
        </div>
      </div>

      <!-- RX / TX Data -->
      <div class="grid grid-cols-2 gap-2 mt-1.5 pt-1.5 border-t border-purple-500/20 relative z-10">
        <div class="neon-inner-well rounded-xl px-2.5 py-1 flex items-center justify-between">
          <span class="text-[8.5px] font-bold text-[#c084fc]">RX RECVD</span>
          <span class="text-[11px] font-black text-[#f97316] font-['Orbitron']">342.85 MB</span>
        </div>
        <div class="neon-inner-well rounded-xl px-2.5 py-1 flex items-center justify-between">
          <span class="text-[8.5px] font-bold text-[#67e8f9]">TX SENT</span>
          <span class="text-[11px] font-black text-[#22d3ee] font-['Orbitron']">089.40 MB</span>
        </div>
      </div>
    </section>

    <!-- Active Server Drawer -->
    <section class="neon-glass-panel rounded-2xl p-2.5 my-1.5 flex items-center justify-between">
      <div class="flex items-center space-x-2">
        <span class="text-2xl">🇸🇬</span>
        <div>
          <div class="text-[11.5px] font-bold text-[#f8fafc]">SG-Cloudflare-Reality-01</div>
          <div class="text-[8px] text-[#c084fc]">VLESS-XTLS | PORT: 443 | TLS 1.3</div>
        </div>
      </div>
      <button class="neon-glass-pill px-2.5 py-1.5 rounded-xl text-[9px] font-extrabold text-[#f8fafc]">SWITCH ⇅</button>
    </section>

    <!-- Dual AI Telemetry Console -->
    <section class="neon-glass-panel rounded-2xl p-2.5 my-1.5">
      <div class="flex items-center justify-between pb-1.5 mb-1.5 border-b border-purple-500/25">
        <span class="text-[9px] font-black text-[#f8fafc] font-['Orbitron']">AI DUAL TELEMETRY CONSOLE</span>
        <span class="text-[7.5px] font-mono bg-[#2e1065] text-[#38bdf8] border border-[#38bdf8]/40 px-1.5 py-0.5 rounded">SYNCED // 120Hz</span>
      </div>
      <div class="grid grid-cols-2 gap-1.5 text-[8px] font-mono">
        <div class="bg-[#05030b]/90 rounded-lg border border-[#a855f7]/30 p-2 leading-relaxed">
          <div class="text-[#c084fc] font-bold">[1] GEMINI-PRO-CORE</div>
          <p class="text-[#94a3b8]">&gt; Route: DPI bypassed</p>
          <p class="text-[#34d399]">&gt; Hop: SIN-CF (0.8ms)</p>
          <p class="text-[#fbbf24]">&gt; Opt: 100% locked █</p>
        </div>
        <div class="bg-[#05030b]/90 rounded-lg border border-[#06b6d4]/30 p-2 leading-relaxed">
          <div class="text-[#22d3ee] font-bold">[2] NEURAL-ENGINE-V2</div>
          <p class="text-[#94a3b8]">&gt; Latency jitter &lt; 1.2ms</p>
          <p class="text-[#67e8f9]">&gt; UDP priority enabled</p>
          <p class="text-[#22d3ee]">&gt; Zero drop rate conf █</p>
        </div>
      </div>
    </section>

    <!-- Footer -->
    <footer class="flex items-center justify-between text-[8.5px] text-[#94a3b8] font-bold py-1">
      <div class="neon-glass-pill px-2 py-0.5 rounded-full text-white">English / မြန်မာ</div>
      <div class="text-right text-[#a855f7]">CHASSIS SERIAL: SS-V2R-99201</div>
    </footer>
  </main>
</body>
</html>
```

---

### ၂။ Android Studio Jetpack Compose Pure UI File (`MainDashboardScreen.kt`)
Android Studio ပရောဂျက်ထဲသို့ ချက်ချင်း copy & paste ပြုလုပ်၍ Preview ကြည့်ရှုနိုင်သော Jetpack Compose Material 3 UI code ဖြစ်ပါသည်။

```kotlin
package com.aiv2ray.client.presentation.dashboard

import androidx.compose.animation.core.*
import androidx.compose.foundation.Canvas
import androidx.compose.foundation.background
import androidx.compose.foundation.border
import androidx.compose.foundation.clickable
import androidx.compose.foundation.layout.*
import androidx.compose.foundation.rememberScrollState
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.foundation.shape.RoundedCornerShape
import androidx.compose.foundation.verticalScroll
import androidx.compose.material3.*
import androidx.compose.runtime.*
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.draw.drawBehind
import androidx.compose.ui.draw.shadow
import androidx.compose.ui.geometry.Offset
import androidx.compose.ui.geometry.Size
import androidx.compose.ui.graphics.*
import androidx.compose.ui.graphics.drawscope.Stroke
import androidx.compose.ui.text.font.FontFamily
import androidx.compose.ui.text.font.FontWeight
import androidx.compose.ui.tooling.preview.Preview
import androidx.compose.ui.unit.dp
import androidx.compose.ui.unit.sp
import kotlin.math.cos
import kotlin.math.sin

// MARK: - Color Palette
object NeonPalette {
    val DeepBackground = Color(0xFF07040D)
    val GlassSurface = Color(0x331E1238)
    val GlassBorder = Color(0x4D9D4EDD)
    val GlassSpecular = Color(0x80D8B4FE)
    val VioletNeon = Color(0xFF8B5CF6)
    val VioletNeonGlow = Color(0xFFC084FC)
    val CyanPulse = Color(0xFF38BDF8)
    val AlertOrange = Color(0xFFF97316)
    val NeonGreen = Color(0xFF22C55E)
    val TextMuted = Color(0xFF94A3B8)
    val TextPrimary = Color(0xFFF8FAFC)
}

// MARK: - Standalone Pure UI Dashboard Composable
@Preview(showBackground = true, widthDp = 390, heightDp = 844)
@Composable
fun MainDashboardScreen() {
    var isConnected by remember { mutableStateOf(true) }
    var apiKeyText by remember { mutableStateOf("AIzaSyB_RECON_77x9Q8") }
    var isEnglish by remember { mutableStateOf(true) }

    Box(
        modifier = Modifier
            .fillMaxSize()
            .background(NeonPalette.DeepBackground)
            .statusBarsPadding()
    ) {
        Column(
            modifier = Modifier
                .fillMaxSize()
                .verticalScroll(rememberScrollState())
                .padding(horizontal = 16.dp, vertical = 12.dp),
            horizontalAlignment = Alignment.CenterHorizontally,
            verticalArrangement = Arrangement.spacedBy(14.dp)
        ) {
            // 1. Status Bar
            Row(
                modifier = Modifier.fillMaxWidth().padding(horizontal = 4.dp),
                horizontalArrangement = Arrangement.SpaceBetween,
                verticalAlignment = Alignment.CenterVertically
            ) {
                Text("CH-01 // AI-HW", color = NeonPalette.VioletNeonGlow, fontSize = 11.5.sp, fontFamily = FontFamily.Monospace, fontWeight = FontWeight.Bold)
                Row(
                    modifier = Modifier
                        .clip(RoundedCornerShape(12.dp))
                        .background(Color(0x3322C55E))
                        .padding(horizontal = 10.dp, vertical = 4.dp),
                    verticalAlignment = Alignment.CenterVertically
                ) {
                    Box(modifier = Modifier.size(6.dp).clip(CircleShape).background(NeonPalette.NeonGreen))
                    Spacer(Modifier.width(6.dp))
                    Text("SECURE TUNNEL", color = NeonPalette.TextPrimary, fontSize = 9.5.sp, fontWeight = FontWeight.Bold, fontFamily = FontFamily.Monospace)
                }
                Text("BAT 98% ⚡", color = NeonPalette.TextPrimary, fontSize = 11.5.sp, fontFamily = FontFamily.Monospace)
            }

            // 2. Title Banner Card
            Column(
                modifier = Modifier
                    .fillMaxWidth()
                    .clip(RoundedCornerShape(20.dp))
                    .background(NeonPalette.GlassSurface)
                    .border(1.dp, NeonPalette.GlassBorder, RoundedCornerShape(20.dp))
                    .padding(vertical = 14.dp, horizontal = 16.dp),
                horizontalAlignment = Alignment.CenterHorizontally
            ) {
                Text("AI V2RAY CLIENT", color = Color.White, fontSize = 21.sp, fontWeight = FontWeight.Black, fontFamily = FontFamily.Monospace, letterSpacing = 2.sp)
                Spacer(Modifier.height(4.dp))
                // Animated ECG Wave Canvas
                AnimatedEcgCanvas()
                Spacer(Modifier.height(4.dp))
                Text("PRECISION TUNNEL ENGINE ■ XRAY CORE V1.8.16", color = NeonPalette.TextMuted, fontSize = 8.5.sp, fontFamily = FontFamily.Monospace)
            }

            // 3. Gemini Engine Key Card
            Column(
                modifier = Modifier
                    .fillMaxWidth()
                    .clip(RoundedCornerShape(20.dp))
                    .background(NeonPalette.GlassSurface)
                    .border(1.dp, NeonPalette.GlassBorder, RoundedCornerShape(20.dp))
                    .padding(14.dp)
            ) {
                Row(modifier = Modifier.fillMaxWidth(), horizontalArrangement = Arrangement.SpaceBetween, verticalAlignment = Alignment.CenterVertically) {
                    Text("✦ GEMINI AI TUNNEL ENGINE", color = Color.White, fontSize = 11.5.sp, fontWeight = FontWeight.Bold, fontFamily = FontFamily.Monospace)
                    Text("aistudio.google.com ↗", color = NeonPalette.CyanPulse, fontSize = 10.sp, fontFamily = FontFamily.Monospace)
                }
                Spacer(Modifier.height(10.dp))
                Row(
                    modifier = Modifier
                        .fillMaxWidth()
                        .clip(RoundedCornerShape(12.dp))
                        .background(Color(0xFF0F081D))
                        .padding(horizontal = 12.dp, vertical = 6.dp),
                    verticalAlignment = Alignment.CenterVertically
                ) {
                    Text(text = "•••••••••••••••••••••••••", color = Color.White, fontSize = 11.sp, fontFamily = FontFamily.Monospace, modifier = Modifier.weight(1f))
                    Button(
                        onClick = {},
                        colors = ButtonDefaults.buttonColors(containerColor = NeonPalette.VioletNeon),
                        contentPadding = PaddingValues(horizontal = 12.dp, vertical = 2.dp),
                        shape = RoundedCornerShape(8.dp),
                        modifier = Modifier.height(28.dp)
                    ) {
                        Text("VERIFY", fontSize = 10.sp, fontWeight = FontWeight.Bold, fontFamily = FontFamily.Monospace)
                    }
                }
            }

            // 4. Center Gauges & Power Button Cluster
            Column(
                modifier = Modifier
                    .fillMaxWidth()
                    .clip(RoundedCornerShape(24.dp))
                    .background(NeonPalette.GlassSurface)
                    .border(1.dp, NeonPalette.GlassSpecular, RoundedCornerShape(24.dp))
                    .padding(16.dp),
                horizontalAlignment = Alignment.CenterHorizontally
            ) {
                Row(modifier = Modifier.fillMaxWidth(), horizontalArrangement = Arrangement.SpaceEvenly, verticalAlignment = Alignment.CenterVertically) {
                    // Latency
                    SpeedometerGauge(value = 38f, unit = "MS PING", label = "LATENCY", color = NeonPalette.AlertOrange)

                    // Power Knob
                    Box(
                        contentAlignment = Alignment.Center,
                        modifier = Modifier
                            .size(100.dp)
                            .shadow(20.dp, CircleShape, ambientColor = NeonPalette.VioletNeonGlow)
                            .clip(CircleShape)
                            .background(Brush.radialGradient(listOf(Color(0xFF2E1065), Color(0xFF0F172A))))
                            .clickable { isConnected = !isConnected }
                    ) {
                        Column(horizontalAlignment = Alignment.CenterHorizontally) {
                            Text("⚡", fontSize = 22.sp)
                            Text(if (isConnected) "ONLINE" else "OFFLINE", color = if (isConnected) NeonPalette.NeonGreen else Color.Gray, fontSize = 10.sp, fontWeight = FontWeight.Black, fontFamily = FontFamily.Monospace)
                            Text("MAIN CHASSIS", color = NeonPalette.TextMuted, fontSize = 7.sp, fontFamily = FontFamily.Monospace)
                        }
                    }

                    // Bandwidth
                    SpeedometerGauge(value = 24.8f, unit = "MB/S", label = "BANDWIDTH", color = NeonPalette.CyanPulse)
                }

                Spacer(Modifier.height(14.dp))

                // RX/TX
                Row(modifier = Modifier.fillMaxWidth(), horizontalArrangement = Arrangement.spacedBy(10.dp)) {
                    Row(
                        modifier = Modifier.weight(1f).clip(RoundedCornerShape(12.dp)).background(Color(0x66080313)).padding(8.dp),
                        horizontalArrangement = Arrangement.SpaceBetween
                    ) {
                        Text("RX RECVD", color = NeonPalette.TextMuted, fontSize = 8.5.sp, fontFamily = FontFamily.Monospace)
                        Text("342.85 MB", color = NeonPalette.AlertOrange, fontSize = 11.sp, fontWeight = FontWeight.Bold, fontFamily = FontFamily.Monospace)
                    }
                    Row(
                        modifier = Modifier.weight(1f).clip(RoundedCornerShape(12.dp)).background(Color(0x66080313)).padding(8.dp),
                        horizontalArrangement = Arrangement.SpaceBetween
                    ) {
                        Text("TX SENT", color = NeonPalette.TextMuted, fontSize = 8.5.sp, fontFamily = FontFamily.Monospace)
                        Text("089.40 MB", color = NeonPalette.CyanPulse, fontSize = 11.sp, fontWeight = FontWeight.Bold, fontFamily = FontFamily.Monospace)
                    }
                }
            }

            // 5. Active Node Drawer
            Row(
                modifier = Modifier
                    .fillMaxWidth()
                    .clip(RoundedCornerShape(18.dp))
                    .background(NeonPalette.GlassSurface)
                    .border(1.dp, NeonPalette.GlassBorder, RoundedCornerShape(18.dp))
                    .padding(horizontal = 14.dp, vertical = 12.dp),
                verticalAlignment = Alignment.CenterVertically,
                horizontalArrangement = Arrangement.SpaceBetween
            ) {
                Row(verticalAlignment = Alignment.CenterVertically) {
                    Text("🇸🇬", fontSize = 22.sp)
                    Spacer(Modifier.width(10.dp))
                    Column {
                        Row(verticalAlignment = Alignment.CenterVertically) {
                            Text("SG-Cloudflare-Reality-01", color = Color.White, fontSize = 12.sp, fontWeight = FontWeight.Bold, fontFamily = FontFamily.Monospace)
                            Spacer(Modifier.width(6.dp))
                            Text("ACTIVE", color = NeonPalette.NeonGreen, fontSize = 8.sp, fontFamily = FontFamily.Monospace)
                        }
                        Text("• VLESS-XTLS | PORT: 443 | TLS 1.3", color = NeonPalette.TextMuted, fontSize = 9.sp, fontFamily = FontFamily.Monospace)
                    }
                }
                Button(
                    onClick = {},
                    colors = ButtonDefaults.buttonColors(containerColor = Color(0x33A855F7)),
                    shape = RoundedCornerShape(8.dp),
                    contentPadding = PaddingValues(horizontal = 10.dp, vertical = 4.dp),
                    modifier = Modifier.height(28.dp)
                ) {
                    Text("SWITCH ⇅", color = Color.White, fontSize = 9.sp, fontFamily = FontFamily.Monospace)
                }
            }

            // 6. Dual Telemetry Console
            Column(
                modifier = Modifier
                    .fillMaxWidth()
                    .clip(RoundedCornerShape(20.dp))
                    .background(Color(0xFF0B0616))
                    .border(1.dp, NeonPalette.GlassBorder, RoundedCornerShape(20.dp))
                    .padding(12.dp)
            ) {
                Row(modifier = Modifier.fillMaxWidth(), horizontalArrangement = Arrangement.SpaceBetween) {
                    Text("AI DUAL TELEMETRY CONSOLE", color = Color.White, fontSize = 10.sp, fontWeight = FontWeight.Bold, fontFamily = FontFamily.Monospace)
                    Text("SYNCED // 120HZ", color = NeonPalette.CyanPulse, fontSize = 8.5.sp, fontFamily = FontFamily.Monospace)
                }
                Spacer(Modifier.height(8.dp))
                Row(modifier = Modifier.fillMaxWidth(), horizontalArrangement = Arrangement.spacedBy(8.dp)) {
                    Column(modifier = Modifier.weight(1f).clip(RoundedCornerShape(8.dp)).background(Color(0xFF06030C)).padding(8.dp)) {
                        Text("[1] GEMINI-PRO-CORE", color = NeonPalette.VioletNeonGlow, fontSize = 8.5.sp, fontWeight = FontWeight.Bold, fontFamily = FontFamily.Monospace)
                        Text("> Route: DPI bypassed", color = NeonPalette.TextMuted, fontSize = 8.sp, fontFamily = FontFamily.Monospace)
                        Text("> Hop: SIN-CF (0.8ms)", color = NeonPalette.NeonGreen, fontSize = 8.sp, fontFamily = FontFamily.Monospace)
                        Text("> Opt: 100% locked █", color = NeonPalette.AlertOrange, fontSize = 8.sp, fontFamily = FontFamily.Monospace)
                    }
                    Column(modifier = Modifier.weight(1f).clip(RoundedCornerShape(8.dp)).background(Color(0xFF06030C)).padding(8.dp)) {
                        Text("[2] NEURAL-ENGINE-V2", color = NeonPalette.CyanPulse, fontSize = 8.5.sp, fontWeight = FontWeight.Bold, fontFamily = FontFamily.Monospace)
                        Text("> Latency jitter < 1.2ms", color = NeonPalette.TextMuted, fontSize = 8.sp, fontFamily = FontFamily.Monospace)
                        Text("> UDP priority enabled", color = NeonPalette.CyanPulse, fontSize = 8.sp, fontFamily = FontFamily.Monospace)
                        Text("> Zero drop rate █", color = NeonPalette.NeonGreen, fontSize = 8.sp, fontFamily = FontFamily.Monospace)
                    }
                }
            }

            // 7. Footer
            Row(modifier = Modifier.fillMaxWidth(), horizontalArrangement = Arrangement.SpaceBetween, verticalAlignment = Alignment.CenterVertically) {
                Row(modifier = Modifier.clip(RoundedCornerShape(12.dp)).background(Color(0x33A855F7)).padding(2.dp)) {
                    Button(onClick = { isEnglish = true }, colors = ButtonDefaults.buttonColors(containerColor = if (isEnglish) NeonPalette.VioletNeon else Color.Transparent), contentPadding = PaddingValues(horizontal = 8.dp, vertical = 2.dp), modifier = Modifier.height(24.dp)) {
                        Text("English", fontSize = 8.5.sp, fontFamily = FontFamily.Monospace)
                    }
                    Button(onClick = { isEnglish = false }, colors = ButtonDefaults.buttonColors(containerColor = if (!isEnglish) NeonPalette.VioletNeon else Color.Transparent), contentPadding = PaddingValues(horizontal = 8.dp, vertical = 2.dp), modifier = Modifier.height(24.dp)) {
                        Text("မြန်မာ", fontSize = 8.5.sp, fontFamily = FontFamily.Monospace)
                    }
                }
                Text("SERIAL: SS-V2R-99201", color = NeonPalette.TextMuted, fontSize = 8.5.sp, fontFamily = FontFamily.Monospace)
            }
        }
    }
}

// MARK: - Animated Helper Components
@Composable
fun AnimatedEcgCanvas() {
    val infiniteTransition = rememberInfiniteTransition(label = "ecg")
    val cometProgress by infiniteTransition.animateFloat(
        initialValue = 0f, targetValue = 1f,
        animationSpec = infiniteRepeatable(tween(2200, easing = LinearEasing), RepeatMode.Restart), label = "p"
    )

    Canvas(modifier = Modifier.fillMaxWidth().height(24.dp)) {
        val w = size.width
        val midY = size.height / 2f
        val path = Path().apply {
            moveTo(0f, midY)
            lineTo(w * 0.36f, midY)
            lineTo(w * 0.39f, midY - 6.dp.toPx())
            lineTo(w * 0.43f, midY + 9.dp.toPx())
            lineTo(w * 0.47f, midY - 14.dp.toPx())
            lineTo(w * 0.51f, midY + 12.dp.toPx())
            lineTo(w * 0.55f, midY - 5.dp.toPx())
            lineTo(w * 0.59f, midY)
            lineTo(w, midY)
        }
        drawPath(path, color = Color(0xFFEF4444).copy(alpha = 0.6f), style = Stroke(width = 2.dp.toPx(), cap = StrokeCap.Round))
    }
}

@Composable
fun SpeedometerGauge(value: Float, unit: String, label: String, color: Color) {
    Column(horizontalAlignment = Alignment.CenterHorizontally) {
        Box(contentAlignment = Alignment.Center, modifier = Modifier.size(72.dp)) {
            Canvas(modifier = Modifier.fillMaxSize().padding(4.dp)) {
                val stroke = 4.dp.toPx()
                drawArc(Color(0x334B5563), 150f, 240f, false, style = Stroke(stroke, cap = StrokeCap.Round))
                drawArc(color, 150f, 160f, false, style = Stroke(stroke, cap = StrokeCap.Round))
            }
            Column(horizontalAlignment = Alignment.CenterHorizontally) {
                Text(if (value < 10) String.format("%.1f", value) else "${value.toInt()}", color = Color.White, fontSize = 13.sp, fontWeight = FontWeight.Bold, fontFamily = FontFamily.Monospace)
                Text(unit, color = NeonPalette.TextMuted, fontSize = 7.sp, fontFamily = FontFamily.Monospace)
            }
        }
        Text(label, color = NeonPalette.TextMuted, fontSize = 8.5.sp, fontFamily = FontFamily.Monospace)
    }
}
```
