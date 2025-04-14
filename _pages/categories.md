---
layout: default
title: 分类归档
---

<div class="categories-container">
  {% for category in site.categories %}
    <section class="category-section" id="{{ category[0] | slugify }}">
      <div class="category-header">
        <h2 class="category-title">
          <span class="category-icon">📂</span>
          {{ category[0] }}
        </h2>
        <span class="post-count">{{ category[1] | size }} 篇文章</span>
      </div>
      
      <div class="post-grid">
        {% for post in category[1] %}
          <article class="post-card">
            <a href="{{ post.url }}" class="post-link">
              <h3 class="post-title">
                <span class="title-text">{{ post.title }}</span>
                <span class="hover-arrow">→</span>
              </h3>
              <div class="post-meta">
                <time class="post-date">{{ post.date | date: "%Y年%m月%d日" }}</time>
                {% if post.tags %}
                  <span class="post-tags">
                    {% for tag in post.tags limit:3 %}
                      <span class="tag">{{ tag }}</span>
                    {% endfor %}
                  </span>
                {% endif %}
              </div>
              {% if post.excerpt %}
                <p class="post-excerpt">{{ post.excerpt | strip_html | truncate: 100 }}</p>
              {% endif %}
            </a>
          </article>
        {% endfor %}
      </div>
    </section>
  {% endfor %}
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
.categories-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem 1rem;
}

/* 分类标题区域 */
.category-header {
  display: flex;
  align-items: baseline;
  justify-content: space-between;
  margin-bottom: 1.5rem;
  padding-bottom: 0.75rem;
  border-bottom: 2px solid #f0f0f0;
}

.category-title {
  font-size: 1.75rem;
  color: #2c3e50;
  margin: 0;
  display: flex;
  align-items: center;
}

.category-icon {
  margin-right: 0.8rem;
  font-size: 1.5rem;
}

.post-count {
  font-size: 0.9rem;
  color: #7f8c8d;
  background: #f5f5f5;
  padding: 0.3rem 0.8rem;
  border-radius: 1rem;
}

/* 文章网格布局 */
.post-grid {
  display: grid;
  gap: 1.5rem;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  margin-bottom: 3rem;
}

/* 文章卡片样式 */
.post-card {
  background: white;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 3px 10px rgba(0, 0, 0, 0.08);
  transition: all 0.3s ease;
  height: 100%;
}

.post-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.12);
}

.post-link {
  display: block;
  padding: 1.5rem;
  text-decoration: none; /* 去除下划线 */
  color: inherit;
  height: 100%;
  box-sizing: border-box;
}

/* 文章标题动效 */
.post-title {
  font-size: 1.2rem;
  margin: 0 0 0.8rem 0;
  color: #3498db;
  line-height: 1.4;
  display: flex;
  justify-content: space-between;
  align-items: center;
  transition: all 0.3s ease;
}

.title-text {
  flex: 1;
}

.hover-arrow {
  opacity: 0;
  transform: translateX(-10px);
  color: #e74c3c;
  font-weight: bold;
  transition: all 0.3s ease;
  margin-left: 0.5rem;
}

.post-card:hover .hover-arrow {
  opacity: 1;
  transform: translateX(0);
}

.post-card:hover .post-title {
  color: #2980b9;
  text-decoration: none; /* 去除下划线 */
}

/* 文章元信息 */
.post-meta {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1rem;
  font-size: 0.85rem;
}

.post-date {
  color: #7f8c8d;
}

.post-tags {
  display: flex;
  gap: 0.5rem;
}

.tag {
  background: #f0f7ff;
  color: #3498db;
  padding: 0.2rem 0.6rem;
  border-radius: 1rem;
  font-size: 0.75rem;
  text-decoration: none; /* 去除标签下划线 */
}

.post-excerpt {
  color: #555;
  font-size: 0.95rem;
  line-height: 1.6;
  margin: 0;
}

/* 响应式设计 */
@media (max-width: 768px) {
  .post-grid {
    grid-template-columns: 1fr;
  }
  
  .category-header {
    flex-direction: column;
    align-items: flex-start;
    gap: 0.5rem;
  }
}
</style>
