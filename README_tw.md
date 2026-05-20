<p align="left">
    <a href="README.md">
        简体中文
    </a>
    <span> • </span>
    <span>
        <b>繁體中文</b>
    </span>
    <span> • </span>
    <a href="README_en.md">
        English
    </a>
    <span> • </span>
    <a href="README_ja.md">
        日本語
    </a>
</p>

<p align="center">
  <a href="https://github.com/hiroi-sora/Umi-OCR">
    <img width="200" height="128" src="https://tupian.li/images/2022/10/27/icon---256.png" alt="Umi-OCR">
  </a>
</p>

<h1 align="center">Umi-OCR 文字辨識工具</h1>

<p align="center">
  <a href="https://github.com/hiroi-sora/Umi-OCR/releases/latest">
    <img src="https://img.shields.io/github/v/release/hiroi-sora/Umi-OCR?style=flat-square" alt="Umi-OCR">
  </a>
  <a href="https://github.com/hiroi-sora/Umi-OCR/blob/main/LICENSE">
    <img src="https://img.shields.io/github/license/hiroi-sora/Umi-OCR?style=flat-square" alt="LICENSE">
  </a>
  <a href="#下載發行版">
    <img src="https://img.shields.io/github/downloads/hiroi-sora/Umi-OCR/total?style=flat-square" alt="downloads">
  </a>
  <a href="https://star-history.com/#hiroi-sora/Umi-OCR">
    <img src="https://img.shields.io/github/stars/hiroi-sora/Umi-OCR?style=flat-square" alt="stars">
  </a>
  <a href="https://github.com/hiroi-sora/Umi-OCR/forks">
    <img src="https://img.shields.io/github/forks/hiroi-sora/Umi-OCR?style=flat-square" alt="forks">
  </a>
  <a href="https://hosted.weblate.org/engage/umi-ocr/">
    <img src="https://hosted.weblate.org/widget/umi-ocr/svg-badge.svg" alt="翻譯狀態">
  </a>
</p>

<div align="center">
  <h3>
    <a href="#目錄">
      使用說明
    </a>
    <span> • </span>
    <a href="#下載發行版">
      下載地址
    </a>
    <span> • </span>
    <a href="CHANGE_LOG.md">
      更新日誌
    </a>
    <span> • </span>
    <a href="https://github.com/hiroi-sora/Umi-OCR/issues">
      回報 Bug
    </a>
  </h3>
</div>
<br>

<div align="center">
  <strong>免費、開源、可批次處理的離線 OCR 軟體</strong><br>
  <sub>適用於 Windows7 x64、Linux x64</sub>
</div><br>

- **免費**：本專案所有程式碼皆開源，完全免費。
- **方便**：解壓即用，離線執行，無需網路。
- **高效**：內建高效率的離線 OCR 引擎，內建多種語言識別庫。
- **靈活**：支援命令列、HTTP 介面等外部呼叫方式。
- **功能**：截圖 OCR / 批次 OCR / PDF 辨識 / 二維碼 / 公式辨識

<p align="center"><img src="https://tupian.li/images/2023/11/19/65599097ab5f4.png" alt="1-標題-1.png" style="width: 80%;"></p>

