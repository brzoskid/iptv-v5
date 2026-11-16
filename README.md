# webOS IPTV Player dla Minix NEO-U1 (v5)

## Co naprawiono w wersji 5.0
- **Pełne obejście przestarzałych certyfikatów SSL/TLS 1.2 na Androidzie 5.1.1 (API 22):**
  - Dedykowana fabryka połączeń `TrustAllHttpDataSource` w `MainActivity.java` wstrzykująca własny `SSLSocketFactory` (TLS 1.1/1.2 + zaufanie dla wszystkich certyfikatów) bezpośrednio do **ExoPlayer 2.13.3**.
  - Natywne pobieranie list M3U oraz przewodników EPG XMLTV w Javie (`fetchUrlAsync`) z obsługą przekierowań HTTP/HTTPS, kompresji GZIP oraz obejściem SSL.
  - Jawne użycie `HlsMediaSource` dla linków `.m3u8?token=...` oraz szczegółowa diagnostyka błędów ExoPlayera na ekranie.
- **Zapamiętywanie ostatnio oglądanego kanału** po restarcie aplikacji.
- **Pełne mapowanie pilota MINIX NEO A2 Lite / A3** oraz wbudowane 3 źródła EPG (`epg.ovh/pl.xml`, `pltv.xml`, `plar.xml`) z przełącznikiem **WŁĄCZ / WYŁĄCZ**.
