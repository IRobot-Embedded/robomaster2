# rmos-ec-remote

遥控器的 ROS2 节点封装

## 使用方法

按遥控器型号启动对应的节点，节点会在`/rmos_ec_remote/joy`话题下发布遥控器的消息，类型为`sensor_msgs/msg/Joy`

## 注意事项

- 若未注明，模拟量范围均为-1~1，左负右正，下负上正

- 启动节点前先设置好对应节点的配置文件，配置文件路径为`config/*.yaml`

- 启动节点前先给串口赋权：`sudo chmod 666 /dev/ttyXXX`

## 消息定义

### DT7/DR16

消息发布频率约为 71.6Hz

| Index | Axis       | Button                                       |
| ----- | ---------- | -------------------------------------------- |
| 0     | 右摇杆左右 | 右拨杆，上 1 下 2 中 3                       |
| 1     | 右摇杆上下 | 左拨杆，上 1 下 2 中 3                       |
| 2     | 左摇杆左右 | 鼠标左键                                     |
| 3     | 左摇杆上下 | 鼠标右键                                     |
| 4     | 拨轮       | 键盘，bit0~7 分表代表 W S A D Q E Shift Ctrl |
| 5     | 鼠标 X     |                                              |
| 6     | 鼠标 Y     |                                              |
| 7     | 鼠标 Z     |                                              |