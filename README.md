![Logo](https://biometricvision.com/git_images/logo_white_sm.png) 

# Introduction

Recognize and compare faces in minutes with this simple to use cloud based facial recognition API. This model has a match accuracy of 99.9% so it works under extreme conditions (Long distance, pixelation, blurred images and high/low contrast). 

(https://biometricvision.com) Is releasing it's API for free to get feedback from the dev community. We are really excited for everyone to test the technology.

**This tutorial shows you how to compare between two images.**

### Example

This image below is a demo showing the results of two images matching as the same person:
![Demo](https://biometricvision.com/git_images/match_man.jpg) 

#### Results

```json
{
    "Confidence": "Match",
    "Features": {
        "Left Eye": "92.52",
        "Right Eye": "86.04",
        "Left Brow": "91.45",
        "Right Brow": "90.31",
        "Forehead": "90.91",
        "Middle Forehead": "89.70",
        "Nose": "87.82",
        "Philtrum": "93.20",
        "Mouth": "91.65",
        "Jaw": "93.75",
        "Left Cheek": "86.44",
        "Right Cheek": "88.50"
}
```
[You can find a working demo UI here](https://bvengine.com)

The 99.9% match accuracy means it will work under extreme conditions:
![Demo](https://biometricvision.com/git_images/extreme_matching.gif)

# Getting Started

There are three steps to use the API:
  1. Get your the API Key, Client ID and Secret Key.
  2. Create an OAuth 2.0 Token.
  3. Upload two images to the compare API.

You can use our postman collection to test your API.
* [Download PostMan Collection][PlDb]

### Step 1: Get your the API Key, Client ID and Secret Key

You can quickly generate your API Key, Client ID and Secret Key by signing up here. Don't worry it's free for 90 days and you don't need to enter credit card details.

* [Get your free API access details](https://app.biometricvision.com/auth/sign-up)

### Step 2: Create an OAuth 2.0 Token

To access the compare API you will need an OAuth 2.0 Token. So, you will need your Client ID and Secret Key to create it.
Below is an example for creating OAuth 2.0 Token using CURL.
```sh
curl -X POST -H "Content-Type: application/json" \
     --data "{\"client_id\": \"CLIENT_ID\",\"client_secret\": \"SECRET_KEY\", \"grant_type\":\"client_credentials\"}" \
     https://bvengine.com/oauth/token
```

**Response:**

```json
{
	"token_type": "Bearer",
	"expires_in": 3600,
	"access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJhdWQiOiIyNTQxMTQ1NiIsImp0aSI6IjNiNTg2YzZjMDdkODBhZThjYWYwMGFlYWI3ZDFiN2E2MjZjZjM0YjgxODJiZjlhOWE0MWMyNjI1YWEzN2YxNTYzNWFjYzVjM2JiNWNhODY2IiwiaWF0IjoxNTgzMjg4OTA4LCJuYmYiOjE1ODMyODg5MDgsImV4cCI6MTU4MzI5MjUwOCwic3ViIjoiIiwic2NvcGVzIjpbXX0.NdZyMzYgYt4dtnFa3ph9MiJGhF00tauH3yy7quBPHcUNkY7ZEysQSWt1YOvQXr1L5E5eMMsaidojYLU8Zknc112TYtbUsdiQMJQyNves_dJpE-0kna3TzE4rDwNFqZXdRCul6FGVb5AzYeH2sAmkny03584cnVZC6WsOsOJacccl1kIjKe0zBS2pKi3EqiDka8z_Er3GboXD4qxSUOvkrO4JN0qNXckIhl7q1SgXwX_JwbwU6Sxzd8y_q7tjCptca3JimRf_ad3U4k3Bp-gErhMby_SoTADrexE3uHuOK8gM1aLW8JH-Vg8rX-rX0m78OgFcC8mpLVtm2a4g1NT_o1ZFCIuJNBxa-cpE13uYgjMwyj8LKQ_xeBGJu7eaOeu5wxMqTa26IKp35lwVFcF8bHCcfjIm1JwrPoEowlBDFUd1thBaprKBRJeguHg4foO4RNK08wQrG_S0m34x_jfhpo5ljlZQyrbGb4x0FB3b-IRV5tXNE1rX8h5UnFexQX5zDHTKtr_nSFl8_HtIHAOYOywPfxpMSWHEyzq6-KY1u1rmnhRIJSVC5VledVjW8lvAfKXtAJK6K315nYWvDoDN2aZ-wftpWkPBDYzjMf9NwoA7AvlvS95_mSsiQC0l6rJor6lqMW2ELBYgRCaqwJ5ebQ1xGB_DnNXx_zwsg7Y6vV0"
}
```
### Step 3: Upload two images to the compare API
Once you get `access_token` now you will be able to use the compare API with your API Key.
Below is an example for using the API.

**Request:**

```sh
curl -X POST -H "Content-Type: application/json" \
     -H "Authorization: Bearer ACESS_TOKEN" \
     -H "X-API-KEY: API_KEY" \
     -F "image1=@/home/user/image1.jpg" \
     -F "image2=@/home/user/image2.jpg" \
     https://bvengine.com/api/compare
```

**Response:**

```json
{
    "Confidence": "Match",
    "Features": {
        "Left Eye": "92.52",
        "Right Eye": "86.04",
        "Left Brow": "91.45",
        "Right Brow": "90.31",
        "Forehead": "90.91",
        "Middle Forehead": "89.70",
        "Nose": "87.82",
        "Philtrum": "93.20",
        "Mouth": "91.65",
        "Jaw": "93.75",
        "Left Cheek": "86.44",
        "Right Cheek": "88.50"
}
```

If the two images are not the same person `Confidence` will be "No Match".

### Swagger Spec

We do have the swagger for those two APIs. You can download it here:
* [Download Swagger Spec][PlGh]

### Need Support

If you run into any issues or problems you are welcome to file a github issue or simple talk to me via (https://app.biometricvision.com/dashboard) once you have access. Or you can chat with me directly at (https://biometricvision.com/) via intercom.

| Technical Features |
| ------ |
| Face match time of 130ms|
| False Accept Rate is 0.1%, False Reject Rate is 0.14% | 
| Proprietary method for storing face templates as an anonymous alphanumeric string of code (binary) | 
| Threshold for ‘Match’ is >=70% | 
| Image formats supported: jpg, jpeg, png, bmp | 
| Built using Python with machine learning | 
| Uses 180 landmarks to create a face template | 

### Release Plan
| Feature | Release Date |
| ------ | ------ |
| Verification (1:1) | Live |
| Identification (1:N) | March 2020|
| Anti-spoofing | April 2020 |
| Liveness detection | April 2020 |

**Enjoy!**

[//]: # ()

   [PlDb]: <https://github.com/biometricvisiondev/facial_recognition/tree/master/postman-collection>
   [PlGh]: <https://github.com/biometricvisiondev/facial_recognition/tree/master/swagger-spec>
