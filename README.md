AlertDialog
-
[![](https://jitpack.io/v/enChenging/AlertDialog.svg)](https://jitpack.io/#enChenging/AlertDialog)


效果图如下：

<div align="left" >
	<img src="https://github.com/enChenging/AlertDialog/blob/master/screenshot/video.gif" width="200">
</div>

## 用法

>Android Studio

将其添加到存储库build.gradle中
```xml
allprojects {
    repositories {
      	...
        maven{url 'https://jitpack.io'}
    }
}
```
 在build.gradle文件中的dependencies下添加引用：
	
```java
implementation 'com.github.enChenging:AlertDialog:1.0'
```


使用：
```java

private String[] bottomData = {"发送给好友", "转载到空间相册", "上传到群相册", "保存到手机", "收藏", "查看聊天图片"};
private List<ItemBean> listData = new ArrayList<>();
     for (int i = 0; i < 100; i++) {
        listData.add(new ItemBean("条目 " + i, 0));
    }
    
new AlertDialog(MainActivity.this)
        .builder()
        .setMsg("仿ios无标题弹窗")
        .setPositiveButton(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Toast.makeText(MainActivity.this, "确定", Toast.LENGTH_SHORT).show();

            }
        })
        .show();

new AlertDialog(MainActivity.this)
        .builder()
        .setTitle("标题")
        .setMsg("仿ios弹窗")
        .setPositiveButton(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Toast.makeText(MainActivity.this, "确定", Toast.LENGTH_SHORT).show();
            }
        })
        .setNegativeButton(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Toast.makeText(MainActivity.this, "取消", Toast.LENGTH_SHORT).show();
            }
        }).show();

new AlertDialog(MainActivity.this)
        .builder(AlertDialog.Type.BOTTOM)
        .addItem("清空列表")
        .setOnItemClickListener(new AlertDialog.OnAlertItemClickListener() {
            @Override
            public void onItemClick(View view, int position) {
                Toast.makeText(MainActivity.this, position + "", Toast.LENGTH_SHORT).show();
            }
        })
        .show();

new AlertDialog(MainActivity.this)
        .builder(AlertDialog.Type.BOTTOM)
        .addItem("相机")
        .addItem("相册")
        .setOnItemClickListener(new AlertDialog.OnAlertItemClickListener() {
            @Override
            public void onItemClick(View view, int position) {
                Toast.makeText(MainActivity.this, position + "", Toast.LENGTH_SHORT).show();
            }
        })
        .show();

new AlertDialog(MainActivity.this)
        .builder(AlertDialog.Type.BOTTOM)
        .addItem(bottomData)
        .setOnItemClickListener(new AlertDialog.OnAlertItemClickListener() {
            @Override
            public void onItemClick(View view, int position) {
                Toast.makeText(MainActivity.this, position + "", Toast.LENGTH_SHORT).show();
            }
        })
        .show();

new AlertDialog(MainActivity.this)
        .builder(AlertDialog.Type.BOTTOM)
        .addItem(listData)
        .setOnItemClickListener(new AlertDialog.OnAlertItemClickListener() {
            @Override
            public void onItemClick(View view, int position) {
                Toast.makeText(MainActivity.this, position + "", Toast.LENGTH_SHORT).show();
            }
        })
        .show();

new AlertDialog(MainActivity.this)
        .builder(AlertDialog.Type.PROGRESS)
        .setProgressTextGone()
        .show();

new AlertDialog(MainActivity.this)
        .builder(AlertDialog.Type.PROGRESS)
        .show();

new AlertDialog(MainActivity.this)
        .builder(AlertDialog.Type.PROGRESS)
        .setProgressText("自定义文字自定义文字自定义文字自定义文字自定义文字")
        .show();

new AlertDialog(MainActivity.this)
        .builder(AlertDialog.Type.CUSTOM_DIALOG, R.layout.custom_dialog_layout)
        .initDialogLayout(new AlertDialog.OnInitDialogLayoutListener() {
            @Override
            public void initView(View view, final Dialog dialog) {
                view.findViewById(R.id.iv_close).setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                        Toast.makeText(MainActivity.this, "消失", Toast.LENGTH_SHORT).show();
                        dialog.dismiss();
                    }
                });
                view.findViewById(R.id.btn_ok).setOnClickListener(new View.OnClickListener() {
                    @Override
                    public void onClick(View v) {
                        Toast.makeText(MainActivity.this, "领取", Toast.LENGTH_SHORT).show();
                        dialog.dismiss();
                    }
                });
            }
        })
        .show();
```


## 混淆

```java
#AlertDialog
-dontwarn com.release.alert.**
-keep class com.release.alert.**{*;}

```

声明
-
本控件用作分享与学习。

关于作者
-
[CSDN博客：https://blog.csdn.net/AliEnCheng/article/details/103778244](https://blog.csdn.net/AliEnCheng/article/details/103778244)





