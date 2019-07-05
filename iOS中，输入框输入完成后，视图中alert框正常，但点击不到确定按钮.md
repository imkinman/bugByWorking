## 问题：iOS中，输入框输入完成后，视图中alert框正常，但点击不到确定按钮 <br>
原因：<br>
&emsp; iOS中，输入框获取焦点时，键盘打开，导致页面整体上移，当失去焦点时，页面实际位置不会恢复，导致视图位置隐性改变。<br><br>
解决：<br>
```
if (/(iPhone|iPad|iPod|iOS)/i.test(window.navigator.userAgent)) {
  var bfscrolltop = document.body.scrollTop;
  $("input, textarea, select").blur(function(){
    document.body.scrollTop = bfscrolltop;
  });
}
```
