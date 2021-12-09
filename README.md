# ROSLab1
Сборку можно провести с помощью catkin. Переходим в директорию с исходниками и инициализируем воркспейс:

`cd src`

`catkin_init_workspace`

Потом собираем:

`cd ..`

`catkin_make`

---

1) Предварительно* необходимо построить приближённую карту местности. Для этого нужно запустить построение карты с помощью launch файла:

`roslaunch my_turtlebot3_navigation run_slam.launch`

2) Немного поездить и сохранить карту:

`rosrun map_server map_saver -f ~/ROSLab_2.git/src/my_turtlebot3_navigation/maps/room_map`

3) Далее мы возвращаем всё к изначальному состоянию, как было до 1 и 2 шага и снова запускаем launch файл:

`roslaunch my_turtlebot3_navigation run_navigation.launch`

4) Указываем цель и смотрим, как робот едет


*пока что алгоритм такой.. 
