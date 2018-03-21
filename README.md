# perks
Перекодирует все файлы в текущем каталоге в нужную кодировку:

`find . -name '*.php' -exec enconv -L russian -i -x utf-8 {} ';'`
