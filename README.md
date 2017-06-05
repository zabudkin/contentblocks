## Content Blocks for Evolution CMS

Конфигурация для блоков берется из папки config. Для создания нового блока нужно создать в этой папке файл .php, который должен вернуть ассоциативный массив. Структура массива следующая:

<table>
<tr><td>title</td><td>Название блока, видимое менеджеру при заполнении</td></tr>
<tr>
<td>templates</td>
<td>
Ассоциативный массив, содержащий шаблон для ключа "owner", а также шаблоны для каждой группы полей.

Т.е. если, например, в массиве полей используется группа "images", то в шаблонах должен быть определен элемент с ключом "images", который будет содержать либо строку шаблона:

```
'images' => '<img src="[+image+]" alt="[+title+]" class="slide">'
```

либо ассоциативный массив шаблонов:

```
'images' => [
  'item'  => '<img src="[+image+]" alt="[+title+]" class="slide">',
  'thumb' => '<div class="thumb" style="background-image: url([+image+])"></div>',
],
```

Во втором случае вывод этих элементов в родительском шаблоне можно использовать как "[+images.item+]" и "[+images.thumb+]".
</td>
</tr>
<tr>
<td>fields</td>
<td>
Ассоциативный массив используемых полей, в котором ключами являются идентификаторы полей, а значениями - массивы опций этих полей.

Возможные опции приведены ниже.
</td>
</tr>
</table>
