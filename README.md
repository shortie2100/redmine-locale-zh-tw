# redmine-locale-zh-tw

Redmine 正體中文（台灣，zh-TW）介面翻譯檔。

Traditional Chinese (Taiwan, zh-TW) translation for [Redmine](https://www.redmine.org/).

## 對應版本

Traditional Chinese translation (to r21827)：翻譯內容同步至 Redmine 原始碼 r21827。

## 特色

- 以 Redmine 內建的 `zh-TW.yml` 為基礎持續維護，修正未翻譯與用語不一致的字串
- 字串鍵值完整涵蓋 `en.yml`，不會出現英文殘留的介面文字
- 檔案路徑與 Redmine 原始碼相同（`config/locales/zh-TW.yml`），可直接覆蓋使用

## 安裝

1. 備份 Redmine 原本的翻譯檔：

   ```bash
   cp /path/to/redmine/config/locales/zh-TW.yml /path/to/redmine/config/locales/zh-TW.yml.orig
   ```

2. 下載本專案的翻譯檔，覆蓋到 Redmine 的 `config/locales/` 目錄：

   ```bash
   curl -fL -o /path/to/redmine/config/locales/zh-TW.yml \
     https://raw.githubusercontent.com/shortie2100/redmine-locale-zh-tw/main/config/locales/zh-TW.yml
   ```

3. 重新啟動 Redmine（例如重啟 Puma / Passenger，或 Docker 容器）讓翻譯生效。

4. 在「管理 → 設定 → 顯示」將預設語言設為「Chinese/Traditional (繁體中文)」，或由使用者在「我的帳戶」中自行選擇語言。

### Docker

使用官方 `redmine` 映像檔時，可以用 volume 掛載覆蓋：

```yaml
services:
  redmine:
    image: redmine
    volumes:
      - ./config/locales/zh-TW.yml:/usr/src/redmine/config/locales/zh-TW.yml:ro
```

## 注意事項

- 升級 Redmine 版本時，新版的 `zh-TW.yml` 會覆蓋本檔案，請在升級後重新套用。
- 新版 Redmine 若新增字串，未翻譯的鍵值會顯示英文，歡迎回報或發 PR 補上。

## 回報與貢獻

發現翻譯錯誤或用語建議，歡迎開 [Issue](https://github.com/shortie2100/redmine-locale-zh-tw/issues) 或送 Pull Request。

## 授權

與 Redmine 相同，本專案採用 [GNU General Public License v2](LICENSE)（或更新版本）授權。
