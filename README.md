# Quantumult X 去广告规则

自用规则集合。规则源自 [@ddgksf2013](https://github.com/ddgksf2013)，脚本已本地化到本仓库，不依赖任何第三方仓库。

## 规则列表

| 应用 | 规则文件 | 依赖脚本 | 状态 |
| :--- | :--- | :--- | :--- |
| 菜鸟 | [`CainiaoAds.conf`](./CainiaoAds.conf) | `amdc.js`<br>`cainiao_json.js` | 可用 |
| 网易邮箱大师 | [`NeteaseMailAds.conf`](./NeteaseMailAds.conf) | 无 | 可用 |

## 订阅地址

菜鸟：

```
https://cdn.jsdelivr.net/gh/zzxyscc6699/cainiao-moyu@master/CainiaoAds.conf
```

网易邮箱大师：

```
https://cdn.jsdelivr.net/gh/zzxyscc6699/cainiao-moyu@master/NeteaseMailAds.conf
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

## 注意事项

**脚本分发**：脚本通过 jsDelivr CDN 加载，不经过 `github.com`。修改仓库文件后需要手动刷新缓存，否则拉到的还是旧内容：

```
https://purge.jsdelivr.net/gh/zzxyscc6699/cainiao-moyu@master/文件名
```

**版本要求**：`NeteaseMailAds.conf` 中的 `jsonjq-response-body` 需要 Quantumult X 1.5.2 以上版本。

**缓存问题**：拦截规则生效后，App 本地可能仍有旧广告素材缓存，必须卸载重装才能看到效果。

---

规则版权归原作者 [@ddgksf2013](https://github.com/ddgksf2013) 所有，仅供个人学习使用。
