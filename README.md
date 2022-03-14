## Laboratory work I

Данная лабораторная работа посвещена изучению утилит для разработки проектов


## Homework

1. Скачайте библиотеку *boost* с помощью утилиты **wget**. Адрес для скачивания `https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz`.
- wget -O boost_1_69_0.tar.gz https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
2. Разархивируйте скаченный файл в директорию `~/boost_1_69_0`
- tar -xvf boost_1_69_0.tar.gz 
3. Подсчитайте количество файлов в директории `~/boost_1_69_0` **не включая** вложенные директории.
- find . -maxdepth 1 -type d | wc
4. Подсчитайте количество файлов в директории `~/boost_1_69_0` **включая** вложенные директории.
- tree 
5. Подсчитайте количество заголовочных файлов, файлов с расширением `.cpp`, сколько остальных файлов (не заголовочных и не `.cpp`).
- find -name "*.cpp" | wc -l
- find -name "*.hpp" | wc -l 
- find -name "*.h" | wc -l
- find . -not(-name "*.cpp" -o -name "*.hpp" -o -name "*.h"\) | wc -l
6. Найдите полный пусть до файла `any.hpp` внутри библиотеки *boost*.
- find ~/boost_1_69_0 -name any.hpp  
7. Выведите в консоль все файлы, где упоминается последовательность `boost::asio`.
- grep -rl «boost::asio»  
8. Скомпилируйте *boost*. Можно воспользоваться [инструкцией](https://www.boost.org/doc/libs/1_61_0/more/getting_started/unix-variants.html#or-build-custom-binaries) или [ссылкой](https://codeyarns.com/2017/01/24/how-to-build-boost-on-linux/).
- ./bootstrap.sh —prefix=boost_output ; ./b2 install 
9. Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию `~/boost-libs`.
- mv /home/user/boost_1_69_0/libs home/user/boost_libs
10. Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.
- find . -type f -exec du -h {} +  
11. Найдите *топ10* самых "тяжёлых".
- find -type f -exec du -Sh {} + | sort -rh | head -n 10  

```
Copyright (c) 2015-2021 The ISC Authors
```
