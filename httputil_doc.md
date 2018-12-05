# wugongxi.git.io
me network

# HttpUtil - 0.1.15 一个基于okhttp的标准RESTful风格的网络框架，支持http和https
This is a network request library that specializes in http and HTTPS. It aims to simplify the network connection module in Android applications.



Maven
```
<dependency>
  <groupId>top.wgx.util</groupId>
  <artifactId>net</artifactId>
  <version>0.1.16</version>
  <type>pom</type>
</dependency>
```
GRADLE
```java
compile 'top.wgx.util:net:0.1.15'
```




Examples

GET A URL
```java
		NetWorkUtil.get("url")
			.param("","")
			.param("","")
			.addHeader("","")
			.addHeader("","")
			.builder(new JCallBack<String>() {
            @Override
            public void onSucceed(String result, Call call) {
            }
        });
```
POST TO A SERVER
```java
		NetWorkUtil.post("url")
		.param("", "")
		.addHeader("", "")
		.builder(new Callback() {
            @Override
            public void onFailure(Call call, IOException e) {
            }

            @Override
            public void onResponse(Call call, Response response) throws IOException {
            }
        });
```

REQUESTS OBJECT
```java
        NetWorkUtil.url("http://www.angame.top/res/bean.txt")
		.param("beankey", "beanvalue")
		.rmHeader("hkk")
		.addHeader("h-bean-key", "h-bean-value")
		.tag("aaaa")
		.builder(new JCallBack<Bean>() {
            @Override
            public void onSucceed(Bean result, Call call) {
                tv.setText(result.name);
            }
            @Override
            public void onFaild(Call call, Exception e) {
                super.onFaild(call, e);
                Log.e("onFaild:", "call:" + (call.isCanceled()) +
				(call.isExecuted()) + e.getMessage());
            }
        });
```

UPLOAD FILE AND DATA
```java
		NetWorkUtil.multPost("url")
		.addHeader("","")
		.param("",new File(""))
		.param("",new File(""))
		.param("","")
		.builder(new JCallBack<String>() {
            @Override
            public void onSucceed(String result, Call call) {
            }
        });
```

```java
        NetWorkUtil.url("http://angame.top/file/t1/bg.jpg")
		.param("jpgkey", "jpgvalue")
		.addHeader("jpg_heander", "jpg_heander-value")
		.builder(new BitmapCallBack() {
            @Override
            public void onSucceed(Bitmap t, Call call) {
                img.setImageBitmap(t);
            }

            @Override
            public void onAfter(Call call) {
                super.onAfter(call);
            }
        });
```


DOWNLOAD FILE

```java
        String path = Environment.getExternalStorageDirectory().getAbsolutePath()+ "/bc.mp4";
        System.out.println(path);
        NetWorkUtil.url("http://www.angame.top/res/video.avi")
		.param("down--k", "down--v")
		.addHeader("down-aab", "down--abc")
		.builder(path, new OnDownLoadListener() {
            @Override
            public void onSucceed(File file, Call call) {
                super.onSucceed(file, call);
                x = 0;
                Toast.makeText(MainActivity.this, "下载成功" 
				+ file.getAbsolutePath(), Toast.LENGTH_SHORT).show();
                Log.e("path:","下载成功" + file.getAbsolutePath());
                videoView.setVideoPath(file.getAbsolutePath());
                System.out.println(file.getAbsolutePath());
                videoView.start();
                videoView.requestFocus();
            }

            @Override
            public void onFaild(String path, Call call, IOException e) {
                super.onFaild(path, call, e);
                tv_progress.setText("失败 " + path);
            }

            @Override
            public void onstart(final String path) {
                super.onstart(path);
                File file = new File(path);
                if (file.isFile() && file.exists()) {
                    file.delete();
                }

                mHandler.post(new Runnable() {
                    @Override
                    public void run() {
                        tv_progress.setText("开始下载" + path);
                    }
                });
            }

            @Override
            public void onDLoadProgress(long total, long progress, String path) {
                super.onDLoadProgress(total, progress, path);
                runOnUiThread(new Runnable() {
                    @Override
                    public void run() {
                tv_progress.setText("进度： " + total + " / " + progress);
                    }
                });
            }
        });
```

`
        //支持根据tag cancel;
        NetWorkUtil.getInstance().cancle("aaaa");
`



#end