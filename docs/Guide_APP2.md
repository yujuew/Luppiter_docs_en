# Guide: Build applications without coding

In addition to IoT data acquisition, storage, and analytics capabilities, the Luppiter Industrial IoT platform provides the ability to build industrial-grade applications quickly without any coding.

This tutorial will show you how to use 2D Configuration's basic usage. Following this tutorial, you'll quickly build a simple device monitoring dashboard application based on the devices which were created in the Quick Start tutorial.



You will learn these below by this guide:

- What is 2D Configuration
- Binding device data
- Interaction events of 2D Configuration
- Building industrial applications quickly
- Viewing and sharing applications made by 2D Configuration



## **1.Understand and create 2D Configuration**



### **1.1 Introduction of 2D Configuration**

Luppiter industrial IoT platform provides confiuration functions which combine data control and management without the participation of professional programmers. Data twin biological model and 2D graphics model can be perfect docking by draging the graphical elements of 2D configuration, which could be changed anytime according to different needs. 2D Configuration introduces the industrial data which was generated in the production process into the digital management system, which achieved the docking of industrial data and software data.

Users can build SCADA monitoring dashboard, HMI edge side applications, large-screen dashboard, data reports and other industrial applications quickly by using 2D configuration.

In this tutorial, we'll quickly build a simple device monitoring dashboard application based on the devices which were created in the Quick Start tutorial.



### **1.2 Create a 2D Configuration**

Firstly, we need to create a 2D Configuration.



Steps:

1) Enter Operation and Maintenance Monitoring > 2D Configuration, the completed 2D Configuration list can be viewed here.

![image2021-6-10_9-40-37.png](http://192.168.3.128:8090/download/attachments/12550374/image2021-6-10_9-40-37.png?version=1&modificationDate=1623289236000&api=v2)



2)Click "Save" to create 2D Configuration model.



We are going to learn the basic usage of 2D Configuration.





## **2. Basic usage of 2D Configuration**



We are going to build a simple device status monitoring application.



### 2.1Basic Operations

**Steps:**

1) Click "Configuration" to get into the drawing and configuration page.

![img](http://192.168.3.128:8090/download/attachments/12550374/image2021-6-10_10-1-12.png?version=1&modificationDate=1623290472143&api=v2)



2)The components can be modified, combined, drawn by dragging operation. Here we can drag out a rectangle, adjust the size and color of it to make it a box.

![img](http://192.168.3.128:8090/download/attachments/12550374/image2021-6-10_10-7-57.png?version=1&modificationDate=1623290878348&api=v2)



### **2.2 Binding data source**

Drag out a "Text" component on the left side, select the "Text" component and click "Configure the data source" on the right side to bind the device's property data parameters.

![img](http://192.168.3.128:8090/download/attachments/12550374/image2021-6-10_10-15-43.png?version=1&modificationDate=1623291343457&api=v2)



Click "Confirm" to save the configuration, we can see that the "Text" component is bound to the device's real-time data now.

![img](http://192.168.3.128:8090/download/attachments/12550374/image2021-6-10_10-24-36.png?version=1&modificationDate=1623291876923&api=v2)



### **2.3 Add data chart**

Drag out a "Line chart" component and click "Configure the data source" to select products, devices, and properties for binding presentation.

![img](http://192.168.3.128:8090/download/attachments/12550374/image2021-6-10_10-29-34.png?version=1&modificationDate=1623292174158&api=v2)



Click "Confirm" to bind real-time and historical data to the "Line chart" component.

![img](http://192.168.3.128:8090/download/attachments/12550374/image2021-6-10_10-31-57.png?version=1&modificationDate=1623292317200&api=v2)



We will learn to create an interactive event in the next tutorial.



## 3.Interactive event

### **3.1 The Introduction of interactive event**



Luppiter 2D Configuration provides flexible interaction event configurations.

| Concept     | Explanation                                                  | Object             | Relationships and number limitations                         |
| :---------- | :----------------------------------------------------------- | :----------------- | :----------------------------------------------------------- |
| Interaction | Select the component to configure the interaction for it. Interactions are triggered by events, and when all conditions are met, a series of actions are raised. | Selected component | A component can configure multiple interactions              |
| Event       | Events are actions that trigger interaction, and support events include: value change, click, double-click, move in, move out. | Selected component | An interaction is raised by an event                         |
| Condition   | Conditions are prerequisites for performing interactive actions after an event is triggered. Conditional objects can select all components within the configuration interface. | Selected component | An interaction can set 0 - n conditions, and the relationships can be set between the conditions |
| Action      | An action response that is triggered by an event and when all conditions are met. The object of the action can select all components within the configuration interface, and the actions currently supported include setting properties, opening links, refreshing components, assigning variables, and so on. | Selected component | An interaction can set 1 to n actions, the action has no sequencing relationship |



### 3.2 Add a simple interactive event



Drag out a "Round rectangle" component, resize and color. Select the rectangle, click "Mutual", and add an "Mutual".

![img](http://192.168.3.128:8090/download/attachments/12550374/image2021-6-10_10-55-24.png?version=1&modificationDate=1623293724227&api=v2)



Select the event as "Click". Select "Action" as the setting property, and select the color change to red.

![img](http://192.168.3.128:8090/download/attachments/12550374/image2021-6-10_10-58-19.png?version=1&modificationDate=1623293899144&api=v2)



Click "Save" to save the changes. After saving the 2D model configuration, you can click "Preview" to view the configuration

![img](http://192.168.3.128:8090/download/attachments/12550374/image2021-6-10_10-59-58.png?version=1&modificationDate=1623293998865&api=v2)



You can click “Share” to generate a share link.

![img](http://192.168.3.128:8090/download/attachments/12550374/image2021-6-10_11-1-20.png?version=1&modificationDate=1623294080304&api=v2)



## **Next Steps: More challenges**



Congratulations! You've learned the basic usage of configuration, and quickly built a simple device monitoring dashboard application based on real-time data by this tutorial. With 2D Configuration, more industrial applications can be made.



Next, you can try to use 2D configurations to build the following dashboard below:

![img](https://gblobscdn.gitbook.com/assets%2F-MT00VdxHgBluCHDC3DW%2F-MT5DFixcl4wCz04NCmu%2F-MT5EeYbYCM5OfyoFr0f%2Fimage2020-12-23_10-15-58.png?alt=media&token=a64c8585-b8a7-42b2-9689-024247e5348f)



**Feedback**

If you have any questions or suggestions, please contact us: [service@zhan-wan.com](mailto:service@zhan-wan.com)