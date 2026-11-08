# 🐋 MOON 做庄模拟器 / Whale Market Simulator

**中文** | [English below](#english)

一个纯前端、单文件的加密货币市场微观结构沙盘：你扮演一名"庄家"，在逐档撮合的订单簿上体验完整的坐庄周期——低位隐匿吸筹 → 对敲刷量造热度 → 幌骗挂单造势 → 拉盘引发 FOMO → 高位分批派发（或砸盘插针收割止损与强平）。

> ⚠️ **仅用于教学与研究**：理解市场操纵的机制、以及风控视角下的识别特征。**真实市场操纵违法**。本模拟不构成任何投资建议。

## 特性

- **真实撮合**：价格-时间优先、多档扫单、做市商循环补量、自成交禁止
- **900 个行为智能体**：前景理论、处置效应（随散户流入状态变化）、Brock-Hommes 策略切换、Cont-Bouchaud 羊群、注意力驱动交易（Barber-Odean）
- **文献校准的市场统计**：波动聚集（双时间尺度 GARCH）、杠杆效应、对数正态跳跃、清算级联（次临界分支）、平方根冲击律（Tóth 2011 / Maitrier-Loeper-Bouchaud 2025）
- **庄家工具箱**：市价/限价单、对敲（留痕并触发交易所风控）、三档幌骗墙、永续合约（资金费率+强平引擎）
- **结算面板**：全程事实记录（PGR/PLR、对敲次数、强平数、收益归因），不评分
- **零依赖**：无后端、无追踪、无外部请求；下载 `index.html` 双击即玩，数据全程留在本地

## 本地运行

无任何构建步骤：

```bash
# 方式一：直接双击 index.html
# 方式二：本地起个静态服务
python3 -m http.server 8080
# 打开 http://localhost:8080
```

## 部署

静态单文件，任意静态托管皆可：

- **GitHub Pages**：仓库 → Settings → Pages → Deploy from branch (`main` / `/root`)
- **Cloudflare Pages**：Workers & Pages → Create → Pages → 直接上传 `index.html`，或连接 Git 仓库（构建命令留空，输出目录 `/`）

## 校准与文献

市场参数全部有文献出处（微结构/ABM、加密操纵实证、行为参数三份审查，155+ 篇），
见 [`out/FINAL-CALIBRATION-REPORT.md`](../out/FINAL-CALIBRATION-REPORT.md)（综合校准报告，含参数溯源表与已知取舍声明）。

## License

MIT

---

<a name="english"></a>
# 🐋 MOON Whale Market Simulator (English)

A single-file, zero-dependency crypto market microstructure sandbox. You play the "whale": quietly accumulate at the lows → wash-trade for volume/heat → spoof walls for momentum → pump to ignite FOMO → distribute into the crowd (or flash-crash to hunt stops and liquidations).

> ⚠️ **For education and research only**: understand how manipulation works and how it looks from a risk-control perspective. **Market manipulation is illegal in real markets.** Not investment advice.

**Highlights**: price-time priority order book with multi-level sweeps · 900 behavioral agents (prospect theory, disposition effect, herding, attention-driven trading) · literature-calibrated stylized facts (volatility clustering, leverage effect, jump/cascade tails, square-root impact law) · whale toolbox (wash trades with exchange-detection risk, spoofing, perps with funding & liquidations) · facts-only settlement panel. No backend, no tracking, no network calls — everything runs locally in your browser.

**Run locally**: double-click `index.html`, or `python3 -m http.server 8080`.
**Deploy**: GitHub Pages (deploy from branch) or Cloudflare Pages (upload `index.html`, no build command, output dir `/`).
