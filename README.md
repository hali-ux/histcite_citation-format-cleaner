# histcite_citation-format-cleaner（histcite使用的Plain Text File格式清洗程序）

你好！👋  
这是一个小巧实用的 Python 小工具，帮助你把从 Web of Science 导出的 textplain 文本“清洗 / 重排”为 HistCite 能识别的格式，方便直接导入 HistCite 做文献综述或学术计量学研究。

Hello! 👋  
This is a small and handy Python tool that cleans and reorders Web of Science textplain exports so they match HistCite's expected format. It's useful if you want to import WOS exports into HistCite for citation analysis or bibliometric work.

---

## 为什么会有这个工具？ / Why this tool?  
- Web of Science 导出的 Plain Text File 与 HistCite 期望的字段顺序和标签不完全一致。  
- 本工具会自动：  
  - 去掉 HistCite 不支持的字段；  
  - 补全 HistCite 需要但缺失的标签（用占位文字标注）；  
  - 按 HistCite 常用的字段顺序重排记录；  
  - 以 Windows ANSI (mbcs) 编码保存，便于在 Windows 上的 HistCite 中打开。

- Web of Science textplain exports don't always match HistCite's field order and supported tags.  
- This tool will automatically:  
  - remove tags unsupported by HistCite;  
  - auto-complete missing required tags with placeholders;  
  - reorder fields into a HistCite-friendly sequence;  
  - save output in Windows ANSI (mbcs) encoding for easier opening in HistCite on Windows.

---

## 功能亮点 / Features  
- 自动识别并移除不支持的标签（例如 D3、DA、CL、BN、RI、OI）。  
- 自动补齐常见缺失的会议信息标签（CT、CY、SP 等）。  
- 按 HistCite 常用的老版 WOS 字段顺序重排（兼容 HistCite 导入）。  
- 批量处理 input 文件夹内的多个 .txt，生成 savedrecs1.txt、savedrecs2.txt … 以供 HistCite 导入。  
- 输出使用 Windows ANSI (mbcs) 编码，提升 Windows 下兼容性。

- Removes unsupported tags (e.g. D3, DA, CL, BN, RI, OI).  
- Auto-fills common missing conference tags (CT, CY, SP, etc.).  
- Reorders records according to a HistCite-friendly WOS core field sequence.  
- Batch processes multiple .txt files in an input folder and outputs savedrecs1.txt, savedrecs2.txt, … for HistCite.  
- Outputs in Windows ANSI (mbcs) encoding for better Windows compatibility.

---

## 快速上手 / Quick start  
1. 把要处理的 .txt 文件放到脚本中指定的 input 文件夹（或修改脚本顶部的 input_folder 路径）。  
2. 修改脚本顶部的 input_folder / output_folder 为你的实际路径。  
3. 在命令行运行脚本：  
   - python "textplain清洗主程序.py"  
4. 在 output 文件夹里得到 savedrecs1.txt、savedrecs2.txt …，这些文件可以直接导入 HistCite。

1. Put the .txt files you want to process into the input folder referenced at the top of the script (or update the input_folder path).  
2. Set input_folder / output_folder to your actual paths in the script.  
3. Run the script:  
   - python "textplain清洗主程序.py"  
4. Find savedrecs1.txt, savedrecs2.txt, … in the output folder — ready to import into HistCite.

示例（Windows PowerShell）：  
- python .\textplain清洗主程序.py

Example (Windows PowerShell):  
- python .\textplain清洗主程序.py

---

## 注意事项 / Notes  
- 脚本默认会移除某些字段（D3、DA、CL、BN、RI、OI），因为这些并非 HistCite 所需或支持。  
- 输出为 ANSI (mbcs)：这是为了与 Windows 上的 HistCite 更好兼容；如果你需要 UTF-8，可以修改脚本中写文件时的 encoding 参数。  
- 不同版本的 WOS 导出偶尔会有差异；如果遇到解析/兼容问题，欢迎提交样例给我以便改进。

- The script removes certain fields by default (D3, DA, CL, BN, RI, OI) because they are not required/supported by HistCite.  
- Output is ANSI (mbcs) for Windows HistCite compatibility. Change the file write encoding in the script if you need UTF-8.  
- WOS export formats can differ between versions. If you encounter parsing or compatibility issues, please share a sample so we can improve the tool.

---

## 想改进 / Contribute or give feedback  
非常欢迎任何 issue、建议或 PR。想要增加功能（比如导出 CSV、GUI 支持、多种编码选项、更多兼容性处理），都可以通过 GitHub 提交 issue 或 PR。

Contributions, issues, and PRs are warmly welcome — whether it's CSV export, a GUI, multiple encoding options, or broader compatibility fixes.

---

## 联系方式 / Contact  
作者邮箱：wsw123467w123467@outlook.com

Author contact: wsw123467w123467@outlook.com

---

##Histcite多平台使用的可能 /The Possibility of Multi-Platform Use of Histcite

本程序主要针对windows平台的histcite辅助使用，同时yangnim21029编写了MAC的histcite
The program mainly focus on histcite on windows platform, meanwhile yangnim21029 had coded the hiscite on mac os
“支持 macOS 13 及以上、Apple Silicon 与 Intel，可在本机导入 Web of Science 完整记录与引用文献的 TXT 导出文件、计算 LCS／GCS 并绘制引文网络，免费开源。”
"relying on macOS 13 or upon, Apple Silicon and Intel, which can input the full records of WOS and  output the TXT of citation, calculating LCS/GCS and drawing the  citation network.Free and open source. 
但是演示视频是采用设定好的演示文本，文本字段与当前环境下的WOS导出的文本字段有着些许差别，此程序能否直接使用，是否可以实现本程序的提前清洗，由于本人身边没有MAC设备无法进行测试，欢迎感兴趣的朋友进行测试，也欢迎给我们两个人进行反馈
But the demo video uses preset demo text, and the text word are slightly different from the text word exported from WOS in the current environment.
Can this program be used directly, and is it possible to perform pre-cleaning with this program? I don't have a MAC device to test it.Welcome to try it out and provide feedback to the two of us.
