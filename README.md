# Petunjuk Prompting / Prompt Engineering (ID)

Panduan ringkas dan praktis untuk menulis prompt yang efektif — untuk model teks (ChatGPT, GPT) dan model generasi gambar (Stable Diffusion, Midjourney, DALL·E, dll). Termasuk contoh template, teknik peningkatan hasil, daftar referensi, dan link sumber belajar (termasuk dua Notion yang Anda minta).

---

## Daftar Isi
- Tujuan
- Prinsip dasar prompting
- Struktur prompt yang baik
- Template prompt teks (ChatGPT / LLM)
- Template prompt gambar (image generation)
- Teknik lanjutan & debugging prompt
- Do's & Don'ts
- Referensi & link materi
- Lisensi

---

## Tujuan
Memberi panduan praktis dan cepat untuk:
- Mendapatkan jawaban lebih relevan, ringkas, dan dapat diandalkan dari LLM.
- Membuat prompt gambar yang konsisten dan artistik.
- Mempercepat iterasi prompt dengan metode sistematis.

---

## Prinsip dasar prompting
1. Jelaskan tujuan (goal) — apa output yang Anda mau.
2. Tentukan peran (role) bila perlu (mis. "Kamu adalah seorang ahli pemasaran").
3. Berikan konteks yang relevan (data, batasan waktu, audience).
4. Spesifik tentang format output (JSON, daftar langkah, bullet).
5. Beri contoh (few-shot) jika ingin gaya atau struktur tertentu.
6. Batasi atau sebutkan yang tidak diinginkan (negative constraints).
7. Iterasi: uji, perbaiki, ulangi.

---

## Struktur prompt yang baik (umum)
- System / Role: instruksi global (untuk ChatGPT system message).
- Instruction: tugas utama.
- Context / Data: informasi pendukung.
- Constraints / Rules: batasan (panjang, gaya, format).
- Example (opsional): contoh input-output yang diinginkan.
- Output format: jelaskan format akhir.

Contoh singkat struktur:
"Kamu adalah [peran]. Tugas: [tugas]. Konteks: [konteks]. Batasan: [batasan]. Format output: [format]. Contoh: [jika perlu]."

---

## Template prompt teks (contoh)

1) Basic Q&A (jelas & ringkas)
"You are an expert [domain]. Provide a concise answer (<= 150 words) to the question below, include 3 actionable steps and 1 reference.
Question: [isi pertanyaan]"

2) Role + Format (report / email)
"Act as a technical writer. Summarize the following meeting notes into a 3-paragraph email for stakeholders with a short 'next steps' bullet list. Meeting notes: [paste]."

3) Few-shot untuk tone/gaya
"You're a friendly product copywriter. Examples:
- Input: 'feature A' → Output: 'Friendly line A...'
Now write for: [new feature]."

4) Chain-of-Thought control (when you want reasoning)
"Explain your reasoning step-by-step before giving the final answer. Then provide a short summary (<= 40 words)."

Catatan:
- Jika butuh sumber atau bukti, tambahkan "Cite sources or be explicit if unknown."
- Untuk output terstruktur gunakan: "Return only JSON with keys: title, summary, steps."

---

## Template prompt gambar (image generation)

Elemen penting untuk prompt gambar:
- Subjek utama (subject)
- Gaya / era / referensi artis (style)
- Komposisi & sudut kamera (angle, lens)
- Pencahayaan & suasana (lighting, mood)
- Warna / palet
- Detil teknis (resolution, aspect ratio)
- Negative prompt (apa yang harus dihindari)

Contoh lengkap:
"Subject: a futuristic city skyline at dusk
Style: cyberpunk, inspired by Syd Mead and Beeple
Composition: wide-angle, low vantage point, leading lines to center
Lighting: neon lights, volumetric fog, warm-orange highlights
Color: cyan-magenta contrast, high saturation
Details: ultra-detailed, photorealistic, 8k, depth of field
Aspect ratio: 16:9
Negative: no watermarks, no text, avoid deformed faces, no low-res"

Negative prompts (penting): "low quality, watermark, text, deformed, extra limbs, bad anatomy"

Referensi prompt untuk image generation:
- Sertakan referensi artis secara etis: "in the style of [artist]" (perhatikan kebijakan hak cipta platform).
- Kombinasikan teknik fotografi: "35mm lens, f/1.8, bokeh" untuk look fotografis.

---

## Teknik lanjutan & debugging prompt
- Temperature & sampling: turunkan randomness (temperature rendah) untuk jawaban deterministik.
- System message (ChatGPT): gunakan untuk aturan permanen (tone, persona).
- Split tasks: minta model memecah tugas besar menjadi langkah-langkah (decomposition).
- Validate outputs: minta model memeriksa konsistensi atau memverifikasi format (self-check).
- Iterasi otomatis: gunakan prompt meta untuk memperbaiki versi sebelumnya (refine).
- Prompt-chaining: gunakan output sebuah prompt sebagai input untuk prompt selanjutnya (e.g., ide -> outline -> full text).

Contoh refine:
"Improve the following draft for clarity and conciseness. Keep bullet points: [draft text]. Produce a 3-sentence summary and a revised draft."

---

## Do's & Don'ts (singkat)
Do:
- Berikan konteks cukup dan format output yang jelas.
- Gunakan contoh bila ingin gaya tertentu.
- Gunakan negative prompts pada gambar.
- Iterasi dan simpan prompt yang berhasil.

Don't:
- Jangan minta 'sempurna' dalam satu prompt; iterasi lebih baik.
- Jangan overload prompt dengan info tak relevan.
- Hindari perintah ambigu seperti "buat lebih menarik" tanpa penjelasan gaya.

---

## Referensi & Link Materi
- Notion: 100 AI Tools & Prompts — https://www.notion.so/100-AI-Tools-Prompts-1f3a1abc2ccd8017885ec10aa9d2265e
- Notion: ChatGPT Prompt for Image Generation & Design — https://adjiputra.notion.site/ChatGPT-Prompt-for-Image-Generation-Design-1c919defa0048084bb3fdffc9c772fbe
- Prompt Engineering Guide (repo): https://github.com/dair-ai/Prompt-Engineering-Guide
- Awesome ChatGPT Prompts: https://github.com/f/awesome-chatgpt-prompts
- OpenAI Guides (general): https://platform.openai.com/docs/guides
- Midjourney Prompts (dokumen resmi): https://docs.midjourney.com/docs/prompts
- Stable Diffusion / SD-WebUI prompt tips: https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Prompts

Catatan: selalu periksa kebijakan hak cipta dan TOS platform saat menggunakan referensi artis atau gaya tertentu.

---

## Contoh cepat (ringkasan)

1) Prompt teks singkat:
"Kamu adalah seorang analis data. Jelaskan langkah utama untuk membersihkan dataset berisi alamat email dan tanggal lahir. Berikan 5 langkah, tiap langkah max 20 kata."

2) Prompt gambar singkat:
"Portrait of an elderly woman, cinematic film lighting, Rembrandt style, high detail, 50mm, shallow depth of field, photorealistic. Negative: watermark, text."

---

## Lisensi
Bebas digunakan dan dimodifikasi. Tidak menggantikan dokumentasi resmi platform atau nasihat hukum/medis/keamanan. Periksa kebijakan setiap layanan sebelum publikasi karya yang dihasilkan.

---

Terima kasih — semoga README ini membantu mempercepat eksperimen prompting Anda!
