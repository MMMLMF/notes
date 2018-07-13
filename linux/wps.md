### wps for linux 不能使用搜狗输入法

ubuntu版本：15.04
中文输入法：搜狗


#### wps文字不能输入中文解决

```bash
$ vi /usr/bin/wps      # 添加内容，字体标注
#!/bin/bash
export XMODIFIERS="@im=fcitx"
export QT_IM_MODULE="fcitx"
gOpt=
#gOptExt=-multiply
gTemplateExt=("wpt" "dot" "dotx")

```

#### wps表格不能输入中文解决\
```bash
$ vi /usr/bin/et      # 添加内容，字体标注
#!/bin/bash
export XMODIFIERS="@im=fcitx"
export QT_IM_MODULE="fcitx"
gOpt=
#gOptExt=-multiply
```

原因：环境变量未正确设置，以上可以直接针对wps设置。
