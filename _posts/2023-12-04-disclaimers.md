---
layout: post
is_post: true
title: "Jekyll - Создание дисклеймера для постов"
date: 2023-12-04 00:00:00 +0500
author: msun_
intro-image:
disclaimer: []
---

### Финальный результат:

{% include disclaimer.html
text="Пример дисклеймера. В статье вы научитесь создавать кастомизируемые дисклеймеры для Jekyll-блога."
%}

### Как это устроено

Jekyll поддерживает include файлы, которые представляют из себя кусок html файла, которй в свою очередь можно использовать в любом месте в .md файлах используя язык шаблонов Liquid.

Для начала нужно создать папку "\_includes" и в ней же создать файл "disclaimer.html".
В файле расположить этот код:

{% highlight html %}
{% raw %}

<div class="disclaimer">
    <p><i> {{ include.text }} </i></p>
</div>

{% endraw %}
{% endhighlight%}

"div" тэг может быть абсолютно любым, самое главное добавить <br>{% raw %} {{ include.text }} {% endraw %} переменную.
Также можно добавить другие переменные по типу {% raw %} {{ include.имя_переменной }} {% endraw %}. Например ссылку на изображение для {% raw %} <img> {% endraw %} тэга и тд и тп.

Теперь в этой же папке ("\_includes") можно создавать сами дисклеймеры с расширением .html. Пример дисклеймера:

{% highlight html %}
{% raw %}

{% include disclaimer.html
text="I'm too lazy to translate this article.<br> Too bad!"
%}

{% endraw %}
{% endhighlight%}

В этом файле мы генерируем уже полный html-код дисклеймера с text переменной.
В самом сайте код этого шаблона будет выглядеть так:

{% highlight html %}
{% raw %}

<div class="disclaimer">
    <p><i> I'm too lazy to translate this article.<br> Too bad! </i></p>
</div>

{% endraw %}
{% endhighlight%}

### Как использовать

Чтобы было проще использовать дисклеймеры в блог-постах я сделал специальную переменную массива в шаблоне поста: "disclaimer: []"
и добавил кусок кода, который добавляет каждый дисклеймер в пост из пременной "disclaimer". В самом посте остается
добавить название дисклеймеров, которые хотите использовать.

Код, добавленный в "/_layouts/posts.md", который добавляет дисклеймеры:

{% highlight html %}
{% raw %}

{% for disclaimer in page.disclaimer %}
    {% include {{ disclaimer | append: ".html" }}  %}
{% endfor %}

{% endraw %}
{% endhighlight%}

Этот код проходит по массиву disclaimer и добавляет каждый ранее созданный нами дисклеймер в наш блог-пост. 
При добавлении дисклеймера в переменную поста писать расширение не нужно - код делает это за нас.

Удачи!