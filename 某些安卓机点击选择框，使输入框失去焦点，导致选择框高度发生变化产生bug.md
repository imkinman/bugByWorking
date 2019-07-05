## 问题：点击选择框，使输入框失去焦点，导致选择框高度发生变化产生bug <br>
原因：<br>
&emsp; 当输入框获取焦点时，会打开键盘，然后直接去点击选项框，会导致选项框的高度，按照当前屏幕（原本屏幕高度 - 键盘高度）的高度计算而变小，因此会导致选项框产生滚动条，不注意的情况下会以为数据变少<br><br>
解决：
 ```
 $("input, textarea").blur(function(){
    $('select').prop('disabled', true);
    setTimeout(function(){
      $('select').prop('disabled', false);
    }, 100);
  });
 ```
