# 微信公众号markdown编辑器
  这是一个Demo示例，点击**预览**，可查看效果
>微信公众号编辑器编辑 器十分不好用，而且还不支持markdown语法

### 特性
- 适配 Android
- 支持代码不转行，横向滚动条
- 支持页面主题样式配置

### 代码示例

```javascript
var OnlineMarkdown = {
  init: function() {
    var self = this;
    self.load().then(function() {
      self.start()
    }).fail(function(){
      self.start();
    });
  },
  start: function() {
    this.updateOutput();
  },
  load: function() {
    return $.ajax({
      type: 'GET',
      url: params.path || './demo.md',
      dateType: 'text',
      timeout: 2000
    }).then(function(data) {
      $('#input').val(data);
    });
  },
  updateOutput: function () {
    var val = this.converter.makeHtml($('#input').val());
    $('#output .wrapper').html(val);
    PR.prettyPrint();
  }
};

OnlineMarkdown.init();
```
---

上面是 `JavaScript`，下面是 `php`：

```php
echo 'hello,world'
```

### 表格示例

| 品类 | 个数 | 备注 |
|-----|-----|------|
| 苹果 | 1   | nice |
| 橘子 | 2   | job |
