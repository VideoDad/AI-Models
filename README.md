# AI-Models
Custom Trained AI Models for object detection in images or video.<br/>

## Delivery
Detects logos of various delivery services<br/>

labels: *amazon, fedex, ups, usps, uhaul, dhl*<br/>

### Available models
| Model | Module | CodeProject.AI Location |
| --- | --- | --- |
| delivery.pt | YOLOv5 6.2 | ObjectDetectionsYOLOv5-6.2\custom-models |
| delivery.onnx | YOLOv5 NET | ObjectDetectionYOLOv5Net\custom-models |
| delivery.pt | YOLOv8 | ObjectDetectionYOLOv8\custom-models |
| delivery.onnx | YOLOv8 NET | _not implemented in CPAI_ |

### Instructions for use with CodeProject.AI
Go to the CodeProject.AI Server Dashboard (localhost:32168) and click on InstallModules. Make sure the YOLO module that you want to use is installed. 
Download the corresponding delivery module from this GitHub repository and place it in the custom-models folder for that module. 
> [!NOTE]
> The default install location for CodeProject.AI modules is C:\Program Files\CodeProject\AI\modules\
> After copying in any new model, be sure to restart the CodeProject.AI server. You can have multiple modules installed, but generally you only want _one_ YOLO module running at one time.

### Testing the Custom Delivery module in CodeProject.AI Explorer
From the CodeProject.AI Server Dashboard (localhost:32168), click on the _blue button_ for the **CodeProject.AI Explorer**. At the bottom of the module you are running, pick **delivery** from the drop-down. Select an image that contains a delivery logo and press the _orange button_ labeled **Custom Detect**.

### Using the Model in Blue Iris
Once you have confirmed that the model is correctly running and detecting delivery logos, you can then add it to a camera in **Blue Iris**.
> [!NOTE]
> It's highly recommended that you create a clone of an existing camera for detecting delivery logos so that you don't have multiple models trying to detect objects. It will also help with isolating alerts.

In Blue Iris, after creating a clone of an existing camera, right-click and choose **Camera settings...**. Go to the **Alert** tab and check the box to **Confirm Alert with AI** then click the **AI Configuration** button.

| Field | Value | Notes |
| --- | --- | --- |
| To confirm | amazon,dhl,fedex,ups,usps,uhaul | You can choose a subset of these if you don't want all |
| To cancel | DoNotCancel | This lets BI keep checking images on a moving vehicle until it sees a logo |
| Custom models | delivery | For best results, make sure you have turned off the default object detection, or use delivery,objects:0 |
| Mark as vehicle | amazon,dhl,fedex,ups,usps,uhaul | All the labels should be considered vehicles |
| Use mainstream if available | Checked | Recommended for better detections and notifications |

This work is licensed under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)<br/>
![CC BY-NC-SA 4.0](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)
