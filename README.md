# rtklib-java-data

RTKLIB Java 独立测试数据仓库，存放超过 2MB 的大文件测试数据。

## 目录结构

```
rinex/       RINEX 观测数据
nav/         RINEX 导航星历
rtcm/        RTCM3 数据流
product/     精密产品 (SP3/CLK/IONEX/ATX/BIA)
reference/   参考解 (.pos)
nmea/        NMEA 数据
config/      配置文件
tle/         TLE 两行根数
```

## 数据场景

| 场景 | 文件 | 系统 | 动态/静态 | 说明 |
|------|------|------|-----------|------|
| 城市峡谷 | downtown_rover_20250408 | G+E+J+C | 动态(~140m) | 手机NLOS/多路径 |
| 街道 | street_rover_20250312 | G+E+J+C | 动态(~250m) | 手机部分遮挡 |
| 开阔地 | opensky_rover_20250408 | G+E+J+C | 动态(~6km) | 手机车载长距离 |
| 城市RTK | urban_base/rover_20000719 | G+E+J+C | 准静态(~3m) | base+rover对+参考解 |
| PPP | ppp_hksl/hkws/wtza/wtzr | G+R+E+C+J+S | 静态/动态 | IGS站+精密产品 |

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

每个数据文件附带 `.meta` 元数据文件。

## License

本仓库测试数据均可自由用于研究和测试。

| 数据类型 | License | 说明 |
|----------|---------|------|
| 手机GNSS数据 | MIT | 可自由使用、修改、分发 |
| 城市RTK/PPP数据 | public | 公开样例数据 |
| IGS精密产品 | IGS Data Policy | 免费用于研究，需引用IGS |
| GFZ精密产品 | IGS Data Policy | 同IGS政策 |

> 精密产品使用时请按IGS数据政策引用相应分析中心。
