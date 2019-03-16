<style type="text/css">
textarea {
  width: 45%;
}
textarea + textarea {
  margin-left: 1%;
}

#contents {
  text-align: center
}

</style>
<head>
  <meta charset="utf-8"/>
</head>
<div id="contents">
  <h1>MTG Arenaでエクスポートした状態で貼り付けてください</h1>
  <textarea id="export" rows="25" placeholder="こちらに貼り付けてください"></textarea>
  <textarea id="result" rows="25" placeholder="リアルタイムに更新されます"></textarea>
</div>


<script>
  const result = document.querySelector('#result')
  document.querySelector('#export').addEventListener('input', e => {
    // 正規表現は候補はいろいろ。\Wを最短マッチでもわかりやすいか。パック名(M19)のカッコは半角なためここでは全角()を使いフリガナとしているが、一瞥のわかりやすさは低い。
    result.textContent = e.target.value.replace(/（[^（）]+）/g, '')
  })

</script>
