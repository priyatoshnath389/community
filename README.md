# 🌟 Ultralytics Community Configs

This repository contains community-contributed Ultralytics model configuration files! 🚀

## 🛠️ Usage

To get started with a model config:

1. 📥 Clone the repository:
```bash
git clone https://github.com/Y-T-G/community
```

2. 🔧 Load the config using Ultralytics:

> [!IMPORTANT]  
> ⚠️ Ensure your Ultralytics version meets the `min_version` specified in the YAML file.

```python
from ultralytics import YOLO
model = YOLO("community/cfg/classify/convnext_tiny.yaml")
```

## 🤝 Contribute

We welcome community contributions! 💡 To add your config, please submit a Pull Request following our [CONTRIBUTING](CONTRIBUTING.md) guidelines.

## 📄 License

This project is protected under the GNU Affero General Public License v3.0 (AGPLv3.0). See the [LICENSE](LICENSE) file for complete details. ⚖️