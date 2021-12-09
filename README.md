# ROSLab1
Сборку можно провести с помощью catkin:

`catkin_make`

---

1) Запускаем симуляцию коммандой:

`roslaunch my_turtlebot3_navigation run_navigation.launch`

2) Можно добавить в rviz следующие топики:

```
/move_base/local_costmap/footprint
/move_base/local_costmap/costmap
/move_base/DWAPlannerROS/local_plan
/move_base_simple/goal
```

3) Указываем цель и смотрим, как робот едет


