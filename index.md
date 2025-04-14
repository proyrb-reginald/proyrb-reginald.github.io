---
layout: default
title: 本站首页
---

<div class="articles-container">
  <!-- 置顶文章区域 -->
  <section class="pinned-section">
    <h2 class="section-title">🌟 精选推荐</h2>
    <div class="pinned-grid">
      {% for post in site.posts %}
        {% if post.pin == true %}
          <article class="pinned-card">
            <a href="{{ post.url }}" class="post-link">
              <div class="post-header">
                <h3 class="post-title">{{ post.title }}</h3>
                <time class="post-date">{{ post.date | date: "%Y年%m月%d日" }}</time>
              </div>
              {% if post.excerpt %}
                <p class="post-excerpt">{{ post.excerpt | strip_html | truncate: 150 }}</p>
              {% endif %}
              {% if post.tags %}
                <div class="post-tags">
                  {% for tag in post.tags limit:5 %}
                    <span class="tag">{{ tag }}</span>
                  {% endfor %}
                </div>
              {% endif %}
            </a>
          </article>
        {% endif %}
      {% endfor %}
    </div>
  </section>

  <!-- 最新文章列表 -->
  <section class="latest-section">
    <h2 class="section-title">📰 最新文章</h2>
    <div class="latest-list">
      {% for post in site.posts %}
        {% unless post.pin == true %}
          <article class="latest-card">
            <a href="{{ post.url }}" class="post-link">
              <div class="post-header">
                <h3 class="post-title">{{ post.title }}</h3>
                <time class="post-date">{{ post.date | date: "%Y年%m月%d日" }}</time>
              </div>
              {% if post.excerpt %}
                <p class="post-excerpt">{{ post.excerpt | strip_html | truncate: 150 }}</p>
              {% endif %}
              {% if post.tags %}
                <div class="post-tags">
                  {% for tag in post.tags %}
                    <span class="tag">{{ tag }}</span>
                  {% endfor %}
                </div>
              {% endif %}
            </a>
          </article>
        {% endunless %}
      {% endfor %}
    </div>
  </section>
</div>

<style>
/* 确保所有链接和交互元素都没有下划线 */
a.post-link,
a.post-link:hover,
a.post-link:focus,
a.post-link:active,
a.post-link:visited {
  text-decoration: none !important;
}

/* 确保内部所有文本元素都没有下划线 */
.post-link * {
  text-decoration: none !important;
}

/* 基础样式 */
.articles-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem 1rem;
}

.section-title {
  color: #2c3e50;
  margin: 0 0 1.5rem 0;
  padding-bottom: 0.75rem;
  border-bottom: 2px solid #f0f0f0;
  font-size: 1.5rem;
}

/* 置顶文章样式 - 更新为与最新文章统一 */
.pinned-grid {
  display: grid;
  gap: 1.5rem;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  margin-bottom: 3rem;
}

.pinned-card {
  background: white;
  border-radius: 8px;
  padding: 1.5rem;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
  transition: all 0.2s ease;
}

.pinned-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

/* 最新文章样式 */
.latest-list {
  display: grid;
  gap: 1rem;
}

.latest-card {
  background: white;
  border-radius: 8px;
  padding: 1.5rem;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
  transition: all 0.2s ease;
}

.latest-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
}

/* 共用文章元素样式 */
.post-link {
  display: block;
  text-decoration: none;
  color: inherit;
  height: 100%;
}

.post-header {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  margin-bottom: 0.8rem;
}

.post-title {
  color: #3498db;
  margin: 0;
  transition: color 0.2s ease;
  font-size: 1.1rem;
  letter-spacing: 0.05em; /* 新增：增加中文字符间距 */
}

.post-link:hover .post-title {
  color: #2980b9;
}

.post-date {
  color: #7f8c8d;
  font-size: 0.85rem;
}

.post-tags {
  display: flex;
  gap: 0.5rem;
  margin-top: 0.8rem;
  flex-wrap: wrap;
}

.tag {
  background: #f0f7ff;
  color: #3498db;
  padding: 0.2rem 0.6rem;
  border-radius: 1rem;
  font-size: 0.75rem;
  border: 1px solid #d6e9ff;
  transition: all 0.2s ease;
}

.post-link:hover .tag {
  background: #e1f0ff;
  border-color: #b3d7ff;
}

.post-excerpt {
  color: #555;
  font-size: 0.95rem;
  line-height: 1.6;
  margin: 0;
}

/* 响应式设计 */
@media (max-width: 768px) {
  .pinned-grid {
    grid-template-columns: 1fr;
  }
  
  .post-header {
    flex-direction: column;
    align-items: flex-start;
    gap: 0.3rem;
  }
  
  .post-date {
    margin-top: 0.3rem;
  }
}

</style>
