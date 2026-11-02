# Ecosystem Services Valuation (geoskill-ecosystem-services-valuation)

> Assesses provisioning, regulating, supporting, and cultural ecosystem service values using the equivalent-factor method. Outputs GeoTIFFs of the four service values and a total-value JSON.

---

## 1. Overview

Based on the equivalent-factor table of Xie Gaodi et al. (1 equivalent ≈ national mean grain output value of 3000 CNY/ha/yr): five LULC classes (forest, grassland, cropland, water, and built-up) are first retrieved via NDVI thresholds; the equivalent coefficient per class × service is then multiplied by pixel area to obtain annual value-density rasters and regional totals for the provisioning, regulating, supporting, and cultural services. Use cases: ecological asset accounting, GEP estimation, and calibration of occupation–compensation balance and ecological compensation standards.

## 3. Quick Start

```bash
pip install -r requirements.txt
python geoskill-ecosystem-services-valuation.py --bbox 116 39 117 40 --synthetic --output-dir ./out
```

## 4. CLI Parameters

Run `python <skill>.py --help` for the full list. Common parameters:

| Parameter | Type | Description |
|---|---|---|
| `--bbox` | `float[4]` | WGS84 bounding box `min_lon min_lat max_lon max_lat` |
| `--input` | `path` | Local input file (GeoJSON/GeoTIFF/etc.) |
| `--output-dir` | `path` | Output directory (default `./output`) |
| `--synthetic` | `flag` | Use synthetic data instead of real input |
| `--quiet` | `flag` | Suppress non-essential stdout |

## 5. Input / Output

| File | Format | Description |
|---|---|---|
| `value_provisioning.tif` | GeoTIFF (float32) | Provisioning service value (CNY/yr/pixel) |
| `value_regulating.tif` | GeoTIFF (float32) | Regulating service value (CNY/yr/pixel) |
| `value_supporting.tif` | GeoTIFF (float32) | Supporting service value (CNY/yr/pixel) |
| `value_cultural.tif` | GeoTIFF (float32) | Cultural service value (CNY/yr/pixel) |
| `service_value_params.json` | JSON | Pixel area, total value per service, LULC pixel counts |
| `output-manifest.json` | JSON | Run manifest (inputs/outputs/QA/software versions) |

## 6. Technical Principle

(see SKILL.md for details)

## 8. License

MIT License. See [`LICENSE`](./LICENSE) for full text.

---

> 中文完整版：[references/SKILL.zh-CN.md](references/SKILL.zh-CN.md)
