# resume-tailor

针对目标岗位 JD 自动分析匹配度、改写简历内容的开源 Claude Skill。

预览页：https://youxch.github.io/resume-tailor/

> 同一份经历，换一个 JD，简历就该换一种写法。

## 这是做什么的

换赛道找工作时最难的不是能力不够，而是 HR 和面试官看不出你的经历和这个岗位之间的关系。resume-tailor 不会帮你编经历，而是把“你做过什么”翻译成“这个岗位想要什么”。

把目标岗位的 JD 粘进去，这个 skill 会：

1. **判断方向**：根据 JD 关键词判断这个岗位最匹配你的哪个专业方向（或两个方向的交叉点）
2. **三视角打分**：分别从 HR / 技术面试官 / 业务负责人三个视角给当前简历内容打分，定位优势和差距
3. **自动改写并迭代**：重写项目描述、关键句，按打分结果反复修改，直到三个视角都达到目标分数再输出

## 怎么用

1. 下载仓库，并把这个 skill 放到 `~/.claude/skills/`（或你的 Claude Code / Claude Desktop 的 skills 目录）
2. 打开 [`SKILL.md`](SKILL.md)，按照里面的提示替换为你自己的信息：
   - 复制 `references/candidate-profile.template.md` → `candidate-profile.md`，填入你自己的教育、技能、论文、荣誉
   - 复制 `references/project-details.template.md` → `project-details.md`，填入你自己的项目细节和"按方向重排素材"的策略
   - 把 `SKILL.md` 里的 "[候选人姓名]"、"方向A / 方向B" 换成你自己的姓名和专业方向
3. 把目标岗位 JD 贴给 Claude，触发 skill，开始定制

## 目录结构

```
resume-tailor/
├── index.html                              # 展示页（GitHub Pages 自动识别为首页）
├── SKILL.md                                # skill 定义（含工作流程、写作规范、评审系统）
├── references/
│   ├── candidate-profile.template.md       # 候选人档案模板
│   ├── project-details.template.md         # 项目详情模板
│   └── style-guide.md                      # 简历写作风格规范（通用方法论）
├── evals/
│   └── evals.json                          # 测试用例
└── specs/                                   # 设计文档
```

## License

MIT
