# 一個用於 ZMK 韌體配置測試的 4×3 鍵盤

! 此文件暫時使用 Gemini 進行翻譯  
不是因為我不會中文，而是我暫時沒時間  
最新版本請以英文為主

[English version](./README.md)

在開始製作最終版的 Dvorak 特化直列式 (ortholinear) 左手數字鍵 (southpaw) 鍵盤之前，我打算先做出一個功能與最終成品相同的縮小版原型，以驗證可行性並作為最終產品的跳板。

Build 了 50 次，終於迎來了第一次成功。

## 如何將韌體燒錄至您的 Seeed XIAO

首先，你需要此專案的 `.uf2` 檔案。`.uf2` 檔案位於 `Action` 標籤分頁中。點擊第一個成功項目，在 `Artifacts` 區塊內有一個 `firmware` 物件。點擊下載 `.zip` 並解壓後，即可獲得 `.uf2` 檔案。

之後，在 Seeed XIAO **連接至電腦後**，連續按兩下板子上的 `RST` 按鈕進入 bootloader 模式。你的 Seeed XIAO 會在檔案總管中顯示為名為 `XIAO-SENSE` 的 USB 磁碟。如果名稱不完全相同，你應該也能輕易辨識出該裝置。

將 `.uf2` 檔案拖進該「USB 磁碟」中。傳輸完成後，Seeed XIAO 會自動退片並重啟進入程式碼。如果功能運作正常，你就完成了 Seeed XIAO 的韌體燒錄。

## 功能

- 4x3 矩陣已啟用
- USB 有線連接
- 基礎打字功能
- 支援 ZMK Studio

### 待加入功能
- 藍牙連接（使用 USB 供電）

## 硬體需求

### 本專案所需的所有組件

- Seeed XIAO nRF52840
- 16 顆機械鍵盤軸體
- 我的 4×3 矩陣 DIP PCB  
  未來可以在台灣的購物平台「蝦皮 (Shopee)」購買，PCB 製造文件隨後也會上傳。
- 74HC595 IC

### 未來更新所需的組件

- 一顆 BL-5C 電池
- 可拆卸式電池連接線
- (選配) LED 條狀圖顯示器 (bar graph display)
- (選配) 給上述顯示器使用的 4 顆電阻

---

這裡的一切基本上都參考自官方文件。你可以查看 [references.md](./references.md) 以獲取更詳細的資訊。  
文件中的參考資料順序應依照使用的時間先後排列。

---

# History

由新到舊排序

## FUNCTION COMPLETED

在 **第 117 次 build** (2026 年 1 月 5 日 → 6 日凌晨) 有線功能完成!  
結果真正的問題在於，我不應該在使用 SPI 時將 MISO (D9) 設定為 `CS` (AKA `latch`) 腳位。  
**各位請記取教訓！** 否則你會浪費大量的時間。

在 **第 107 次 build** (2026 年 1 月 5 日)，我終於讓加入 74595 的版本通過編譯。  
還需要更多配置才能讓它正常運作，但它已經通過編譯且基本上可以執行。  
一切終於快要告一個段落了……

## ZMK Studio function added successfully

在 **第 85 次 build** (2025 年 12 月 26 日)，我終於成功加入了 ZMK Studio。  
好喔，所以所有的問題都出在 [.dtsi](./boards/shields/zmk_4x3test/zmk_4x3test-layouts.dtsi) 文件中的 `chosen` 節點。它真的是「被選中的節點」。

## 釐清直欄 (Column) 與橫列 (Row)
在 **第 66 次 build** (2025 年 11 月 11 日)，我終於發現我誤解了 Column 和 Row 的意思。  
作為一個小提醒，我在這裡做個筆記：

＼|第 0 欄 (Col 0)|第 1 欄 (Col 1)|第 2 欄 (Col 2)
--|--------|--------|--------
第 0 列 (Row 0)|RC(0,0)|RC(0,1)|RC(0,2)
第 1 列 (Row 1)|RC(1,0)|RC(1,1)|RC(1,2)

## First successful build

終於在 **第 51 次 build** 成功編譯，並在 **第 54 次** 時才意識到這件事。  
之所以沒在成功當下發現，是因為我當時是用 Samsung Galaxy Tab S7 FE 搭配 [VS code 網頁版](https://vscode.dev)，非常卡頓，很難獲得即時的進度回饋。