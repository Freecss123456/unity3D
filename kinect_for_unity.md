参考：http://blog.csdn.net/dingxiaowei2013/article/details/18402979 \

#-*-简介-*-\
    Kinect有三个镜头，中间的镜头是 RGB 彩色摄影机，用来采集彩色图像。左右两边镜头则分别为红外线发射器和红外线CMOS 摄影机所构成的3D结构光深度感应器，用来采集深度数据。彩色摄像头最大支持1280*960分辨率成像，红外摄像头最大支持640*480成像。Kinect还搭配了追焦技术，底座马达会随着对焦物体移动跟着转动。Kinect也内建阵列式麦克风，由四个麦克风同时收音，比对后消除杂音，并通过其采集声音进行语音识别和声源定位。 \
    Kinect坐标系：
![KinectCoordinate](https://github.com/Freecss123456/unity3D/blob/master/image/kinect2.0%E5%9D%90%E6%A0%87%E7%B3%BB.png)


#-*-内置函数-*-\
    UserDetected() 当一个新的用户被检测到的时候invoked，这个可以用来启动姿势识别 
    UserLost() 当用户消失的时候invoked 这个可以被用来清理或者释放资源，但你不需要特意停止在之前加上的姿势识别  \
    GestureInProgress() 当姿势初始状态被检测的时候invoked，但是姿势并没有完成或者取消，这个可以被用来报告姿势的进程或者姿势按照预期的精确完成状况，例如人物的走路或者跑步姿势  
    GestureGompleted() 姿势被完成的时候invoked，你可以在这里使用姿势识别，和决定是否需要重新设置新的姿势（比如重启检测）  
    GestureCancelled() 如果姿势别取消时候invoked，姿势的取消是由姿势检测路径来决定的，如果没有在规定时间内按照姿势检测路径完成姿势，那么这个姿势就会取消，你也可以在这里设定是否需要重新设置新的姿势（比如重启检测）  
    
#-*-现在默认能识别的姿势-*-
RaiseRightHand/RaiseLeftHand 抬起左右手高于肩膀一秒

Psi 举起双手高于肩膀一秒

Tpose T姿势

Stop 右手放下，左手缓慢贴住身侧（腰以下）或者左右调换

Wave 挥手 左右都行

SwipeLeft 右手挥向左侧

SwipeRight 与上面相反

SwipeUp/SwipeDown 左右都行 上下翻动

ZoomOut 一开始左右手合并放在前面，然后向不同方向分开

ZoomIn 一开始两手相距0.7米以上并放在前面，然后慢慢合并

Wheel 左右手在前面相距肩膀宽度距离，软后抓住假想方向盘转动

Jump 在1.5秒内屁股至少在高度上上升了10cm

Squat 蹲下 在1.5秒内屁股至少在高度上下降了10cm

Push 用左手或者右手在1.5秒内向前推

Pull 用左手或者右手在1.5秒内后拉

LeanLeft 右侧肩向前，也就是向左侧身

LeanRight 与上面相反

KickLeft 向前踢左脚

KickRight 向前踢右脚

#-*-kinect识别关节对照图-*-\
参考网址：http://www.bubuko.com/infodetail-2104441.html
![jointMap](https://github.com/Freecss123456/unity3D/blob/master/image/kinect_Joints.png)
