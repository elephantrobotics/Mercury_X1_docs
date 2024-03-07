# 7 机械臂使用场景案例

本章节呈现了经典的机械臂使用案例，以展示产品在富有代表性的场景中的应用。这包括了机械臂在不同领域的典型应用，突显了产品的多功能性和适用性。通过这些案例，用户可以深入了解机械臂在实际应用中的灵活性和效能，为他们在特定场景中的应用提供参考。

**1、画画案例：**

```python
from pymycobot.mycobot import MyCobot
import time
import math

# 创建 MyCobot 实例，指定串口和波特率
mc = MyCobot('COM3',115200)

# 发送目标坐标点，使机械臂移动到指定位置
mc.send_coords([52.9, -64.4, 409.7, -91.23, -0.25, -89.81], 50, 0)
# 暂停 2 秒
time.sleep(2)

# 发送目标坐标点，使机械臂移动到另一个指定位置
mc.send_coords([21.5, 145.5, 233.6, -89.72, 19.19, 13.45], 50, 0)
# 暂停 2 秒
time.sleep(2)

# 循环发送目标坐标点，使机械臂按圆形轨迹运动
for i in range(1, 361):
    x = 21.5 + 30 * math.cos(i / 180.0 * math.pi)
    y = 145.5 + 30 * math.sin(i / 180.0 * math.pi)
    mc.send_coords([x, y, 233.6, -89.72, 19.19, 13.45], 100, 0)
    # 暂停 0.7 秒
    time.sleep(0.7)

# 发送目标坐标点，使机械臂回到初始位置
mc.send_coords([52.9, -64.4, 409.7, -91.23, -0.25, -89.81], 50, 0)
‵‵‵

**2、跳舞案例:**

```python
from pymycobot.mycobot import MyCobot
import time

if __name__ == '__main__':
    # 创建 MyCobot 实例，指定串口和波特率
    mc = MyCobot('COM3',115200)

    # 设置开始开始时间
    start = time.time()
    # 让机械臂到达指定位置
    mc.send_angles([-1.49, 115, -153.45, 30, -33.42, 137.9], 80)
    # 判断其是否到达指定位置
    while not mc.is_in_position([-1.49, 115, -153.45, 30, -33.42, 137.9], 0):
        # 让机械臂恢复运动
        mc.resume()
        # 让机械臂移动0.5s
        time.sleep(0.5)
        # 暂停机械臂移动
        mc.pause()
        # 判断移动是否超时
        if time.time() - start > 3:
            break
    # 设置开始时间
    start = time.time()
    # 让运动持续30秒
    while time.time() - start < 30:
        # 让机械臂快速到达该位置
        mc.send_angles([-1.49, 115, -153.45, 30, -33.42, 137.9], 80)
        # 将灯的颜色为[0,0,50]
        mc.set_color(0, 0, 50)
        time.sleep(0.7)
        # 让机械臂快速到达该位置
        mc.send_angles([-1.49, 55, -153.45, 80, 33.42, 137.9], 80)
        # 将灯的颜色为[0,50,0]
        mc.set_color(0, 50, 0)
        time.sleep(0.7)
```

**3、木块搬运案例：**

```python
from pymycobot import PI_PORT, PI_BAUD
import time
def gripper_test(mc):
    print("Start check IO part of api\n")
    # 检测夹爪是否正在移动
    flag = mc.is_gripper_moving()
    print("Is gripper moving: {}".format(flag))
    time.sleep(1)

    # Set the current position to (2048).
    # Use it when you are sure you need it.
    # Gripper has been initialized for a long time. Generally, there
    # is no need to change the method.
    # mc.set_gripper_ini()
    # 设置关节点1，让其转动到2048这个位置
    mc.set_encoder(1, 2048)
    time.sleep(2)
    # 设置六个关节位，让机械臂以20的速度转动到该位置

    mc.set_encoders([1024, 1024, 1024, 1024, 1024, 1024], 20)
    # mc.set_encoders([2048, 2900, 2048, 2048, 2048, 2048], 20)
    # mc.set_encoders([2048, 3000,3000, 3000, 2048, 2048], 50)
    time.sleep(3)
    # 获取关节点1的位置信息
    print(mc.get_encoder(1))
    # 设置夹爪转动到2048这个位置
    mc.set_encoder(7, 2048)
    time.sleep(3)
    # 设置夹爪让其转到1300这个位置
    mc.set_encoder(7, 1300)
    time.sleep(3)

    # 以70的速度让夹爪到达2048状态，2048会报错，故改成255
    mc.set_gripper_value(255, 70)
    time.sleep(3)
    # 以70的速度让夹爪到达1500状态，1500会报错，故改成255
    mc.set_gripper_value(255, 70)
    time.sleep(3)
   
    num=5
    while num>0:
        # 设置夹爪的状态，让其以70的速度快速打开爪子
        mc.set_gripper_state(0, 70)
        time.sleep(3)
        # 设置夹爪的状态，让其以70的速度快速收拢爪子
        mc.set_gripper_state(1, 70)
        time.sleep(3)
        num-=1

    # 获取夹爪的值
    print("")
    print(mc.get_gripper_value())
    # mc.release_all_servos()

if __name__ == "__main__":
    # 创建 MyCobot 实例，指定串口和波特率
    mc = MyCobot('COM3',115200)

    mc.set_encoders([2048, 2048, 2048, 2048, 2048, 2048], 20)
    time.sleep(3)
    gripper_test(mc)

```