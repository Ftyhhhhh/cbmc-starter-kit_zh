[![构建状态][coverity_img]][coverity]
[![构建状态][codecov_img]][codecov]

[CProver 文档](https://diffblue.github.io/cbmc/)

关于
=====

CBMC 是一个用于 C 和 C++ 程序的有界模型检查器。它支持 C89、C99、大部分的 C11、C17、C23 以及 gcc 和 Visual Studio 提供的大多数编译器扩展。它还通过 Scoot 支持 SystemC。它可以验证数组边界（缓冲区溢出）、指针安全性、异常和用户指定的断言。此外，它还可以检查 C 和 C++ 与其他语言（如 Verilog）的一致性。验证通过展开程序中的循环并将生成的等式传递给决策程序来执行。

有关完整信息，请参见 [cprover.org](http://www.cprover.org/cbmc)。

要了解 CProver 的各种工具及其使用方法，请参见 [TOOLS_OVERVIEW.md](TOOLS_OVERVIEW.md)。


版本
========

获取[最新版本](https://github.com/diffblue/cbmc/releases)
* 发布版本经过测试，可用于生产环境。

获取当前的*开发*版本：`git clone https://github.com/diffblue/cbmc.git`
* 开发版本不推荐用于生产环境。

安装
==========

### Windows

 Windows 可以通过在[发布页面](https://github.com/diffblue/cbmc/releases)上找到的 .msi 安装 cbmc 二进制文件。

注意，我们依赖于 Visual C++ 组件。如果你没有安装，请在运行 cbmc 之前从 [Microsoft](https://support.microsoft.com/en-gb/help/2977003/the-latest-supported-visual-c-downloads) 下载并运行 vcredist.x64.exe 进行安装。

### Linux

对于不同的 Linux 环境，有以下选择：

1. 通过发行版的软件库安装 CBMC，但缺点是这可能会安装较旧版本的 cbmc，这取决于发行版的软件包维护策略。

2. 通过每个发布版本构建的 `.deb` 包安装 CBMC，可在[发布页面](https://github.com/diffblue/cbmc/releases)上找到。
   下载 `.deb` 包并以 `root` 权限运行 `apt install cbmc-x.y.deb`，其中 `x.y` 替换为你要安装的版本。

   *注意*：由于 libc/libc++ ABI 兼容性和包依赖名称的原因，如果你选择这种方式，请确保安装适合你使用的操作系统版本的包。

3. 使用[这里](COMPILING.md)的说明从源代码编译

### macOS

macOS 上有一个可用的包在 [Homebrew/core](https://formulae.brew.sh/formula/cbmc)。
如果你已经安装了 homebrew，可以运行

```sh
$ brew install cbmc
```

来安装 CBMC，如果你想更新到最新版本，运行

```sh
$ brew upgrade cbmc
```

以更新。

Homebrew 会始终将公式更新到最新可用版本，默认情况下无论你是否愿意升级，CBMC 的升级版本都将被自动下载。如果你不希望这样，你可以通过以下命令固定 CBMC 版本：

```sh
$ brew pin cbmc
```

如果你想安装历史版本而不是最新版本，你可以使用我们维护的 [homebrew tap](https://github.com/diffblue/homebrew-cbmc)。相关说明可在[文档](doc/ADR/homebrew_tap.md)中找到。

报告错误
===========

如果你遇到问题，请提交错误报告：
* 创建一个[issue](https://github.com/diffblue/cbmc/issues)

贡献代码
=============================

1. Fork 仓库
2. 克隆仓库 `git clone git@github.com:YOURNAME/cbmc.git`
3. 从 `develop` 分支（默认分支）创建一个分支
4. 进行修改（遵循[编码指南](https://github.com/diffblue/cbmc/blob/develop/CODING_STANDARD.md)）
5. 将更改推送到你的分支
6. 创建一个针对 `develop` 分支的 Pull Request

新贡献者可以查看[小型项目](https://github.com/diffblue/cbmc/blob/develop/FEATURE_IDEAS.md)页面，了解一些小型的、有针对性的功能创意。

许可证
=======
4-clause BSD 许可证，请参见 `LICENSE` 文件。


[codebuild]: https://us-east-1.console.aws.amazon.com/codesuite/codebuild/projects/cbmc/history?region=us-east-1
[codebuild_img]: https://codebuild.us-east-1.amazonaws.com/badges?uuid=eyJlbmNyeXB0ZWREYXRhIjoiajhxcmNGUEgyV0xZa2ZFaVd3czJmbm1DdEt3QVdJRVdZaGJuMTUwOHFrZUM3eERwS1g4VEQ3Ymw3bmFncldVQXArajlYL1pXbGZNVTdXdndzUHU4Ly9JPSIsIml2UGFyYW1ldGVyU3BlYyI6IkVUUEdWVEt0SUFONlhyNVAiLCJtYXRlcmlhbFNldFNlcmlhbCI6MX0%3D&branch=develop
[codebuild_windows]: https://us-east-1.console.aws.amazon.com/codesuite/codebuild/projects/cbmc-windows/history?region=us-east-1
[codebuild_windows_img]: https://codebuild.us-east-1.amazonaws.com/badges?uuid=eyJlbmNyeXB0ZWREYXRhIjoiTFQ4Q0lCSEc1Rk5NcmlzaFZDdU44Vk8zY0c1VCtIVWMwWnJMRitmVFI5bE94Q3dhekVPMWRobFU2Q0xTTlpDSWZUQ3J1eksrWW1rSll1OExXdll2bExZPSIsIml2UGFyYW1ldGVyU3BlYyI6InpqcloyaEdxbjBiQUtvNysiLCJtYXRlcmlhbFNldFNlcmlhbCI6MX0%3D&branch=develop
[coverity]: https://scan.coverity.com/projects/diffblue-cbmc
[coverity_img]: https://scan.coverity.com/projects/13552/badge.svg
[codecov]: https://codecov.io/gh/diffblue/cbmc
[codecov_img]: https://codecov.io/gh/diffblue/cbmc/branch/develop/graphs/badge.svg
