# Voxlet wheels

The [Voxlet](https://voxlet-app.vercel.app) Mac app (formerly Voice Clone Kit) downloads these two prebuilt Python wheels when it installs its optional training engine (GPT-SoVITS). With them, the app doesn't have to compile the packages on each Mac, which would need Apple's Command Line Tools.

This repository holds only these build outputs. The app's source isn't here.

| Wheel | Upstream | Licence |
| --- | --- | --- |
| `pyopenjtalk-0.4.1-cp310-cp310-macosx_14_0_arm64.whl` | [r9y9/pyopenjtalk](https://github.com/r9y9/pyopenjtalk) | MIT. The wheel also contains compiled code from Open JTalk, MeCab and the HTS Engine API, each under its own BSD-style licence; see the upstream repository. |
| `jieba_fast-0.53-cp310-cp310-macosx_14_0_arm64.whl` | [deepcs233/jieba_fast](https://github.com/deepcs233/jieba_fast) | MIT |

## How they were built

They are the PyPI source releases `pyopenjtalk==0.4.1` and `jieba-fast==0.53`, unmodified, built with `pip wheel --no-deps`. Build settings: CPython 3.10.22, `MACOSX_DEPLOYMENT_TARGET=14.0`, macOS on Apple Silicon.

The files are in the [`engine-wheels-1`](../../releases/tag/engine-wheels-1) release, together with `SHA256SUMS`. The app checks every download against these hashes:

```
9966f4b6939d6dffc6dfcbbb7553a80217edbdfe04e6c754164b9886d169b50a  jieba_fast-0.53-cp310-cp310-macosx_14_0_arm64.whl
85573598b425f5d7e2b441cacdd1132cb9502e32f4d80c18211fa2f2e68bd529  pyopenjtalk-0.4.1-cp310-cp310-macosx_14_0_arm64.whl
```
