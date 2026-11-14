# William Stock Analysis

可独立安装的股票深度研究 Skills Package。当前公开版本：**0.3.5**。

**[下载最新版安装包](https://github.com/wiwxi/william-stock-analysis-releases/releases/latest/download/william-stock-analysis.tar.gz)** · **[版本说明与校验文件](https://github.com/wiwxi/william-stock-analysis-releases/releases/latest)**

## 包含什么

- 14 个 William 股票研究 skills，以及随包提供的 humanizer-zh。
- 八部分投资报告框架、商业模式与参与方分析、财务与风险分析、图文说明。
- 情景估值、定量安全边际、可复算工作簿接口及独立审查流程。
- 安装程序、运行代码、模板、方法说明、测试与许可证。

此仓库仅发布技能安装包及其使用文件，不提供作者的公司研究报告、Obsidian 笔记、个人工作区、账户凭据或付费数据权限。下载者无需访问其他仓库。

## 最简单的安装方式

下载安装包并解压，得到 `william-stock-analysis/` 文件夹。把该文件夹交给支持本地 skills 的 AI 助手，并发送：

> 请读取这个 William Stock Analysis package 的 README 和安装说明，确认当前助手实际使用的持久化 skills 目录。先核验 manifest.json 中的文件摘要，再运行 installation/install.py 的预览；确认仅处理本包所属文件后执行安装，不覆盖其他技能或人工改动。完成后核对 15 个技能入口，并报告运行依赖和当前环境限制。

具体宿主是否支持 SKILL.md、能否访问网络和运行本地程序，取决于宿主本身。文件包不能单靠上传聊天窗口就保证完成持久化安装。

## 命令行安装

需要 Python 3.11 或更高版本。在新目录中下载并验证：

```sh
curl -fL -o william-stock-analysis.tar.gz https://github.com/wiwxi/william-stock-analysis-releases/releases/latest/download/william-stock-analysis.tar.gz
curl -fL -o SHA256SUMS https://github.com/wiwxi/william-stock-analysis-releases/releases/latest/download/SHA256SUMS
shasum -a 256 -c SHA256SUMS
tar -xzf william-stock-analysis.tar.gz
cd william-stock-analysis
```

Linux 如无 `shasum`，可用 `sha256sum -c SHA256SUMS`。然后把下面示例路径替换为当前助手实际使用的 skills 目录：

```sh
STOCK_SKILLS_ROOT="/absolute/path/to/your/skills"
python3 installation/install.py --package . --manifest manifest.json --root "$STOCK_SKILLS_ROOT"
python3 installation/install.py --package . --manifest manifest.json --root "$STOCK_SKILLS_ROOT" --apply
PYTHONPATH="$STOCK_SKILLS_ROOT/william-stock-analysis/package/runtime" python3 -m william_stock capabilities
```

第一条安装命令预览变更，带 `--apply` 的命令才执行安装。实际使用前，应确认宿主已经发现新技能。生成和重算工作簿还需要包内说明列出的依赖及真实重算引擎；安装包不包含模型服务、数据授权或 LibreOffice。

## 使用示例

安装完成并让宿主发现技能后，可以说：

> 使用 william-stock-analysis，对我指定的股票进行完整深度研究。按八部分结构说明投资判断、商业模式、股东回报、行业环境、市场定价、下行风险、买入条件和核查依据；明确数据截止时间，提供情景价格和定量安全边际。

研究结果依赖实际可取得的证据与运行能力，技能不承诺收益或预测准确性。

## 版本与完整性

0.3.5 安装包保持原已验收字节不变。归档内 README 标题误写为 0.3.4；`manifest.json`、`pyproject.toml` 和运行时版本均为 **0.3.5**。这是文档标题错误，不影响本次版本身份。

安装包 SHA-256：

```text
c5085dc939e9cc2c5496e068d1e5c243a05029fc5a599b4258cc10964e835b06
```

`releases/latest` 始终指向最新正式发布；需要固定版本时，使用 [v0.3.5](https://github.com/wiwxi/william-stock-analysis-releases/releases/tag/v0.3.5)。

## 许可

保留包内原有许可与第三方声明，见 [LICENSE](LICENSE) 和 [NOTICE](NOTICE)。公开提供下载不将其他来源材料或第三方服务一并授权。
