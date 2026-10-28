# rewritefidelity

**用规则在查询改写的保真度里定位可疑位置。**

`rewritefidelity` —— 用一组明示的正则规则扫描输入，报告查询改写的保真度相关的命中行与片段

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`rewritefidelity.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install nydorbcd-rewritefidelity
```

装完直接用命令名调用：

```bash
rewritefidelity --help
```

也可以不用安装，直接把 `rewritefidelity.py` 拷走用——它只依赖标准库。

## 为什么需要它

规则表公开可读，每条命中都能对应到一条明示的规则

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 查询改写的保真度 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python rewritefidelity.py --file input.txt
python rewritefidelity.py --text "示例内容"
python rewritefidelity.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 正则匹配会有漏报与误报——它是筛子，不是裁判。
- 不提供修复方案，也不重写内容。

## 跑测试

```bash
python test_rewritefidelity.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/nydorbcd/rewritefidelity>

---

## 关于作者

nydorbcd 做查询改写的保真度相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://nydorbcd.github.io>
- 仓库：<https://github.com/nydorbcd/rewritefidelity>

## 许可

MIT，见 [LICENSE](LICENSE)。
