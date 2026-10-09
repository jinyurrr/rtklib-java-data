# rtklib-java-data

RTKLIB Java 独立测试数据仓库，存放超过 2MB 的大文件测试数据。

## 目录结构

`
rinex/       RINEX 观测数据
nav/         RINEX 导航星历
rtcm/        RTCM3 数据流
product/     精密产品 (SP3/CLK/IONEX/ATX/BIA)
reference/   参考解 (.pos)
nmea/        NMEA 数据
config/      配置文件
tle/         TLE 两行根数
`

## 数据来源

| 来源 | 说明 |
|------|------|
| MobileGNSS-SPP | 手机GNSS多场景动态数据（downtown/street/opensky/elevated） |
| Net_Diff | 城市RTK base+rover对 + PPP数据 + 精密产品 |
| GFZ | GBM精密轨道和钟差 |
| IGS | IGS电离层格网 |

## 使用方式

在主仓库 rtklib-java 目录下运行：

```powershell
./test-data/download-test-data.ps1
```

或手动克隆：

```bash
git clone https://github.com/jinyurrr/rtklib-java-data.git test-data-large
```

## 文件命名规范

```
{scenario}_{role}_{date}[_{type}].{ext}
```

每个数据文件附带 `.meta` 元数据文件，包含场景、角色、卫星系统、日期、来源等信息。

## 许可

测试数据仅供研究和测试使用，请遵守原始数据源的许可协议。
