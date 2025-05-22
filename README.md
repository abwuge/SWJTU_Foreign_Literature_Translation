<div align="center">
  <h1>西南交通大学本科毕业论文外文资料翻译LaTeX模板</h1>
  
  [![LICENSE](https://badgen.net/static/LICENSE/非商业许可)](LICENSE)
</div>

------------------------------------------------------------

## 简介
本项目为西南交通大学本科毕业论文外文资料翻译LaTeX模板。

<!-- 点击[此处](https://abwuge.github.io/SWJTU_Bachelor_Thesis/SWJTU_Bachelor_Thesis.pdf)预览该模板。

## 使用说明
### 创建项目
1. 克隆或从[Release](../../releases/latest)下载本项目到本地：
   ```shell
   git clone https://github.com/abwuge/SWJTU_Bachelor_Thesis.git
   ```
2. 打开项目文件夹。
3. 将`SWJTU_Bachelor_Thesis.tex`中的示例内容修改为个人论文内容。
4. 按照论文结构，在`chapters/`、`appendix/`等文件夹中编辑各章节内容。
5. 编译主文件，生成PDF论文。请使用XeLaTeX进行编译：
   
   Windows PowerShell:
   ```powershell
   "build/appendix", "build/chapters" | % { md -Force $_ }
   xelatex -synctex=1 -interaction=nonstopmode -file-line-error -output-directory=build SWJTU_Bachelor_Thesis.tex
   biber --output-directory=build SWJTU_Bachelor_Thesis
   xelatex -synctex=1 -interaction=nonstopmode -file-line-error -output-directory=build SWJTU_Bachelor_Thesis.tex
   xelatex -synctex=1 -interaction=nonstopmode -file-line-error -output-directory=build SWJTU_Bachelor_Thesis.tex
   ```
   Shell:
   ```shell
   mkdir -p build/appendix build/chapters
   xelatex -synctex=1 -interaction=nonstopmode -file-line-error -output-directory=build SWJTU_Bachelor_Thesis.tex
   biber --output-directory=build SWJTU_Bachelor_Thesis
   xelatex -synctex=1 -interaction=nonstopmode -file-line-error -output-directory=build SWJTU_Bachelor_Thesis.tex
   xelatex -synctex=1 -interaction=nonstopmode -file-line-error -output-directory=build SWJTU_Bachelor_Thesis.tex
    ```
    > 编译链：xelatex -> biber -> xelatex*2
6. 参考文献请在`bibliography/references.bib`中维护。

你也可以将本模板上传到[Overleaf](https://cn.overleaf.com/)平台进行在线编写：
1. 从[Release](../../releases/latest)中下载最新版本的源代码压缩包。
2. 在Overleaf创建新项目，上传项目压缩包。
3. 打开项目后，点击左上角菜单，并将编译器从pdfLaTeX改为XeLaTeX。
4. 点击右上角重新编译，即可正常编译项目。

或者点击[此处](https://abwuge.github.io/SWJTU_Bachelor_Thesis)直接在Overleaf中创建该项目。

### 宏包键值对参数介绍
- `[ ]` `major`：所在专业，请使用教务处的标准专业名称。
  > 不同专业的论文要求可能不同，若不手动设置专业名称，将使用西南交通大学提供的模板作为默认模板。
  > 
  > 若您发现设定专业后，格式仍然为交大默认模板，很可能是尚未实现对应专业，请[提交 Issue](../../issues/new)


### 模板自定义命令介绍
#### 无参数命令
- `\songti`：将中文切换到模板内置字体——宋体。
- `\heiti`：将中文切换到模板内置字体——黑体。
- `\boxsurd`：在当前位置生成已选中的复选框。
- `\swjtuTableOfContents`：生成目录页。

#### 普通参数命令
- `\swjtuIntroduction{章节名}`：生成绪论章节。
- `\swjtuChapter{章节名}`：生成普通章节。
- `\swjtuConclusion{章节名}`：生成结论章节。
- `\swjtuAcknowledgments{章节名}`：生成致谢章节。
- `\swjtuBibliography{章节名}`：生成参考文献章节。
- `\swjtuAppendix{章节名}`：生成附录章节。
- `\swjtuExplanation{符号, 解释; ...}`：生成公式的符号注释。
  ```latex
  % 使用示例
  % 若符号或解释本身含有分隔符，用`{}`包围即可，`{}`本身也可嵌套
  \swjtuExplanation{
    符号1, 解释1;
    {含有","的符号2}, {含有";"或"{}"的解释2};
  }
  ```


#### 键值对参数命令
- `\swjtuTitlePage`：生成扉页。
  - `[ ]` `ctitle`：中文标题。
  - `[ ]` `etitle`：英文标题。
  - `[ ]` `grade`：年级。
  - `[ ]` `id`：学号。
  - `[ ]` `name`：姓名。
  - `[ ]` `major`：专业。
  - `[ ]` `advisor`：指导老师。
  - `[ ]` `year`：年份。
  - `[ ]` `month`：月份。
- `\swjtuIntegrityDeclaration`：生成学术诚信声明页。
  - `[ ]` `signature`：作者签名图片路径。
  - `[ ]` `year`：年份。
  - `[ ]` `month`：月份。
  - `[ ]` `day`：日期。
- `\swjtuCopyrightAuthorization`：生成版权使用授权书。
  - `[0]` `confidentialityPeriod`：保密年限，小于等于0为不保密。
  - `[ ]` `authorSignature`：作者签名图片路径。
  - `[ ]` `advisorSignature`：指导教师签名图片路径。
  - `[ ]` `authorYear`/`authorMonth`/`authorDay`：作者签署日期。
  - `[ ]` `advisorYear`/`advisorMonth`/`advisorDay`：指导教师签署日期。
- `\swjtuTask`：生成任务书。
  - `[ ]` `class`：班级。
  - `[ ]` `name`：姓名。
  - `[ ]` `id`：学号。
  - `[ ]` `issueYear`/`issueMonth`/`issueDay`：发题日期。
  - `[ ]` `dueYear`/`dueMonth`/`dueDay`：完成日期。
  - `[ ]` `title`：课题题目。
  - `[ ]` `purpose`：目的意义。
  - `[ ]` `tasks`：应完成的任务。
  - `[ ]` `requirement`：毕业要求达成度。
  - `[ ]` `weeks`：总周数。
  - `[ ]` `partOne`/`partOneWeeks` ~ `partFive`/`partFiveWeeks`：各部分内容及周数。
  - `[ ]` `partReview`/`partReviewWeeks`：评阅及答辩内容及周数。
  - `[ ]` `remark`：备注。
  - `[ ]` `advisor`：指导教师。
  - `[ ]` `advisorYear`/`advisorMonth`/`advisorDay`：指导教师签署日期。
- `\swjtuAbstractCN`：生成中文摘要。
  - `[ ]` `abstract`：中文摘要正文。
  - `[ ]` `keywords`：中文关键词（请自行用分号分隔）。
- `\swjtuAbstractEN`：生成英文摘要。
  - `[ ]` `abstract`：英文摘要正文。
  - `[ ]` `keywords`：英文关键词（请自行用分号分隔）。

**注1**：键值对参数命令的参数均为可选参数。在参数名之前用`[]`表示其默认值。
> 例如：`[ ]`表示默认参数为空，`[0]`表示默认参数为0。

**注2**：由于本人能力有限，模板中部分自定义命名中修改了全局定义。因此若您未按照主文件示例的命令执行方式进行论文撰写，恐有非预期行为。

### 模板自定义环境说明
- `allsongti`：中英文字体均设置为内置字体——宋体。
- `allheiti`：中英文字体均设置为内置字体——黑体。
- `swjtuCodeBlock`: 代码框。

## 目录结构说明
   ```powershell
   .
   │  LICENSE                   # 许可证
   │  SWJTU_Bachelor_Thesis.tex # 主文件
   │  
   ├─appendix # 附录
   │      appendix1.tex
   │      appendix2.tex
   │      
   ├─bibliography # 参考文献
   │      references.bib
   │      
   ├─chapters # 主体
   │      acknowledgments.tex # 致谢
   │      chapter1.tex        # 正常章节
   │      conclusion.tex      # 结论
   │      introduction.tex    # 绪论
   │      
   ├─fonts # 模板内置字体（取自Windows，商用请注意版权）
   │      simhei.ttf  # 黑体
   │      simsun.ttc  # 宋体
   │      TIMES.TTF   # 新罗马正常
   │      TIMESBD.TTF # 新罗马粗体
   │      TIMESBI.TTF # 新罗马粗斜
   │      TIMESI.TTF  # 新罗马斜体
   │      
   ├─signatures # 电子签名图片
   │      advisor.png # 指导教师
   │      author.png  # 作者
   │      
   └─style # 格式文件
           swjtu.sty
   ```

## VS Code 配置说明
可以使用 [Visual Studio Code](https://code.visualstudio.com/) 进行论文编写，配合 [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) 插件可获得良好体验。你可以将如下 settings.json 配置文件放置于 `.vscode/settings.json`：

```json
{
    "latex-workshop.latex.outDir": "./build",
    "latex-workshop.latex.recipes": [
        {
            "name": "xelatex -> biber -> xelatex*2",
            "tools": [
                "xelatex",
                "biber",
                "xelatex",
                "xelatex"
            ]
        }
    ],
    "latex-workshop.latex.tools": [
        {
            "name": "xelatex",
            "command": "xelatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-output-directory=build",
                "%DOC%"
            ]
        },
        {
            "name": "biber",
            "command": "biber",
            "args": [
                "--output-directory=build",
                "%DOCFILE%"
            ]
        }
    ],
    "latex-workshop.formatting.latexindent.args": [
        "-c",
        "%DIR%/build/",
        "%TMPFILE%",
        "-y=defaultIndent: '%INDENT%'"
    ]
}
```

Windows下的[TeX Live](https://tug.org/texlive/) & [VS Code](https://code.visualstudio.com/)配置方法可参考[知乎文章](https://zhuanlan.zhihu.com/p/382472221)。

## 贡献
### 贡献指南
欢迎大家为本模板贡献代码、修正bug或完善文档！
- 如有建议或问题，请提交Issue。
- 欢迎提交Pull Request。
- 贡献前请确保遵循各自专业的最新论文撰写规范。

### 感谢所有贡献者！
[![贡献者](https://contrib.rocks/image?repo=abwuge/SWJTU_Bachelor_Thesis)](https://github.com/abwuge/SWJTU_Bachelor_Thesis/graphs/contributors)

### Star

> [!TIP] 
> 若对您有帮助，请给这个项目点上 Star!

<a href="https://www.star-history.com/#abwuge/SWJTU_Bachelor_Thesis&Date">
 <picture>
   <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=abwuge/SWJTU_Bachelor_Thesis&type=Date&theme=dark" />
   <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=abwuge/SWJTU_Bachelor_Thesis&type=Date" />
   <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=abwuge/SWJTU_Bachelor_Thesis&type=Date" />
 </picture>
</a> -->
