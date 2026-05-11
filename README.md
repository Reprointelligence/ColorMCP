<h3 align="center">Precision Color Science &amp; Print Calibration for Every AI and Machine</h3>

<p align="center">
  <a href="https://colormcp.colorcontrol.ai"><img src="https://img.shields.io/badge/Live%20Server-colormcp.colorcontrol.ai-6c63ff?style=flat-square&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHBhdGggZmlsbD0id2hpdGUiIGQ9Ik0xMiAyQzYuNDggMiAyIDYuNDggMiAxMnM0LjQ4IDEwIDEwIDEwIDEwLTQuNDggMTAtMTBTMTcuNTIgMiAxMiAyem0tMSAxNy45M1Y0LjA3YzMuOTQuNDkgNyAzLjg1IDcgNy45M3MtMy4wNiA3LjQ0LTcgNy45M3oiLz48L3N2Zz4=" alt="Live Server"></a>
  <a href="https://www.reprointelligence.com/products/colormcp-color-management-ai-assistant/"><img src="https://img.shields.io/badge/Product%20Page-Reprointelligence-3ecfcf?style=flat-square" alt="Product Page"></a>
  <img src="https://img.shields.io/badge/Protocol-MCP%201.0-f7c26c?style=flat-square" alt="MCP">
  <img src="https://img.shields.io/badge/Tools-65%2B-6c63ff?style=flat-square" alt="Tools">
  <img src="https://img.shields.io/badge/Free%20Tier-Available-3ecfcf?style=flat-square" alt="Free">
  <img src="https://img.shields.io/badge/Built%20with-Go-00ADD8?style=flat-square&logo=go" alt="Go">
</p>

<p align="center">
  <a href="https://colormcp.colorcontrol.ai"><strong>Live Demo &amp; Chat</strong></a> ·
  <a href="https://www.reprointelligence.com/products/colormcp-color-management-ai-assistant/"><strong>Product Page</strong></a> ·
  <a href="#-quick-start">Quick Start</a> ·
  <a href="#-tools">Tools</a> ·
  <a href="#-integrations">Integrations</a>
</p>

---

## The Problem

Color science is hard to get right. CIELAB conversions, DeltaE calculations, ICC profile lookups, Colorimetrically accurate press calibration — these require verified implementations of CIE, ISO, and ANSI standards. An LLM explaining or approximating the math will give you something that *looks* correct but rarely *is*.

