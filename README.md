# ROSLab1
Сборку можно провести с помощью catkin. Переходим в директорию с исходниками и инициализируем воркспейс:

`cd src`

`catkin_init_workspace`

Потом собираем:

`cd ..`

`catkin_make`

---

1) Предварительно*\ необходимо построить приближённую карту местности. Для этого нужно раскомментировать следующие строчки в launch файле:

```xml
	<!-- <arg name="slam_methods" default="gmapping" doc="slam type [gmapping, cartographer, hector, karto, frontier_exploration]"/>
	<include file="$(find turtlebot3_slam)/launch/turtlebot3_slam.launch">
		<arg name="model" default="$(arg model)"/>
		<arg name="slam_methods" default="$(arg slam_methods)"/>
		<arg name="configuration_basename" default="turtlebot3_lds_2d_gazebo.lua"/>
		<arg name="open_rviz" default="true"/>
	</include> 
  <include file="$(find turtlebot3_teleop)/launch/turtlebot3_teleop_key.launch"/> -->
```

2) Закомментировать:

```xml
  <include file="$(find turtlebot3_navigation)/launch/turtlebot3_navigation.launch">
    <arg name="model" default="$(arg model)"/>
    <arg name="map_file" default="$(arg map_file)"/>
  </include>
```

3) Чтобы запустить построение карты необходимо запустить launch файл:

`roslaunch my_turtlebot3_slam turtlebot3_empty_world.launch`

4) Немного поездить и сохранить карту:

`rosrun map_server map_saver -f ~/ROSLab_2.git/src/my_turtlebot3_slam/maps/room_map`

*\пока что алгоритм такой.. 

5) Далее мы возвращаем всё к изначальному состоянию, как было до 1 и 2 шага и снова запускаем launch файл:

`roslaunch my_turtlebot3_slam turtlebot3_empty_world.launch`

6) Указываем цель и смотрим, как робот едет

