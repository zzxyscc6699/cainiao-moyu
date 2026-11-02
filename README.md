# Quantumult X 去广告规则

自用规则集合。规则源自 [@ddgksf2013](https://github.com/ddgksf2013)，脚本已本地化到本仓库，不依赖任何第三方仓库。

## 规则列表

| 应用 | 规则文件 | 依赖脚本 | 状态 |
| :--- | :--- | :--- | :--- |
| 菜鸟 | [`CainiaoAds.conf`](./CainiaoAds.conf) | `amdc.js`<br>`cainiao_json.js` | 可用 |
| 网易邮箱大师 | [`NeteaseMailAds.conf`](./NeteaseMailAds.conf) | 无 | 可用 |
| 喜马拉雅 | [`Ximalaya.conf`](./Ximalaya.conf) | `ximalaya.js` | 可用 |
| 哈啰单车 | [`HelloBike.conf`](./HelloBike.conf) | `easybike-ad.js` | 可用 |
| 美团 | [`MT.conf`](./MT.conf)<br>[`MT.list`](./MT.list) | `MT.js` | 可用 |
| 什么值得买 | [`SmzdmAds.conf`](./SmzdmAds.conf) | `smzdm_json.js` | 可用 |
| 高德地图 | [`AmapAds.conf`](./AmapAds.conf) | `amap.js`<br>`amdc.js` | 可用 |
| 12306 | [`12306.conf`](./12306.conf)<br>[`12306.list`](./12306.list) | `12306.js` | 可用 |
| 酷安 | [`Coolapk.conf`](./Coolapk.conf) | `coolapk.js` | 可用 |

## 订阅地址

菜鸟：

```
https://cdn.jsdelivr.net/gh/zzxyscc6699/cainiao-moyu@master/CainiaoAds.conf
```

网易邮箱大师：

```
https://cdn.jsdelivr.net/gh/zzxyscc6699/cainiao-moyu@master/NeteaseMailAds.conf
```

喜马拉雅：

```
https://cdn.jsdelivr.net/gh/zzxyscc6699/cainiao-moyu@master/Ximalaya.conf
```

哈啰单车：

```
https://cdn.jsdelivr.net/gh/zzxyscc6699/cainiao-moyu@master/HelloBike.conf
```

美团（需要加两条，重写 + 分流）：

```
https://cdn.jsdelivr.net/gh/zzxyscc6699/cainiao-moyu@master/MT.conf
https://cdn.jsdelivr.net/gh/zzxyscc6699/cainiao-moyu@master/MT.list
```

什么值得买：

```
https://cdn.jsdelivr.net/gh/zzxyscc6699/cainiao-moyu@master/SmzdmAds.conf
```

高德地图：

```
https://cdn.jsdelivr.net/gh/zzxyscc6699/cainiao-moyu@master/AmapAds.conf
```

12306（需要加两条，重写 + 分流）：

```
https://cdn.jsdelivr.net/gh/zzxyscc6699/cainiao-moyu@master/12306.conf
https://cdn.jsdelivr.net/gh/zzxyscc6699/cainiao-moyu@master/12306.list
```

酷安：

```
https://cdn.jsdelivr.net/gh/zzxyscc6699/cainiao-moyu@master/Coolapk.conf
```

## 使用方法

1. Quantumult X → 重写 → 引用 → 右上角 `+`
2. 粘贴上面对应的订阅地址
3. 确认「重写」和「MitM」两个开关都已开启
4. 安装并信任 QX 根证书（设置 → 通用 → 关于本机 → 证书信任设置）
5. 卸载并重新安装目标 App（清除本地已缓存的广告素材）

## 文件说明

| 文件 | 类型 | 说明 |
| :--- | :--- | :--- |
| `CainiaoAds.conf` | 规则 | 菜鸟 App 去广告，13 条规则 |
| `amdc.js` | 脚本 | 改写 amdc 返回体，使广告 SDK 取不到素材 |
| `cainiao_json.js` | 脚本 | 裁剪首页推广模块的 JSON 数据 |
| `NeteaseMailAds.conf` | 规则 | 网易邮箱大师去广告，7 条规则 |
| `Ximalaya.conf` | 规则 | 喜马拉雅去广告 + 会员功能调试，10 条规则 |
| `ximalaya.js` | 脚本 | 喜马拉雅接口改写，362 KB |
| `HelloBike.conf` | 规则 | 哈啰单车净化，8 条规则 |
| `easybike-ad.js` | 脚本 | 哈啰接口解密与改写，118 KB |
| `MT.conf` | 规则 | 美团重写规则，10 条 |
| `MT.list` | 分流 | 美团域名与 HTTPDNS IP 拦截，46 条 |
| `MT.js` | 脚本 | 美团接口改写，4.6 KB |
| `SmzdmAds.conf` | 规则 | 什么值得买净化，13 条规则 |
| `smzdm_json.js` | 脚本 | 什么值得买接口 JSON 改写 |
| `AmapAds.conf` | 规则 | 高德地图净化，18 条规则 |
| `amap.js` | 脚本 | 高德地图接口改写 |
| `12306.conf` | 规则 | 12306 去广告，1 条规则 |
| `12306.list` | 分流 | ad.12306.cn 直连，1 条 |
| `12306.js` | 脚本 | 12306 广告接口伪造响应 |
| `Coolapk.conf` | 规则 | 酷安净化，7 条规则 |
| `coolapk.js` | 脚本 | 酷安接口改写（混淆代码） |

## 注意事项

**脚本分发**：脚本通过 jsDelivr CDN 加载，不经过 `github.com`。修改仓库文件后需要手动刷新缓存，否则拉到的还是旧内容：

```
https://purge.jsdelivr.net/gh/zzxyscc6699/cainiao-moyu@master/文件名
```

**版本要求**：`NeteaseMailAds.conf` 中的 `jsonjq-response-body` 需要 Quantumult X 1.5.2 以上版本。

**缓存问题**：拦截规则生效后，App 本地可能仍有旧广告素材缓存，必须卸载重装才能看到效果。

---

规则版权归原作者所有：菜鸟、网易邮箱大师规则来自 [@ddgksf2013](https://github.com/ddgksf2013)，喜马拉雅脚本来自 [WeiGiegie/666](https://github.com/WeiGiegie/666)，哈啰单车、美团规则来自 [ZenmoFeiShi/Qx](https://github.com/ZenmoFeiShi/Qx)。仅供个人学习使用。

## 分流订阅说明

大部分规则只需要加「重写」订阅，但以下规则**同时需要分流**：

| 应用 | 重写订阅 | 分流订阅 |
| :--- | :--- | :--- |
| 美团 | `MT.conf` | `MT.list` |
| 12306 | `12306.conf` | `12306.list` |

分流规则用于拦截广告域名、或把特定域名设为直连（`DIRECT`）。如果只加重写不加分流，可能出现广告拦不干净、或者 App 请求被绕进代理导致异常的情况。
