如果您在使用智能图像服务中有疑问，您可以参考以下的问题及解答：

## 文字识别

### 怎么提高身份证 OCR 识别的准确性？
识别的准确性跟字体、拍照光线、清晰度等因素有关，建议图片文字清晰，光线自然无反光，身份证占图片比例超过 80% 。如少数民族身份证含两种以上语言，会干扰识别结果。

### 身份证 OCR 是怎么收费的？
按调用接口次数收费，具体请查看 [计费说明](/document/product/641/12424)。

### 是否可以识别电子账单/商品吊牌数字/运动 APP 的步数/商超货架商品等？
可以使用通用 OCR 识别，准确率一般在85%左右，不过根据使用场景的不同，准确率也有所差异。

### 是否可以识别银行汇票/保险单/手写的发票/个人征信报告？
您可以使用我们的通用 OCR 识别，如需要定制化开发，请 [联系我们](http://console.tcecqpoc.fsphere.cn/workorder/category/create?level1_id=83&level2_id=86&level1_name=%E5%AD%98%E5%82%A8%E4%B8%8ECDN&level2_name=%E4%B8%87%E8%B1%A1%E4%BC%98%E5%9B%BE%20CI)。

### OCR 文字识别出的文字是什么类型的？保存在哪里？

识别出来后返回的是 json 字符串，开发可以自定义存储格式。

## 图片标签

### 怎么提高图片标签的准确性？
您可以在我们的标签系统上使用自定义标签，通过训练提高准确性。目前标签有上百个热词，平均准确率有 80%，后续还会继续扩大标签范围。如有遇到未识别的标签，也可反馈给我们进行优化。

### 是否可以用图片标签识别图片里的水印和 LOGO？
若水印和 LOGO 内容是文字的话，可以使用我们的通用 OCR 识别；若是图形的话，在一定训练的基础上，可以使用图片标签将内容分类。

## 人脸识别

### 人脸对比对照片有什么要求？
要图片光线自然，无过度曝光；人脸不存在遮挡，人脸区域分辨率不低于 100*100；人脸为正，如横拍的照片带有exif信息，旋转后亦可处理。

### 人脸对比如何判断是否为同一个人？
根据 far（错误通过率）来定阈值，如 far=0.1% 对应的阈值分数为 70 分，far=0.01% 对应的阈值分数为 80 分； far=0.001% 对应的阈值分数为 90 分。通常来说 75 分以上可以判断为同一个人，建议您根据实际应用场景适当调节分数阈值。

### 是否可以识别一张照片的多个人脸？
可以，调用 [人脸检测接口](/document/product/641/12415)，并把检测模式改成 0 即可。

### 戴眼镜、假发、浓妆、光线、美颜、多人合照等特殊情况的匹配效果，能否提供测试地址？
特殊情况拍摄的匹配效果，您可访问 [开发平台](/act/event/ci_demo.html)进行测试，并可以在 SDK 下载页面下载。

## 人脸核身

### 人脸核身有基于 PaaS 和 SaaS 两种模式，具体区别在哪里？ 
PaaS 模式提供了后台接口的简单示例，您可以更灵活的调用接口；SaaS 模式提供了一个完整可用的 demo，您可以用更低的开发成本将服务集成到产品中。

### 人脸核身对图片和视频的质量有哪些要求？
对图片的要求时候光线自然，像素不低于 775\*498，无过度曝光；对视频的要求是人脸的位置变化较小且始终在视频中，视频分辨率不低于 270*480，读数字语速偏慢约1秒1字，声音宏亮，周围环境安静噪音小。

### 人脸核身是否支持嵌入到微信小程序／H5 开发／原生客户端／PC 端等？
我们的接口是基于 http 协议，只要支持 http 协议都可以使用，与调用端无关。

### 申请人脸核身通过后，免费体验是怎么计算的？
人脸核身提供 4 个 [API 接口](/document/product/641/12407)，其中 [活体检测—获取唇语验证码](/document/product/641/12431) 接口免费，其余 3 项服务各有 25 次不限时间的免费体验。






