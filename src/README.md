# 4改5场景网元License匹配工具
# Automation tool for software migration between old and new cloud core platforms

CN:支持4改5场景，用于现网CGW/DGW这种老平台网元到UNC/UDG新平台网元的license条目的映射关系。通过上传ESDP系统下载的老旧平台网元的同一份最新license文件的对比表，工具可自行将"Spart"页签的Spart条目自动映射成新平台网元Spart，便于网设人员在CPQ平台快速配置新平台网元对应Spart。
EN:The 4G-to-5G reconstruction scenario is supported, which is used to map the license items of old platform VNFs (such as CGW and DGW) on the live network to those of new platform VNFs (such as UNC and UDG). By uploading the comparison excel of the latest same license file of the old platform VNFs downloaded from the ESDP system, the tool can automatically map the Spart items on the Spart sheet to those of the new platform VNFs. This helps network design personnel quickly configure the corresponding Sparts for the new platform VNFs on the CPQ platform.

## 📁 项目结构 Project Structure
CN: 
4改5 License映射工具/
├── 4改5 License映射工具.exe                # 主运行程序
└── README.md                              # 说明文档(若不存在，请直接读取本文)
└── License映射集 (UNC&UDG) v1.3.xlsx      #  主程序页面运行【上传License映射集】->【选择文件】，选此文件上传。本文件由xuhao 00935646提供并维护。注意，后续或有更新，单元格列名需完全一致。
└── 4改5 Bpart Spart 映射.xlsx             #  主程序页面运行【上传4改5 Bpart Spart 映射】->【选择文件】，选此文件上传。本文件由xuhao 00935646提供并维护。注意，后续或有更新，单元格列名需完全一致。
└── UNClicense对比【参考格式，真实场景请从ESDP获取项目网元对比表】.xlsx                    # 样例，主程序页面运行【现网网元License文件对比表】->【选择文件】，选此文件上传。该文件根据各自实际场景，从ESDP下载需转换的现网实际网元的license对比表。
└── 转换后_NE_UDG【最终结果】.xlsx          # 样例，主程序页面运行【导出映射后的表】->【本地路径】。该文件为程序主页面转换完成后导出的最终参考表的样例。