![1-標題-2.png](https://tupian.li/images/2023/11/19/6559909fdeeba.png)

## 目錄

- [截圖辨識](#截圖OCR)
  - [排版解析](#文字後處理) - 辨識不同排版，按正確順序輸出文字
- [批次辨識](#批次OCR)
  - [忽略區域](#忽略區域) - 排除截圖浮水印處的文字
- [二維碼](#二維碼) 支援掃碼或生成二維碼圖片
- [文件辨識](#文件辨識) 從 PDF 掃描檔中提取文字，或轉為雙層可搜尋 PDF
- [全域設定](#全域設定)
- [命令列呼叫](docs/README_CLI.md)
- [HTTP 介面](docs/http/README.md)
- [建構專案（Windows、Linux）](#建構專案)

## 使用原始碼

開發者請務必閱讀 [建構專案](#建構專案) 。

## 下載發行版

以下發布連結均長期維護，提供穩定版本的下載。

- **藍奏雲** https://hiroi-sora.lanzoul.com/s/umi-ocr （推薦，免註冊/無限速）
- **GitHub** https://github.com/hiroi-sora/Umi-OCR/releases/latest
- **Source Forge** https://sourceforge.net/projects/umi-ocr


<details>
<summary><b>•&nbsp;&nbsp;Scoop 安裝器</b>（點擊展開）</summary>

[Scoop](https://scoop.sh/) 是一款 Windows 下的命令列安裝程式，可方便地管理多個應用程式。您可以先安裝 Scoop，再使用以下指令安裝 `Umi-OCR`：

- 新增 `extras` 桶：
```
scoop bucket add extras
```

- （可選 1）安裝 Umi-OCR（內建 `Rapid-OCR` 引擎，相容性佳）：
```
scoop install extras/umi-ocr
```

- （可選 2）安裝 Umi-OCR（內建 `Paddle-OCR` 引擎，速度稍快）：
```
scoop install extras/umi-ocr-paddle
```

- 請勿同時安裝兩者，以免捷徑被覆蓋。但您可以額外匯入 [外掛模組](https://github.com/hiroi-sora/Umi-OCR_plugins) ，隨時切換不同的 OCR 引擎。

</details>
</br>

## 開始使用

軟體發布包下載格式為 `.7z` 壓縮檔或 `.7z.exe` 自解壓檔。自解壓檔可在沒有安裝壓縮軟體的電腦上直接解壓縮。

本軟體無需安裝。解壓後，點擊 `Umi-OCR.exe` 即可啟動程式。

遇到任何問題，請提 [Issue](https://github.com/hiroi-sora/Umi-OCR/issues) ，我會盡可能協助您。

## 介面語言

Umi-OCR 支援多國介面語言。在第一次開啟軟體時，會根據您的電腦系統設定自動切換語言。

如果需要手動切換語言，請參考下圖：`全域設定` → `語言/Language`。

<p align="center"><img src="https://tupian.li/images/2023/11/19/65599c3f9e600.png" alt="1-標題-1.png" style="width: 80%;"></p>

## 分頁頁籤

Umi-OCR v2 由一系列彈性好用的**分頁頁籤**組成。您可以依照自己的喜好，開啟需要的分頁。

分頁列左上角可以切換**視窗置頂**。右上角能夠**鎖定分頁**，以防止日常使用中誤觸關閉。

### 截圖OCR

<p align="center"><img src="https://tupian.li/images/2023/11/19/65599097aba8e.png" alt="2-截圖-1.png" style="width: 80%;"></p>

**截圖OCR**：開啟此分頁後，即可用快速鍵喚起截圖，辨識圖中的文字。
- 左側的圖片預覽欄，可直接用滑鼠選取複製。
- 右側的辨識記錄欄，可以編輯文字，允許選取多個記錄並複製。
- 也支援在別處複製圖片，並貼上到 Umi-OCR 進行辨識。
- 關於 [公式辨識](https://github.com/hiroi-sora/Umi-OCR/issues/254) 功能

#### 文字後處理

<p align="center"><img src="https://tupian.li/images/2023/11/19/6559909f3e378.png" alt="2-截圖-2.png" style="width: 80%;"></p>

關於 **OCR 文字後處理 - 排版解析方案**：可整理 OCR 結果的排版與順序，使文字更適合閱讀和使用。預設方案：
- `多欄-按自然段換行`：適合大部分情境，自動識別多欄版面，按自然段規則進行換行。
- `多欄-總是換行`：每段語句都進行换行。
- `多欄-無換行`：強制將所有語句合併到同一行。
- `單欄-按自然段换行`/`總是換行`/`無換行`：與上述類似，但 不區分多欄版面。
- `單欄-保留縮排`：適用於解析程式碼截圖，保留行首縮排和行中空格。
- `不做處理`：OCR 引擎的原始輸出，預設每段語句都進行換行。

上述方案均能自動處理橫排和直排（從右到左）的排版。（直排文字還需要 OCR 引擎本身支援）

---

### 批次OCR

<p align="center"><img src="https://tupian.li/images/2023/11/19/655990a2511e0.png" alt="3-批次-1.png" style="width: 80%;"></p>

**批次OCR**：此分頁用於批次匯入本機圖片進行辨識。
- 支援格式：`jpg, jpe, jpeg, jfif, png, webp, bmp, tif, tiff`。
- 儲存辨識結果支援的格式：`txt, jsonl, md, csv(Excel)`。
- 與截圖 OCR 一樣，支援 `文字後處理` 功能，整理 OCR 文字的排版與順序。
- 沒有數量上限，可一次性匯入幾百張圖片進行任務。
- 支援任務完成後自動關機/待命。
- 如果要辨識超大像素的長圖或大圖，請調整：**分頁的設定 → 文字辨識 → 限制圖像邊長 → 【調高數值】**。
- 擁有特殊功能 `忽略區域`。

#### 忽略區域

<p align="center"><img src="https://tupian.li/images/2023/11/19/6559911d28be7.png" alt="3-批次-2.png" style="width: 80%;"></p>

關於 **OCR 文字後處理 - 忽略區域**：批次 OCR 中的一種特殊功能，適用於排除圖片中不想要的文字。
- 在批次辨識分頁的右欄設定中可進入忽略區域編輯器。
- 如上方範例，圖片頂部和右下角存在多個浮水印 / LOGO。如果批次辨識這類圖片，浮水印會對辨識結果造成干擾。
- 按住右鍵，繪製多個矩形框。這些區域內的文字將在任務中被忽略。
- 請儘量將矩形框畫得大一些，完全包裹住浮水印所有可能出現的位置。
- 注意，只有處於忽略區域框內部的整個文字區塊（而不是單個字元）會被忽略。如下圖所示，黃色邊框的深色矩形是一個忽略區域。那麼只有 `key_mouse` 才會被忽略。`pubsub_connector.py`、`pubsub_service.py` 這兩個文字區塊得以保留。
<p align="center"><img src="https://tupian.li/images/2024/05/30/66587bf03ae15.png" alt="忽略區域範圍示例.png" style="width: 80%;"></p>

---

### 文件辨識

<p align="center"><img src="https://github.com/hiroi-sora/Umi-OCR/assets/56373419/fc2266ee-b9b7-4079-8b10-6610e6da6cf5" alt="" style="width: 80%;"></p>

**文件辨識**：
- 支援格式：`pdf, xps, epub, mobi, fb2, cbz`。
- 對掃描檔進行 OCR，或提取原有文字。可輸出為 **雙層可搜尋 PDF**。
- 支援設定 **忽略區域**，可用於排除頁首頁尾的文字。
- 可設定任務完成後 **自動關機/休眠**。

---

### 二維碼

<p align="center"><img src="https://tupian.li/images/2023/11/19/655991268d6b1.png" alt="4-二維碼-1.png" style="width: 80%;"></p>

**掃碼**：
- 截圖/貼上/拖入本機圖片，讀取其中的二維碼、條形碼。
- 支援一圖多碼。
- 支援 19 種協定，如下：

`Aztec`,`Codabar`,`Code128`,`Code39`,`Code93`,`DataBar`,`DataBarExpanded`,`DataMatrix`,`EAN13`,`EAN8`,`ITF`,`LinearCodes`,`MatrixCodes`,`MaxiCode`,`MicroQRCode`,`PDF417`,`QRCode`,`UPCA`,`UPCE`

<p align="center"><img src="https://tupian.li/images/2023/11/19/6559911cda737.png" alt="4-二維碼-2.png" style="width: 80%;"></p>

**生成碼**：
- 輸入文字，生成二維碼圖片。
- 支援 19 種協定和**糾錯等級**等參數。

---

### 全域設定

<p align="center"><img src="https://tupian.li/images/2023/11/19/655991252e780.png" alt="5-全域設定-1.png" style="width: 80%;"></p>

**全域設定**：在這裡可以調整軟體的全域參數。常用功能如下：
- 一鍵新增捷徑或設定開機自啟。
- 變更介面**語言**。Umi 支援繁中、英語、日本語等語言。
- 切換介面**主題**。Umi 擁有多個亮/暗主題。
- 調整介面**文字的大小**與**字型**。
- 切換 OCR 外掛模組。
- **渲染器**：軟體介面預設支援顯示卡加速渲染。如果在您的電腦上出現截圖閃爍、UI 錯位的情況，請調整 `介面與外觀` → `渲染器`，嘗試切換到不同的渲染方案，或關閉硬體加速。

## 呼叫介面：

- [命令列手冊](docs/README_CLI.md)
- [HTTP 介面手冊](docs/http/README.md)

---

## 關於專案結構

### 各倉庫：

- [主倉庫](https://github.com/hiroi-sora/Umi-OCR) 👈
- [外掛模組庫](https://github.com/hiroi-sora/Umi-OCR_plugins)
- [Windows 執行庫](https://github.com/hiroi-sora/Umi-OCR_runtime_windows)
- [Linux 執行庫](https://github.com/hiroi-sora/Umi-OCR_runtime_linux)

### 工程結構：

`**` 後綴表示本倉庫（`主倉庫`）包含的內容。

```
Umi-OCR
├─ Umi-OCR.exe
├─ umi-ocr.sh
└─ UmiOCR-data
   ├─ main.py **
   ├─ version.py **
   ├─ qt_res **
   │  └─ 專案 qt 資源，包括圖示和 qml 原始碼
   ├─ py_src **
   │  └─ 專案 python 原始碼
   ├─ plugins
   │  └─ 外掛模組
   └─ i18n **
      └─ 翻譯檔案
```

支援的離線 OCR 引擎：

- [PaddleOCR-json](https://github.com/hiroi-sora/PaddleOCR-json)
- [RapidOCR-json](https://github.com/hiroi-sora/RapidOCR-json)

執行環境框架：

- [PyStand](https://github.com/skywind3000/PyStand) 客製版

## 運作原理與架構

Umi-OCR 是一款基於 **Python + Qt (PySide2/QML) + 獨立離線 OCR 引擎** 打造的跨平台桌面軟體。其底層運作原理與架構特色如下：

### 1. 前端 UI 與控制層 (Python + PySide2 + QML)
* **QML 介面**：採用 Qt Quick/QML 技術繪製，確保極高的流暢度、流暢的微動畫以及現代化的主題切換機制。
* **PySide2 連接器**：Python 負責底層業務邏輯控制，並透過 `qmlRegisterType` 將各種 Connector（連線器，如 `MissionConnector`、`PluginsConnector`）註冊為 QML 元件，實現 QML 介面與 Python 後台的雙向高效通信。

### 2. 獨立進程 OCR 引擎 (Subprocess + JSON IPC)
* **核心痛點解決**：在 Python 中直接載入 PaddleOCR 等大型 C++ 深度學習庫，常會因為記憶體洩漏、多執行緒鎖定 (GIL) 或系統相容性問題導致主程式崩潰。
* **為了解決此痛點，Umi-OCR 採用「進程隔離」設計**：
  - 當軟體啟動或使用者發起 OCR 任務時，Python 會以 **子進程 (Subprocess)** 方式拉起獨立的離線 OCR 引擎（如 `PaddleOCR-json` 或 `RapidOCR-json`）。
  - Python 與 OCR 引擎之間透過標準輸入輸出流 (stdin/stdout) 管道，進行 **JSON 格式的處理請求與辨識結果交換 (IPC)**。
  - 這極大優化了記憶體回收機制，就算 OCR 引擎子進程異常崩潰，也完全不影響主程式運作。

### 3. 可攜式執行環境封裝
* **Windows (PyStand)**：採用客製化的 PyStand C++ 啟動器封裝嵌入式 Python 解譯器，無須在使用者電腦上安裝 Python 環境，解壓即可雙擊執行。
* **Linux**：透過 `umi-ocr.sh` 啟動，使用獨立的 Linux 執行庫與環境依賴包完成無痛部署。

## 建構專案

請跳轉至下列倉庫或參考說明，完成對應平台的開發/執行環境部署。

- [Windows](https://github.com/hiroi-sora/Umi-OCR_runtime_windows)
- [Linux](https://github.com/hiroi-sora/Umi-OCR_runtime_linux)
- **macOS**：
  目前官方**尚未支援 macOS**（已被列入遠期開發計劃）。
  Umi-OCR 的圖形介面使用 Python + PySide2 (QML) 編寫，可直接在 macOS 下啟動前端；但由於離線 OCR 核心引擎（如 PaddleOCR-json 等 C++ 執行檔）尚未編譯相容於 macOS 的版本，因此辨識功能在 macOS 下暫時無法使用。

  > [!IMPORTANT]
  > **相容性警告 (PySide2)**：
  > 官方 `PySide2` 僅支援到 **Python 3.10**，且 PyPI (pip) **沒有提供 Apple Silicon (arm64) 的原生安裝檔**。
  > 若您在 Apple Silicon (M1/M2/M3) 的 Mac 上使用 Python 3.11+ (例如 Python 3.13.x) 執行 `pip install PySide2`，將會遭遇 `Could not find a version that satisfies the requirement PySide2` 錯誤。

  **解決方案 1：使用 Conda 安裝原生 arm64 庫（推薦，免模擬）**
  Conda-forge 提供支援 macOS arm64 的 PySide2 編譯版本。
  1. 安裝 Conda。若您已安裝 Homebrew，可直接在終端機執行命令安裝 Miniconda：
     ```bash
     brew install --cask miniconda
     conda init $(basename $SHELL)
     ```
     *(完成後請重啟終端機以啟用 conda)*
  2. 建立並啟動一個 Python 3.10 的虛擬環境：
     ```bash
     conda create -n umi-env python=3.10
     conda activate umi-env
     ```
  3. 安裝依賴庫：
     ```bash
     conda install -c conda-forge pyside2
     pip install bottle
     ```
  4. 進入專案目錄執行前端：
     ```bash
     cd UmiOCR-data
     python main.py
     ```

  **解決方案 2：使用 Rosetta 2 (Intel 模擬模式)**
  1. 安裝 Python 3.10 (Intel x86_64 版本)。
  2. 強制以 Intel 模擬方式建立虛擬環境：
     ```bash
     cd UmiOCR-data
     arch -x86_64 python3.10 -m venv venv
     source venv/bin/activate
     ```
  3. 安裝依賴庫：
     ```bash
     pip install PySide2 bottle
     ```
  4. 執行前端：
     ```bash
     python main.py
     ```



---

## 軟體在地化翻譯：

本專案使用 Weblate 平台進行 UI 介面的在地化翻譯協作。我們歡迎任何譯者參與翻譯工作，您可以進入此連結 [Weblate: Umi-OCR](https://hosted.weblate.org/engage/umi-ocr/) ，線上校對、補充現有語言，或新增語言。

感謝以下譯者，為 Umi-OCR 貢獻了在地化翻譯工作：

| 譯者                                                                                 | 貢獻語言                  |
| ------------------------------------------------------------------------------------ | ------------------------- |
| [bob](https://hosted.weblate.org/user/q021)                                          | English, 繁體中文, 日本語 |
| [Qingzheng Gao](https://github.com/QZGao)                                            | English, 繁體中文         |
| [Weng, Chia-Ling](https://hosted.weblate.org/user/ChiaLingWeng)                      | English, 繁體中文         |
| [linzow](https://hosted.weblate.org/user/linzow)                                     | English, 繁體中文         |
| [Marcos i](https://hosted.weblate.org/user/ultramarkorj9)                            | English, Português        |
| [Eric Guo](https://hosted.weblate.org/user/qwedc001)                                 | English                   |
| [steven0081](https://hosted.weblate.org/user/steven0081)                             | English                   |
| [Brandon Cagle](https://hosted.weblate.org/user/random4t4x14)                        | English                   |
| [plum7x](https://hosted.weblate.org/user/plum7x)                                     | 繁體中文                  |
| [hugoalh](https://hosted.weblate.org/user/hugoalh)                                   | 繁體中文                  |
| [Anarkiisto](https://hosted.weblate.org/user/Anarkiisto)                             | 繁體中文                  |
| [ドコモ光](https://hosted.weblate.org/user/umren190402)                              | 日本語                    |
| [杨鹏](https://hosted.weblate.org/user/ypf)                                          | Português                 |
| [Вячеслав Анатольевич Малышев](https://hosted.weblate.org/user/1969)                 | Русский                   |
| [Muhammadyusuf Kurbonov](https://hosted.weblate.org/user/muhammadyusuf.kurbonov2002) | Русский                   |
| [தமிழ்நேரம்](https://hosted.weblate.org/user/TamilNeram/)                                | தமிழ்                       |

如果有資訊錯誤或人員缺漏，請在 [這個討論](https://github.com/hiroi-sora/Umi-OCR/discussions/449) 中回覆。

---

## 贊助

Umi-OCR 專案主要由作者 [hiroi-sora](https://github.com/hiroi-sora) 利用業餘時間開發與維護。如果您喜歡這款軟體，歡迎贊助。

- 使用者可透過 [愛發電](https://afdian.com/a/hiroi-sora) 贊助作者。

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=hiroi-sora/Umi-OCR&type=Date)](https://star-history.com/#hiroi-sora/Umi-OCR&Date)

## [更新日誌](CHANGE_LOG.md)

## 開發計劃

<details>
<summary>已完成的工作</summary>

- 分頁頁籤框架。
- OCR API 控制器。
- OCR 任務控制器。
- 主題管理器，支援切換淺色/深色主題。
- 實作 **批次OCR**。
- 實作 **截圖OCR**。
- 快速鍵機制。
- 系統工作列選單。
- 文字區塊後處理（排版最佳化）。
- 引擎記憶體清理。
- 軟體介面多國語言。
- 命令列模式。
- Win7 相容。
- Excel (csv) 輸出格式。
- `Esc` 中斷截圖操作
- 外置主題檔案
- 字型切換
- 載入動畫
- 忽略區域。
- 二維碼辨識。
- 批次辨識分頁的圖片預覽視窗。
- PDF 辨識。
- 呼叫本機圖片瀏覽器開啟圖片。[#335](https://github.com/hiroi-sora/Umi-OCR/issues/335)
- 重複上一次截圖。[#357](https://github.com/hiroi-sora/Umi-OCR/issues/357)
- 修 Bug：文件辨識在 Windows7 系統的相容性問題。
- HTTP/命令列介面新增二維碼辨識/生成功能。(#423)
- 二維碼介面的文件。
- Linux 平台移植。
- HTTP 文件辨識介面。

</details>

##### 遠期計劃

<details>
<summary>展開</summary>

這些是預想中的功能，在開發初期已預留好介面，將在遠期慢慢實作。

但開發途中受限於實際情況，可能變更功能設計、新增或取消功能。

- [ ] 重構底層外掛模組機制。
- [ ] 線上 OCR API 外掛模組。
- [ ] 獨立的數學公式辨識外掛模組。
- [ ] 「數學公式」分頁，提供獨立的數學公式辨識/Latex 渲染。
- [ ] 檢查更新機制。
- [ ] 排版解析之外的文字後處理模組（如保留數字、半全形字元轉換、文字糾錯）。
- [ ] 關鍵介面函式新增事件觸發方式。

- 基於 GPU 的離線 OCR。
- 圖片翻譯。
- 離線翻譯。
- 固定區域辨識。
- 辨識表格圖片，輸出為 Excel。
- 歷史記錄系統。
- 相容 MacOS / Ubuntu 等平台。

</details>
