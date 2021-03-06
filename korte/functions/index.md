---
layout: default
title: Functions
title_prefix: KorTE
fa-icon: fas fa-redo
priority: 2
---

KorTE include some basic functions by default.

{% include toc_include.md max_level=2 %}

{% raw %}

## CYCLE

This functions allows to pick a value in a list in a cyclic way:

```liquid
assertEquals("a", Template("{{ cycle(['a', 'b'], 2) }}")())
assertEquals("b", Template("{{ cycle(['a', 'b'], -1) }}")())
```

## RANGE

Along the `..` operator, allows you to create a range and to specify a custom step instead of the default 1.

```liquid
assertEquals("[0, 1, 2, 3]", Template("{{ 0..3 }}")())
assertEquals("[0, 1, 2, 3]", Template("{{ range(0,3) }}")())
assertEquals("[0, 2]", Template("{{ range(0,3,2) }}")())
```

## PARENT

This function is used inside a `{% block %}` block when used in inheritance to place the content of the block defined in ancestors. Acts like a `super.myblock()` in kotlin.

```liquid
{% block myblock %}
    Before the default content
    {{ parent() }}
    After the default content
{% endblock %}
```

{% endraw %}