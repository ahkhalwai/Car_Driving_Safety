# Car Driving Safety 

[image1]: ./challenge.jpg    
[image2]: ./layout.jpg
[image3]: ./output.jpg

Participation in the Intel Edge AI Udacity Scholarship Show Case Group Project  
* Follow Udacity Git Commit Message Style Guide: https://udacity.github.io/git-styleguide/     

Our story starts from Maximum car accidents in the world.  In the early stages we perform statistical inference to detect action recognition in the video stream to inform us what type of driver level? status in real time. In this showcase project our goal is to extend our learning experience from the Intel Edge AI Scholarship Foundation Course with a hands-on project.   

In this Intel® Edge AI Group showcase project, our goal is to extend our learning experience from Intel® Edge AI Scholarship Foundation Course Nanodegree and Hands-on Implementation from:    
* Import OpenVINO Toolkit, build and compile successfully on Google Colab.  
* Load pre-trained models.  
* Perform model optimization.   
* Result.

## Load Pre-trained Models   

*  You can use public or pre-trained models. To download the pre-trained models, use the OpenVino Model Downloader or go to [driver-action-recognition-adas-0002-encoder](https://docs.openvinotoolkit.org/latest/_models_intel_driver_action_recognition_adas_0002_encoder_description_driver_action_recognition_adas_0002_encoder.html) or [driver-action-recognition-adas-0002-decoder](https://docs.openvinotoolkit.org/latest/_models_intel_driver_action_recognition_adas_0002_decoder_description_driver_action_recognition_adas_0002_decoder.html)

* Before running the demo with a trained model, make sure the model is converted to the Inference Engine format (*.xml + *.bin) using [The Model Optimizer](https://docs.openvinotoolkit.org/latest/_docs_MO_DG_Deep_Learning_Model_Optimizer_DevGuide.html)

## How It Works

The demo pipeline consists of several frames, namely Data, Encoder, Decoder and Render. Every step implements PipelineStep interface by creating a class derived from PipelineStep base class. See steps.py for implementation details.

* DataStep reads frames from the input video.
* EncoderStep preprocesses a frame and feeds it to the encoder model to produce a frame embedding.
* DecoderStep feeds embeddings produced by the EncoderStep to the decoder model and produces predictions.
* RenderStep renders prediction results.

Pipeline steps are composed in AsyncPipeline. Every step can be run in separate thread by adding it to the pipeline with parallel=True option. When two consequent steps occur in separate threads, they communicate via message queue (for example, deliver step result or stop signal).

## Result

### Challenge                        
![][image1]                 
### Layout                      
![][image2] 
### Output                      
![][image3] 



## References

* [Action Recognition Models](https://docs.openvinotoolkit.org/latest/usergroup11.html)
* [Action Recognition Python](https://docs.openvinotoolkit.org/2019_R1/_inference_engine_ie_bridges_python_sample_action_recognition_README.html)
* [Awesome Action Recognition](https://github.com/jinwchoi/awesome-action-recognition)
* [Safe Driving : Driver Action Recognition using SURF Keypoints](https://www.researchgate.net/publication/332824537_Safe_Driving_Driver_Action_Recognition_using_SURF_Keypoints)
* [Driver Activity Recognition for Intelligent Vehicles: A Deep Learning Approach](https://ieeexplore.ieee.org/document/8678436)

## Collaborators:  

| Name | Slack Name |
| ------------------------- | ------------------------- |
| [Kubra Doğmuş](https://github.com/kubradogmus) | kübra doğmuş | 
| [Lakshmi Prasannakumar](https://github.com/LakshmiPrasannan) | Lakshmi Prasannakumar |
| [Radhika Joshi](https://github.com/RadhikaRJ) | Radhika Joshi |
| [Halwai Aftab Hasan](https://github.com/ahkhalwai) | aftab |



## License
This system is available under the GNU - 3.0 license. See the [LICENSE](https://github.com/ahkhalwai/action_recognition_adas/blob/master/LICENSE) file for more info.

