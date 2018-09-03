# gocaptcha
一个简单的Go语言实现的验证码

##图片实例

![image](https://raw.githubusercontent.com/lifei6671/gocaptcha/master/example/image_1.jpg)
![image](https://raw.githubusercontent.com/lifei6671/gocaptcha/master/example/image_2.jpg)
![image](https://raw.githubusercontent.com/lifei6671/gocaptcha/master/example/image_3.jpg)
![image](https://raw.githubusercontent.com/lifei6671/gocaptcha/master/example/image_4.jpg)

##简介

基于Golang实现的图片验证码生成库，可以实现随机字母个数，随机直线，随机噪点等。可以设置任意多字体，每个验证码随机选一种字体展示。

##实例

###使用：

```
	go get github.com/worldlove/gocaptcha/
```

###使用的类库

```
	go get github.com/golang/freetype
	go get github.com/golang/freetype/truetype
	go get golang.org/x/image
```
###使用说明

```
//初始化配置
func init() {
	// gocaptcha.ReadFonts("fonts", ".ttf") //配置字体目录
	cap = gocaptcha.NewCaptchaImage(*image.RGBA) //配置背景色, 如果设置为nil, 则随机生成
	cap.SetSize(128, 60) //配置图片大小(x, y)
	cap.SetLine(1)       //配置干扰线条数
	cap.SetDisturbance(gocaptcha.MEDIUM) //配置干扰级别
}

img, str := cap.Create(6, gocaptcha.ALL) //设置字符个数与字符类型 ALL=[:alnum:], NUM=[:digit:], ALPHA=[:alpha:], LOWER=[a-z], UPPER=[A-Z]

//...之后可自行处理图片和字符串

```