EN:
4to5 license mapping tool/
├── 4-5 license mapping tool.exe            # Main running program
└── README.md                               # Description document (If the document does not exist, read this document directly.)
└── License Mapping Set (UNC&UDG) v1.3.xlsx # On the main program page, click 【Uploading License Mapping Set】 and select this file to upload. This file is provided and maintained by Xu Hao 00935646. Note that the column names in the Excel must be the same as those in the following updated file.
└── 4-5 Bpart Spart Mapping.xlsx            # On the main program page, click Upload 4-5 Bpart Spart Mapping and select this file to upload. This file is provided and maintained by Xu Hao 00935646. Note that the column names in the Excel must be the same as those in the following updated file.
└── UNClicense对比【参考格式，真实场景请从ESDP获取项目网元对比表】.xlsx  # This is an example. On the main program page, click 【Excel Comparison for current Core NE License Files】 and select this file to upload. You can download the license comparison excel of the real NEs to be converted from ESDP based on the actual scenario.
└── 转换后_NE_UDG【最终结果】.xlsx           # This is an example. On the main program page, click 【Exporting the Mapped Excel】and select the local path. This file is an example of the final reference excel exported after the conversion is complete on the main program page.
```

## 🚀 快速开始 Getting Started Quickly
 
### 1. 运行主程序 Running the main program

方法：解压Zip后双击直接运行 "ESN提取与License自动下载对比工具.exe"（推荐）
Method: After extracting the ZIP file, double-click to directly run "Tool for Comparing ESN Extraction and Automatic License Downloading.exe" (recommended).



### 2. Function specification

#### Main Functions Introduction：

- **一键启动完整流程**
  - 手动执行：运行.exe后，在程序界面选择【选择文件夹】，选取本地解压后的离线健康检查数据包文件夹目录【可选择含网元名称的父级目录】。
  - 自动执行：程序界面自动提取所有该文件夹路径下的所有核心网网元ESN数据，并显示在程序主页面。
  - 手动执行：点击"保存为Excel",程序将在.exe同路径文件夹下自动生成文件：ESN提取结果.xlsx，保存网元名称,ESN数据。
  - 手动执行：点击"启动浏览器自动下载"，页面自动调取个人办公电脑的Chrom浏览器，自动打开ESDP网页。随后，首次使用登录需手动输入华为账号登录ESDP系统。程序运行中，请勿操作或关闭已打开运行的浏览器。程序结束后，会自动关闭浏览器。
  - 自动执行：进入ESDP后，程序会自动根据提取到的ESN数据从ESDP系统，自动下载.xml或.dat的License文件，并自动在ESDP系统直接下载同一份license对比.xlsx文件。该.xlsx文件可用于配置还原参考使用。

- **One-Click Start Complete Process**
- Manual Execution: After running the.exe file, select [Select Folder] on the program interface and select the directory of the offline health check data package folder extracted locally [a parent directory containing the NE name can be selected].
- Automatic Execution: The program interface automatically extracts all ESN data of core network NEs under the specified folder path and displays it on the main program page.
- Manual Execution: Click "Save as Excel," and the program will automatically generate a file named ESN List.xlsx in the same path folder as the.exe file, saving the NE names and ESN data.
- Manual Execution: Click "Start Browser for Automatic Download." The program will automatically invoke the Chrome browser on your personal office computer and open the ESDP webpage. For the first login, you need to manually enter your Huawei account to log in to the ESDP system. During the program's operation, do not perform any operations or close the already opened browser. After the program completes, the browser will automatically close.
- Automatic Execution: After entering the ESDP system, the program will automatically download the.xml or.dat license file from the ESDP system based on the extracted ESN data and automatically download the same license comparison file in.xlsx format directly from the ESDP system. This.xlsx file can be used as a reference for configuration restoration.


## 📋 使用说明operation instructions

### 【选择文件夹】：手动选择本地已解压的离线健康检查数据包文件夹路径
### [Select Folder]: Manually select the path of the decompressed offline health check data package folder on the local computer.



CN:
1. 点击【文件夹选择】
2. 手动选择本地PC需上传文件。当前只支持windows PC环境。
3. 程序界面自动提取该文件夹路径下的ESN数据。
EN:
1. Click [Select Folder].  
2. Manually select the files on the local PC that need to be uploaded. Currently, only Windows PC environments are supported.  
3. The program interface automatically extracts the ESN data from the folder path.

### 【保存为Excel】(可选): 保存页面显示的所有ESN数据信息到本地.exe相同路径
###  [Save as Excel] (Optional): Save all ESN data information displayed on the page to the same local path as the.exe file.
CN:
1. 点击【保存为Excel】，程序将保存页面显示的所有ESN数据信息到本地.exe相同路径，文件名称为："ESN提取结果.xlsx"。
2. 本步骤不是必须执行步骤，可选。若已准备好所有ESN文件或ESN数据不从离线健康检查提取，请直接将已获得的ESN数据保存在.exe文件夹相同路径的"ESN提取结果.xlsx"【可自行新建】中。
3. 可选场景为默认提取.exe程序页面的ESN数据。
EN:
1. Click [Save as Excel], and the program will save all the ESN data information displayed on the page to the same local path as the.exe file, with the file name being "ESN Extraction Results.xlsx".  
2. This step is not mandatory and is optional. If all ESN files are already prepared or the ESN data is not extracted from the offline health check, you can directly save the obtained ESN data into the "ESN Extraction Results.xlsx" file [which can be created by yourself] in the same path as the.exe folder.  
3. The optional scenario is the default extraction of ESN data from the.exe program page.

### 【追加文件夹】【清空表格】(可选): 程序页面追加其他路径离线健康检查数据或清空已选ESN数据
### [Add New Folder] [Clear Table] (Optional): Add offline health check data of other paths to the program page or clear the selected ESN data.
1. 略
1. Skip

### 【启动浏览器自动下载】: 启动调用本地Chrome浏览器登录ESDP页面
### [Start Chrome browser for automatic download]: Launches the local Chrome browser to log in to the ESDP page.



CN:
1. 点击【启动浏览器自动下载】，程序将调用本地Chrome浏览器并自动打开到ESDP网页。
2. 首次登录需人工填入账号信息认证。
3. 程序运行期间，可将浏览器界面最小化或忽略，切勿关闭程序启动打开的浏览器界面，否则程序会中断后续操作。
4. 程序将自动在ESDP网页根据已提取到的ESN数据，自行下载ESN所存在的最新状态为    VALID的license文件.xml和.dat格式。命名格式为ESDP显示网元名称+.xml/.dat后缀。
5. 程序将自动上传license的.xml和.dat格式文件，进行同文件比对，并下载对比结果的.xlsx文件。命名格式为ESDP显示网元名称+_LicenseCompare.xlsx文件。命名格式为ESDP显示网元名称
6. 程序运行完后，会将license文件以及对比结果文件即.xml,.dat,.xlsx文件保存在【最终license对比结果】文件夹中。
EN:
1. Click Start Auto Download in Browser. The program will invoke the local Chrome browser and automatically open the ESDP website.
2. You need to manually enter the account information for authentication upon the first login.
3. During the program running, you can minimize the browser window or ignore it. Do not close the browser window opened by the program. Otherwise, the program will interrupt subsequent operations.
4. The program will automatically download the latest license files in.xml and.dat formats whose status is VALID based on the extracted ESN data from the ESDP website. The file name is in the format of ESN displayed on the ESDP website+.xml/.dat.
5. The program will automatically upload the license files in.xml and.dat formats, compare the files, and download the comparison result file in.xlsx format. The file name is in the format of ESN displayed on the ESDP website+_LicenseCompare.xlsx.
6. After the program is executed, the license files and the comparison result files in.xml,.dat, and.xlsx formats will be saved in the Final License Comparison Result folder.

## ⚙️ 配置要求 Configuration Requirements

### 必需依赖 Required dependencies

```
windows PC支持的Chrome浏览器
Chrome supported by Windows PCs.
```

## 📝 注意事项

1. **使用范围**：本项目工具基于核心网现网洞察诉求开发，对UDM/HSS/UIM/UPCF/UPCF/UPCC/EPC网元/5GC网元/MGW网元/IMS网元(除SPG) 网元的离线健康检查，可直接使用此工具。如在此基础有新的开发诉求，请随我联系。
2. **无法支持**：本程序不支持SPG网元的ESN提取，但支持页面提供SPG网元的LSN信息，并页面日志提示“SPG网元不支持ESN，LSN已提取在上表，请使用LSN手动查询”。
3. **验证反馈**：若核心网网元提取出现报错或以上罗列使用范围未包含的核心网网元，欢迎留言私下，我会加以补充。
3. **日志预览**：支持操作步骤实时显示预览。
4. **浏览器**：程序依赖主流浏览器，首选Chrome.

## 📝 日志说明

对常见告警、报错等日志说明：
1. "发现重复ESN: **********，已跳过": 为提升ESN下载和对比效率，程序已设置去重算法，规避重复下载对比同一网元的行为。
2. "警告: 在*****的txt文件中未找到ESN信息,SPG网元不支持ESN，LSN已提取在上表，请使用LSN手动查询"： SPG网元仅支持LSN查询License文件，本程序仅提供LSN提取，不进行SPG网元License文件下载和对比。
3. "使用 XML文件 导出失败:********": 部分老旧平台网元的license文件不支持.xml格式，该报错出现后将继续尝试.dat文件格式继续后面程序。
4. "*****下载失败":此处报错表示该网元可能退网或ESN已无效，即便手动在ESDP系统也无法查询到对应license文件。请人工二次核对，程序跳过该网元。

## 📄 免责声明

本项目仅供学习&研究&效率提升使用，对最终结果无责，最终结果强烈建议需人工校验。

## 📄 Screen recording demonstration
 
播放视频


附件(3)