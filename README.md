# facemesh_face-landmark-detector

This is trainable face-landmark-detector 
Base model is facemesh of Tensorflow Hub : https://tfhub.dev/mediapipe/tfjs-model/facemesh/1/default/1
Updated at 12/14/2021

# Process

Facemesh tfjs model is frozen graph. It's not trainable.
I analyze graph model using netron and assign weight by converting original name to converted name.
Some of variable could not be converted to trainable maybe due to version ristriction.
And then model is saved to keras trainable model.

# graph

This graph model is constructed by many resBlock. And output branch are 3.
1. 1404 point: 468 face landmark point that each has x,y,z axis
2. 1 point: that represents posibility of the photo has human face
3. 266 point: I don't know about this 

![스크린샷 2021-12-14 오후 2 47 30-side](https://user-images.githubusercontent.com/10595278/145940840-35ac911e-c140-46a8-96f3-51404ec92d92.png)
