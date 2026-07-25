# Docker 01-24 图示复扫记录

扫描时间：2026-07-25

## 结论

已通过。初扫发现的旧式图示和碎卡片图已完成修复，最终复扫未发现阻断问题。

## 全局检查

- 全站 `div` 平衡：通过，`DOCKER_ALL_BALANCED`
- 17-24 页旧式 `diagram-note-card`、`diagram-step`、`stack-diagram`：均为 0
- 12-24 页整体符合前面规则
- 最终复扫：无 `diagram-note-card` 残留，无超过 6 步的 `diagram-step` 图
- `01-03`、`01-09`、`01-11` 保留 `stack-diagram`：这三张图表达 Docker 镜像/技术栈本身的层级结构，层数可接受，层级图更贴合意境

## 已修复项

这些图在初扫中仍使用旧式 `diagram-step`、`diagram-note-card` 或 `stack-diagram`，或呈现为碎卡片堆；现已按语义重画或复核保留。

| 文件 | 图示 | 问题 |
|---|---|---|
| `01-教学资料-Docker认知与容器化思想.html` | 图示 3：Docker 把应用和运行环境一起打包 | 已复核，恢复并保留层级表达 |
| `01-教学资料-Docker认知与容器化思想.html` | 图示 9：镜像分层结构与缓存价值 | 已复核，恢复并保留层级表达 |
| `01-教学资料-Docker认知与容器化思想.html` | 图示 11：云原生技术栈分层 | 已复核，恢复并保留层级表达 |
| `02-教学资料-Docker安装与初体验.html` | 图示 3：用户敲 docker run hello-world | 9 个 `diagram-step`，超过 6 步 |
| `03-教学资料-镜像管理.html` | 图示 5：mysql:8.0 镜像分层结构与 history 视角 | 仍为 `stack-diagram` |
| `04-教学资料-容器管理.html` | 图示 8：Docker 拉取/使用 mysql:8.0 镜像 | 11 个 `diagram-step`，超过 6 步 |
| `06-教学资料-Dockerfile基础指令.html` | 图示 2：你的应用镜像（FROM 之上的层） | 仍为 `stack-diagram` |
| `08-教学资料-Dockerfile构建实践.html` | 图示 7：读取 Dockerfile | 9 个 `diagram-step`，超过 6 步 |
| `08-教学资料-Dockerfile构建实践.html` | 图示 10：判断缓存命中的规则 | 8 个 `diagram-step`，超过 6 步 |
| `09-教学资料-Docker网络.html` | 图示 7：自定义网络实现业务分组隔离 | 仍有 8 个 `diagram-note-card` |
| `10-教学资料-Docker数据卷与持久化.html` | 图示 1：可写层（容器专属） | 仍为 `stack-diagram` |
| `11-教学资料-Docker Compose多容器编排.html` | 图示 3：Compose 在容器生态中的定位 | 仍为 `stack-diagram` |
| `14-教学资料-K8s集群搭建.html` | 图示 6：kubeadm 多节点 K8s 集群 | 17 张普通卡片且无流程/对比/路线语义，疑似碎卡片堆 |

## 可接受但建议复核

这些图虽然使用了 `diagram-step` 或代码树，但数量不多，或本身偏清单/文件结构/排查结构，可以先不作为阻断项。

| 文件 | 图示 | 说明 |
|---|---|---|
| `01-教学资料-Docker认知与容器化思想.html` | 图示 13：云原生技术演进与课程路径 | 5 个步骤，未超过 6，可接受 |
| `01-教学资料-Docker认知与容器化思想.html` | 图示 14：CTTS 从痛点到交付的完整逻辑链 | 5 个步骤，且之前已做行高规则优化，可接受 |
| `05-教学资料-镜像与容器管理综合实践.html` | 图示 5：容器故障排查五步法 | 6 个步骤，边界可接受 |
| `02-24` 多处 `diagram-code-tree` | 文件结构、YAML 结构、目录结构、命令/排查树 | 代码树语义合理时可保留 |

## 最终校验

- `DOCKER_ALL_BALANCED`
- `NO_NOTE_CARD_REMAINS`
- `NO_LONG_STEP_VISUALS`
- stack 例外：`01-03`、`01-09`、`01-11`，均为合理层级语义
