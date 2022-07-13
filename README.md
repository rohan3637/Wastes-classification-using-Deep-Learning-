<div align="center">

# Waste Management

</div>

# Approach Details

* We are trying to solve a problem of segregating the images of waste into Non-Recyclable, Recyclable and Organic waste.
* The dataset was taken from kaggle: https://www.kaggle.com/sapal6/waste-classification-data-v2
* These are some of the images from the datset:<br/>
<div align="center">
<table>
    <tr>
        <th>Non-Recyclable</th>
        <th>Recyclable</th>
        <th>Organic</th>
    </tr>
    <tr>
        <td><img src="https://user-images.githubusercontent.com/58647922/125157888-21e08c80-e18b-11eb-9a84-77fb4efd658b.png" width="300px" height="200px"></td>
        <td><img src="https://user-images.githubusercontent.com/58647922/125157903-3d4b9780-e18b-11eb-91b9-699dc274bc75.png" width="300px" height="200px"></td>
        <td><img src="https://user-images.githubusercontent.com/58647922/125157959-87347d80-e18b-11eb-972f-24086b0e71c1.png" width="300px" height="200px"></td>
    </tr>
    <tr>
        <td><img src="https://user-images.githubusercontent.com/58647922/125157998-b64aef00-e18b-11eb-9935-720438dfbb68.png" width="300px" height="200px"></td>
        <td><img src="https://user-images.githubusercontent.com/58647922/125158034-e85c5100-e18b-11eb-8ffc-19d695712046.png" width="300px" height="200px"></td>
        <td><img src="https://user-images.githubusercontent.com/58647922/125158008-c06ced80-e18b-11eb-9fe2-fad5084e705e.png" width="300px" height="200px"></td>
    </tr>
</table>
</div>
</br>

* The images from the dataset are rescaled to (224,224) dimensions and the pixels were normalized before passing to the model.
* Encodings for the images are generated using three approaches i.e. MobileNetv2, Inception ResNetv2, XceptionNet.
* These image encodings are then passed to Fully Connected DNN, Random Forest Classifier and XGBClassifier to make make predictions and segregate the images and to produce the metrics based on the predictions.

# System Flow Chart

<b>NOTE: </b>Here N: Non-Recyclable, R: Recyclable, O: Organic<br/>

<div align="center">

<img src="https://user-images.githubusercontent.com/58647922/125249847-47989d80-e313-11eb-906a-9fe8b9249a03.png">

</div>

# Architectures

<div align="center">

# MobileNet V2
  
<img align="center" src="https://user-images.githubusercontent.com/58647922/125158364-5ace3080-e18e-11eb-86fa-80bff116c49b.png">

<br/>

# Inception ResNet V2

<img align="center" src="https://user-images.githubusercontent.com/58647922/125158532-6ff78f00-e18f-11eb-8ee9-64ea74dee41c.png">

<br/>

# XceptionNet

<img align="center" src="https://user-images.githubusercontent.com/58647922/125158681-3d9a6180-e190-11eb-8861-fdd7a7f842ad.png">

<br/>

</div>

# Equations :
  
# 1. Relu Activation Function
<img align="center" src="https://user-images.githubusercontent.com/58647922/125158783-f2cd1980-e190-11eb-91ab-e49a7d8dbaf6.png" width="400px">


# 2. Softmax Activation Function
<img align="center" src="https://user-images.githubusercontent.com/58647922/125158797-04aebc80-e191-11eb-9bb9-ac7c73ae7ddb.png" width="400px">


# 3. Categorical CrossEntropy
<img align="center" src="https://user-images.githubusercontent.com/58647922/125158813-1728f600-e191-11eb-8e0c-916e80901a5d.png" width="400px">


# 4. Gini Index
<img align="center" src="https://user-images.githubusercontent.com/58647922/125158833-28720280-e191-11eb-9aa2-46bac0d97fd6.png" width="400px">


# 5. Information Gain
<img src="https://user-images.githubusercontent.com/58647922/125158922-b64ded80-e191-11eb-9bc7-cd4b557e282a.png">


# Performance Metrics

