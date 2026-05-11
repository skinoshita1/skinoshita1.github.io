---
layout: single
title: "Other Projects"
permalink: /other-projects/
header:
  overlay_color: "#2d4a3e"
  overlay_filter: 0.4
  overlay_image: /assets/images/header-other.jpeg
---

A collection of work and interests outside my main research and professional focus.

---

## Writing

I write occasionally on climate, energy, and related topics on 
[Substack](https://satowa.substack.com). Posts range from commentary on climate 
innovation to reflections on the intersection of science, finance, and policy.


<div id="substack-feed">Loading posts...</div>

<script>
async function loadSubstackPosts() {
  const feed = document.getElementById('substack-feed');
  try {
    const response = await fetch(
      'https://api.rss2json.com/v1/api.json?rss_url=https://satowa.substack.com/feed'
    );
    const data = await response.json();
    
    if (data.status !== 'ok') throw new Error('Feed failed');
    
    const html = data.items.slice(0, 3).map(post => {
      const date = new Date(post.pubDate).toLocaleDateString('en-US', {
        year: 'numeric', month: 'long', day: 'numeric'
      });
      return `
        <div style="margin-bottom: 1.5rem; padding-bottom: 1.5rem; border-bottom: 1px solid #eee;">
          <div style="font-size: 0.85rem; color: #888; margin-bottom: 0.3rem;">${date}</div>
          <a href="${post.link}" target="_blank" rel="noopener" 
             style="font-size: 1.1rem; font-weight: bold; text-decoration: none;">
            ${post.title}
          </a>
          <p style="margin-top: 0.5rem; color: #555; font-size: 0.95rem;">
            ${post.description.replace(/<[^>]+>/g, '').slice(0, 150)}...
          </p>
          <a href="${post.link}" target="_blank" rel="noopener">Read on Substack →</a>
        </div>
      `;
    }).join('');
    
    feed.innerHTML = html;
  } catch (error) {
    feed.innerHTML = '<p>Could not load posts. <a href="https://satowa.substack.com">Visit Substack directly →</a></p>';
  }
}

loadSubstackPosts();
</script>
---

## Media

I'm building this out gradually — check back for photography, creative projects, 
and other interests here or on [Instagram](https://www.instagram.com/fieldnotes_bysatowa/).
