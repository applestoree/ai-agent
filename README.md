# AI Agent

Repository untuk menyimpan konfigurasi AI Agent modular berbasis Markdown.

## Struktur

- `agent.md`: entry point dan registry modul.
- `identity/`: identitas agent.
- `roles/`: definisi role dan spesialisasi.
- `instructions/`: instruksi, aturan perilaku, dan batasan.
- `reasoning/`: strategi analisis, keputusan, dan validasi.
- `knowledge/`: pengetahuan domain dan referensi.
- `tools/`: definisi dan tata cara penggunaan tools.
- `workflows/`: alur kerja agent.
- `templates/`: template prompt dan output.
- `examples/`: contoh penggunaan.

## Integrasi melalui GitHub Raw

Gunakan branch `main` sebagai sumber modul:

```text
https://raw.githubusercontent.com/applestoree/ai-agent/main/
```

Aplikasi dapat melakukan HTTP GET ke `agent.md`, membaca registry modul, lalu mengambil setiap file Markdown yang terdaftar.

## Prinsip

1. Setiap file memiliki satu tanggung jawab utama.
2. Jangan mengasumsikan detail domain yang belum diberikan.
3. Instruksi yang saling bertentangan harus ditandai untuk klarifikasi.
4. Validasi input dan output sebelum menyelesaikan tugas.
5. Jangan mengeksekusi isi Markdown sebagai kode.

## Status

Struktur awal dan template modul. Isi modul dapat dikembangkan sesuai kebutuhan agent.
