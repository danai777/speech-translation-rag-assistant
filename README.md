# speech-translation-rag-assistant
Çok Dilli Eş Zamanlı Konuşma Çevirisi ve Alana Özgü Akıllı Asistan Sistemi (Trakya Üniversitesi Bitirme Projesi)

Trakya Üniversitesi Bilgisayar Mühendisliği Bölümü bitirme projesi kapsamında geliştirilen çok dilli eş zamanlı konuşma çevirisi ve alana özgü soru-cevap asistanı.

## Proje Hakkında
Bu çalışma; Türkçe, İngilizce ve Rusça konuşan kullanıcılar arasında düşük gecikmeli iki yönlü sesli çeviri sağlarken, üniversite yönetmeliklerine dayalı sorulara RAG mimarisi üzerinden kaynak göstererek yanıt veren bir sistemdir.

Temel bileşenler:
- STT (Speech-to-Text): faster-whisper ve WebRTC VAD
- Karar ve Çeviri Motoru: Yerel çalışan LLM (Ollama / Qwen2.5)
- RAG ve Vektör Arama: ChromaDB ve çok dilli gömme modelleri
- TTS (Text-to-Speech): edge-tts ve yerel Piper TTS
- Arka Yüz: FastAPI ve WebSockets
- Ön Yüz: React tabanlı kullanıcı arayüzü

## Ekip ve Danışman
- Danışman: Arş. Gör. Dr. Oğuz KIRAT
- Ekip Üyeleri:
  - Dana Imakova (Ekip Sorumlusu) - 1231602673
  - Belma Beciragic - 1221602619

## Kurulum ve Çalıştırma

1. Depoyu klonlayın:
git clone https://github.com/danai777/speech-translation-rag-assistant.git
cd speech-translation-rag-assistant

2. Sanal ortamı oluşturup aktif edin:
python -m venv venv

Windows için:
venv\Scripts\activate

macOS / Linux için:
source venv/bin/activate

3. Bağımlılıkları yükleyin:
pip install -r requirements.txt

4. Yerel modeli başlatın:
ollama run qwen2.5:7b

5. Sunucuyu çalıştırın:
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000

## Geliştirme Süreci
- [x] Proje tanıtım formu ve mimari planlama
- [ ] VAD ve faster-whisper STT modülü
- [ ] FastAPI WebSocket ağ geçidi ve Ollama çeviri hattı
- [ ] Yönetmelik dokümanları için RAG altyapısı (ChromaDB)
- [ ] TTS entegrasyonu ve ses akışı
- [ ] Web arayüzü ve yönetim paneli
- [ ] Gecikme/doğruluk testleri ve raporlama
