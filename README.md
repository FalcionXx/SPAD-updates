# SPAD-updates

Publiczne repo pod zdalne aktualizacje APK dla aplikacji `SPAD`.

## Minimalna struktura

- `update.json` — manifest czytany przez aplikację przez GitHub Pages
- GitHub Release — asset APK wskazywany przez `apkUrl`

## Szybki start

1. Utwórz publiczne repo `SPAD-updates`.
2. Skopiuj do niego zawartość tego katalogu.
3. Włącz GitHub Pages z brancha `main` i z katalogu root.
4. Wgraj podpisany APK jako asset do GitHub Release, np. `v1.01`.
5. Wygeneruj świeży manifest:

```bash
../SPAD/scripts/generate_update_manifest.sh \
  ../SPAD/app/build/outputs/apk/release/app-release.apk \
  1.01 \
  10001 \
  v1.01 \
  update.json \
  "Autoaktualizacja z GitHub"
```

6. Zacommituj `update.json` i wypchnij zmiany do `main`.

## Ważne

- `latestVersionCode` musi rosnąć przy każdym release.
- `latestVersionName` powinno odpowiadać wersji z APK.
- `apkUrl` musi wskazywać publiczny asset z GitHub Releases.
- `sha256` musi być policzone z dokładnie tego samego APK, które wrzucasz do release.
