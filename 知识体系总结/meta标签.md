### meta标签

通常所说的 meta 标签，是在 HTML 网页源代码中一个重要的 html 标签。

meta 标签用来描述一个HTML网页文档的属性，例如：网页描述、关键词等。

### 作用

meta 标签是 HTML 标记 head 区的一个关键标签。

它提供的信息虽然用户不可见，但却是文档的最基本元信息。

meta标签的内容设计对于搜索引擎营销来说是至关重要的一个因素，合理利用 meta 标签的 `description` 和 `keywords` ，加入网站的关键字或者网页的关键字，可以使网站更加贴近用户体验。

### meta 的属性
1. name 
该属性定义文档级元数据的名称。
```
    <meta name="renderer" content="webkit">
```
name 属性的可能值：
* description：页面的描述
```
    <meta name="description" content="淘宝网 - 亚洲较大的网上交易平台，提供各类服饰、美容、家居、数码、话费/点卡充值… 数亿优质商品，同时提供担保交易(先收货后付款)等安全交易保障服务，并由商家提供退货承诺、破损补寄等消费者保障服务，让你安心享受网上购物乐趣！">
```

* keywords: 关键字,逗号分隔
```
    <meta name="keyword" content="淘宝,掏宝,网上购物,C2C,在线交易,交易市场,网上交易,交易市场,网上买,网上卖,购物网站,团购,网上贸易,安全购物,电子商务,放心买,供应,买卖信息,网店,一口价,拍卖,网上开店,网络购物,打折,免费开店,网购,频道,店铺">
```       

* viewport：它提供有关视口初始大小的提示，仅供移动设备使用。
```
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=yes">
```

2. http-equiv
此属性定义了能够改变服务器与用户引擎行为的编译。


3. charset
鼓励使用 utf-8 字符编码

上面三个属性不能同时存在于同一个 meta标签中。

```
    <meta charset="utf-8">
```

4. content
此属性包含 name 或 http-equiv 属性的值，具体取决于所使用的值。


5. version





