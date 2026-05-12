---
layout: page
title: "Archive"
permalink: /archive/
description: "Full archive of all journal entries."
---

<section>
  <div class="ledger-columns" style="margin-bottom:0">
    <div class="col-header date">Date</div>
    <div class="col-header title">Entry</div>
    <div class="col-header cat">Account</div>
  </div>

  <table class="ledger-table" aria-label="Full archive">
    <thead class="visually-hidden">
      <tr><th>Date</th><th>Title</th><th>Category</th></tr>
    </thead>
    <tbody>
      {% assign posts_by_year = site.posts | group_by_exp: "post", "post.date | date: '%Y'" %}
      {% for year_group in posts_by_year %}
        <tr>
          <td colspan="3" style="background: var(--accent-light, #e8f5ed); font-family: monospace; font-weight: 700; color: #1a4731; padding: 0.5rem 1rem; border-bottom: 2px solid #c5ddd0;">
            FY {{ year_group.name }}
          </td>
        </tr>
        {% for post in year_group.items %}
        {% assign words = post.content | number_of_words %}
        {% assign reading_time = words | divided_by: 200 | plus: 1 %}
        <tr class="ledger-row">
          <td class="col-date">{{ post.date | date: "%d %b" }}</td>
          <td class="col-title">
            <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
          </td>
          <td class="col-category">
            {% if post.categories.size > 0 %}
              <span class="tag">{{ post.categories | first }}</span>
            {% elsif post.tags.size > 0 %}
              <span class="tag">{{ post.tags | first }}</span>
            {% endif %}
          </td>
        </tr>
        {% endfor %}
      {% endfor %}
    </tbody>
  </table>
</section>
