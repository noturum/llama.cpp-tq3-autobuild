# llama.cpp-tq3 Autobuild

Pre-built binaries of [llama.cpp-tq3](https://github.com/turbo-tan/llama.cpp-tq3) for Windows x64 with CUDA support.

This repo provides a GitHub Actions workflow that automatically builds `llama.cpp-tq3` (a llama.cpp fork with TQ3 quantization support) from the upstream source. No source code is stored here -- only the CI workflow that fetches, builds, and packages the binaries.

## Usage

1. Go to the **Actions** tab of this repository
2. Select **"Build llama.cpp-tq3 (Windows CUDA)"**
3. Click **"Run workflow"**
4. Configure build options:
   - **CUDA version**: 12.1 through 13.0 (default: 12.8)
   - **Build type**: Release or RelWithDebInfo
   - **CUDA architectures**: Semicolon-separated list (default: 52;61;75;80;86;89;90)
5. Wait for the build to finish
6. Download the zipped artifact from the workflow run page

## Build Matrix

| Component | Status |
|-----------|--------|
| Platform  | Windows x64 (amd64) |
| CUDA      | 12.x, 13.x |
| Compiler  | MSVC (Visual Studio 2022) |
| Generator | Ninja |
| Linkage   | Shared (.dll + .lib) |

## Included Binaries

The archive contains:
- `llama-cli.exe` - CLI tool for inference
- `llama-server.exe` - OpenAI-compatible HTTP server
- `llama-bench.exe` - Performance benchmark tool
- `llama-perplexity.exe` - Perplexity measurement
- `llama-quantize.exe` - Model quantization
- `llama-tokenize.exe` - Tokenizer utility
- `llama-*.exe` - Other utility tools
- `llama.dll` / `llama.lib` - Runtime library
- CUDA runtime DLLs (cudart, cublas, etc.)

## Upstream

- Source: https://github.com/turbo-tan/llama.cpp-tq3
- TQ3 model: https://huggingface.co/YTan2000/Qwopus3.6-27B-v2-TQ3_4S