## Custom CNN + Fully Connected DNN
<b>Accuracy: </b> 74.23% <br/>
<img src="https://user-images.githubusercontent.com/58647922/125159030-720f1d00-e192-11eb-8929-ba232aa67c67.png"> <br/>
![screenshot-github com-2021 07 10-15_23_47](https://user-images.githubusercontent.com/58647922/125159113-feb9db00-e192-11eb-9041-738fee8ac398.png)


## MobileNetV2 + Fully Connected DNN
<b>Accuracy: </b> 78.87% <br/>
<img src="https://user-images.githubusercontent.com/58647922/125159276-1776c080-e194-11eb-8732-924c5c34e687.png"> <br/>
![screenshot-github com-2021 07 10-15_33_26](https://user-images.githubusercontent.com/58647922/125159308-3e34f700-e194-11eb-9122-8726a4b18133.png)


## Inception ResNetv2 + Fully Connected DNN
<b>Accuracy: </b> 80.32% <br/>
<img src="https://user-images.githubusercontent.com/58647922/125159571-e4353100-e195-11eb-90b6-0cbdb967344c.png"> <br/>
![screenshot-github com-2021 07 10-15_46_27](https://user-images.githubusercontent.com/58647922/125159599-0a5ad100-e196-11eb-9a23-90c7764b2bbc.png) 


## XceptionNet + Fully Connected DNN
<b>Accuracy: </b> 80.66% <br/>
<img src="![image](https://user-images.githubusercontent.com/58647922/125159656-5efe4c00-e196-11eb-9f4d-be5900768b44.png"> <br/>
![screenshot-github com-2021 07 10-15_49_22](https://user-images.githubusercontent.com/58647922/125159673-70dfef00-e196-11eb-8820-7a1ddce3daee.png) 

# Results:
<table>
    <tr>
        <th>Models</th>
        <th>Accuracy</th>
    </tr>
    <tr>
        <td>Custom CNN + Fully Connected DNN</td>
        <td>74.23%</td>
    </tr>
    <tr>
        <td>Custom CNN + XGB Model</td>
        <td>48%</td>
    </tr>
    <tr>
        <td>Custom CNN + Random Forest</td>
        <td>45%</td>
    </tr>
    <tr>
        <td>MobileNet V2 + Fully Coneected DNN</td>
        <td>78.87%</td>
    </tr>
    <tr>
        <td>MobileNet V2 + XGB Model</td>
        <td>48%</td>
    </tr>
    <tr>
        <td>MobileNet V2 + Random Forest</td>
        <td>47%</td>
    </tr>
    <tr>
        <td>Inception ResNet V2 + Fully Connected DNN</td>
        <td>80.32%</td>
    </tr>
    <tr>
        <td>Inception ResNet V2 + XGB Model</td>
        <td>48%</td>
    </tr>
    <tr>
        <td>Inception ResNet V2 + Random Forest</td>
        <td>47%</td>
    </tr>
    <tr>
        <td>XceptionNet + Fully Connected DNN</td>
        <td>80.66%</td>
    </tr>
    <tr>
        <td>XceptionNet + XGB Model</td>
        <td>48%</td>
    </tr>
    <tr>
        <td>XceptionNet + Random Forest</td>
        <td>47%</td>
    </tr>
</table>

# Predictions:

* The predictions made by the final best model are shown below<br/>
<div align="center">
<table>
    <tr>
        <th>Images</th>
        <th>Predicted Waste Class</th>
    </tr>
    <tr>
        <td><image src="https://user-images.githubusercontent.com/58647922/125161878-89ee9d00-e1a2-11eb-8a80-e054551a4129.png" height="150px"></td>
        <td>Non-Recyclable</td>
    </tr>
    <tr>
        <td><image src="https://user-images.githubusercontent.com/58647922/125162193-27969c00-e1a4-11eb-826a-17ba25185014.png" width="200px" height="150px"></td>
        <td>Recyclable</td>
    </tr>
    <tr>
        <td><image src="https://user-images.githubusercontent.com/58647922/125162204-3b420280-e1a4-11eb-8cf8-60144af94101.png" width="200px" height="150px"></td>
        <td>Organic</td>
    </tr>
    <tr>
        <td><image src="https://user-images.githubusercontent.com/58647922/125162676-e5228e80-e1a6-11eb-8ecc-f519299f2b96.png" height="150px"></td>
        <td>Non-Recyclable</td>
    </tr>
    <tr>
        <td><image src="https://user-images.githubusercontent.com/58647922/125162664-da67f980-e1a6-11eb-9ba8-cc5bc83e97bf.png" width="200px" height="150px"></td>
        <td>Recyclable</td>
    </tr>
    <tr>
        <td><image src="https://user-images.githubusercontent.com/58647922/125162348-ece13380-e1a4-11eb-8803-a2b1ffb26479.png" height="150px"></td>
        <td>Organic</td>
    </tr>
    <tr>
        <td><image src="https://user-images.githubusercontent.com/58647922/125162628-970d8b00-e1a6-11eb-905b-7d13e7e685ba.png" width="200px" height="150px"></td>
        <td>Non-Recyclable</td>
    </tr>
</table>
</div>

