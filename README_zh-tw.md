# Eagle 自定義收藏屬性 (Eagle Attributes)
語言: [English](README.md) / [繁體中文](README_zh-tw.md) / [简体中文](README_zh-cn.md)

Eagle 是一款功能強大的素材管理工具，能夠讓您方便地收藏、管理和搜尋數位素材。

對於有程式設計基礎的使用者，您可以透過編寫自訂腳本（例如用戶腳本），來擴展 Eagle 收藏的功能。自訂收藏項目的標題、連結、圖片解析度，以及新增註解和標籤，以滿足您的特定需求。

## 可用屬性
以下是您可以在腳本中使用的屬性列表：
| 屬性名稱 | 描述 |
| --------- | ----------- |
| eagle-title | 覆蓋收藏素材的標題 |
| eagle-src | 覆蓋收藏素材的網址 |
| eagle-annotation | 為收藏素材添加註解 |
| eagle-tags | 為收藏素材添加標籤 |
| eagle-link | 覆蓋收藏素材的來源網址 |

## 使用方法

以下是在您的網站上實施這些屬性的逐步指南：

1. 選擇您想要修改的元素。
2. 在該元素的標籤中，新增您想使用的屬性。例如，要修改標題，新增 `eagle-title` 屬性。
3. 在屬性的值中，輸入您想要的內容。例如，`eagle-title="我的自訂標題"` 將設置標題為 "我的自訂標題"。

```javascript
// 選擇頁面上的所有 img 標籤
var images = document.getElementsByTagName('img');

// 遍歷每個 img 標籤
for (var i = 0; i < images.length; i++) {
    // 為每個 img 標籤增加 eagle-title 屬性
    images[i].setAttribute('eagle-title', 'my custom title');
}
```

## 示範案例

### 自訂收藏標題

要自訂網頁上圖片的收藏標題，請為圖片元素新增 `eagle-title` 屬性，並設定您希望的標題。當您使用 Eagle 瀏覽器擴充功能收藏圖片時，您設定的標題將被保留。

```html
<img src="https://example.com/test.png" eagle-title="我的自訂標題">
```
![範例圖片](.readme/eagle-title-html.jpg "HTML 中的樣子")
![範例圖片](.readme/eagle-title-collect.jpg "收藏至 Eagle 後的樣子")

### 自訂收藏圖片網址

有時候，網站可能只顯示圖片的縮圖而非完整尺寸。如果您知道原始完整圖片的網址，您可以使用 `eagle-src` 屬性直接設定元素的完整圖片網址。當您收藏該圖片時，您將獲得原始完整圖片的網址。

```html
<img src="https://example.com/test_small.jpg" eagle-src="https://example.com/test_original.jpg">
```

### 定義自訂圖片連結並新增註解

要為圖片設定自訂連結並新增註解，可同時使用 `eagle-link` 和 `eagle-annotation` 屬性。以下是一個示例：

```html
<img src="https://example.com/test_small.jpg" eagle-link="https://example.com" eagle-annotation="我的自訂註解">
```

在此示例中，當您使用 Eagle 瀏覽器擴充功能收藏這個圖片時，將直接獲得自訂連結網址，並且圖片的註解將會是 "我的自訂註解"。

## 常見問題

Q: 我在哪裡可以找到更多有關 Eagle 的資訊？ \
A: 您可以在我們的 [官方網站](https://eagle.cool/) 上找到更多有關 Eagle 的資訊。

Q: 我在哪裡可以找到更多有關編寫腳本的資訊？ \
A: 您可以參考像是 [Greasy Fork](https://greasyfork.org/zh-TW) 和 [Tampermonkey](https://www.tampermonkey.net/) 的網站來獲取編寫腳本的資訊。