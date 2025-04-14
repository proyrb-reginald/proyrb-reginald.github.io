---
layout: page
title: 关于本站
permalink: /about/
---

<div class="about-container">
  <section class="about-section">
    <h2 class="about-title">🛠️ 技术专注领域</h2>
    <ul class="tech-list">
      <li><strong>嵌入式开发</strong>：ARM架构/RTOS/硬件驱动开发</li>
      <li><strong>图形框架</strong>：LVGL应用开发与性能优化</li>
      <li><strong>核心语言</strong>：现代C/C++(11/14/17标准)实战</li>
      <li><strong>算法工程化</strong>：嵌入式场景下的数据结构与算法实现</li>
    </ul>
  </section>

  <section class="about-section">
    <h2 class="about-title">🚀 内容特色</h2>
    <div class="code-block">
      <pre><code>// 用代码注释风格呈现价值主张
#define BLOG_VALUE \  
  1. 从寄存器操作到系统设计的全栈嵌入式知识 \  
  2. 真实项目中的LVGL界面开发避坑指南 \  
  3. 可复用的Linux驱动开发模板与调试技巧</code></pre>
    </div>
  </section>

  <section class="about-section">
    <h2 class="about-title">📚 资源体系</h2>
    <div class="resource-table">
      <table>
        <thead>
          <tr>
            <th>资源类型</th>
            <th>说明</th>
            <th>典型内容示例</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>技术文章</td>
            <td>深度技术解析</td>
            <td>《LVGL内存优化五步法》</td>
          </tr>
          <tr>
            <td>项目案例</td>
            <td>完整开发流程重现</td>
            <td>鸿蒙智能家居中控方案</td>
          </tr>
          <tr>
            <td>代码仓库</td>
            <td>即用型模块实现</td>
            <td>STM32+LVGL组件库</td>
          </tr>
          <tr>
            <td>视频教程</td>
            <td>硬件实操演示</td>
            <td>驱动调试技巧实录</td>
          </tr>
        </tbody>
      </table>
    </div>
  </section>

  <blockquote class="about-quote">
    "构建可触摸的智能世界" —— 这是我的技术信仰<br>
    期待与您共同探讨嵌入式技术的无限可能！
  </blockquote>
</div>

<style>
/* 基础容器样式 */
.about-container {
  max-width: 900px;
  margin: 0 auto;
  padding: 0rem 1rem;
  color: #333;
  line-height: 1.6;
}

/* 标题样式 */
.about-title {
  color: #2c3e50;
  margin: 2rem 0 1rem;
  padding-bottom: 0.5rem;
  border-bottom: 2px solid #f0f0f0;
  font-size: 1.4rem;
}

/* 技术列表样式 */
.tech-list {
  padding-left: 1.5rem;
  margin: 1rem 0;
}

.tech-list li {
  margin-bottom: 0.8rem;
  padding-left: 0.5rem;
}

.tech-list strong {
  color: #3498db;
}

/* 代码块样式 */
.code-block {
  background: #f8f9fa;
  border-radius: 8px;
  padding: 1.2rem;
  margin: 1.5rem 0;
  overflow-x: auto;
  box-shadow: 0 2px 4px rgba(0,0,0,0.05);
}

.code-block pre {
  margin: 0;
  font-family: 'SFMono-Regular', Consolas, 'Liberation Mono', Menlo, monospace;
  font-size: 0.9rem;
  line-height: 1.5;
  color: #e83e8c;
}

/* 表格样式 */
.resource-table {
  margin: 1.5rem 0;
  overflow-x: auto;
}

.resource-table table {
  width: 100%;
  border-collapse: collapse;
  box-shadow: 0 2px 5px rgba(0,0,0,0.05);
}

.resource-table th,
.resource-table td {
  padding: 0.8rem 1rem;
  text-align: left;
  border-bottom: 1px solid #eee;
}

.resource-table th {
  background-color: #f8f9fa;
  font-weight: 600;
  color: #2c3e50;
}

.resource-table tr:hover {
  background-color: #f5f7fa;
}

/* 引用样式 */
.about-quote {
  margin: 2.5rem 0;
  padding: 1.2rem 1.5rem;
  background: #f8f9fa;
  border-left: 4px solid #3498db;
  color: #555;
  font-style: italic;
  border-radius: 0 8px 8px 0;
}

/* 响应式设计 */
@media (max-width: 768px) {
  .about-container {
    padding: 1rem;
  }
  
  .resource-table th,
  .resource-table td {
    padding: 0.6rem;
    font-size: 0.9rem;
  }
  
  .code-block {
    padding: 1rem;
  }
}
</style>