Bu projeye eklemeyi düşündüğüm 3 GitHub reposu var. Önce bu projeyi incele (README, klasör yapısı, kullanılan diller, bağımlılıklar, hangi AI kodlama aracıyla çalıştığımız), sonra her repoyu kendi linkinden açıp README'sini oku ve bu proje için işe yarayıp yaramayacağına karar ver.

## Repolar

1. **ub-mode** – https://github.com/unclebob/ub-mode
   Uncle Bob'un (Robert C. Martin) AI ajanları için hazırladığı skill. Ajana disiplinli geliştirme dayatıyor: TDD, kök neden düzeltme, küçük commit'ler. Kod kalitesini şu araçlarla ölçüyor:
   - Karmaşıklık skoru (CRAP < 10): https://github.com/unclebob/crapper
   - Kod tekrarı tespiti: https://github.com/unclebob/dryer
   - Mutation testing: https://github.com/unclebob/mutator
   Kurulum: `SKILL.md` dosyası `~/.claude/skills/ub-mode/SKILL.md` (ya da kullandığımız ajanın skills klasörü) altına kopyalanır, sonra `/ub-mode` ile çağrılır.

2. **dsh-our-free-model** – https://github.com/Ebony-Vinyl/dsh-our-free-model
   "dsh" (DeepSeek Harness) adlı AI kodlama aracı için bir eklenti. Hesap ya da API anahtarı olmadan DeepSeek V4.1 Flash, Kimi K3 gibi modelleri ücretsiz kullandırıyor ve OpenAI uyumlu yerel bir port açıyor. İstekler üçüncü taraf ağ geçitlerinden geçiyor (OpenCode Zen ve Kilo AI).
   Bunu yalnızca dsh kullanıyorsak ya da bu projede ücretsiz, OpenAI uyumlu bir model ucuna gerçekten ihtiyaç varsa değerlendir. Gizli veya hassas kod içeren projelerde bu riski açıkça belirt.

3. **Elephant-Goldfish Model (EGM)** – https://github.com/google/elephant-goldfish-model
   Google'ın spec (tasarım dokümanı) odaklı geliştirme eklentisi. Bağlamı bilen bir ajan tasarımı yazıyor, sıfır bağlamla başlayan ajanlar da onu inceleyip kör noktaları buluyor. Komutlar: `egm-brainstorm`, `egm-draft`, `egm-review`.
   Kurulum:
   - Claude Code: `claude plugin marketplace add google/elephant-goldfish-model` ve ardından `claude plugin install egm@egm`
   - Codex: `codex plugin marketplace add google/elephant-goldfish-model` ve ardından `codex plugin add egm@egm`
   - Antigravity: `agy plugin install https://github.com/google/elephant-goldfish-model`

## Senden istediğim

**Adım 1 – Değerlendirme (henüz hiçbir şey kurma):**
Her repo için şu tabloyu doldur:

| Repo | Karar (KUR / KURMA / OPSİYONEL) | Bu projede ne işe yarar? | Gereksinimler uyuyor mu? (OS, dil, ajan aracı) | Risk veya dezavantaj |

Kararını bu projenin gerçek durumuna dayandır: dili, test altyapısı olup olmadığı, ekip büyüklüğü, kullandığımız AI aracı (Claude Code, Codex, Cursor vb.). Genel övgü yazma; işe yaramayacaksa net bir şekilde "KURMA" de.

Değerlendirmede özellikle şunlara dikkat et:
- **ub-mode:** crapper, dryer ve mutator projenin diliyle çalışıyor mu? Projede test altyapısı var mı?
- **EGM:** Projede tasarım kararı gerektiren büyük özellikler var mı, yoksa çoğunlukla küçük düzeltmeler mi yapılıyor?
- **dsh-our-free-model:** Bunu kullanırsak kodun ve verilerin hangi üçüncü taraflara gideceğini yaz.

**Adım 2 – Onay:**
Tablonun ardından "KUR" dediklerinin kurulum adımlarını sırasıyla yaz: hangi komut, hangi klasöre ne kopyalanacak, global mi yoksa proje bazında mı kurulacak. Sonra benim onayımı bekle.

**Adım 3 – Kurulum (ben onay verdikten sonra):**
Onayladıklarımı kur, çalıştığını doğrula (örneğin skill veya eklenti listede görünüyor mu, bir komut çalışıyor mu) ve sonucu kısaca raporla. Kurulum projede dosya değiştirdiyse hangi dosyaların değiştiğini söyle.

Kurallar:
- Sadece yukarıdaki resmi GitHub linklerinden kur. Benzer isimli kopya repo veya paket kullanma.
- Benden onay almadan hiçbir şey kurma ve hiçbir dosyayı değiştirme.
- Gizli bilgileri (API anahtarı, `.env` dosyası vb.) hiçbir yere gönderme ve commit'leme.
