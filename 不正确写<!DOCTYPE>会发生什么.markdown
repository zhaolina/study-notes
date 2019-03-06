> 前言

最近在重构项目，发现同样的组件库 antd，新旧项目的 Table 字体大小不一样

> 坑

最后定位发现，是因为旧项目的 html 的 <!DOCTYPE> 写的并不标准，标准的 DOCTYPE 应该是

````<!DOCTYPE html>````

后面这个 html 十分重要，如果忽略不写

浏览器就会加载它的默认样式，在开发者工具里展示 user agent stylesheet

震惊～

看来是基本功太不扎实了...