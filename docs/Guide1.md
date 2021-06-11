# Guide: Quick Start

This tutorial will take you through the basic concepts and processes of using the DAC (Data Analytic Core) Industrial Internet of Things platform. Follow the tutorial. You'll use digital twins from scratch to quickly access and view real-time data based on the core capabilities of DAC.

With this tutorial, you can learn:

* Platform basic concepts
* Create a product
* Create a device
* Use a virtual sample device
* Real-time data transfer 
* View historical data

## 1. Introduction

The Luppiter IIoT platform® DAC (Data Analytic Core) provides connectivity and management capabilities for massive number of devices, provides IoT access, digital twin, algorithm management, rapid application building and other capabilities. DAC can help users simplify the complexity of massive device management and save development resources and manual operations with iWork application framework and third-party applications. DAC can be used to access IIoT devices to quickly build industrial-grade applications, form industry solutions, and improve management productivity across the board. Therefore, DAC accelerates the digital transformation of enterprises, and make Industry 4.0 a reality.

![img](https://gblobscdn.gitbook.com/assets%2F-MT00VdxHgBluCHDC3DW%2F-MT8l-RgkEFeU17lS_5B%2F-MT93puNgyoNXw3FeuGb%2F%E6%9E%B6%E6%9E%84%E5%9B%BE.png?alt=media&token=86e6603c-c9bb-4a25-bb8e-70914ce563ba)

Luppiter Industrial Internet architecture

The Industrial Internet Architecture of Luppiter ® is presented above, in which the IoT Platform Layer Is DAC. DAC offers four main competencies:

**IoT Connectivity:** DAC supports multiple protocols for multiple types of device access. DAC adopting standardize digital models to map physical world devices into digital twins.

**Data Processing and Analytics:** DAC adopts distributed big data components that provide large-scale data computing, analytics, storage capabilities, and support the rules engine.

**Fast Application Developing:** Users can use the Application Development Tool Suite to quickly and autonomously build industrial-grade applications without programming.

**AI Analytics:** DAC provides common algorithms, scene algorithms, supports custom algorithms and online training, and manages AI algorithms in collaboration with the cloud.



## 2. Start using DAC



![img](https://gblobscdn.gitbook.com/assets%2F-MT00VdxHgBluCHDC3DW%2F-MT4Lzdj7APb1CfhXYJI%2F-MT4Mrzcvm5sXa8Lhm7F%2Fimage2020-11-18_15-31-27.png?alt=media&token=ade2effc-8dc3-4fed-a74e-372463c8fbae)

As the usage process shown above, in order to start using DAC, accessing devices is required to collect and transmit data. In DAC, you first need to create a **product**-**device** as a "digital twin" of the real-world physical device in the digital world. **Product** usually refers to a collection of devices of a class with the same functional definitions or characteristics. Devices are physical device entities that belong to a product. For example, a product is a product of a certain model, and the device is a device under that model.

In this tutorial, you'll learn to connect to a sample virtual device (no real device required). Go ahead and start creating a product.



## 3. Create a product

A product is a device model, a collection of devices of a class that shares the same functional definition or characteristics. In DAC, devices are connected to DAC directly or through gateways using MQTT protocols. DAC platform and device edge layer communicate based on Topic. Product Topic includs communication Topic, thing model Topic, and custom Topic. 

Feature definitions for products include properties, events, and services. As an entity of a product, devices under that product automatically inherit Topic and features defined by the product.

In this tutorial, in order to access the virtual device of the Fanuc machine, we will create a product model of the Fanuc machine. You can choose to customize the creation manually, or directly to the import template (https://docs.zhan-wan.com/quick_start/create_product#upload_product_model).



### **3.1 Create a product manually**

**How to do it:**

1. Access to the **devices management > products**;

2. Click the **Custom Creation** button, go to the create product page.

![img](https://gblobscdn.gitbook.com/assets%2F-MT00VdxHgBluCHDC3DW%2F-MT4XiEE1EkNqGoPlcjN%2F-MT4gSmq6ymI7tNt1875%2Fimage.png?alt=media&token=5d307259-e564-4be0-a43f-b48d55518c29)

Follow the instruction to fill in the necessary product information.

![img](https://gblobscdn.gitbook.com/assets%2F-MT00VdxHgBluCHDC3DW%2F-MT4XiEE1EkNqGoPlcjN%2F-MT4gw9bmF_gYHrCaeTz%2Fimage.png?alt=media&token=a4497dba-ba61-42e8-8096-84e8718fcc16)

3. Click on **Save** to create a product.

###  3.2 Define Product Features

Once the product has been created successfully, click **View Details** to access **Product Details** for the product you have created. The product **feature definition** tab contains **properties, services, events**, which are defined as follows.

| Product Features | **Feature Definition**                                       |
| ---------------- | ------------------------------------------------------------ |
| Properties       | There are read-only properties and read-write properties. Read-only properties only support escalation from device-side updates to the platform. Read-write properties support being sent to the device side by platform updates. |
| Services         | Services can be called from the DAC platform and be performed on the device side. The most common services are reboot, emergency stop, LED change, etc. Devices will reply the results to the platform after performing the service. |
| Events           | Events can be used for reporting events information such as alarms, faults, information, etc. from device side to DAC platform. |

#### 3.2.1Define Product Properties

Based on the acquisition data of the fanuc sample virtual device, we will establish product  properties.

**Steps:**

1. Access to the **devices management > products > product details**.

2. Click the **Feature Definition** tab, click **Property** tab.

3. Click **Create a property** button. 

![img](https://gblobscdn.gitbook.com/assets%2F-MT00VdxHgBluCHDC3DW%2F-MT4jh3LHAbnZqsZOE_A%2F-MT4l012UO3fY1d1_PCb%2Fimage.png?alt=media&token=c8ec2fe7-8b0d-4cad-9d24-4f811c8fe91b)

Fill in the property information as the following image, click **Save** to create a product property called **AxisName**.

![img](https://gblobscdn.gitbook.com/assets%2F-MT00VdxHgBluCHDC3DW%2F-MT4l3DJMYixHMg2Yjeo%2F-MT4lLtHwwweMqEgAfHr%2Fimage.png?alt=media&token=3d2b4be8-0b8c-4d99-bad3-72b142ded2ec)

Follow the table below to continue creating product properties:

| Property            | **ID**              | **Data Type** | **Access** | **其他信息**                                 |
| ------------------- | ------------------- | ------------- | ---------- | -------------------------------------------- |
| AxisName            | AxisName            | text          | Read Only  |                                              |
| AbsoluteCoordinateX | AbsoluteCoordinateX | float         | Read Only  | Value range: 0-300; Step size: 0.001; Unit:/ |
| AbsoluteCoordinateY | AbsoluteCoordinateY | float         | Read Only  | Value range: 0-300; Step size: 0.001; Unit:/ |
| AbsoluteCoordinateZ | AbsoluteCoordinateZ | float         | Read Only  | Value range: 0-300; Step size: 0.001; Unit:/ |
| JinGSpeed           | JinGSpeed           | int32         | Read Only  | Value range: 0-60000; Step size: 1; Unit:/   |
| JinGFValue          | JinGFValue          | int32         | Read Only  | Value range: 0-500; Step size: 1; Unit:/     |
| RotateSpeedSValue   | RotateSpeedSValue   | int32         | Read Only  | Value range: 0-500; Step size: 1; Unit:/     |
| AxisLoad            | AxisLoad            | int32         | Read Only  | Value range: 0-500; Step size: 1; Unit:/     |
| MachiningPartsValue | MachiningPartsValue | text          | Read Only  | Data length: 100                             |

### **3.3 Import templates to automatically create products**

You can also create producta quickly by importing tproduct templates. In this section, you can download the ready-to-use product template below.

[教程产品模板guide_product.json - 3KB](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-MT00VdxHgBluCHDC3DW%2F-MT4m7FVfJxsHvO6qEv1%2F-MT4nTOV18lQtVPPzhfR%2Fguide_product.json?alt=media&token=5cf502b6-4d57-4f66-a70e-fb2013b3be74)

1. Access to **devices management > products** . Click **Import Template** button. Upload the product template you just downloaded (guide_product.json). Click **Save** button to import the template.

![img](https://gblobscdn.gitbook.com/assets%2F-MT00VdxHgBluCHDC3DW%2F-MT4m7FVfJxsHvO6qEv1%2F-MT4oLVekbuIJL-H0R0F%2Fimage.png?alt=media&token=9df0e03e-b0f5-45f8-ae6f-7e46234e71c1)

2. Click **Standard Create** button. You will find a template called Guide_Fanuc that has been added by your importing. Check the template Guide_Fanuc and click **>** button to add it to the selected templates.

![img](https://gblobscdn.gitbook.com/assets%2F-MT00VdxHgBluCHDC3DW%2F-MT4uxaBWQy18ZaXnnCR%2F-MT4vEYmrm2_2gy8FZS2%2Fimage.png?alt=media&token=bc17f8bb-9079-49ed-af48-3fd5b71282ea)

3. Check the template. Click **Save** to create a Guide_Fanuc product based on the template.

![img](https://gblobscdn.gitbook.com/assets%2F-MT00VdxHgBluCHDC3DW%2F-MT4w0LmmaEpY5B09tkr%2F-MT4wxpQNCk7hIe1_ml7%2Fimage.png?alt=media&token=ad533d75-c295-456f-b2e2-35dfddecb152)

4. After creating the Guide_Fanuc product, you can view the product details. View **Features > Property**. You will find that the product has already got the properties.

![img](https://gblobscdn.gitbook.com/assets%2F-MT00VdxHgBluCHDC3DW%2F-MT4x-IgUCQEORNgNni-%2F-MT4xnszIBkBdmCoPGLT%2Fimage.png?alt=media&token=75b958d8-18cd-404e-b819-ac9cd48c4d77)

After creating the Guide_Fanuc product, we will create a device under it. In next section, we will learn how to create a device.



## 4. Create a device

A device is an entity under a certain product. Devices under a product automatically inherit the Topic class and feature definitions defined by the product (properties, services, events).

After creating Guide_Fanuc product, you need to add a device to connect the physical device to DAC. 

**Steps:**

1. Access **devices management > devices**. Click **Add Device** button.
2. Select Guide_Fanuc product. Fill in the device name and region information.

![img](https://gblobscdn.gitbook.com/assets%2F-MT00VdxHgBluCHDC3DW%2F-MT4xsRxIDKjI7GjuWD2%2F-MT4yoWVHzh6WZkrPTEE%2Fimage.png?alt=media&token=e83d7b29-a594-4345-bae4-4bf1c0b1b1d0)

3. Click **Add** button. Add a device called Guide_Test01 under Guide_Fanuc product.

![img](https://gblobscdn.gitbook.com/assets%2F-MT00VdxHgBluCHDC3DW%2F-MT4xsRxIDKjI7GjuWD2%2F-MT4z8ZvlIVL9Yhx3_9q%2Fimage.png?alt=media&token=3dd55325-c365-4c1a-b04c-fdd6ef916e81)

Once a device has been created at DAC platform, you can configure the actual device tp access DAC. In the next section, we'll use a virtual device to send data to the platform.



## 5. Use a virtual device

After creating a product and a device on the DAC platform, an actual device can be connected to the DAC platform. In this guide, you can download and use a ready-to-use sample virtual device to represent an actual device. The virtual device will send sample data to DAC platform on a configured interval.

[下载虚拟示例设备data-gen-edu.rar - 8MB](https://firebasestorage.googleapis.com/v0/b/gitbook-28427.appspot.com/o/assets%2F-MT00VdxHgBluCHDC3DW%2F-MT5Hf6eIjR329AkC5XK%2F-MT5Hx4j0PD6lKLpzTlK%2Fdata-gen-edu.rar?alt=media&token=19f5a7a1-6227-4c55-9d91-d1d94c8978e3)

In this section, you will learn how to configure, connect, and use the sample virtual device.

### **5.1 Check device** certification

Access **Devices management > devices** and find the Guide_Test01 device you just created. Click **View** to view its device detail.

There are information about device certification on the device detail site. Click the eye icon in the device secret box to check device certification information.

![img](https://gblobscdn.gitbook.com/assets%2F-MT00VdxHgBluCHDC3DW%2F-MT4zOtwMr4QP3Q9zU8O%2F-MT51LMcEG56J_GJftEa%2Fimage.png?alt=media&token=92b0e293-8d2d-4287-a595-5b43d79757f1)

As shown below, the device certification include Product ID, Device ID, and Device Secret. You will need these information later for device layer configuration. You can click the copy icon to copy the information to your clip board.

![img](https://gblobscdn.gitbook.com/assets%2F-MT00VdxHgBluCHDC3DW%2F-MT4zOtwMr4QP3Q9zU8O%2F-MT51qoCPB8bMjUWTh9y%2Fimage.png?alt=media&token=08bc90b2-691e-4468-bfe2-9f9b33814988)



### **5.2 Configure the virtual device**

Download and unzip the virtual device data-gen-edu. Open config.yaml using Note or any editor of your choice.

You may need to change some config information acoording to the notes as showing below. 

![img](https://gblobscdn.gitbook.com/assets%2F-MT00VdxHgBluCHDC3DW%2F-MT4zOtwMr4QP3Q9zU8O%2F-MT53JIOQNcOc8K0P2QN%2Fimage.png?alt=media&token=0d0bab3b-cde1-40b3-a2dc-787f14f7ead9)

Here are the explaination of the configuration information:

| Name         | Description                                                  |
| ------------ | ------------------------------------------------------------ |
| frequency    | You can customize the interval at which virtual devices regularly send data to the platform in seconds |
| ip           | DAC platform's MQTT Server IP.                               |
| port         | DAC platform's MQTT port.                                    |
| username     | MQTT username, which is **Device ID** in device certification. |
| password     | MQTT password, which is **Device Secret** in device certification. |
| product code | **Product ID** in device certification                       |
| device code  | **Device ID** in device certification                        |



### **5.3 Start virtual device**

Save config.yaml file. Double click to run data-gen-edu application. Click **OK**, start running the sample virtual machine to send data.

![img](https://gblobscdn.gitbook.com/assets%2F-MT00VdxHgBluCHDC3DW%2F-MT53dJIfm9N3b9mDKac%2F-MT54-PERytOTe_hZ8Zo%2Fimage.png?alt=media&token=18c27225-4b73-4a0d-978e-6b5ea9d92ba9)

Now, the virtual device has start sending data. In the next step, we will receive and check the data on the DAC platform.



## 6. Receive the data at DAC

Go to DAC platform and access **devices management > devices** after starting the virtual device. Turn on Enable status to active the device. Once a device is activated, DAC will start receiving data from the device.

![img](https://gblobscdn.gitbook.com/assets%2F-MT00VdxHgBluCHDC3DW%2F-MT55TqyGE2g71ImBVb7%2F-MT56CVF-VNPK5WrWokI%2Fimage.png?alt=media&token=38a6b742-4460-46e0-a1af-389cab3a863e)

If the configuration is correct, DAC will start receiving data sent by the virtual device. The Online/Offline status of Guide_Test01 will be Online.

Access **devices management>devices>device detail** and check properties update by viewing **Thing Model Data > Property Status**.

![img](https://gblobscdn.gitbook.com/assets%2F-MT00VdxHgBluCHDC3DW%2F-MT55TqyGE2g71ImBVb7%2F-MT587MgfF20vJJg8WTv%2Fimage.png?alt=media&token=c0f5114c-6dea-4c3b-acee-e133890e1122)

You can view the history data of a property by click **View Data** action. You can also filter history data by selecting start and end time.

![img](https://gblobscdn.gitbook.com/assets%2F-MT00VdxHgBluCHDC3DW%2F-MT58IHKEG-KSIJJ3hdT%2F-MT58sbYVKp3TeSuAHLt%2Fimage.png?alt=media&token=61ae5991-b926-4db5-8480-b20d151be112)

Dac also support viewing history data chart. In the next section, we will learn how to view properties' history data chart.

## 7. View history data chart

Apart from the method mentioned in the last section, you can also view history data chart of device's properties.

Go to **Monitor > Monitoring**. You can filter product by selecting Guide_Fanuc. You will see the Guide_Test01's real-time data under Guide_Fanuc product. Click the chart icon on the upper right corner to view the history data chart.

![img](https://gblobscdn.gitbook.com/assets%2F-MT00VdxHgBluCHDC3DW%2F-MT59WT0M9OIkucf3M1P%2F-MT5BPpfOUMLSxkc0WVJ%2Fimage.png?alt=media&token=3f6b753b-63a8-42ba-922e-83056f423c3a)

Select the history time duration. Select the properties that you would like to view. For example, select AxisName, JinGSpeed, JinGFSpeed, and RotateSpeedSValue. Click **Search** and the selected properties' history chart will be presented.

![img](https://gblobscdn.gitbook.com/assets%2F-MT00VdxHgBluCHDC3DW%2F-MT59WT0M9OIkucf3M1P%2F-MT5B_TjtA1xRtiE-RTa%2Fimage.png?alt=media&token=d57779d5-271c-4ccb-b52a-9b5134d56e26)

Congratulations! Till now, you have already learned the basic operations of DAC platform. You have successfully connected a sample device and checked the history data chart.

## Next Step: More Challenges

Congratulations! You have completed the Quick Start Guide. In this guide tutorial, you have learned the basic concepts and the steps of using DAC platform. You have successfully connect a  virtual example device, created a digital twin on the DAC platform, obtained and checked the real time device data.

You can also learn:



