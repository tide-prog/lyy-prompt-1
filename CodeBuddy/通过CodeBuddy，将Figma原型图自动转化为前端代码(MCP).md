# 通过CodeBuddy，将Figma原型图自动转化为前端代码(MCP)

## 第一步：安装
[文档教程](https://cloud.tencent.com/developer/article/2548237 "文档教程")【https://cloud.tencent.com/developer/article/2548237】
 
## 第二步：使用提示词

https://www.figma.com/design/kUDBGxBWmUmglNkuIySb1a/%E8%AE%BE%E8%AE%A1%E7%A8%BF?node-id=269-78&t=oVKl4arX7al3pGbg-4 根据提供的figma链接，生成对应的html页面，要求css也放在html当中

要求：
导入全局通用css：https://hk-saas-cdn.lianyayun.com/static/jext/css/global.css?t=v2.1.20。
读取【https://hk-saas-cdn.lianyayun.com/static/jext/css/global.css?t=v2.1.20】，并结合使用。
模块的内容宽度可用类名 cw1400。
H5调整时，考虑不同宽度的自适应。
在992px以下宽度开始调整，必须全部使用rem单位。
移动端样式在768px以下宽度开始调整，必须全部使用rem单位。
移动端名称或标题大小为0.32和0.36rem之间。
移动端正文或描述大小为0.26和0.3rem之间。
移动端最小字体为0.26rem。
根据样式加入鼠标移入效果。
如果模块有列表样式请使用 PHP 的 foreach 循环。
hover样式写到@media(any-hover: hover){}中。
用PHP生成模拟数据。
交互功能也需要实现。

限制：
html标题不要用h标签,{}中的样式不要换行，单位用px，模块不要固定高度，用padding控制边距。
No000是固定前缀，不可更换。
除了No000Wrap类名，其他类名只保持一个单词或简写，不可多个单词拼接，且必须是id名+类名，例如：#No000Title .title{}。
css的属性和值需要隔开一个空格，例如：#No000Title .title{font-size: *px;color: *;}。

格式参考：
```html
<div class="No000Wrap">
    <section id="No000Title" class="cw1440">
        <h3 class="title">xxxx</h3>
    </section>
    <section id="No000Con" class="cw1440"></section>
</div>
<script></script>
<style>
/* 模块布局 */
.No000Wrap{
    --titleSize: 0.36rem;
    --titleColor: #000;
    --conSize: 0.3rem;
    --conColor: #666;
}

/* 模块标题样式 */
#No000Title{}
#No000Title .title{}
@media (max-width: 992px) {
    #No000Title{}
}
@media (max-width: 768px) {
    #No000Title{}
}

/* 模块内容样式 */
#No000Con{}
@media (max-width: 992px) {
	#No000Con{}
}
@media (max-width: 768px) {
    #No000Con{}
}
</style>
```

## 第三步：检查代码
1.宽高检查，生成的代码宽高都是固定的px需要自行换算为%。
2.对鼠标效果检查，如果设计稿有鼠标移入样式的话，需要自行将效果修改到鼠标移入事件后。
3.生成的代码中图片和图标是没有的，需要到figma下载。
4.就是对移动端效果检查。

## 第四步：生成的代码

```html
    <!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>新闻资讯</title>
    <link rel="stylesheet" href="https://hk-saas-cdn.lianyayun.com/static/jext/css/global.css?t=v2.1.20">
</head>
<body>
    <div class="No000Wrap">
        <section id="No000Title" class="cw1440">
            <div class="title">新闻资讯</div>
            <div class="desc">聚焦行业动态与企业资讯，持续传递前沿医疗显示信息</div>
        </section>
        <section id="No000Con" class="cw1440">
            <div class="list">
                <div class="item gray">
                    <div class="img"></div>
                    <div class="info">
                        <div class="meta">
                            <span class="date">2025.10.28</span>
                            <span class="tag">公司新闻</span>
                        </div>
                        <div class="tit">巨融医疗DSA介入手术终端正式入驻青岛市第三人民医院</div>
                        <div class="txt">万物向新,蓄势而生。5月29日，深圳市巨融医疗科技有限公司苏州分公司正式落地...</div>
                    </div>
                </div>
                <div class="item white">
                    <div class="img"></div>
                    <div class="info">
                        <div class="meta">
                            <span class="date">2025.10.28</span>
                            <span class="tag">公司新闻</span>
                        </div>
                        <div class="tit">全国布局再落一子!巨融医疗苏州分公司正式落地</div>
                        <div class="txt">万物向新,蓄势而生。5月29日，深圳市巨融医疗科技有限公司苏州分公司正式落地...</div>
                    </div>
                </div>
                <div class="item gray">
                    <div class="listScroll">
                        <div class="scrollItem">
                            <div class="meta">
                                <span class="date">2025.10.28</span>
                                <span class="tag">公司新闻</span>
                            </div>
                            <div class="tit">巨融医疗产品亮相2021深圳市医学会年乳腺学组学术年会</div>
                        </div>
                        <div class="line"></div>
                        <div class="scrollItem">
                            <div class="meta">
                                <span class="date">2025.10.28</span>
                                <span class="tag">公司新闻</span>
                            </div>
                            <div class="tit">巨融医疗助力内蒙古自治区巴彦淖尔市临河区人民医院放射科室建设</div>
                        </div>
                        <div class="line"></div>
                        <div class="scrollItem">
                            <div class="meta">
                                <span class="date">2025.10.28</span>
                                <span class="tag">公司新闻</span>
                            </div>
                            <div class="tit">巨融医疗科技新品闪耀邵阳市医学会放射学专业委员</div>
                        </div>
                        <div class="line"></div>
                        <div class="scrollItem">
                            <div class="meta">
                                <span class="date">2025.10.28</span>
                                <span class="tag">公司新闻</span>
                            </div>
                            <div class="tit">共庆妇女节，致敬"她力量"</div>
                        </div>
                    </div>
                </div>
            </div>
            <div class="btn">
                <span>了解详细</span>
                <div class="icon"></div>
            </div>
        </section>
    </div>
    <style>
        /* 模块布局 */
        .No000Wrap{padding: 100px 0 127px 0;--titleSize: 0.36rem;--titleColor: #222;--descSize: 0.3rem;--descColor: #666;--dateSize: 0.26rem;--dateColor: #888;--tagSize: 0.26rem;--tagColor: #222;--titSize: 0.34rem;--titColor: #222;--titHover: #1E64AE;--txtSize: 0.3rem;--txtColor: #666;--btnSize: 0.3rem;--btnColor: #222;--borColor: linear-gradient(90deg, #1E64AE 0%, #2790FF 100%);--cardBor: 10px;}
        
        /* 模块标题样式 */
        #No000Title{display: flex;flex-direction: column;align-items: center;gap: 10px;}
        #No000Title .title{font-size: 50px;font-weight: 500;color: var(--titleColor);line-height: 1.326;}
        #No000Title .desc{font-size: 18px;color: var(--descColor);line-height: 1.667;}
        @media (max-width: 992px) {
            #No000Title .title{font-size: 36px;line-height: 1.326;}
            #No000Title .desc{font-size: 0.3rem;line-height: 1.667;}
        }
        @media (max-width: 768px) {
            #No000Title{padding: 0 0.32rem;}
            #No000Title .title{font-size: var(--titleSize);text-align: center;}
            #No000Title .desc{font-size: var(--descSize);text-align: center;}
        }
        
        /* 模块内容样式 */
        #No000Con{padding: 60px 260px 0 260px;}
        #No000Con .list{display: flex;gap: 40px;}
        #No000Con .item{width: 440px;border-radius: var(--cardBor);padding: 0;display: flex;flex-direction: column;overflow: hidden;}
        #No000Con .item.gray{background: #F6F6F6;}
        #No000Con .item.white{background: #fff;box-shadow: 0 4px 30px 0 rgba(30, 100, 174, 0.2);}
        #No000Con .img{width: 440px;height: 280px;background: #737373;border-radius: var(--cardBor) var(--cardBor) 0 0;}
        #No000Con .info{padding: 30px 40px;display: flex;flex-direction: column;gap: 20px;}
        #No000Con .meta{display: flex;align-items: center;gap: 10px;}
        #No000Con .date{font-size: 16px;color: var(--dateColor);line-height: 1.5;}
        #No000Con .tag{font-size: 16px;color: var(--tagColor);line-height: 1.5;}
        #No000Con .tit{font-size: 24px;font-weight: 500;color: var(--titColor);line-height: 1.5;height: 80px;overflow: hidden;}
        #No000Con .txt{font-size: 18px;color: var(--txtColor);line-height: 1.667;height: 59px;overflow: hidden;opacity: 0.88;}
        #No000Con .listScroll{padding: 40px;height: 470px;overflow-y: auto;display: flex;flex-direction: column;gap: 20px;}
        #No000Con .scrollItem{display: flex;flex-direction: column;gap: 10px;}
        #No000Con .scrollItem .tit{font-size: 18px;font-weight: 400;height: auto;}
        #No000Con .line{width: 100%;height: 1px;background: #D9D9D9;}
        #No000Con .btn{margin: 60px auto 0 0;display: flex;align-items: center;gap: 10px;padding: 10px 30px;border-radius: 99px;border: 2px solid var(--borColor);background: transparent;cursor: pointer;width: fit-content;}
        #No000Con .btn span{font-size: 18px;font-weight: 500;color: var(--btnColor);line-height: 1.667;}
        #No000Con .icon{width: 16px;height: 16px;background: linear-gradient(90deg, #1E64AE 0%, #2790FF 100%);clip-path: polygon(0 0, 40% 0, 40% 40%, 100% 40%, 100% 60%, 40% 60%, 40% 100%, 0 100%);}
        @media(any-hover: hover){
            #No000Con .btn:hover{background: var(--borColor);}
            #No000Con .btn:hover span{color: #fff;}
            #No000Con .btn:hover .icon{background: #fff;}
            #No000Con .item.white:hover{transform: translateY(-5px);transition: transform 0.3s ease;}
            #No000Con .item.gray:hover{transform: translateY(-5px);transition: transform 0.3s ease;}
            #No000Con .scrollItem:hover .tit{color: var(--titHover);transition: color 0.3s ease;}
        }
        @media (max-width: 992px) {
            #No000Con{padding: 0.6rem 0 0 0;}
            #No000Con .list{flex-wrap: wrap;gap: 0.4rem;}
            #No000Con .item{width: 4.4rem;}
            #No000Con .img{width: 4.4rem;height: 2.8rem;}
            #No000Con .tit{font-size: 22px;height: auto;}
            #No000Con .txt{font-size: 0.3rem;height: auto;}
            #No000Con .btn{margin: 0.6rem auto 0 auto;}
        }
        @media (max-width: 768px) {
            #No000Con{padding: 0.5rem 0 0 0;}
            #No000Con .list{gap: 0.3rem;}
            #No000Con .item{width: 100%;padding: 0;}
            #No000Con .img{width: 100%;height: 4.8rem;}
            #No000Con .info{padding: 0.4rem;gap: 0.3rem;}
            #No000Con .date{font-size: var(--dateSize);}
            #No000Con .tag{font-size: var(--tagSize);}
            #No000Con .tit{font-size: var(--titSize);height: auto;}
            #No000Con .txt{font-size: var(--txtSize);height: auto;}
            #No000Con .listScroll{height: auto;max-height: 6rem;padding: 0.4rem;}
            #No000Con .scrollItem .tit{font-size: var(--descSize);}
            #No000Con .btn{margin: 0.5rem auto 0 auto;padding: 0.2rem 0.6rem;}
            #No000Con .btn span{font-size: var(--btnSize);}
        }
    </style>
</body>
</html>

```

## 总结
以上就是对【使用工具通过CodeBuddy，将Figma原型图自动转化为前端代码(MCP)】初使用的反馈，使用这个方法是可以较完美的把设计稿转为前端代码，但是缺点就是大小都是px固定的需要我们自己去转换位百分百，但是对于一些简单的样式还是很有帮助的