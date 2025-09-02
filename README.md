# 🛣️ Distance Calculator

> **Professional distance and duration calculator supporting multiple routing providers with async processing optimized for Google Colab**

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/iamsherman1234/distance-calculator/blob/main/notebooks/distance_calculator_demo.ipynb)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.7+](https://img.shields.io/badge/python-3.7+-blue.svg)](https://www.python.org/downloads/)
[![GitHub stars](https://img.shields.io/github/stars/iamsherman1234/distance-calculator?style=social)](https://github.com/iamsherman1234/distance-calculator/stargazers)

## 🌟 Features

- **🔥 Multiple Routing Providers**: Google Maps, OSRM, OpenRouteService, GraphHopper, HERE Maps, Mapbox, and more
- **⚡ Async Processing**: High-performance concurrent processing with configurable batch sizes
- **🛡️ Pre-configured API Keys**: Ready-to-use with built-in API keys for major providers
- **📊 Smart Data Handling**: Supports CSV, Excel files via upload, URL, or file path
- **🎯 Flexible Usage**: Interactive mode for beginners, simple mode for quick tasks
- **💪 Error Resilience**: Robust error handling and progress tracking
- **📱 Colab Optimized**: Specifically designed for Google Colab environment

## 🚀 Quick Start

### Option 1: Google Colab (Recommended)
Click the badge above to open in Colab and start immediately!

### Option 2: Local Installation
```bash
pip install git+https://github.com/iamsherman1234/distance-calculator.git
```

## 📖 Usage Examples

### Interactive Mode (Beginner-Friendly)
```python
# Guides you through all options step by step
result_df = calculate_distances_interactive()
```

### Quick Mode (Advanced Users)
```python
# Use OSRM (no API key required)
result_df = calculate_distances_simple(provider="OSRM")

# Use Google Maps with custom settings
result_df = calculate_distances_simple(
    provider="Google Maps", 
    api_key="your-api-key",
    batch_size=50,
    max_workers=10
)
```

## 🗂️ Required Data Format

Your CSV/Excel file must contain these columns:
- `str_lat`: Starting latitude
- `str_lon`: Starting longitude  
- `des_lat`: Destination latitude
- `des_lon`: Destination longitude

**Example:**
| str_lat | str_lon | des_lat | des_lon |
|---------|---------|---------|---------|
| 40.7128 | -74.0060| 34.0522 | -118.2437|
| 51.5074 | -0.1278 | 48.8566 | 2.3522   |

## 🌐 Supported Providers

|       Provider        |      API Key      |     Status        |      Features   |
|-----------------------|-------------------|-------------------|------------------|
| **OSRM**              | ❌ Free           | ✅ Public Server  | Fast, no limits   |
| **Google Maps**       | ✅ Pre-configured | ✅ Ready          | High accuracy     |
| **OpenRouteService**  | ✅ Pre-configured | ✅ Ready          | European focus    |
| **GraphHopper**       | ✅ Pre-configured | ✅ Ready          | Flexible routing  |
| **Mapbox OSRM**       | ✅ Pre-configured | ✅ Ready          | Mapbox quality    |
| **HERE Maps**         | 🔑 Bring your own | ⚙️ Configurable   | Enterprise grade  |

## ⚙️ Configuration Options

```python
calc = DistanceCalculator()
result = calc.process_coordinates(
    df,
    provider="Google Maps",     # Choose provider
    batch_size=25,              # Requests per batch
    max_workers=5,              # Concurrent workers
    use_async=True              # Async processing
)
```

## 📊 Output Format

Results include original data plus:
- **Distance**: Route distance in kilometers
- **Duration**: Travel time in minutes

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- Built with [routingpy](https://github.com/gis-ops/routingpy)
- Optimized for Google Colab
- Supports all major routing providers

## 📞 Support

- 🐛 [Report Issues](https://github.com/iamsherman1234/distance-calculator/issues)
- 💬 [Discussions](https://github.com/iamsherman1234/distance-calculator/discussions)
- 📚 [Documentation](docs/)

---
⭐ **Star this repo if it helped you!**
```
