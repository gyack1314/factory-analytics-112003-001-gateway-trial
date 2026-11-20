# 共用网关的分批上线试验与扩围决策

本目录保存工业园内的合成业务资料。网关邻接与产线接入台账，按周候选和抽签记录，原始维修单和补充凭证，施工能力与审批流水。分钟从试验起点计，首周为第 0 周。lottery 的 weight 为当轮抽签权重，eligible_weight_total 仅含可抽签网关。chosen 标记当周首次获准上线的网关。ready 相关字段描述接入条件，路由记录描述实际连接。

数据文件位于 `data/`，采用 UTF-8 JSON。表由对象数组组成，单份配置由对象表示。字段后缀 `min`、`day`、`hour`、`cents`、`kg` 和 `m` 标记单位。未提供的事实用 `null` 表示，绝对区间右端不包含在内。名称和编号为本目录内的资料标识。

运行环境为 Python 3.11，资料检查只使用标准库。

- 查看目录与样本数量：`python3 inspect_inputs.py`
- 运行资料测试：`python3 -m unittest discover -s tests -v`
- 编译检查：`python3 -m compileall -q inspect_inputs.py tests`
