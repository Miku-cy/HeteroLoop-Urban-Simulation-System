# 贡献指南

感谢您对 HeteroLoop 都市仿真系统的兴趣！欢迎贡献代码、报告问题或提出改进建议。

---

## 如何贡献

### 1. Fork 仓库

点击 GitHub 页面右上角的 **Fork** 按钮，创建您自己的仓库副本。

### 2. 克隆仓库

```bash
git clone https://github.com/你的用户名/HeteroLoop-Urban-Simulation-System.git
cd HeteroLoop-Urban-Simulation-System
```

### 3. 创建分支

```bash
git checkout -b feature/你的功能名称
# 例如：
git checkout -b feature/add-new-vehicle-type
git checkout -b fix/collision-detection-bug
```

### 4. 进行修改

- 💻 编写代码
- 🎨 添加或改进 3D 模型
- 📝 更新文档
- 🐛 修复 bug

### 5. 测试您的更改

```bash
# 方式一：直接在浏览器中打开 index.html
open index.html  # macOS
start index.html  # Windows

# 方式二：使用本地服务器
python3 -m http.server 8080
# 然后访问 http://localhost:8080
```

### 6. 提交更改

```bash
git add .
git commit -m "feat: 添加新功能"
```

### 7. 推送到 GitHub

```bash
git push origin feature/你的功能名称
```

### 8. 创建 Pull Request

在 GitHub 上创建 PR，描述您的更改内容和动机。

---

## 代码规范

### JavaScript 代码

- 使用 **ES6+** 语法
- 变量使用 `const` 或 `let`，避免使用 `var`
- 函数使用**箭头函数**或**传统函数声明**
- 类名使用 `CamelCase`
- 函数和变量使用 `camelCase` 或 `snake_case`
- 所有函数需要**文档注释**

### Three.js 最佳实践

```javascript
// ❌ 避免：每次创建新对象
for (let i = 0; i < 100; i++) {
  const geometry = new THREE.BoxGeometry(1, 1, 1);
  const material = new THREE.MeshStandardMaterial();
  const cube = new THREE.Mesh(geometry, material);
  scene.add(cube);
}

// ✅ 推荐：使用对象池
const geometry = new THREE.BoxGeometry(1, 1, 1);
const material = new THREE.MeshStandardMaterial();
for (let i = 0; i < 100; i++) {
  const cube = new THREE.Mesh(geometry, material);
  cube.position.set(i, 0, 0);
  scene.add(cube);
}
```

### 提交信息格式

```
<type>: <subject>

<body>
```

**Type 类型：**

| Type | 说明 | 示例 |
|------|------|------|
| `feat` | 新功能 | `feat: 添加电瓶车换道行为` |
| `fix` | 修复 bug | `fix: 修复车辆碰撞检测错误` |
| `docs` | 文档更新 | `docs: 更新 README 操作说明` |
| `style` | 代码格式 | `style: 统一代码缩进` |
| `refactor` | 重构 | `refactor: 重构交通信号灯系统` |
| `perf` | 性能优化 | `perf: 优化渲染性能` |
| `test` | 测试相关 | `test: 添加碰撞检测测试` |
| `chore` | 维护任务 | `chore: 更新依赖版本` |

### 示例

```
feat: 添加行人路径规划系统

- 实现 A* 寻路算法
- 添加人行横道通行逻辑
- 支持天桥优先路径选择

影响范围：
- 行人移动延迟降低 40%
- 交通堵塞减少 25%
```

---

## 功能开发指南

### 添加新实体类型

1. 创建实体类，继承基础实体
2. 实现 `update()` 方法
3. 添加到实体管理器
4. 在 dashboard 中注册统计指标

### 修改交通信号灯

```javascript
// 信号灯状态
const TrafficLightState = {
  RED: 0,
  YELLOW: 1,
  GREEN: 2
};

// 自适应控制
function adaptiveControl(density) {
  if (density > 0.8) {
    return TrafficLightState.GREEN; // 高密度，绿灯
  } else if (density > 0.3) {
    return TrafficLightState.YELLOW; // 中等密度，黄灯
  }
  return TrafficLightState.RED; // 低密度，红灯
}
```

### 优化性能

- 使用 `requestAnimationFrame` 替代 `setInterval`
- 使用对象池减少对象创建
- 实现视锥剔除（Frustum Culling）
- 使用 LOD（细节层次）优化远处物体

---

## 测试要求

### 手动测试清单

- [ ] 在不同浏览器中测试（Chrome, Firefox, Safari, Edge）
- [ ] 测试响应式布局
- [ ] 验证键盘快捷键
- [ ] 检查控制台错误
- [ ] 验证性能指标准确性

### 自动化测试

对于核心功能，建议添加自动化测试：

```javascript
// tests/basic-test.js 示例
function testCollisionDetection() {
  const vehicle1 = { x: 0, y: 0, width: 2, height: 1 };
  const vehicle2 = { x: 1, y: 0, width: 2, height: 1 };
  
  const collision = checkCollision(vehicle1, vehicle2);
  
  console.assert(collision === true, '车辆应该碰撞');
}
```

---

## 问题反馈

### Bug 报告

请包含以下信息：

- **复现步骤**：清晰的步骤说明
- **预期行为**：您认为应该发生什么
- **实际行为**：实际发生了什么
- **环境信息**：
  - 浏览器和版本
  - 操作系统
  - 显卡型号（如果是渲染问题）
- **截图/录屏**：如果有的话

### 功能建议

请描述：

- **问题背景**：为什么需要这个功能
- **您的解决方案**：您期望的改进方案
- **可能的替代方案**：其他可行的方案
- **使用场景**：这个功能的使用场景

### Issue 模板

```markdown
## Bug 描述
[简洁描述问题]

## 复现步骤
1. [步骤一]
2. [步骤二]
3. [步骤三]

## 预期行为
[描述预期]

## 实际行为
[描述实际]

## 环境
- 浏览器：[浏览器名称和版本]
- 操作系统：[操作系统]
```

---

## 开发资源

### Three.js 文档

- [Three.js 官方文档](https://threejs.org/docs/)
- [Three.js 示例](https://threejs.org/examples/)
- [Three.js GitHub](https://github.com/mrdoob/three.js)

### 学习资源

- [WebGL 教程](https://webglfundamentals.org/)
- [Three.js 入门教程](https://threejsfundamentals.org/)

### 工具推荐

- [Three.js Editor](https://threejs.org/editor/) - 在线 3D 编辑器
- [Blender](https://www.blender.org/) - 3D 建模软件
- [VS Code](https://code.visualstudio.com/) - 代码编辑器（推荐）

---

## 行为准则

- ✅ 保持友好和专业的沟通
- ✅ 尊重不同的观点和经验
- ✅ 专注于对项目最有利的事情
- ❌ 拒绝任何形式的骚扰
- ❌ 禁止人身攻击或侮辱
- ❌ 禁止垃圾信息或无关内容

---

## 许可证

通过贡献代码，您同意您的贡献将按照 MIT 许可证授权。

---

## 联系方式

- GitHub Issues: [报告问题](https://github.com/Miku-cy/HeteroLoop-Urban-Simulation-System/issues)
- GitHub Discussions: [讨论区](https://github.com/Miku-cy/HeteroLoop-Urban-Simulation-System/discussions)
- GitHub Profile: [Miku-cy](https://github.com/Miku-cy)

---

## 致谢

感谢所有贡献者的努力！🎉

---

<p align="center">
  <strong>让我们一起让城市交通仿真更智能！</strong><br/>
  <sub>构建更好的城市出行体验 🚗</sub>
</p>