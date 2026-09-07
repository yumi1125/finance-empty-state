# Finance Empty State

用于金融 Web / B 端产品的统一空状态插画 Skill。

它将一类容易被误读的报告结果转译为清晰、克制的视觉场景：**多源数据调取与模型评估已经完成，但指定周期、机构或行为维度内的有效记录较少，暂时没有可展示的统计结果。** 画面保持中性偏正向，不暗示系统失败、申请被拒、风险告警或用户过错。

> A Codex skill for generating consistent financial empty-state illustrations. It communicates that retrieval and model evaluation completed successfully, while valid observations remain too sparse for a meaningful result—without implying failure, rejection, or risk.

![Finance empty-state examples](examples/overview.png)

## 生成示例

<table>
  <tr>
    <td align="center"><img src="examples/consumer-demand-application.png" width="180" alt="消费需求申请概览"><br>消费需求申请概览</td>
    <td align="center"><img src="examples/application-count-time-distribution.png" width="180" alt="申请次数时间分布"><br>申请次数时间分布</td>
    <td align="center"><img src="examples/bank-institution-application-distribution.png" width="180" alt="银行机构申请分布"><br>银行机构申请分布</td>
    <td align="center"><img src="examples/nonbank-online-application-intent.png" width="180" alt="非银线上申请意向"><br>非银线上申请意向</td>
    <td align="center"><img src="examples/special-period-application-intent.png" width="180" alt="特殊时段申请意向"><br>特殊时段申请意向</td>
  </tr>
  <tr>
    <td align="center"><img src="examples/installment-count-distribution.png" width="180" alt="消费分期笔数分布"><br>消费分期笔数分布</td>
    <td align="center"><img src="examples/installment-cumulative-amount.png" width="180" alt="周期累计消费分期金额"><br>周期累计消费分期金额</td>
    <td align="center"><img src="examples/installment-limit-distribution.png" width="180" alt="消费分期额度分布"><br>消费分期额度分布</td>
    <td align="center"><img src="examples/installment-institution-count-distribution.png" width="180" alt="消费分期机构数分布"><br>消费分期机构数分布</td>
    <td align="center"><img src="examples/installment-performance.png" width="180" alt="消费履约情况"><br>消费履约情况</td>
  </tr>
</table>

## Skill 特点

- **固定核心语义**：先表达“处理已完成”，再表达“有效样本较少、暂无统计结果”。
- **金融业务场景化**：可组合申请、消费、分期、额度、银行/非银机构、时间周期、履约与延期等对象。
- **统一但不雷同**：以颜色、材质、视角、阴影和信息密度保持一致，每张图使用不同的主场景、动作和道具。
- **无文字表达**：画面不依赖标题、数字、货币符号或伪文字，适合与产品文案分离使用。
- **稀疏证据设计**：用少量可数记录、大片有序留空和完整流程说明“行为较少”，避免被理解为数据源故障。
- **人物按需出现**：统一人物造型，但人物只用于解释动作；场景始终是主角。
- **洁净的蓝白 2.5D**：品牌蓝 `#326FF7` 为主，白色与淡蓝支撑，青色仅作小面积重点，表面采用连续柔和渐变。
- **严格负面约束**：禁止红色告警、叉号、锁、404、拒绝印章、下跌趋势、损坏设备、焦虑人物和无关微装饰。
- **透明输出与检查**：要求 RGBA、四角 alpha 为 0，并提供棋盘格背景清理脚本作为窄范围兜底。

## 适用范围

适用于：

- 金融报告、风控报告与模型评估报告的无数据状态
- 消费金融、银行和非银机构的申请行为分布
- 消费分期笔数、金额、额度、机构数、履约与延期统计
- 指定周期或特殊时段内记录较少的趋势与分布页面

不适用于：

- 网络失败、权限不足、服务异常或页面 404
- 申请拒绝、逾期告警、欺诈风险或负面评分
- 需要表达确定审批结论、风险结论或合规结论的画面

## 安装

克隆到 Codex Skills 目录：

```bash
git clone https://github.com/yumi1125/finance-empty-state.git \
  ~/.codex/skills/finance-empty-state
```

也可以下载仓库后，将整个 `finance-empty-state` 文件夹复制到：

```text
~/.codex/skills/finance-empty-state
```

重新打开 Codex 会话后，Skill 可根据金融空状态相关请求自动触发，也可显式调用：

```text
$finance-empty-state
```

## 使用示例

```text
使用 $finance-empty-state 生成三个场景，核心都是消费分期额度分布，
用电池加载程度表达额度。三张只改变场景、动作和道具，
人物造型、色彩、视角、阴影和信息密度保持一致。
```

```text
使用 $finance-empty-state 生成一张消费履约延期金额汇总空状态插画。
画面使用竖直沙漏和少量金币表达延期金额，主角拿着空白记录本观察，
不出现文字、数字、货币符号或告警元素。
```

```text
修改上一张图片：只移动黄色指引线的起点，其他人物、物件、光影、
透明背景和构图全部保持不变。
```

## 工作方式

Skill 会先把请求整理为内部 brief，核心字段包括：

```text
business_dimension   业务维度
time_scope           时间范围
institution_scope    机构范围
completed_process    已完成的数据与模型阶段
absent_measure       暂无有效统计的指标
likely_reason        行为频率低或观察样本不足
main_object          画面主物件
supporting_objects   必要辅助物件
sparse_evidence      两到三个可数的稀疏证据
scene_story          具体场所、动作和结果
character_action     人物在场景中的必要动作
target_size          目标尺寸
background           透明背景要求
```

随后按“场所 → 动作 → 业务对象 → 可见结果”检查场景逻辑，并在原尺寸与约 `240×240` 缩略尺寸下验收语义、洁净度和透明边缘。

## 定向修改

当一张图的大部分内容已经正确时，应明确要求只修改一个缺陷，并列出必须保持不变的内容。例如：

```text
保留已确认的主体、构图、物件数量、视角、配色、光照、透明背景和人物造型。
只修改：将黄色虚线的起点移动到下方淡蓝色文件夹。
不要添加文字、符号、人物、新物件或装饰性小元素。
```

## 透明背景处理

优先要求图像生成工具直接输出真实透明背景。如果生成器把浅色棋盘格烘焙进 RGB 图，可使用附带脚本清理与画布边缘连通的浅色背景：

```bash
python3 scripts/remove_checkerboard.py source.png output.png
```

脚本依赖 [Pillow](https://pypi.org/project/pillow/)，且只作为透明背景失败后的兜底；内部白色卡片、报告页和设备表面不会因为颜色相近而被直接整体删除。

## 目录结构

```text
finance-empty-state/
├── SKILL.md
├── agents/openai.yaml
├── references/
│   ├── style-system.md
│   ├── semantic-library.md
│   └── prompt-patterns.md
├── scripts/remove_checkerboard.py
└── examples/
```

详细视觉参数见 [`references/style-system.md`](references/style-system.md)，业务语义组合见 [`references/semantic-library.md`](references/semantic-library.md)，生产与定向修改模板见 [`references/prompt-patterns.md`](references/prompt-patterns.md)。

## License

[MIT](LICENSE)
