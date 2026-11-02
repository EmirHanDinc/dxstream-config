# dxstream-config

DXStream uygulamalarının (Samsung TV, Google TV, iOS) günde en fazla bir kez okuduğu uzaktan ayar dosyası:
https://emirhandinc.github.io/dxstream-config/config.json

Kaynağı DXStream deposunda `tv-web/remote-config/`; yayın deposu github.com/EmirHanDinc/dxstream-config (GitHub Pages).
Değişiklik `main` dalına gönderilince birkaç dakika içinde yayına girer; uygulamalar en geç 24 saat içinde görür.
Dosya okunamazsa ya da bozuksa uygulamalar son kayıtlı ayarla, o da yoksa derlemedeki değerlerle çalışır.

| Alan | Anlamı |
|---|---|
| `opensubtitles.enabled` | `false`: "İnternetten altyazı" özelliği gizlenir (ör. servis sorunluyken). |
| `opensubtitles.key` | Boş değilse derlemedeki OpenSubtitles uygulama anahtarının yerine geçer (eski anahtar iptal edilince). Yalnızca harf/rakam. **Yayın deposu herkese açık; anahtar orada herkesçe görülebilir** — yalnızca gerektiğinde doldurun. |
| `opensubtitles.message` | Kısa duyuru; oynatıcıdaki altyazı panelinde ve Ayarlar → Altyazı'da gösterilir (ör. "Altyazı servisi bakımda"). Boş: gösterilmez. |

Bu dosyaya kişisel veri, hesap bilgisi ya da sunucu adresi konmaz.

## Yayınlama (ilk kez)
```bash
cd tv-web/remote-config && tools/publish.sh
```
## Değiştirme
`config.json`'ı düzenleyip yine `tools/publish.sh` çalıştırın.
