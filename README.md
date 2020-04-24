
# 製作成品與資源連結
* [index.html](https://gmwu185.github.io/layoutTraining-week-02-portfolio/index.html)
* [work-pse-position.html](https://gmwu185.github.io/layoutTraining-week-02-portfolio/work-pse-position.html)
* [work-flex-position.html](https://gmwu185.github.io/layoutTraining-week-02-portfolio/work-flex-position.html)
* [Adobe XD 設計稿](https://xd.adobe.com/view/7cc08d73-d444-4b6f-7a94-01ffbdf8ce0a-0af1/)


# 製作與細節
- 透過工具類樣式為主組合畫面。
- [Google web font](https://fonts.google.com/) 的字體依字重與斜體處理成獨立樣式，認識系統預設 `roboto` 與 [Google web font - roboto](https://fonts.google.com/specimen/Roboto) 的字重差異，前者於裝置預設通用較高，後者可做更細的字重規畫。
- 容器主要透過 flex 排版，沒配合斷點下透過 flex 處理出簡易的自適應排版。
- 透過 `display:` 的 `block`、`inline-block`; 處理元素內排版，`<span></span>` 控制字串於容器斷行，可延伸用於自適應讓字串在容器於不同寬度時，在行內自動斷行方式。
- 中文正體與英文斜體處理。
- 偽元素 `display: inline-block` 屬性與字元對齊 (`.c-centerList`)。
- `.workList` 區塊配合背景圖的三種排版方式，三種方式需針對 `margin` 負值做上移溢位處理，溢位的父層元素需要進行補值計算高度 ( 父層容器高度 `1558 px` )。
	- [index.html](https://gmwu185.github.io/layoutTraining-week-02-portfolio/index.html) 使用容器背景圖加相對定位 、`.workList__inner` (子層)( `position: relative;` + `top: -80px;`)。
	- [work-pse-position.html](https://gmwu185.github.io/layoutTraining-week-02-portfolio/work-pse-position.html) 使用偽類背景與本體元素 (`.workList` 相對定位) 和偽元素 (`.workList--pseudoBg` 絕對定位) 定位處理，這理有使用 `margin` 負值做上移溢位處理，但如果透過 高度配合 `margin-top` or `margin-bottom` 來做背景高度比例處理，加上 `top` 負值一樣可以實現定位效果，另外可配合 `z-index` 來操作層疉。
	- [work-flex-position.html](https://gmwu185.github.io/layoutTraining-week-02-portfolio/work-flex-position.html) 使用 `display: flex` 與 `flex-wrap: wrap` 在父層操作，內層元素轉為子元件後透過 .`u-mt--neg-80` 上移溢位的定位處理，`.u-alignItems--flexStart` 為 flex 的預設值可下可不下。
- `@2` or `2X` for retina 圖片與背景圖處理。
- 盡可能依 Adobe XD 畫面設計稿的區塊尺寸來處理畫面與容器高寬，部份文字區塊不可能直接使用 `line-Height` 實現，多行配合 `margin` 來推補到文字區塊的尺寸，單行以 `line-Height` 處理文字區塊的高度。