ColorMCP solves this by giving your AI **live access to 65+ precision-verified color and print calibration tools** via the [Model Context Protocol (MCP)](https://modelcontextprotocol.io). Your AI asks the tool. The tool computes. The answer is exact.

---

## What is ColorMCP?

ColorMCP is a **free and powerful MCP server** purpose-built for color science and print calibration. It exposes a rich set of tools — covering color space conversions, ΔE formulas, chromatic adaptation, ICC profile lookups, CGATS TR015 press calibration, and more — to any MCP-capable AI client.

The underlying implementations are based on:
- **CIE** international colorimetric standards
- **ISO 12647-2** and **CGATS TR015** press calibration
- **ANSI** and **DIN** standards (DIN99, DIN99b/c/d)
- **Reprointelligence's own** research and commercial-grade color management developments

> ColorMCP is a **computation engine, not a teacher.** When your AI invokes a ColorMCP tool, it receives a verified result — not an LLM approximation.

---

## Who is it for?

| Audience | Use Case |
|---|---|
| **Print engineers & press operators** | Colorimetric Gray / CGATS TR015 gray balance calibration, TVI analysis, colorimetric press targets |
| **Prepress & color management professionals** | ICC profile lookups, Lab↔CMYK workflow checks, rendering intent decisions |
| **Color scientists & researchers** | CIE-correct Lab/XYZ/LCH/CAM conversions, ΔE2000, chromatic adaptation |
| **AI/LLM developers** | Add reliable, standards-based color reasoning to any MCP-capable agent |
| **Software & RIP developers** | OEM integration for AI-assisted color workflows, press calibration automation |

---

## Tools at a Glance

ColorMCP exposes **70 tools** across the following domains:

### Color Space Conversions

| Tool | Description |
|---|---|
| `rgb_to_cielab` | sRGB → CIELAB D50 (ICC printing standard, Bradford D65→D50) |
| `cielab_to_rgb` | CIELAB D50 → sRGB |
| `rgb_to_cielab_d65` | sRGB → CIELAB D65 (screen/display, no adaptation) |
| `xyz_to_cielab` | XYZ → CIELAB D50 |
| `xyz_to_cielab_d65` | XYZ D65 → CIELAB D65 |
| `cielab_d50_to_xyz` | CIELAB D50 → XYZ |
| `cielab_d65_to_xyz` | CIELAB D65 → XYZ |
| `cielab_to_cielch` | CIELAB → CIELCH (L*, C*, H°) |
| `cielch_to_cielab` | CIELCH → CIELAB |
| `cielab_d50_to_d65` | CIELAB D50 → CIELAB D65 (Bradford) |
| `cielab_d65_to_d50` | CIELAB D65 → CIELAB D50 (Bradford) |
| `hex_to_rgb` | CSS hex → sRGB (0–255) |
| `rgb_to_hex` | sRGB → CSS hex |
| `rgb_to_hsl` | sRGB → HSL |
| `hsl_to_rgb` | HSL → sRGB |
| `xyz_to_xyy` | XYZ → CIE xyY |
| `xyy_to_xyz` | CIE xyY → XYZ |
| `xyz_to_luv` | XYZ D50 → CIELUV (L*u*v*) |
| `luv_to_xyz` | CIELUV → XYZ |
| `luv_to_lchuv` | CIELUV → CIELCH_uv |
| `lchuv_to_luv` | CIELCH_uv → CIELUV |
| `xyz_to_jzazbz` | XYZ D65 → JzAzBz (HDR/WCG perceptual space) |
| `jzazbz_to_xyz` | JzAzBz → XYZ D65 |
| `color_conversion_path` | Recipe guide — returns the exact tool chain for any conversion path |

### DIN99 Color Spaces

| Tool | Description |
|---|---|
| `cielab_to_din99` | CIELAB → DIN99 (original, 16° rotation, DIN 6176) |
| `din99_to_cielab` | DIN99 → CIELAB |
| `cielab_to_din99b` | CIELAB → DIN99b (26° rotation) |
| `din99b_to_cielab` | DIN99b → CIELAB |
| `cielab_to_din99c` | CIELAB → DIN99c (0° rotation, improved blue region) |
| `din99c_to_cielab` | DIN99c → CIELAB |
| `cielab_to_din99d` | CIELAB → DIN99d (50° rotation, best blue uniformity) |
| `din99d_to_cielab` | DIN99d → CIELAB |
| `cielab_to_din99o` | CIELAB → DIN99o (optimised, most perceptually uniform) |
| `din99o_to_cielab` | DIN99o → CIELAB |

### Delta E & Color Difference

| Tool | Description |
|---|---|
| `deltae76` | ΔE*76 (CIE 1976) — Euclidean CIELAB distance |
| `deltae94` | ΔE*94 (CIE 1994) — graphic arts parameters |
| `deltae2000` | ΔE*00 (CIEDE2000) — most accurate CIE formula |
| `din99_deltae` | ΔE in DIN99 space from DIN99 coordinates |
| `cielab_deltae_din99` | ΔE DIN99 from CIELAB input (original) |
| `cielab_deltae_din99b` | ΔE DIN99b from CIELAB input |
| `cielab_deltae_din99c` | ΔE DIN99c from CIELAB input |
| `cielab_deltae_din99d` | ΔE DIN99d from CIELAB input |
| `cielab_deltae_din99o` | ΔE DIN99o from CIELAB input (perceptually most uniform) |

### Color Temperature & Illuminants

| Tool | Description |
|---|---|
| `xyz_to_cct` | XYZ → CCT in Kelvin (Robertson 1968) |
| `cct_to_xyz` | CCT → XYZ via Planck radiation + CIE 1931 CMFs |
| `cct_to_cielab_d65` | CCT → CIELAB D65 |
| `cct_to_cielab_d50` | CCT → CIELAB D50 |
| `daylight_illuminant_to_xyz` | CIE daylight illuminant (S0/S1/S2) → XYZ (4000–25000 K) |
| `daylight_illuminant_to_cielab_d65` | CIE daylight → CIELAB D65 |
| `daylight_illuminant_to_cielab_d50` | CIE daylight → CIELAB D50 |

### Color Appearance Models

| Tool | Description |
|---|---|
| `xyz_to_ciecam16` | XYZ D65 → CIECAM16 (J, C, h, M, s, Q, H) |
| `xyz_to_ciecam02` | XYZ D65 → CIECAM02 + CAM02-UCS (J', a', b') |

### ICC Profiles

| Tool | Description |
|---|---|
| `icc_lookup_a2b` | Forward ICC lookup: device values → CIELAB (A→B table) |
| `icc_lookup_b2a` | Inverse ICC lookup: CIELAB → device values (B→A table) |
| `list_icc_output_profiles` | List all available ICC output profiles by channel count |

### Press Calibration (CGATS TR015 / ISO 12647)

| Tool | Description |
|---|---|
| `colorimetric_calibration` | Unified CMYK/RGB/Spot colorimetric press calibration via ICC — primary calibration tool |
| `press_calibration` | TTVP-S / ISO 12647 RIP linearisation corrections (single channel) |
| `press_calibration_cmyk` | TTVP-S corrections for all four CMYK channels in one call |
| `press_printing_standard` | TTVI50 aims + colorimetric Lab reference for named printing standards |
| `press_standard_reference_table` | Full TTVP-S reference curve across all tone steps for a standard and channel |
| `ttvps_target` | TTVP-S target printed area for a given digital setpoint and TTVI50 |
| `rltv_spot_color` | RLTV colorimetric area coverage for spot colors and ECG/EXG channels |
| `cgats_tr015_workflow` | Step-by-step CGATS TR015 calibration workflow guide |
| `cgats_tr015_calibration` | Full CGATS TR015 calibration run from measured patch data |
| `cgats_tr015_npdc_targets` | CGATS TR015 NPDC aim table for CMY and K channels |
| `cgats_tr015_gray_balance_cmy_compositions` | CGATS TR015 CMY gray balance triplets per Equation 1 |
| `press_calibration_strategy` | Expert knowledge: G7/CGATS TR015, TVI/ISO, digital — theory and comparison |

### Scientific Calculator

| Tool | Description |
|---|---|
| `scientific_calculator` | Batch arithmetic expressions with variables, functions, and constants |

### Server Info

| Tool | Description |
|---|---|
| `about` | Authorship, version, and support information |
| `colormcp_about` | Background, expertise, and purpose of ColorMCP |

---

## Try it — No Setup Required

### Interactive Demo Chat

Visit **[colormcp.colorcontrol.ai](https://colormcp.colorcontrol.ai)** and click **Chat Demo** — a live AI assistant with full access to all ColorMCP tools. Ask it to:

- *"Convert Lab [55, 10, −20] to RGB"*
- *"What's the ΔE 2000 between [50, 5, −10] and [52, 3, −8]?"*
- *"Colorimetric press calibration — GRACoL2006, substrate Lab 90 1.5 0.2, patches at 25/50/75%…"*

No account. No API key. Just ask.

### Try It Out (API)

The landing page also includes an interactive **Try It Out** panel where you can call any tool directly from your browser and inspect the raw JSON response.

---

## Quick Start

### Connect via MCP endpoint

```
https://colormcp.colorcontrol.ai/free
```

This is a standard **HTTP+SSE MCP endpoint**. No authentication required for the free tier.

### Claude Desktop

```json
{
  "mcpServers": {
    "colormcp": {
      "command": "npx",
      "args": ["-y", "mcp-remote", "https://colormcp.colorcontrol.ai/free"]
    }
  }
}
```

### Cursor / Windsurf

Add to your MCP settings:

```json
{
  "colormcp": {
    "serverUrl": "https://colormcp.colorcontrol.ai/free"
  }
}
```

### Any MCP-compatible client

Point your client to `https://colormcp.colorcontrol.ai/free` — ColorMCP speaks standard MCP 1.0 over HTTP+SSE. No plugins, no custom installs, no API keys.

---

## Integrations

ColorMCP works out of the box with any MCP-capable client:

| Client | Status |
|---|---|
| Claude Desktop | Supported |
| Cursor | Supported |
| Windsurf | Supported |
| Continue.dev | Supported |
| LibreChat | Supported |
| Any MCP 1.0 client | Supported |

> **Recommended:** Models with 27B+ parameters and verified tool-calling support. A minimum 24k token context window is advised for complex multi-step calibration workflows.

---

## Free Tier

The free tier is available to everyone — individuals, researchers, and non-commercial projects — with no registration required.

Organisations using ColorMCP in a commercial context exceeding **50,000 API requests per year** are required to obtain a commercial licence. [Contact us](https://www.reprointelligence.com/contact-us/) if you're unsure whether your use qualifies.

---

## About Reprointelligence

ColorMCP is built and maintained by **[Reprointelligence CY LTD](https://www.reprointelligence.com)** — specialists in AI-supported color management and print process control with decades of experience in press calibration, ICC profiling, and color science software.

Need expert support for print workflows, ICC profiling, press calibration, or custom color software integration? [Get in touch.](https://www.reprointelligence.com/contact-us/)

---

## License

ColorMCP free tier is provided as-is under Reprointelligence's [Terms of Use](https://colormcp.colorcontrol.ai#terms). All color calculations follow published CIE, ISO, ANSI, and DIN standards.

---

<p align="center">
  <a href="https://www.reprointelligence.com">Reprointelligence CY LTD</a> &mdash; <a href="https://colormcp.colorcontrol.ai">colormcp.colorcontrol.ai</a>
</p>
