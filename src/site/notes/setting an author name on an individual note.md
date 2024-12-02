---
{"dg-publish":true,"author":{"name":"Fake Porsen"},"permalink":"/setting-an-author-name-on-an-individual-note/","dgPassFrontmatter":true,"noteIcon":"","created":"2024-12-02T08:51:34.695-06:00","updated":"2024-12-02T14:41:10.503-06:00"}
---

this should include an author name if i did this correctly. the name is set in the properties for each individual note. 

steps to accomplish this:
1. select "allow all front matter to pass through" (BE CAREFUL)
2. add the following code to note.njk:
```
{%- if author.name -%}
<div> <span class="author">{{author.name}}</span></div>
{%- endif -%}
```

the above code should go AFTER this line:
```
<div><i icon-name="calendar-clock"></i> <span class="human-date" data-date="{{updated}}"></span></div>
{%- endif -%}
```

so that it now looks like this:
```
<div><i icon-name="calendar-clock"></i> <span class="human-date" data-date="{{updated}}"></span></div>
{%- endif -%}
{%- if author.name -%}
<div> <span class="author">{{author.name}}</span></div>
{%- endif -%}

```

3. then, on an obsidian note, add the following to the frontmatter:
```
author: {
	name: "Fake Porsen"}
```

