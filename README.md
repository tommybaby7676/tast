<!doctype html>
<html lang="zh-Hant">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>好玩遊戲</title>

  <style>
    /* 讓整頁像一張 1080x1920 海報 */
    html, body{
      height:100%;
      margin:0;
      background:#000; /* 海報外的底色 */
      overflow:hidden;
      font-family: Arial, "Noto Sans TC", sans-serif;
    }

    /* 用 aspect-ratio 固定 9:16，並在任何螢幕自動縮放 */
    .poster{
      position: relative;
      width: min(100vw, calc(100vh * (9 / 16)));
      aspect-ratio: 9 / 16; /* = 1080/1920 */
      height: auto;
      margin: 0 auto;
      top: 50%;
      transform: translateY(-50%);
      background: #111;
      overflow: hidden;
    }

    /* 單圖鋪滿（你只要換這張圖檔即可） */
    .poster img{
      position:absolute;
      inset:0;
      width:100%;
      height:100%;
      object-fit: cover; /* 要整張不裁切就改 contain */
      display:block;
      user-select:none;
      -webkit-user-drag:none;
    }

    /*
      CTA 熱區（視覺在圖內，但其實是透明可點區）
      你只要改 top/left/width/height 就能對齊你圖裡的按鈕位置
    */
    .cta-hotspot{
      position:absolute;
      /* 這些數值是示範：大概落在下方中間的按鈕區 */
      left: 12%;
      top: 78%;
      width: 76%;
      height: 11%;
      border-radius: 999px;
      text-indent: -9999px;
      overflow: hidden;

      /* 預設完全透明；要方便你對位時，臨時把 opacity 調高 */
      background: rgba(255,255,255,0.0);
    }

    /* 讓鍵盤使用者也能按到（可存活但不礙眼） */
    .cta-hotspot:focus{
      outline: 2px solid rgba(255,255,255,0.65);
      outline-offset: 4px;
    }
  </style>
</head>

<body>
  <main class="poster" aria-label="活動海報">
    <
