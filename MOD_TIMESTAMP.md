# 1  **Mod Timestamp**

## 1.1 **Why**

In most SLAM algorithms(Fast LIO,LIO SAM), the timestamp of a LiDAR message is assumed to be the time when the first point in the message was sampled. However, the timestamp of the LiDAR messages from Robosense driver is the time when last point sampled. Unlike the Velodyne driver, Robosense driver do not offer an option to change this to the time of the first point. Therefore, I modified this driver and provided a compile option that sets the timestamp to the first point. 

## 1.2 How

In the CMakeLists, set the variable **TIMESTAMP** to **FIRST**.

~~~cmake
#=======================================
# Custom Timestamp (FIRST, LAST)
#=======================================
set(TIMESTAMP FIRST)
~~~

In the CMakeLists, set the variable **POINT_TYPE** to **XYZIRT**.

~~~cmake
#=======================================
# Custom Point Type (XYZI, XYZIRT)
#=======================================
set(POINT_TYPE XYZIRT)
~~~

