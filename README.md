<h1 align="center">Computer vision and Deep learning-based Drowsiness Detection System using IoT</h1>

- Drowsiness detection

  We used MediaPipe face mesh which is a face geometry solution that estimates 468 3D face landmarks in real-time even on mobile devices. It uses machine learning (ML) to derive 3D surface geometry and requires only a camera input without a dedicated depth sensor. By using lightweight model architecture and GPU acceleration throughout the process, the solution can deliver critical real-time performance for the live experience. The face geometry data is composed of common 3D geometric primitives, including face position transformation matrix and triangular face mesh.

  The inbuilt camera will detect the face and start by localizing the facial landmarks by extracting the eye regions to determine if either the eyes are opened or closed. we will be monitoring the eye aspect ratio to see if the defined threshold value raise which is 0.5 in our case but does not increase again for a sufficiently long amount of consecutive frames, thus implying that the driver/user has closed their eyes. Then, the system will raise the alarm and also will inform the responsible person on behalf of the driver to avoid any mistakes. Here we used 3rd party cloud library package called Twilio to send SMS alerts.

  ![DrowsiImage_m](https://user-images.githubusercontent.com/84900433/163725357-54a37569-2764-4e22-9ed1-3efdb0094ef4.png)


Do the below changes in [Drowsiness](Drowsiness/)/[drowsiness.py](Drowsiness/drowsiness.py)
      
   Create your [TWILIO](https://www.twilio.com/) account. Add your credentials in 
     
     ```python
      def message():
    # Through Twilio send a message and make a call
    account_sid = "<account_sid>"  # Put your Twilio account SID here
    auth_token = "<auth_token>"  # Put your auth token here

    client = Client(account_sid, auth_token)

    # Send a message
    message = client.api.account.messages.create(
        to="+<receiver>",  # Put your cellphone number here
        from_="+<sender>",  # Put your Twilio number here
        body="Driver is Sleeping....")
    print("[INFO] sending message...")
     ```


_For more information, refer to the [Deep Learning & Computer Vision for IoT based Intelligent Driver Assistant System](https://ieeexplore.ieee.org/abstract/document/9605823)._

## Contact

- Hirushiharan Thevendran –  [LinkedIn](https://www.linkedin.com/in/hirushiharan-thevendran-a08a82152?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_contact_details%3B54o2t%2B3cRw6IQKiNxmk27A%3D%3D) – [Email](hirushiharant@gmail.com)
- Ashaya Nagendran –  [LinkedIn](https://www.linkedin.com/in/akshaya-nagendran-437557196?lipi=urn%3Ali%3Apage%3Ad_flagship3_profile_view_base_contact_details%3BKC%2FsFC%2FSQWmXOpQ1l7dtSw%3D%3D) – [Email](akshayanagendran52@gmail.com)

<!-- Markdown link & img dfn's -->

[npm-image]: https://img.shields.io/npm/v/datadog-metrics.svg?style=flat-square
[npm-url]: https://npmjs.org/package/datadog-metrics
[npm-downloads]: https://img.shields.io/npm/dm/datadog-metrics.svg?style=flat-square
[travis-image]: https://img.shields.io/travis/dbader/node-datadog-metrics/master.svg?style=flat-square
[travis-url]: https://travis-ci.org/dbader/node-datadog-metrics
[wiki]: https://github.com/yourname/yourproject/wiki

Testing pull request
