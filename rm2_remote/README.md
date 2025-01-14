# rm2_remote

## 使用方法

1. 编译；

2. 指定串口，按遥控器型号启动对应的节点，节点会在`/rm2_remote/joy`话题下发布遥控器的消息：

    ```shell
    ros2 run rm2_remote dji_dr16 --ros-args -p serial_port:=/dev/ttyUSB0
    ```

## note

- 若未注明，模拟量范围均为-1~1，左负右正，下负上正

- 启动节点前给串口赋权：`sudo chmod 666 /dev/ttyXXX`

## 消息定义

### DT7/DR16 `dji_dr16` `sensor_msgs/joy`

消息发布频率约为 71.6Hz

需要注意：鼠标输入和摇杆输入在正常情况下灵敏度差别很大，两者的数量级可以相差数百倍，使用时多加小心

| Index | Axis         | Button                                       |
| ----- | ------------ | -------------------------------------------- |
| 0     | 右摇杆左右   | 右拨杆，上 1 下 2 中 3                       |
| 1     | 右摇杆上下   | 左拨杆，上 1 下 2 中 3                       |
| 2     | 左摇杆左右   | 鼠标左键                                     |
| 3     | 左摇杆上下   | 鼠标右键                                     |
| 4     | 拨轮         | 键盘，bit0~7 分表代表 W S A D Q E Shift Ctrl |
| 5     | 鼠标 X(左右) |                                              |
| 6     | 鼠标 Y(上下) |                                              |
| 7     | 鼠标 Z(滚轮) |                                              |